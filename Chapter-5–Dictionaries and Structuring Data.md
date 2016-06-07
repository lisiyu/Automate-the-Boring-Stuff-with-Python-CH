#Chapter 5 – Dictionaries and Structuring Data 字典和结构化数据
[相关视频教程](https://youtu.be/o3m8XhnVDWs)

In this chapter, I will cover the dictionary data type, which provides a flexible way to access and organize data. Then, combining dictionaries with your knowledge of lists from the previous chapter, you’ll learn how to create a data structure to model a tic-tac-toe board.  
在本章中，我将介绍字典数据类型，它提供了一种灵活的方式来访问和组织数据。字典结合之前章节学习的知识您将学习如何创建一个数据结构来实现井字棋棋盘.

##The Dictionary Data Type 字典数据类型

Like a list, a dictionary is a collection of many values. But unlike indexes for lists, indexes for dictionaries can use many different data types, not just integers. Indexes for dictionaries are called keys, and a key with its associated value is called a key-value pair.  
像列表一样，字典是许多值的集合。不过与列表的索引不同，字典的索引可以使用许多不同的数据类型，而不仅仅是整数。字典索引被称为键，并与它相关联的值一起称为键-值对。  

In code, a dictionary is typed with braces, {}. Enter the following into the interactive shell:  
在代码中，一个字典类型用大括号{}表示。输入以下内容到交互窗体：

	myCat = {'size': 'fat', 'color': 'gray', 'disposition': 'loud'}
	
This assigns a dictionary to the myCat variable. This dictionary’s keys are 'size', 'color', and 'disposition'. The values for these keys are 'fat', 'gray', and 'loud', respectively. You can access these values through their keys:  
这里定义了一个叫myCat的字典类型变量.这个字典的键是'size','color'和'disposition'.和这些键f分别对应的值是'fat','gray'和'loud',

	>>> myCat['size']
	'fat'
	>>> 'My cat has ' + myCat['color'] + ' fur.'
	'My cat has gray fur.'
	
Dictionaries can still use integer values as keys, just like lists use integers for indexes, but they do not have to start at 0 and can be any number.  
字典仍然可以使用整数值作为键，就像列表使用整数的索引，但它们不需要从0开始，可以是任何数字。  

	>>> spam = {12345: 'Luggage Combination', 42: 'The Answer'}
	
##Dictionaries vs. Lists 字典与词典

Unlike lists, items in dictionaries are unordered. The first item in a list named spam would be spam[0]. But there is no “first” item in a dictionary. While the order of items matters for determining whether two lists are the same, it does not matter in what order the key-value pairs are typed in a dictionary. Enter the following into the interactive shell:  
和列表不一样,字典中的元素是无序的.在列表spam中的第一个元素应该是spam[0].但是在字典中没有第一个元素的概念.列表中元素的排列顺序会影响到比较两个列表是否相同.但是在字典中键值对的排列顺序对这个比较没有影响.输入以下内容到交互窗体:

	>>> spam = ['cats', 'dogs', 'moose']
	>>> bacon = ['dogs', 'moose', 'cats']
	>>> spam == bacon
	False
	>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
	>>> ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}
	>>> eggs == ham
	True
	
Because dictionaries are not ordered, they can’t be sliced like lists.  
因为字典是无序的，他们不能像列表一样被切片。

Trying to access a key that does not exist in a dictionary will result in a KeyError error message, much like a list’s “out-of-range” IndexError error message. Enter the following into the interactive shell, and notice the error message that shows up because there is no 'color' key:  
试图访问不字典中存在的键会导致KeyError异常的错误信息，就像列表的“out-of-range”IndexError错误消息。输入以下内容到交互窗体,因为这里没有键'color'留意错误信息.  

	>>> spam = {'name': 'Zophie', 'age': 7}
	>>> spam['color']
	Traceback (most recent call last):
	  File "<pyshell#1>", line 1, in <module>
		spam['color']
	KeyError: 'color'
	
Though dictionaries are not ordered, the fact that you can have arbitrary values for the keys allows you to organize your data in powerful ways. Say you wanted your program to store data about your friends’ birthdays. You can use a dictionary with the names as keys and the birthdays as values. Open a new file editor window and enter the following code. Save it as birthdays.py.  
因为字典类型没有顺序之分,事实上这让你可以通过任意键以强有力的方式组织你的数据.  加入你想写一个程序来存储你朋友的生日信息.你可以在字典中采用名字做为键和生日作为值来实现.打开一个新的文件编辑器窗口，并输入以下代码。将它保存为birthdays.py。  

	birthdays = {'Alice': 'Apr 1', 'Bob': 'Dec 12', 'Carol': 'Mar 4'}

		while True:
			print('Enter a name: (blank to quit)')
			name = input()
			if name == '':
			   break

			if name in birthdays:
			  print(birthdays[name] + ' is the birthday of ' + name)
			else:
			   print('I do not have birthday information for ' + name)
			   print('What is their birthday?')
			   bday = input()
			   birthdays[name] = bday
			   print('Birthday database updated.')
			   
