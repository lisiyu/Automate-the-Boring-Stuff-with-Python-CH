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
setdefault（）方法是一个很好的确保关键存在的快捷方式。这里有一个很短的程序用来计算字符串中的每个字母出现的次数。打开文件编辑器窗口，并输入以下代码，将其保存为characterCount.py：

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