You create an initial dictionary and store it in birthdays. You can see if the entered name exists as a key in the dictionary with the in keyword, just as you did for lists. If the name is in the dictionary, you access the associated value using square brackets ?; if not, you can add it using the same square bracket syntax combined with the assignment operator.    
你可以初始化一个字典存储生日信息.你可以看到，如果输入的名称作为存在字典中的关键字中的键,就像对列表操作一样.如果名字在字典中，您使用方括号访问相关的值.如果没有，你可以使用相同的方括号赋值运算符添加.

When you run this program, it will look like this:  
当你运行这个程序，它会是这样的：

	Enter a name: (blank to quit)
	Alice
	Apr 1 is the birthday of Alice
	Enter a name: (blank to quit)
	Eve
	I do not have birthday information for Eve
	What is their birthday?
	Dec 5
	Birthday database updated.
	Enter a name: (blank to quit)
	Eve
	Dec 5 is the birthday of Eve
	Enter a name: (blank to quit)

Of course, all the data you enter in this program is forgotten when the program terminates. You’ll learn how to save data to files on the hard drive in Chapter 8.  
当然，程序终止时，所有你在这个程序中输入数据会丢失。在第8章您将学习如何将数据保存到硬盘驱动器上的文件中。  

##The keys(), values(), and items() Methods 键,值和元素方法

There are three dictionary methods that will return list-like values of the dictionary’s keys, values, or both keys and values: keys(), values(), and items(). The values returned by these methods are not true lists: They cannot be modified and do not have an append() method. But these data types (dict_keys, dict_values, and dict_items, respectively) can be used in for loops. To see how these methods work, enter the following into the interactive shell:  
有三种字典keys(), values(), and items()方法将返回字典的键，值或键值对.由这些方法所返回的值像列表但它们不能被修改，不能使用append()方法。但这些返回的数据类型可以用在循环中.要了解这些方法的工作模式，输入以下代码到交互窗体：  

	spam = {'color': 'red', 'age': 42}
	for v in spam.values():
			print(v)

	red
	42

Here, a for loop iterates over each of the values in the spam dictionary. A for loop can also iterate over the keys or both keys and values:  
在这里for循环可以遍历字典spam中的值.for循环可以遍历键或键和值:  

	for k in spam.keys():
			print(k)

	color
	age

	for i in spam.items():
			print(i)

	('color', 'red')
	('age', 42)

Using the keys(), values(), and items() methods, a for loop can iterate over the keys, values, or key-value pairs in a dictionary, respectively. Notice that the values in the dict_items value returned by the items() method are tuples of the key and value.  
 用keys(), values(), 和items()方法可以遍历键,值,键值对.注意，在由items()方法返回的dict_items值的值是键和值的元组
 
If you want a true list from one of these methods, pass its list-like return value to the list() function. Enter the following into the interactive shell:  
如果你想从这些方法获得真正的列表，可以把返回值传递给list()函数。输入以下内容到交互窗体：  

	spam = {'color': 'red', 'age': 42}
	spam.keys()
	dict_keys(['color', 'age'])
	list(spam.keys())
	['color', 'age']
	
The list(spam.keys()) line takes the dict_keys value returned from keys() and passes it to list(), which then returns a list value of ['color', 'age'].  
该list(spam.keys())将返回dict_keys的值传递到list()，然后返回['color', 'age']列表。  

You can also use the multiple assignment trick in a for loop to assign the key and value to separate variables. Enter the following into the interactive shell:  
您也可以使用多重赋值方法在for循环中定义键和值给独立的变量。  

	spam = {'color': 'red', 'age': 42}
	for k, v in spam.items():
			print('Key: ' + k + ' Value: ' + str(v))

	Key: age Value: 42
	Key: color Value: red
	
##Checking Whether a Key or Value Exists in a Dictionary
##检查一个键或值是否存在字典中

Recall from the previous chapter that the in and not in operators can check whether a value exists in a list. You can also use these operators to see whether a certain key or value exists in a dictionary. Enter the following into the interactive shell:  
在前面的章节中的中，我们用in操作符可以检查列表中是否存在某个值。您也可以使用in操作符查看在字典中某个键或值是否存在。在交互窗体输入以下内容:  

	spam = {'name': 'Zophie', 'age': 7}
	'name' in spam.keys()
	True
	'Zophie' in spam.values()
	True
	'color' in spam.keys()
	False
	'color' not in spam.keys()
	True
	'color' in spam
	False
	
In the previous example, notice that 'color' in spam is essentially a shorter version of writing 'color' in spam.keys(). This is always the case: If you ever want to check whether a value is (or isn’t) a key in the dictionary, you can simply use the in (or not in) keyword with the dictionary value itself.  
在前面的例子中，'color' in spam 本质上是'color' in spam.keys()的简写。通常应用在这样的场景:当你仅仅想查询一个键或值是否存在字典中而不关心这个本身是键还是值就可以使用.

##The get() Method
##get()方法

It’s tedious to check whether a key exists in a dictionary before accessing that key’s value. Fortunately, dictionaries have a get() method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key does not exist.
Enter the following into the interactive shell:  
如果在访问一个键的值之前需要先检查键是否存在字典中就太麻烦了.幸好在字典中有一个包含两个参数的get()的方法:用来检索值的键,键不存时的返回值.在交互窗体输入以下内容:

	picnicItems = {'apples': 5, 'cups': 2}
	'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'
	'I am bringing 2 cups.'
	'I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.'
	'I am bringing 0 eggs.'
	
Because there is no 'eggs' key in the picnicItems dictionary, the default value 0 is returned by the get() method. Without using get(), the code would have caused an error message, such as in the following example:  
因为字典picnicItems中没有'egs'键，默认值0由get()方法返回。如果不使用get()，带码会造成错误消息，如下面的例子：

	picnicItems = {'apples': 5, 'cups': 2}
	'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'
	Traceback (most recent call last):
	  File "<pyshell#34>", line 1, in <module>
		'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'
	KeyError: 'eggs'
	
##The setdefault() Method

You’ll often have to set a value in a dictionary for a certain key only if that key does not already have a value. The code looks something like this:  
您通常需要给字典中某些没有值的键设定一个值。该代码看起来是这样的：

	spam = {'name': 'Pooka', 'age': 5}
	if 'color' not in spam:
		spam['color'] = 'black'
		
The setdefault() method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key does not exist. If the key does exist, the setdefault() method returns the key’s value. Enter the following into the interactive shell:  
setdefault()方法提供了一种单行代码实现这个功能的途径.传递给方法的第一个参数是检查键是否存在，第二个参数是如果该键不存在值时设置该键的值。如果键不存在setdefault()方法返回该键的值.在交互窗体输入以下代码:  

	>>> spam = {'name': 'Pooka', 'age': 5}
	>>> spam.setdefault('color', 'black')
	'black'
	>>> spam
	{'color': 'black', 'age': 5, 'name': 'Pooka'}
	>>> spam.setdefault('color', 'white')
	'black'
	>>> spam
	{'color': 'black', 'age': 5, 'name': 'Pooka'}
	
The first time setdefault() is called, the dictionary in spam changes to {'color': 'black', 'age': 5, 'name': 'Pooka'}. The method returns the value 'black' because this is now the value set for the key 'color'. When spam.setdefault('color', 'white') is called next, the value for that key is not changed to 'white' because spam already has a key named 'color'.  
第一次调用setdefault()是字典spam变成{'color': 'black', 'age': 5, 'name': 'Pooka'}.因为现在值通过键'color'进行了设置方法调用返回值'black'.当第二次调用spam.setdefault('color', 'white')时,键对应的值并没有变成'white',因为spam已经有键'color'存在.

The setdefault() method is a nice shortcut to ensure that a key exists. Here is a short program that counts the number of occurrences of each letter in a string. Open the file editor window and enter the following code, saving it as characterCount.py:  
setdefault（）方法是一个很好的确保键存在的快捷方式。这里有一个很短的程序用来计算字符串中的每个字母出现的次数。打开文件编辑器窗口，并输入以下代码，将其保存为characterCount.py：

	message = 'It was a bright cold day in April, and the clocks were striking thirteen.'
	count = {}

	for character in message:
		count.setdefault(character, 0)
		count[character] = count[character] + 1

	print(count)
	
The program loops over each character in the message variable’s string, counting how often each character appears. The setdefault() method call ensures that the key is in the count dictionary (with a default value of 0) so the program doesn’t throw a KeyError error when count[character] = count[character] + 1 is executed. When you run this program, the output will look like this:  
该程序遍历变量message字符串的每个字符，计算每个字符出现的频率。调用setdefault()方法并设置默认参数为0确保键在计数字典中count[character] = count[character] + 1时程序不会报错.运行这个程序,输出结果如下:  

	{' ': 13, ',': 1, '.': 1, 'A': 1, 'I': 1, 'a': 4, 'c': 3, 'b': 1, 'e': 5, 'd': 3, 'g': 2, 'i':
	6, 'h': 3, 'k': 2, 'l': 3, 'o': 2, 'n': 4, 'p': 1, 's': 3, 'r': 5, 't': 6, 'w': 2, 'y': 1}
	
From the output, you can see that the lowercase letter c appears 3 times, the space character appears 13 times, and the uppercase letter A appears 1 time. This program will work no matter what string is inside the message variable, even if the string is millions of characters long!  
从输出中，你可以看到，小写字母c出现3次，空格字符出现13次，以及大写字母A出现1次。无论是消息变量里面是什么字符串，即使该字符串是数以百万计的字符长这个程序都可以运行.  

##Pretty Printing 美化打印

If you import the pprint module into your programs, you’ll have access to the pprint() and pformat() functions that will “pretty print” a dictionary’s values. This is helpful when you want a cleaner display of the items in a dictionary than what print() provides. Modify the previous characterCount.py program and save it as prettyCharacterCount.py.  
如果导入pprint模块到你的程序，你将获得pprint（）和pformat（）函数，将“美化打印”，字典的值。当你想完全打印字典的元素这是非常有帮助的。修改前面的程序characterCount.py并将其保存为prettyCharacterCount.py。  

	import pprint
	message = 'It was a bright cold day in April, and the clocks were striking
	thirteen.'
	count = {}

	for character in message:
		count.setdefault(character, 0)
		count[character] = count[character] + 1

	pprint.pprint(count)
	
This time, when the program is run, the output looks much cleaner, with the keys sorted.  
这一次程序运行时，输出看起来更干净，用键进行了排序。

	{' ': 13,
	 ',': 1,
	 '.': 1,
	 'A': 1,
	 'I': 1,
	 'a': 4,
	 'b': 1,
	 'c': 3,
	 'd': 3,
	 'e': 5,
	 'g': 2,
	 'h': 3,
	 'i': 6,
	 'k': 2,
	 'l': 3,
	 'n': 4,
	 'o': 2,
	 'p': 1,
	 'r': 5,
	 's': 3,
	 't': 6,
	 'w': 2,
	 'y': 1}
	 
The pprint.pprint() function is especially helpful when the dictionary itself contains nested lists or dictionaries.
If you want to obtain the prettified text as a string value instead of displaying it on the screen, call pprint.pformat() instead. These two lines are equivalent to each other:  
当字典本身包含嵌套的列表或字典时pprint.pprint（）函数特别有用。如果你想获得美化文本作为一个字符串值，而不是在屏幕上显示出来，可以调用pprint.pformat()代替。下面两行代码是彼此等效：  

	pprint.pprint(someDictionaryValue)
	print(pprint.pformat(someDictionaryValue))
	
#Using Data Structures to Model Real-World Things
#用数据结构模型现实世界的事物
[相关教学视频](https://youtu.be/mf28IhDfMGk)

在因特网出现之前,地球上相隔十万八千里的人也可以玩棋类游戏.每个玩家在家建立一个棋盘，然后通过轮流邮寄明信片给对方来描述下一步怎么走.为了实现这个,玩家们需要先约定一种描述走棋方法的规则.国际象棋中,棋盘上的空间是由数字和字母组成的坐标.如图5所示:
[图五](https://automatetheboringstuff.com/images/000002.jpg)

The chess pieces are identified by letters: K for king, Q for queen, R for rook, B for bishop, and N for knight.Describing a move uses the letter of the piece and the coordinates of its destination. A pair of these moves describes what happens in a single turn (with white going first); for instance, the notation 2. Nf3 Nc6 indicates that white moved a knight to f3 and black moved a knight to c6 on the second turn of the game.    
棋子是用字母标识：K为王，Q为皇后，R为车，B的主教，和N为骑士。描述每一步采用的棋子的标识和其目的地格子的坐标.两方各走一步描述一回合内发生的动作(执白先走).例如，符号2.NF3 NC6表示:在比赛的第二轮白方移动骑士到F3和黑方移动骑士到C6.   

There’s a bit more to algebraic notation than this, but the point is that you can use it to unambiguously describe a game of chess without needing to be in front of a chessboard. Your opponent can even be on the other side of the world! In fact, you don’t even need a physical chess set if you have a good memory: You can just read the mailed chess moves and update boards you have in your imagination.  
虽然用代数符号来表示有一点繁琐,但是你可以用它来清楚的对战一盘棋，而无需在棋盘前当面对局。你的对手甚至可以是世界另一边的人！如果你的记忆力足够好你连一个真实的棋盘都不需要:你只需要阅读描述棋子移动的卡片通过想象来更新棋谱和给出你的对应招式.  

Computers have good memories. A program on a modern computer can easily store billions of strings like '2. Nf3 Nc6'. This is how computers can play chess without having a physical chessboard. They model data to represent a chessboard, and you can write code to work with this model.  
计算机有超强的记忆。现代计算机上的程序可以轻松存储数十亿像'2.NF3 NC6'这样的字符串.这就是为啥电脑可以不使用物理棋盘来完成对局.用数据模型表示一个棋盘,你可以通过编写代码来实现这个模型.  

This is where lists and dictionaries can come in. You can use them to model real-world things, like chessboards. For the first example, you’ll use a game that’s a little simpler than chess: tic-tac-toe.  
引入列表和字典，你可以用它们来现实世界东西的模型，如棋盘。对于第一个示例，您将使用比国际象棋简单一些的游戏：井字棋  

##A Tic-Tac-Toe Board 井字棋棋盘
A tic-tac-toe board looks like a large hash symbol (#) with nine slots that can each contain an X, an O, or a blank. To represent the board with a dictionary, you can assign each slot a string-value key, as shown in Figure 5-2.  
一个井字棋盘看起来像一个大的符号（＃）与9个空格，每个都包含X，O或是空白。为了用字典表示井字棋盘，您可以给每个格子定义字符串值，如图5-2所示。
[图5-2](https://automatetheboringstuff.com/images/000003.png)

This dictionary is a data structure that represents a tic-tac-toe board. Store this board-as-a-dictionary in a variable named theBoard. Open a new file editor window, and enter the following source code, saving it as ticTacToe.py:   
这个词典是一个数据结构，它表示一个井字棋盘。存储此字典在名为theBoard的变量中。打开一个新的文件编辑器窗口，然后输入以下代码，将其保存为ticTacToe.py：

	theBoard = {'top-L': ' ', 'top-M': ' ', 'top-R': ' ',
				'mid-L': ' ', 'mid-M': ' ', 'mid-R': ' ',
				'low-L': ' ', 'low-M': ' ', 'low-R': ' '}
				
The data structure stored in the theBoard variable represents the tic-tactoe  
存储在变量theBoard中的数据结构代表了井字棋盘如图5-3所示:

[图5-3](https://automatetheboringstuff.com/images/000006.png)

Since the value for every key in theBoard is a single-space string, this dictionary represents a completely clear board. If player X went first and chose the middle space, you could represent that board with this dictionary:  
由于在theBoard每个键的值都是一个空字符串.这个字典就代表了空白的棋盘。如果其中一个玩家x第一步选择了中间的位置,你需要用下面的字典来代表:

	theBoard = {'top-L': ' ', 'top-M': ' ', 'top-R': ' ',
				'mid-L': ' ', 'mid-M': 'X', 'mid-R': ' ',
				'low-L': ' ', 'low-M': ' ', 'low-R': ' '}
				
The data structure in theBoard now represents the tic-tac-toe board  
在theBoard的数据结构现在代表图5-4所示的井字棋盘.
[图5-4](https://automatetheboringstuff.com/images/000008.png)

A board where player O has won by placing Os across the top might look like this:  
如果玩家o通过在顶部多个0连成一行获胜看起来会是这样的:

	theBoard = {'top-L': 'O', 'top-M': 'O', 'top-R': 'O',
				'mid-L': 'X', 'mid-M': 'X', 'mid-R': ' ',
				'low-L': ' ', 'low-M': ' ', 'low-R': 'X'}
				
The data structure in theBoard now represents the tic-tac-toe board  
在theBoard的数据结构现在代表图5-5所示的井字棋盘.
[图5-5](https://automatetheboringstuff.com/images/000010.png)

Of course, the player sees only what is printed to the screen, not the contents of variables. Let’s create a function to print the board dictionary onto the screen. Make the following addition to ticTacToe.py (new code is in bold):  
当然，玩家只看到被打印到屏幕上的内容，并不是变量内容。让我们创建一个函数来打印棋盘字典到屏幕上。在ticTacToe.py中添加以下内容（新代码以粗体显示）：

	def printBoard(board):
		print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R'])
		print('-+-+-')
		print(board['mid-L'] + '|' + board['mid-M'] + '|' + board['mid-R'])
		print('-+-+-')
		print(board['low-L'] + '|' + board['low-M'] + '|' + board['low-R'])
	printBoard(theBoard)
	
When you run this program, printBoard() will print out a blank tic-tactoe board.  当你运行这个程序，printBoard（）将打印出棋盘如下。

	| |
	-+-+-
	| |
	-+-+-
	| |
	
The printBoard() function can handle any tic-tac-toe data structure you pass it. Try changing the code to the following:  
printBoard（）函数可以处理传递给它的任何井字棋的数据结构。试将代码改变为以下内容：

	theBoard = {'top-L': 'O', 'top-M': 'O', 'top-R': 'O', 'mid-L': 'X', 'mid-M':
	'X', 'mid-R': ' ', 'low-L': ' ', 'low-M': ' ', 'low-R': 'X'}

	def printBoard(board):
		print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R'])
		print('-+-+-')
		print(board['mid-L'] + '|' + board['mid-M'] + '|' + board['mid-R'])
		print('-+-+-')
		print(board['low-L'] + '|' + board['low-M'] + '|' + board['low-R'])
	printBoard(theBoard)
	
Now when you run this program, the new board will be printed to the screen.    
现在，当你运行这个程序，新的棋盘将被打印到屏幕上。

	O|O|O
	-+-+-
	X|X|
	-+-+-
	| |X  
	
Because you created a data structure to represent a tic-tac-toe board and wrote code in printBoard() to interpret that data structure, you now have a program that “models” the tic-tac-toe board. You could have organized your data structure differently (for example, using keys like 'TOP-LEFT' instead of 'top-L'), but as long as the code works with your data structures, you will have a correctly working program.   
因为你创建的数据结构来表示一个井字棋盘和printBoard代码来解释该数据结构，你现在有一个井字棋盘的“模板”程序.你可以以不同方式组织你的数据结构（例如，使用键值 'TOP-LEFT'代替 'top-L'），只要该代码可与您的数据结构匹配，你的程序就能正常运行。  

For example, the printBoard() function expects the tic-tac-toe data structure to be a dictionary with keys for all nine slots. If the dictionary you passed was missing, say, the 'mid-L' key, your program would no longer work.  
例如，printBoard（）函数需要井字棋数据结构是9个键值对的字典。假设字典少了'mid-L'键，你的程序将不再工作。

	O|O|O
	-+-+-
	Traceback (most recent call last):
	  File "ticTacToe.py", line 10, in <module>
		printBoard(theBoard)
	  File "ticTacToe.py", line 6, in printBoard
		print(board['mid-L'] + '|' + board['mid-M'] + '|' + board['mid-R'])
	KeyError: 'mid-L'

Now let’s add code that allows the players to enter their moves. Modify the ticTacToe.py program to look like this:  
现在，让我们添加代码，允许玩家进行旗子移动。像这样修改ticTacToe.py：

theBoard = {'top-L': ' ', 'top-M': ' ', 'top-R': ' ', 'mid-L': ' ', 'mid-M': ' ', 'mid-R': ' ', 'low-L': ' ', 'low-M': ' ', 'low-R': ' '}


	def printBoard(board):
		print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R'])
		print('-+-+-')
		print(board['mid-L'] + '|' + board['mid-M'] + '|' + board['mid-R'])
		print('-+-+-')
		print(board['low-L'] + '|' + board['low-M'] + '|' + board['low-R'])
	turn = 'X'
	for i in range(9):
		printBoard(theBoard)
		print('Turn for ' + turn + '. Move on which space?')
		move = input()
		theBoard[move] = turn
		if turn == 'X':
			turn = 'O'
		else:
			turn = 'X'
	printBoard(theBoard)
	
The new code prints out the board at the start of each new turn, gets the active player’s move, updates the game board accordingly and then swaps the active player before moving on to the next turn.
When you run this program, it will look something like this:  
新的代码在每一轮开始的时候打印出棋盘,并获取棋手的棋子动向,更新棋盘,并在下一轮棋手移动棋子前交换激活棋手.当你运行这个程序,你会看到类似这样的东西:

	 | |
	-+-+-
	 | |
	-+-+-
	 | |
	Turn for X. Move on which space?
	mid-M
	 | |
	-+-+-
	 |X|
	-+-+-
	 | |
	Turn for O. Move on which space?
	low-L
	 | |
	-+-+-
	 |X|
	-+-+-
	O| |

	--snip--

	O|O|X
	-+-+-
	X|X|O
	-+-+-
	O| |X
	Turn for X. Move on which space?
	low-M
	O|O|X
	-+-+-
	X|X|O
	-+-+-
	O|X|X
	
This isn’t a complete tic-tac-toe game—for instance, it doesn’t ever check whether a player has won—but it’s enough to see how data structures can be used in programs.  
这不是一个完整的井字棋游戏.例如，它没有在任何时候检查玩家是否赢得了比赛的功能,但它足以展示数据结构在程序中如何使用。  

If you are curious, the source code for a complete tic-tac-toe program is described in the resources available from http://nostarch.com/automatestuff/  
如果你很好奇，一个完整的井字棋程序的源代码是怎样的可以从http://nostarch.com/automatestuff/  获取资源.

##Nested Dictionaries and Lists
##嵌套的字典和列表

Modeling a tic-tac-toe board was fairly simple: The board needed only a single dictionary value with nine key-value pairs. As you model more complicated things, you may find you need dictionaries and lists that contain other dictionaries and lists. Lists are useful to contain an ordered series of values, and dictionaries are useful for associating keys with values. For example, here’s a program that uses a dictionary that contains other dictionaries in order to see who is bringing what to a picnic. The totalBrought() function can read this data structure and calculate the total number of an item being brought by all the guests.  
建模井字棋盘是相当简单：该模型只需要九个键-值对的字典值.当你想建模更复杂的东西，你会发现你需要字典和列表中包含其他字典和列表.列表在包含有序值序列时非常有用，字典在键与值相关联时非常有用.例如,下面是一个使用包含其它有序字典,查看谁带来什么野餐的程序。totalBrought（）函数可以读取该数据结构并通过计算得到客人带某一个食物的总数.

	allGuests = {'Alice': {'apples': 5, 'pretzels': 12},
				 'Bob': {'ham sandwiches': 3, 'apples': 2},
				 'Carol': {'cups': 3, 'apple pies': 1}}


	def totalBrought(guests, item):
		numBrought = 0
		for k, v in guests.items():
			numBrought = numBrought + v.get(item, 0)
		return numBrought

	print('Number of things being brought:')
	print(' - Apples         ' + str(totalBrought(allGuests, 'apples')))
	print(' - Cups           ' + str(totalBrought(allGuests, 'cups')))
	print(' - Cakes          ' + str(totalBrought(allGuests, 'cakes')))
	print(' - Ham Sandwiches ' + str(totalBrought(allGuests, 'ham sandwiches')))
	print(' - Apple Pies     ' + str(totalBrought(allGuests, 'apple pies')))

Inside the totalBrought() function, the for loop iterates over the key-value pairs in guests. Inside the loop, the string of the guest’s name is assigned to k, and the dictionary of picnic items they’re bringing is assigned to v. If the item parameter exists as a key in this dictionary, it’s value (the quantity) is added to numBrought. If it does not exist as a key, the get() method returns 0 to be added to numBrought.
The output of this program looks like this:    
在totalBrought()中,采用了键值对来循环迭代.在循环中，客人名称的字符串被分配到K，他们带来的野餐字符串被分配到v,如果该项目参数存在如本字典的键，它的值（数量）加入到numBrought中.如果它不存在，则get（）方法返回0被添加到numBrought。整个程序运行输出如下:

	Number of things being brought:
	- Apples 7
	- Cups 3
	- Cakes 0
	- Ham Sandwiches 3
	- Apple Pies     1

This may seem like such a simple thing to model that you wouldn’t need to bother with writing a program to do it. But realize that this same totalBrought() function could easily handle a dictionary that contains thousands of guests, each bringing thousands of different picnic items. Then having this information in a data structure along with the totalBrought() function would save you a lot of time!  
这似乎是这样一个简单事情的模型，你不会需要编写一个程序来做到这一点.但是，认识到totalBrought()函数通过字典，可以很容易地处理包含成千上万的客人，每人带来数千种不同野餐项目。当遇到具有类似数据结构信息的事务需要处理时totalBrought()函数会为您节省大量的时间！  

You can model things with data structures in whatever way you like, as long as the rest of the code in your program can work with the data model correctly. When you first begin programming, don’t worry so much about the “right” way to model data. As you gain more experience, you may come up with more efficient models, but the important thing is that the data model works for your program’s needs.  
你可以以你喜欢的方式对任何数据结构建模,只要在你的程序中用数据模型可以正常工作。当你第一次开始编程，不用太在乎是否使用了“正确”的数据模型.当你获得更多的经验，你就能实现更多有效的模型，但重要的是，数据模型适用于你的程序的需求。  

##Summary 总结

You learned all about dictionaries in this chapter. Lists and dictionaries are values that can contain multiple values, including other lists and dictionaries. Dictionaries are useful because you can map one item (the key) to another (the value), as opposed to lists, which simply contain a series of values in order. Values inside a dictionary are accessed using square brackets just as with lists. Instead of an integer index, dictionaries can have keys of a variety of data types: integers, floats, strings, or tuples. By organizing a program’s values into data structures, you can create representations of real-world objects. You saw an example of this with a tic-tac-toe board.  
你在本章学习了字典。列表和字典可以包含多个值，也可以包括其他列表和字典值。字典可以映射一个键到另一个值，相对于列表，它只是简单地包含一系列值的顺序。字典里面的值像列表一样可以用方括号访问.和列表的整数索引不同，字典可以有多种数据类型的键：整数，浮点数，字符串或元组。通过程序的将值转换为数据结构，您可以创建现实世界对象的模型。就像井字棋盘例子一样。

##Practice Questions练习题

Q:1. What does the code for an empty dictionary look like?
Q:2. What does a dictionary value with a key 'foo' and a value 42 look like?
Q:3. What is the main difference between a dictionary and a list?
Q:4. What happens if you try to access spam['foo'] if spam is {'bar': 100}?
Q:5. If a dictionary is stored in spam, what is the difference between the expressions 'cat' in spam and 'cat' in spam.keys()?
Q:6. If a dictionary is stored in spam, what is the difference between the expressions 'cat' in spam and 'cat' in spam.values()?
Q:7. What is a shortcut for the following code?

if 'color' not in spam:
    spam['color'] = 'black'
Q:8. What module and function can be used to “pretty print” dictionary values?  

Practice Projects
For practice, write programs to do the following tasks.  
编写程序来执行以下任务  

Fantasy Game Inventory  
幻想游戏

You are creating a fantasy video game. The data structure to model the player’s inventory will be a dictionary where the keys are string values describing the item in the inventory and the value is an integer value detailing how many of that item the player has. For example, the dictionary value {'rope': 1, 'torch': 6, 'gold coin': 42, 'dagger': 1, 'arrow': 12} means the player has 1 rope, 6 torches, 42 gold coins, and so on.   
您正在创建一个幻想视频游戏。玩家背包的数据结构是一本字典，其键是各装备名称字符串，其值是一个整数代表玩家拥有某种装备多少件。例如:一个值如下的字典:{'rope': 1, 'torch': 6, 'gold coin': 42, 'dagger': 1, 'arrow': 12}表示该玩家拥有绳1根，火把6只，金币42个,匕首1把，箭头12只

Write a function named displayInventory() that would take any possible “inventory” and display it like the following:  
编写一个名为displayInventory（）的函数，包含任何可能的装备并且按照以下方式显示出来:

	Inventory:
	12 arrow
	42 gold coin
	1 rope
	6 torch
	1 dagger
	Total number of items: 62
	
Hint: You can use a for loop to loop through all the keys in a dictionary.  
提示：您可以通过for循环遍历字典中的所有键。

	# inventory.py
	stuff = {'rope': 1, 'torch': 6, 'gold coin': 42, 'dagger': 1, 'arrow': 12}

	def displayInventory(inventory):
		print("Inventory:")
		item_total = 0
		for k, v in inventory.items():
			# FILL IN THE CODE HERE
		print("Total number of items: " + str(item_total))

	displayInventory(stuff)
	
List to Dictionary Function for Fantasy Game Inventory
列表转成字典函数幻想游戏

Imagine that a vanquished dragon’s loot is represented as a list of strings like this:  
假设，杀死一条龙的战利品表示为这样的字符串列表：

	dragonLoot = ['gold coin', 'dagger', 'gold coin', 'gold coin', 'ruby']

Write a function named addToInventory(inventory, addedItems), where the inventory parameter is a dictionary representing the player’s inventory (like in the previous project) and the addedItems parameter is a list like dragonLoot. The addToInventory() function should return a dictionary that represents the updated inventory. Note that the addedItems list can contain multiples of the same item. Your code could look something like this:  
编写一个函数addToInventory(inventory, addedItems)添加战利品到玩家背包.addedItems参数是dragonLoot爆出物品列表。函数的返回是更新玩家背包.注意，addedItems列表可包含相同项目。您的代码可以是这个样子：

	def addToInventory(inventory, addedItems):
		# your code goes here

	inv = {'gold coin': 42, 'rope': 1}
	dragonLoot = ['gold coin', 'dagger', 'gold coin', 'gold coin', 'ruby']
	inv = addToInventory(inv, dragonLoot)
	displayInventory(inv)

The previous program (with your displayInventory() function from the previous project) would output the following:  
用前面编写的displayInventory（）函数将输出以下内容：  

	Inventory:
	45 gold coin
	1 rope
	1 ruby
	1 dagger

	Total number of items: 48
