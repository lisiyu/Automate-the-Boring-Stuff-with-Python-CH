# list 列表
## [相关视频教程](https://youtu.be/5n6o1MaXDoE)

One more topic you’ll need to understand before you can begin writing programs in earnest is the list data type and its cousin, the tuple. Lists and tuples can contain multiple values, which makes it easier to write programs that handle large amounts of data. And since lists themselves can contain other lists, you can use them to arrange data into hierarchical structures.  
在你真正开始编写程序还有一个重要项目需要明白,这就是列表数据类型和他的表弟，定值列表。列表和定值列表可以包含多个值，这使得它更容易编写处理大量数据的程序。而且，由于列表内部可以包含其他列表，你可以用它们来进行数据排序操作.    
In this chapter, I’ll discuss the basics of lists. I’ll also teach you about methods, which are functions that are tied to values of a certain data type. Then I’ll briefly cover the list-like tuple and string data types and how they compare to list values. In the next chapter, I’ll introduce you to the dictionary data type.  
在本章中，我们将学习列表的基础知识。我也会教你使用函数把数值绑定到某一数据类型的方法.然后，我将简要介绍和列表数据类型类似的定值列表和字符串数据类型，以及他们和列表数据类型的区别.在下一章中，我将向您介绍字典数据类型.  

## The List Data Type 列表数据类型

A list is a value that contains multiple values in an ordered sequence. The term list value refers to the list itself (which is a value that can be stored in a variable or passed to a function like any other value), not the values inside the list value. A list value looks like this: ['cat', 'bat', 'rat', 'elephant']. Just as string values are typed with quote characters to mark where the string begins and ends, a list begins with an opening square bracket and ends with a closing square bracket, []. Values inside the list are also called items. Items are separated with commas (that is, they are comma-delimited). For example, enter the following into the interactive shell:  
列表是包含多个有序序列值的值。术语'列表值'指的是列表本身（这可以存储在一个变量中或像任何其他函数的值一样可以传递），而不是指列表内的元素的值。一个列表的值看起来像这样:['cat', 'bat', 'rat', 'elephant'].他是以左方括号开始中间用引号引起来的区分每个字符串开始和结尾,字符串之间用逗号隔开并以右方括号结束.列表内的值也被称为项目。项目之间用逗号分开（也就是说，它们是用逗号分隔）。例如，输入以下内容到交互窗体：  

	>>> [1, 2, 3]
	   [1, 2, 3]
	   >>> ['cat', 'bat', 'rat', 'elephant']
	   ['cat', 'bat', 'rat', 'elephant']
	   >>> ['hello', 3.1415, True, None, 42]
	   ['hello', 3.1415, True, None, 42]
	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	   >>> spam
	   ['cat', 'bat', 'rat', 'elephant']

The spam variable is still assigned only one value: the list value. But the list value itself contains other values. The value [] is an empty list that contains no values, similar to '', the empty string.  
变量spam还是只分配了一个值：列表值。但列表值本身包含其他值。列表[]不包含任何值，类似于''空字符串/我们称为空列表。

## Getting Individual Values in a List with Indexes
## 用索引来访问列表中的项目值

Say you have the list ['cat', 'bat', 'rat', 'elephant'] stored in a variable named spam. The Python code spam[0] would evaluate to 'cat', and spam[1] would evaluate to 'bat', and so on. The integer inside the square brackets that follows the list is called an index. The first value in the list is at index 0, the second value is at index 1, the third value is at index 2, and so on. Figure 4-1 shows a list value assigned to spam, along with what the index expressions would evaluate to.  
假设你有一个列表['cat', 'bat', 'rat', 'elephant']存储在一个变量spam中.Python代码会将spam[0]值识别为为“cat”，spam[1]识别为“bat”，依此类推。列表中方括号内的整数称为索引.列表中的第一个值是在索引0，第二个值是在索引1中，第三个值是在索引2，依此类推.图4-1显示分配给spam列表的值及对应索引表达式。
  
![图4-1](https://automatetheboringstuff.com/images/000074.png)
> Figure 4-1. A list value stored in the variable spam, showing which value each index refers to  

For example, type the following expressions into the interactive shell. Start by assigning a list to the variable spam.  
例如，键入下面的表达式到交互窗体。我们从给变量spam赋值一个列表开始学起。  

	   >>> spam = ['cat', 'bat', 'rat', 'elephant']
	   >>> spam[0]
	   'cat'
	   >>> spam[1]
	   'bat'
	   >>> spam[2]
	   'rat'
	   >>> spam[3]
	   'elephant'
	   >>> ['cat', 'bat', 'rat', 'elephant'][3]
	   'elephant'
	(1) >>> 'Hello ' + spam[0]
	(2)'Hello cat'
	   >>> 'The ' + spam[1] + ' ate the ' + spam[0] + '.'
	   'The bat ate the cat.'
	   
Notice that the expression 'Hello ' + spam[0] ➊ evaluates to 'Hello ' + 'cat' because spam[0] evaluates to the string 'cat'. This expression in turn evaluates to the string value 'Hello cat'   
请注意，表达“Hello”+spam[0](1)计算结果为'Hello'+'cat'，因为spam[0]计算得到字符串'cat'。这个表达式的字符串值“Hello cat"  
Python will give you an IndexError error message if you use an index that exceeds the number of values in your list value.  
如果使用超过列表值项目数的索引值Python将会给你一个IndexError错误消息.  

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[10000]
	Traceback (most recent call last):
	  File "<pyshell#9>", line 1, in <module>
		spam[10000]
	IndexError: list index out of range

Indexes can be only integer values, not floats. The following example will cause a TypeError error:  
索引只能是整数值，不能是浮点数。下面的例子将导致一个TypeError错误

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[1]
	'bat'
	>>> spam[1.0]
	Traceback (most recent call last):
	  File "<pyshell#13>", line 1, in <module>
		spam[1.0]
	TypeError: list indices must be integers, not float
	>>> spam[int(1.0)]
	'bat' 
	 
Lists can also contain other list values. The values in these lists of lists can be accessed using multiple indexes, like so:  
列表还可以包含其他列表值。在列表中的这些列表值可以使用多个索引，像这样来访问：
  
	>>> spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]
	>>> spam[0]
	['cat', 'bat']
	>>> spam[0][1]
	'bat'
	>>> spam[1][4]
	50
	
The first index dictates which list value to use, and the second indicates the value within the list value. For example, spam[0][1] prints 'bat', the second value in the first list. If you only use one index, the program will print the full list value at that index.   
第一索引指示要使用哪个列表值，第二表示列表值内的值。例如，spam[0] [1]打印“bat”，他是第一个列表中的第二个值.如果您只使用一个索引，该程序将打印索引处的完整列表值。  

## Negative Indexes 负索引

While indexes start at 0 and go up, you can also use negative integers for the index. The integer value -1 refers to the last index in a list, the value -2 refers to the second-to-last index in a list, and so on. Enter the following into the interactive shell:  
虽然索引从0开始增加，你也可以使用负整数的索引。整数值-1指的是在一个列表中的最后一个索引，值-2是指列表中倒数第二个值的索引，依此类推.输入以下内容到交互窗口： 
 
	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[-1]
	'elephant'
	>>> spam[-3]
	'bat'
	>>> 'The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.'
	'The elephant is afraid of the bat.'  
	
## Getting Sublists with Slices 通过切片获取子列表  

Just as an index can get a single value from a list, a slice can get several values from a list, in the form of a new list. A slice is typed between square brackets, like an index, but it has two integers separated by a colon. Notice the difference between indexes and slices.  
和索引可以从一个列表中的获取单个单个值类似，切片可以从列表获得多个值，并以一个新的列表形式显示。切片的表达形式和索引类似都是在中括号中,但是切片是两个以冒号分隔的整数值.注意索引和切片之间的差异.  

	spam[2] is a list with an index (one integer).
	spam[1:4] is a list with a slice (two integers).

In a slice, the first integer is the index where the slice starts. The second integer is the index where the slice ends. A slice goes up to, but will not include, the value at the second index. A slice evaluates to a new list value. Enter the following into the interactive shell:  
在一个切片中，第一整数是切片的开始索引。第二个整数是切片的结束索引。切片取索引值依次增加到第二个值，但不会包括在第二索引处的值。在交互窗体输入以下代码: 
 
	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[0:4]
	['cat', 'bat', 'rat', 'elephant']
	>>> spam[1:3]
	['bat', 'rat']
	>>> spam[0:-1]
	['cat', 'bat', 'rat']

As a shortcut, you can leave out one or both of the indexes on either side of the colon in the slice. Leaving out the first index is the same as using 0, or the beginning of the list. Leaving out the second index is the same as using the length of the list, which will slice to the end of the list. Enter the following into the interactive shell:  
你可以在切片冒号的两侧留空一个或同时留空作为一种快捷方式。第一索引值留空和使用0效果一样或者代表从列表的开头起。第二个索引值留空这将切片到列表的末尾.在交互窗体输入以下代码: 

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[:2]
	['cat', 'bat']
	>>> spam[1:]
	['bat', 'rat', 'elephant']
	>>> spam[:]
	['cat', 'bat', 'rat', 'elephant']
	
## Getting a List’s Length with len()  获得一个列表的长度LEN（）

The len() function will return the number of values that are in a list value passed to it, just like it can count the number of characters in a string value. Enter the following into the interactive shell:   
该LEN（）函数将返回是一个列表的项目的数目，就像它可以返回一个字符串值的字符长度。在交互窗体输入以下代码:

	>>> spam = ['cat', 'dog', 'moose']
	>>> len(spam)
	3 

## Changing Values in a List with Indexes 通过索引改变表变值

Normally a variable name goes on the left side of an assignment statement, like spam = 42. However, you can also use an index of a list to change the value at that index. For example, spam[1] = 'aardvark' means “Assign the value at index 1 in the list spam to the string 'aardvark'.” Enter the following into the interactive shell:  
通常，变量名在赋值语句的左边，如spam = 42.同样的您也可以使用列表的索引来修改该索引处的数值。例如，spam[1] = 'aardvark' 的意思是将spam列表中索引1的值修改为字符串'aardvark'。 在交互窗体输入以下代码: 

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam[1] = 'aardvark'
	>>> spam
	['cat', 'aardvark', 'rat', 'elephant']
	>>> spam[2] = spam[1]
	>>> spam
	['cat', 'aardvark', 'aardvark', 'elephant']
	>>> spam[-1] = 12345
	>>> spam
	['cat', 'aardvark', 'aardvark', 12345]

## List Concatenation and List Replication列表的连接和复制

The + operator can combine two lists to create a new list value in the same way it combines two strings into a new string value. The * operator can also be used with a list and an integer value to replicate the list. Enter the following into the interactive shell:  

+运算符可以将两个列表相加创建一个新的列表值，它是将两个列表字符串合并到一个新的列表.*运算符也可以将列表复制相应的整数次组成新的列表。输入以下内容到交互窗体:  

	>>> [1, 2, 3] + ['A', 'B', 'C']
	[1, 2, 3, 'A', 'B', 'C']
	>>> ['X', 'Y', 'Z'] * 3
	['X', 'Y', 'Z', 'X', 'Y', 'Z', 'X', 'Y', 'Z']
	>>> spam = [1, 2, 3]
	>>> spam = spam + ['A', 'B', 'C']
	>>> spam
	[1, 2, 3, 'A', 'B', 'C']
	
## Removing Values from Lists with del Statements用del语句删除列表中的值

The del statement will delete values at an index in a list. All of the values in the list after the deleted value will be moved up one index. For example, enter the following into the interactive shell:  
del语句将列表中指定索引中的值删除。在索引值被删除后之后，列表中的值将上移一个索引。例如，输入以下内容到交互窗体：

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> del spam[2]
	>>> spam
	['cat', 'bat', 'elephant']
	>>> del spam[2]
	>>> spam
	['cat', 'bat']
	
The del statement can also be used on a simple variable to delete it, as if it were an “unassignment” statement. If you try to use the variable after deleting it, you will get a NameError error because the variable no longer exists.  
del语句也可以用来删除一个变量，就好像它是一个“取消分配”的声明语句。如果你尝试在删除后使用变量，你会得到一个NameError错误，因为变量已经不存在。  
In practice, you almost never need to delete simple variables. The del statement is mostly used to delete values from lists.  
在实践中，你几乎永远不需要删除变量。 del语句主要是用来从列表中删除值。  

## Working with Lists 用列表开展工作

When you first begin writing programs, it’s tempting to create many individual variables to store a group of similar values. For example, if I wanted to store the names of my cats, I might be tempted to write code like this:  
当你第一次开始写程序，很可能创建许多单独的变量来存储一组类似的值。例如，我想保存我的猫的名字，我可能会写这样的代码：  

	catName1 = 'Zophie'
	catName2 = 'Pooka'
	catName3 = 'Simon'
	catName4 = 'Lady Macbeth'
	catName5 = 'Fat-tail'
	catName6 = 'Miss Cleo'
	
(I don’t actually own this many cats, I swear.) It turns out that this is a bad way to write code. For one thing, if the number of cats changes, your program will never be able to store more cats than you have variables. These types of programs also have a lot of duplicate or nearly identical code in them. Consider how much duplicate code is in the following program, which you should enter into the file editor and save as allMyCats1.py:  
(我发誓,我实际上并不拥有这么多猫。)事实证明，这是一个糟糕的代码实现方​​式。一方面，如果猫的数量变化，你的程序将永远无法存储比你变量更多的猫。这些类型的程序也有很多重复或几乎相同的代码。想想在下面的程序有多少重复的代码，进入文件编辑器，并保存为allMyCats1.py：  

	print('Enter the name of cat 1:')
	catName1 = input()
	print('Enter the name of cat 2:')
	catName2 = input()
	print('Enter the name of cat 3:')
	catName3 = input()
	print('Enter the name of cat 4:')
	catName4 = input()
	print('Enter the name of cat 5:')
	catName5 = input()
	print('Enter the name of cat 6:')
	catName6 = input()
	print('The cat names are:')
	print(catName1 + ' ' + catName2 + ' ' + catName3 + ' ' + catName4 + ' ' +
	catName5 + ' ' + catName6)
	
Instead of using multiple, repetitive variables, you can use a single variable that contains a list value. For example, here’s a new and improved version of the allMyCats1.py program. This new version uses a single list and can store any number of cats that the user types in. In a new file editor window, type the following source code and save it as allMyCats2.py:  
你可以使用一个包含列表值的单变量而不是使用多个重复的变量。例如，这里新的allMyCats1.py程序改进的版本.新版本使用一个单独的列表，并可以存储任意数量的猫，在用户键入一个新的文件编辑器窗口中，键入下面的源代码，并保存为allMyCats2.py:  

	catNames = []
	while True:
		print('Enter the name of cat ' + str(len(catNames) + 1) +
		  ' (Or enter nothing to stop.):')
		name = input()
		if name == '':
			break
		catNames = catNames + [name] # list concatenation
	print('The cat names are:')
	for name in catNames:
		print('  ' + name)
		
When you run this program, the output will look something like this:  
当你运行这个程序，输出会是这个样子：  

	Enter the name of cat 1 (Or enter nothing to stop.):
	Zophie
	Enter the name of cat 2 (Or enter nothing to stop.):
	Pooka
	Enter the name of cat 3 (Or enter nothing to stop.):
	Simon
	Enter the name of cat 4 (Or enter nothing to stop.):
	Lady Macbeth
	Enter the name of cat 5 (Or enter nothing to stop.):
	Fat-tail
	Enter the name of cat 6 (Or enter nothing to stop.):
	Miss Cleo
	Enter the name of cat 7 (Or enter nothing to stop.):

	The cat names are:
	  Zophie
	  Pooka
	  Simon
	  Lady Macbeth
	  Fat-tail
	  Miss Cleo
	  
The benefit of using a list is that your data is now in a structure, so your program is much more flexible in processing the data than it would be with several repetitive variables.  
使用列表的好处是将你的数据结构化，所以程序在处理数据时比几个重复变量更加灵活。

## Using for Loops with Lists  使用for循环使用列表
## [相关教学视频](https://youtu.be/umTnflPbYww)

In Chapter 2, you learned about using for loops to execute a block of code a certain number of times. Technically, a for loop repeats the code block once for each value in a list or list-like value. For example, if you ran this code:  
在第二章中，您了解了使用循环让代码块重复执行若干次。从技术上讲，一个for循环中的代码块重复执行相当于按照列表或类似列表的值中的每一个值执行一次。例如，下面的代码：

	for i in range(4):
		print(i)
	
the output of this program would be as follows:  
代码执行结果如下

	0
	1
	2
	3
	
This is because the return value from range(4) is a list-like value that Python considers similar to [0, 1, 2, 3]. The following program has the same output as the previous one:    
这是因为range(4)的返回值Python认定类似于列表值[0，1，2，3]。下面的程序具有与前一个相同的输出：  

	for i in [0, 1, 2, 3]:
		print(i)

What the previous for loop actually does is loop through its clause with the variable i set to a successive value in the [0, 1, 2, 3] list in each iteration.   前面的for循环实际上是通过i每次值取列表[0，1，2，3]的索引值为连续递增变量子句实现。
 > NOTE In this book, I use the term list-like to refer to data types that are technically named sequences. You don’t need to know the technical definitions of this term, though.  
> 注意 在这本书中，我使用术语列表类似指代在技术上命名类似列表的数据类型。你不需要知道这个词的技术定义.

A common Python technique is to use range(len(someList)) with a for loop to iterate over the indexes of a list. For example, enter the following into the interactive shell:  
一个常见的​​Python用法是使用range(LEN(someList))for循环遍历列表的索引。例如，输入以下内容带交互窗体：  

	>>> supplies = ['pens', 'staplers', 'flame-throwers', 'binders']
	>>> for i in range(len(supplies)):
		print('Index ' + str(i) + ' in supplies is: ' + supplies[i])

	Index 0 in supplies is: pens
	Index 1 in supplies is: staplers
	Index 2 in supplies is: flame-throwers
	Index 3 in supplies is: binders

Using range(len(supplies)) in the previously shown for loop is handy because the code in the loop can access the index (as the variable i) and the value at that index (as supplies[i]). Best of all, range(len(supplies)) will iterate through all the indexes of supplies, no matter how many items it contains.  
在先前所示的range(len(supplies)) 是非常方便的，因为在循环的代码可以访问的索引（作为变量i）和值索引处(supplies[i])。最重要的是range(len(supplies))可以遍历所有索引对应的内容,无论包含多少个项目。

## The in and not in Operators 
## in和not in操作符


You can determine whether a value is or isn’t in a list with the in and not in operators. Like other operators, in and not in are used in expressions and connect two values: a value to look for in a list and the list where it may be found. These expressions will evaluate to a Boolean value. Enter the following into the interactive shell:  
你可以用in 或not in运算符判断一个值是否存在一个列表中.和其他操作运算符一样,in和not in运算符用在表达式中连接两个值:一个在列表中寻的值和可能被找到这个值的列表.这个运算符的结果是一个布尔值.在交互窗体中输入以下代码:  

	>>> 'howdy' in ['hello', 'hi', 'howdy', 'heyas']
	True
	>>> spam = ['hello', 'hi', 'howdy', 'heyas']
	>>> 'cat' in spam
	False
	>>> 'howdy' not in spam
	False
	>>> 'cat' not in spam
	True

For example, the following program lets the user type in a pet name and then checks to see whether the name is in a list of pets. Open a new file editor window, enter the following code, and save it as myPets.py:  
例如，下面的程序可以让用户输入一个宠物的名字，然后再检查看名字是否在宠物列表中。打开一个新的文件编辑器窗口，输入以下代码，并保存为myPets.py：  

	myPets = ['Zophie', 'Pooka', 'Fat-tail']
	print('Enter a pet name:')
	name = input()
	if name not in myPets:
		print('I do not have a pet named ' + name)
	else:
		print(name + ' is my pet.')
	The output may look something like this:

	Enter a pet name:
	Footfoot
	I do not have a pet named Footfoot  
	
##The Multiple Assignment Trick  
##多重赋值技巧 
The multiple assignment trick is a shortcut that lets you assign multiple variables with the values in a list in one line of code. So instead of doing this:  
多重赋值技巧是一个快捷方式，可以让你在一行代码中通过列表给多个变量同时赋值,以代替这样的繁琐赋值方式:

	>>> cat = ['fat', 'orange', 'loud']
	>>> size = cat[0]
	>>> color = cat[1]
	>>> disposition = cat[2]
	
you could type this line of code:  你可以在一行内这样写  
	
	>>> cat = ['fat', 'orange', 'loud']
	>>> size, color, disposition = cat
	
The number of variables and the length of the list must be exactly equal, or Python will give you a ValueError:  
变量的数目和列表的长度必须完全相等，否则Python会给你一个ValueError错误：  

	>>> cat = ['fat', 'orange', 'loud']
	>>> size, color, disposition, name = cat
	Traceback (most recent call last):
	  File "<pyshell#84>", line 1, in <module>
		size, color, disposition, name = cat
	ValueError: need more than 3 values to unpack
	
The multiple assignment trick can also be used to swap the values in two variables:  
多重赋值技巧也可以用于交换两个变量的值：  

	>>> a, b = 'Alice', 'Bob'
	>>> a, b = b, a
	>>> print(a)
	'Bob'
	>>> print(b)
	'Alice'
	
##Augmented Assignment Operators
##增强赋值运算符

When assigning a value to a variable, you will frequently use the variable itself. For example, after assigning 42 to the variable spam, you would increase the value in spam by 1 with the following code:  
当值分配给一个变​​量，你会经常使用的变量本身。例如，分配42给变量spam后，可以通过下面的代码增加spam值：  

	>>> spam = 42
	>>> spam = spam + 1
	>>> spam
	43
	
As a shortcut, you can use the augmented assignment operator += to do the same thing:  
作为一种快捷方式，可以使用增强赋值运算符+ =做同样的事情： 
 
	>>> spam = 42
	>>> spam += 1
	>>> spam
	43

###Table 4-1. The Augmented Assignment Operators	

|Augmented assignment statement |Equivalent assignment statement |  
| ---|--- |
|spam += 1 |spam = spam + 1 |  
|spam -= 1 |spam = spam - 1 |  
|spam *= 1 |spam = spam * 1 |  
|spam /= 1 |spam = spam / 1 |  
|spam %= 1 |spam = spam % 1 |  

The += operator can also do string and list concatenation, and the *= operator can do string and list replication. Enter the following into the interactive shell:  
	+=运算符也可以做字符串连接列表，而* =运算符可以做字符串和列表复制。输入以下内容交互的shell：
	
	>>> spam = 'Hello'
	>>> spam += ' world!'
	>>> spam
	'Hello world!'

	>>> bacon = ['Zophie']
	>>> bacon *= 3
	>>> bacon
	['Zophie', 'Zophie', 'Zophie']


##Methods 方法
[相关视频教程](https://youtu.be/Z9IxxW7428A)

A method is the same thing as a function, except it is “called on” a value. For example, if a list value were stored in spam, you would call the index() list method (which I’ll explain next) on that list like so: spam.index('hello'). The method part comes after the value, separated by a period.  
方法类似于函数,只不过他调用返回为值.例如,如果有一个列表存在spam中,你可以像这样spam.index('hello')调用列表的index() 方法来获取一个值, 方法跟随在用点号隔开的变量后面.  
Each data type has its own set of methods. The list data type, for example, has several useful methods for finding, adding, removing, and otherwise manipulating values in a list.  
每个数据类型都有其自己的一套方法。例如,列表数据类型具有用于在列表中查找，添加，删除和以其他方式操纵值的方法。  
###Finding a Value in a List with the index() Method
###用index()方法在列表找查找某个值

List values have an index() method that can be passed a value, and if that value exists in the list, the index of the value is returned. If the value isn’t in the list, then Python produces a ValueError error. Enter the following into the interactive shell:  
列表中的值具有可传递值的index()方法，如果该列表中存在该值就会返回这个值的索引.如果该值不在列表中，那么Python产生ValueError异常错误。输入以下内容到交互窗体：  

	>>> spam = ['hello', 'hi', 'howdy', 'heyas']
	>>> spam.index('hello')
	0
	>>> spam.index('heyas')
	3
	>>> spam.index('howdy howdy howdy')
	Traceback (most recent call last):
	  File "<pyshell#31>", line 1, in <module>
		spam.index('howdy howdy howdy')
	ValueError: 'howdy howdy howdy' is not in list

When there are duplicates of the value in the list, the index of its first appearance is returned. Enter the following into the interactive shell, and notice that index() returns 1, not 3:  
当在列表中存在多个相同的值，则返回其第一次出现的索引。输入以下内容交互窗体并注意index()返回1，而不是3：

	>>> spam = ['Zophie', 'Pooka', 'Fat-tail', 'Pooka']
	>>> spam.index('Pooka')
	1
		
###Adding Values to Lists with the append() and insert() Methods
###用append()和insert()方法向列表中增加值

To add new values to a list, use the append() and insert() methods. Enter the following into the interactive shell to call the append() method on a list value stored in the variable spam:  
使用append（）和insert（）方法将新值添加到列表。输入以下内容到交互窗体.调用append（）方法对存储在变量spam的值进行操作：  

	>>> spam = ['cat', 'dog', 'bat']
	>>> spam.append('moose')
	>>> spam
	['cat', 'dog', 'bat', 'moose']
	
The previous append() method call adds the argument to the end of the list. The insert() method can insert a value at any index in the list. The first argument to insert() is the index for the new value, and the second argument is the new value to be inserted. Enter the following into the interactive shell:  
append()方法是增加参数到列表的末尾.insert()方法可以在列表任意索引位置插入值.insert()方法的第一个参数是插入新值的位置索引,第二个参数是插入列表的新的值.在交互窗体输入以下内容:  

	>>> spam = ['cat', 'dog', 'bat']
	>>> spam.insert(1, 'chicken')
	>>> spam
	['cat', 'chicken', 'dog', 'bat']

Notice that the code is spam.append('moose') and spam.insert(1, 'chicken'), not spam = spam.append('moose') and spam = spam.insert(1, 'chicken'). Neither append() nor insert() gives the new value of spam as its return value. (In fact, the return value of append() and insert() is None, so you definitely wouldn’t want to store this as the new variable value.) Rather, the list is modified in place. Modifying a list in place is covered in more detail later in Mutable and Immutable Data Types.  
请注意代码spam.append('moose')和spam.insert(1, 'chicken'), 并是指spam = spam.append('moose')和spam = spam.insert(1, 'chicken'). append() 和 insert()都没有给spam新的值并返回他们.事实上 append()和insert()的返回值是None,所以你绝对不要认为是作为新的变量值存储。相反,列表只是本地进行修改.本地修改列表数据在后面的可变和不可变的数据类型中将详细讲解.  
Methods belong to a single data type. The append() and insert() methods are list methods and can be called only on list values, not on other values such as strings or integers. Enter the following into the interactive shell, and note the AttributeError error messages that show up:  
方法属于某个单一数据类型。append()和insert()方法是列表数据的方法只能在列表数据类型中被调用,不可以在整形或字符串数据类型中使用.在交互窗体输入以下类容,并留意返回的错误提醒.  
 
	>>> eggs = 'hello'
	>>> eggs.append('world')
	Traceback (most recent call last):
	  File "<pyshell#19>", line 1, in <module>
		eggs.append('world')
	AttributeError: 'str' object has no attribute 'append'
	>>> bacon = 42
	>>> bacon.insert(1, 'world')
	Traceback (most recent call last):
	  File "<pyshell#22>", line 1, in <module>
		bacon.insert(1, 'world')
	AttributeError: 'int' object has no attribute 'insert'
	
###Removing Values from Lists with remove()
###使用remove()方法从列表删除删除值

The remove() method is passed the value to be removed from the list it is called on. Enter the following into the interactive shell:  
remove()方法调用时将其传递的值从列表中删除.在交互窗体输入以下内容:

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam.remove('bat')
	>>> spam
	['cat', 'rat', 'elephant']
	
Attempting to delete a value that does not exist in the list will result in a ValueError error. For example, enter the following into the interactive shell and notice the error that is displayed:  
试图删除不存在列表中的值将导致ValueError异常。例如，输入以下内容到交互窗体，并注意所显示的错误：  

	>>> spam = ['cat', 'bat', 'rat', 'elephant']
	>>> spam.remove('chicken')
	Traceback (most recent call last):
	  File "<pyshell#11>", line 1, in <module>
		spam.remove('chicken')
	ValueError: list.remove(x): x not in list
	
If the value appears multiple times in the list, only the first instance of the value will be removed. Enter the following into the interactive shell:  
如果该值中多次出现在列表中，仅第一个值的实例将被删除。输入以下内容到交互窗体：  

	>>> spam = ['cat', 'bat', 'rat', 'cat', 'hat', 'cat']
	>>> spam.remove('cat')
	>>> spam
	['bat', 'rat', 'cat', 'hat', 'cat']
	
The del statement is good to use when you know the index of the value you want to remove from the list. The remove() method is good when you know the value you want to remove from the list.  
如果你知道你想从列表中删除的值的索引可以使用del()语句。如果你知道你想从列表中删除的值可以使用remove()方法。  

###Sorting the Values in a List with the sort() Method
###用sort()方法对列表中的值进行排序

Lists of number values or lists of strings can be sorted with the sort() method. For example, enter the following into the interactive shell:  
数值或字符串列表的值可以用sort()法进行排序。例如，输入以下内容到交互窗体：  
	>>> spam = [2, 5, 3.14, 1, -7]
	>>> spam.sort()
	>>> spam
	[-7, 1, 2, 3.14, 5]
	>>> spam = ['ants', 'cats', 'dogs', 'badgers', 'elephants']
	>>> spam.sort()
	>>> spam
	['ants', 'badgers', 'cats', 'dogs', 'elephants']
	
You can also pass True for the reverse keyword argument to have sort() sort the values in reverse order. Enter the following into the interactive shell:  
您也可以通过reverse=True的关键字参数对sort()方法以倒序进行排序。输入以下内容交互窗体:

	>>> spam.sort(reverse=True)
	>>> spam
	['elephants', 'dogs', 'cats', 'badgers', 'ants']
	
There are three things you should note about the sort() method. First, the sort() method sorts the list in place; don’t try to capture the return value by writing code like spam = spam.sort().   
在使用sort()方法的时候你应该留意三件事情。首先，sort（）方法排序是在本地操作;不要试图通过编写spam= spam.sort()代码来获取返回值。  
Second, you cannot sort lists that have both number values and string values in them, since Python doesn’t know how to compare these values. Type the following into the interactive shell and notice the TypeError error:  
其次，你无法排序有数值和字符串两种值的列表，因为Python不知道如何将这些值进行比较。键入以下内容到交互窗体，注意错误类型：  

	>>> spam = [1, 3, 2, 4, 'Alice', 'Bob']
	>>> spam.sort()
	Traceback (most recent call last):
	 File "<pyshell#70>", line 1, in <module>
	   spam.sort()
	TypeError: unorderable types: str() < int()
	
Third, sort() uses “ASCIIbetical order” rather than actual alphabetical order for sorting strings. This means uppercase letters come before lowercase letters. Therefore, the lowercase a is sorted so that it comes after the uppercase Z. For an example, enter the following into the interactive shell:  
第三,sort()方法采用“ASCIIbetical order”方式而不是字母实际顺序进行字符串排序.这就意味着大写字母肯定会排在小写字母之前.因此小写字母的a会排在大写字母Z后面.例如,输入以下内容到交互窗体:  
	>>> spam = ['Alice', 'ants', 'Bob', 'badgers', 'Carol', 'cats']
	>>> spam.sort()
	>>> spam
	['Alice', 'Bob', 'Carol', 'ants', 'badgers', 'cats']
	
If you need to sort the values in regular alphabetical order, pass str. lower for the key keyword argument in the sort() method call.  
如果您需要指定按字母顺序排列进行排序，可以通过关键字str.lower来调用sort（）方法。

	>>> spam = ['a', 'z', 'A', 'Z']
	>>> spam.sort(key=str.lower)
	>>> spam
	['a', 'A', 'z', 'Z']
	
这将导致函数sort()处理列表中的值时都当成小写,他们在列表中的实际大小写方式不会被改变.

###Example Program: Magic 8 Ball with a List
###范例程序：用列表方式实现 魔法8号球

Using lists, you can write a much more elegant version of the previous chapter’s Magic 8 Ball program. Instead of several lines of nearly identical elif statements, you can create a single list that the code works with. Open a new file editor window and enter the following code. Save it as magic8Ball2.py.  
使用列表，你可以为前一章的魔术8球写一个更优雅的版本.你可以创建一个列表完成这些代码功能,取代之前的几乎相同的多行elif语句.打开一个新的文件编辑器窗口，并输入以下代码。将其保存为magic8Ball2.py  

	import random

	messages = ['It is certain',
		'It is decidedly so',
		'Yes definitely',
		'Reply hazy try again',
		'Ask again later',
		'Concentrate and ask again',
		'My reply is no',
		'Outlook not so good',
		'Very doubtful']

	print(messages[random.randint(0, len(messages) - 1)])   
	
##EXCEPTIONS TO INDENTATION RULES IN PYTHON
##Python中的例外情况缩进规则

In most cases, the amount of indentation for a line of code tells Python what block it is in. There are some exceptions to this rule, however. For example, lists can actually span several lines in the source code file. The indentation of these lines do not matter; Python knows that until it sees the ending square bracket, the list is not finished. For example, you can have code that looks like this:  
在通常情况下Python的代码缩进告诉你这部分代码属于什么块.但是,也有一些例外情况.例如,列表实际上可以分布在源代码文件中的若干行。这些行的缩进并不重要,python知道只有看到结束的括号,列表才算结束.例如,你可以这样写代码:

	spam = ['apples',
		'oranges',
						 'bananas',
	'cats']
	print(spam)
	
Of course, practically speaking, most people use Python’s behavior to make their lists look pretty and readable, like the messages list in the Magic 8 Ball program.  
当然，实际大多数人使用Python的行为，会尽量使他们的列表看起来漂亮和更具有可读性，就像魔术8球程序中的消息列表。  
You can also split up a single instruction across multiple lines using the \ line continuation character at the end. Think of \ as saying, “This instruction continues on the next line.” The indentation on the line after a \ line continuation is not significant. For example, the following is valid Python code:  
你也可以在行末尾使用续行符 \ 将单行分割成多行.\符号好像在说“这个指令在下一行继续。”在\续行之后的行缩进没有意义.例如，以下是有效的Python代码：  

	print('Four score and seven ' + \
		  'years ago...')
		  
These tricks are useful when you want to rearrange long lines of Python code to be a bit more readable.  
当你想重新排列Python长代码,使其可读性更强这一点这些技巧是有用的。  
When you run this program, you’ll see that it works the same as the previous magic8Ball.py program.  
当你运行这个程序，你会看到它的工作原理同前面的magic8Ball.py程序。  
Notice the expression you use as the index into messages: random.randint(0, len(messages) - 1).This produces a random number to use for the index, regardless of the size of messages. That is, you’ll get a random number between 0 and the value of len(messages) - 1.The benefit of this approach is that you can easily add and remove strings to the messages list without changing other lines of code.If you later update your code, there will be fewer lines you have to change and fewer chances for you to introduce bugs.          
注意索引信息使用表达式：random.randint(0, len(messages) - 1)。这将产生一个随机数以用于索引，而不管消息的大小的。也就是说，你会得到0和(messages) - 1值之间的随机数。这种方法的好处是，你可以轻松地添加和删除字符串消息列表不改变代码的其他行。如果你更新代码是改变的行数越少,引入错误的机会也就越少。  
###List-like Types: Strings and Tuples
###其他类似于列表的数据类型:字符串和元组

Lists aren’t the only data types that represent ordered sequences of values. For example, strings and lists are actually similar, if you consider a string to be a “list” of single text characters. Many of the things you can do with lists can also be done with strings: indexing; slicing; and using them with for loops, with len(), and with the in and not in operators. To see this, enter the following into the interactive shell:  
列表并不是代表值为有序序列的唯一数据类型。例如,如果把字符串中每一个单一的文本字符当成一个元素,字符串和列表其实差不多.很多你可以用列表做的事情，也可以用字符串做：索引;切片;用len()与in,not in操作符来实现for循环。尝试这些请在交互式窗体输入以下内容:  

	>>> name = 'Zophie'
	>>> name[0]
	'Z'
	>>> name[-2]
	'i'
	>>> name[0:4]
	'Zoph'
	>>> 'Zo' in name
	True
	>>> 'z' in name
	False
	>>> 'p' not in name
	False
	>>> for i in name:
			print('* * * ' + i + ' * * *')

	* * * Z * * *
	* * * o * * *
	* * * p * * *
	* * * h * * *
	* * * i * * *
	* * * e * * *
	
##Mutable and Immutable Data Types
##可变和不可变的数据类型

But lists and strings are different in an important way. A list value is a mutable data type: It can have values added, removed, or changed. However, a string is immutable: It cannot be changed. Trying to reassign a single character in a string results in a TypeError error, as you can see by entering the following into the interactive shell:  
不过，列表和字符串有很大的不同。列表值是一个可变数据类型：它可以有值的添加，删除或更改。但是字符串数据类型是不能改变的.试图重新分配字符串中字的单字符将会产生数据类型错误，你可以通过输入以下到交互式窗体看到：  

	>>> name = 'Zophie a cat'
	>>> name[7] = 'the'
	Traceback (most recent call last):
	  File "<pyshell#50>", line 1, in <module>
		name[7] = 'the'
	TypeError: 'str' object does not support item assignment
 
 The proper way to “mutate” a string is to use slicing and concatenation to build a new string by copying from parts of the old string. Enter the following into the interactive shell:  
改变字符串正确的方法是用切片和联接方法从旧字符串的一部分复制建立一个新的字符串。输入以下内容交互的窗体：

	>>> name = 'Zophie a cat'
	>>> newName = name[0:7] + 'the' + name[8:12]
	>>> name
	'Zophie a cat'
	>>> newName
	'Zophie the cat'
	
We used [0:7] and [8:12] to refer to the characters that we don’t wish to replace. Notice that the original 'Zophie a cat' string is not modified because strings are immutable.  
我们使用[0：7]和[8:12]代表我们不希望替换的字符。请注意，“Zophie a cat'字符串原来的值并没有被修改，因为字符串是不可变的。  

Although a list value is mutable, the second line in the following code does not modify the list eggs:  
虽然列表值是可变的，但是下面的代码的第二行并没修改列表eggs：  

	>>> eggs = [1, 2, 3]
	>>> eggs = [4, 5, 6]
	>>> eggs
	[4, 5, 6]

The list value in eggs isn’t being changed here; rather, an entirely new and different list value ([4, 5, 6]) is overwriting the old list value ([1, 2, 3]). This is depicted in Figure 4-2.  
eggs列表值不被此修改;更确切地说，一个完全不同的新列表值（[4，5，6]）替代了旧列表值（[1，2，3]）。如图4-2所示。  

If you wanted to actually modify the original list in eggs to contain [4, 5, 6], you would have to do something like this:  
如果你想实际修改eggs的原始列表为[4，5，6，你必须这样做：

	>>> eggs = [1, 2, 3]
	>>> del eggs[2]
	>>> del eggs[1]
	>>> del eggs[0]
	>>> eggs.append(4)
	>>> eggs.append(5)
	>>> eggs.append(6)
	>>> eggs
	[4, 5, 6]

 [图4-2](https://automatetheboringstuff.com/images/000076.jpg)  
 
 In the first example, the list value that eggs ends up with is the same list value it started with. It’s just that this list has been changed, rather than overwritten. Figure 4-3 depicts the seven changes made by the first seven lines in the previous interactive shell example. 
在第一个例子中，该eggs列表值是它开始使用相同的列表的值。只是，这个列表已经改变，而不是覆盖.图4-3描绘了前一个交互窗体中七行代码的进行的七个变化.
[图4-3](https://automatetheboringstuff.com/images/000078.jpg)

Changing a value of a mutable data type (like what the del statement and append() method do in the previous example) changes the value in place, since the variable’s value is not replaced with a new list value.  
在原位置更改可变数据类型的值（像什么del语句和append（）方法），取决于变量的值是不是能够被一个新的列表值替换。  

Mutable versus immutable types may seem like a meaningless distinction, but Passing References will explain the different behavior when calling functions with mutable arguments versus immutable arguments. But first, let’s find out about the tuple data type, which is an immutable form of the list data type.  
可变与不变类型似乎是一个毫无意义的区别，但调用带有可变参数与不变参数的函数时，将发生不同的行为。首先，让我们了解了元组数据类型，它是列表数据类型的不可变的形式。  

##The Tuple Data Type
##元组数据类型

The tuple data type is almost identical to the list data type, except in two ways. First, tuples are typed with parentheses, ( and ), instead of square brackets, [ and ]. For example, enter the following into the interactive shell:  
元组数据类型和列表数据类型是几乎相同的，除了以下两点。首先，元组类型用小括号而不是方括号。例如，输入以下内容到交互窗体：

	>>> eggs = ('hello', 42, 0.5)
	>>> eggs[0]
	'hello'
	>>> eggs[1:3]
	(42, 0.5)
	>>> len(eggs)
	3
 
But the main way that tuples are different from lists is that tuples, like strings, are immutable. Tuples cannot have their values modified, appended, or removed. Enter the following into the interactive shell, and look at the TypeError error message:  
但是元组和列表有一个最大不同,元组像字符串是不可改变的.元组不能改变,追加和删除某个元素的值.在交互窗体输入以下代码,留意错误信息:

	>>> eggs = ('hello', 42, 0.5)
	>>> eggs[1] = 99
	Traceback (most recent call last):
	  File "<pyshell#5>", line 1, in <module>
		eggs[1] = 99
	TypeError: 'tuple' object does not support item assignment
	
If you have only one value in your tuple, you can indicate this by placing a trailing comma after the value inside the parentheses. Otherwise, Python will think you’ve just typed a value inside regular parentheses. The comma is what lets Python know this is a tuple value. (Unlike some other programming languages, in Python it’s fine to have a trailing comma after the last item in a list or tuple.) Enter the following type() function calls into the interactive shell to see the distinction:  

如果你在你的元组只有一个值，你可以在括号内的值之后结尾放置一个逗号，表明这是一个元组。否则，Python会认为你刚刚输入括号内的为定值。逗号让Python知道这是一个元组值。不同于其他编程语言,在列表或元组的最后一个项目之后有一个逗号是可以的.输入以下内容类型到交互窗体调用type()函数可以看到他们的区别：  

	>>> type(('hello',))
	<class 'tuple'>
	>>> type(('hello'))
	<class 'str'>
	
You can use tuples to convey to anyone reading your code that you don’t intend for that sequence of values to change. If you need an ordered sequence of values that never changes, use a tuple. A second benefit of using tuples instead of lists is that, because they are immutable and their contents don’t change, Python can implement some optimizations that make code using tuples slightly faster than code using lists.  
如果你不打算改变一序列的值您可以使用元组传达给任何阅读你代码的人。如果您需要有序序列值永远不会改变，请使用元组。使用元组而不是列表的第二个好处是，因为他们是不可改变的，它们的内容不会改变，Python可以实现一些优化，让使用元组的代码比列表更快。

##Converting Types with the list() and tuple() Functions
##使用list()和tuple()函数在列表和元组间转换

Just like how str(42) will return '42', the string representation of the integer 42, the functions list() and tuple() will return list and tuple versions of the values passed to them. Enter the following into the interactive shell, and notice that the return value is of a different data type than the value passed:  
就像str(42)可以返回42,字符串来自于整数42,函数list()和tuple()也能把对应的值传给列表或元组.输入以下内容到交互窗体，注意返回值是不同的数据类型:

	>>> tuple(['cat', 'dog', 5])
	('cat', 'dog', 5)
	>>> list(('cat', 'dog', 5))
	['cat', 'dog', 5]
	>>> list('hello')
	['h', 'e', 'l', 'l', 'o']
	
Converting a tuple to a list is handy if you need a mutable version of a tuple value.  
如果你需要一个元组的可变版本是用这个转化方法特别666.

###References引用

As you’ve seen, variables store strings and integer values. Enter the following into the interactive shell:  
正如你所看到的，变量存储字符串和整数值。输入以下内容到交互窗体：

	>>> spam = 42
	>>> cheese = spam
	>>> spam = 100
	>>> spam
	100
	>>> cheese
	42
	
You assign 42 to the spam variable, and then you copy the value in spam and assign it to the variable cheese. When you later change the value in spam to 100, this doesn’t affect the value in cheese. This is because spam and cheese are different variables that store different values.  
最先我们定义了变量spam并幅值为42,接着我们把spam的值复制并赋值给变量cheese.
接下来我们把spam的值修改为100,但这并不影响cheese的值. 这是因为spam和cheese是不同的变量存储了不同的值.  
But lists don’t work this way. When you assign a list to a variable, you are actually assigning a list reference to the variable. A reference is a value that points to some bit of data, and a list reference is a value that points to a list. Here is some code that will make this distinction easier to understand. Enter this into the interactive shell:  
但列表不以这种方式工作。当您赋值列表给一个变量，你实际上是分配列表引用给变量。引用是指向数据的一些比特的值，一个列表的引用是指向一个列表中的值。下面是一些使这种区别更容易理解代码。输入以下内容到交互窗体:

	>>> spam = [0, 1, 2, 3, 4, 5]
	>>> cheese = spam
	>>> cheese[1] = 'Hello!'
	>>> spam
	[0, 'Hello!', 2, 3, 4, 5]
	>>> cheese
	[0, 'Hello!', 2, 3, 4, 5]
	
This might look odd to you. The code changed only the cheese list, but it seems that both the cheese and spam lists have changed.  
这看起来可能会迷惑你。该代码只更改了cheese，但似乎无论是cheese还是spam列表都已经改变。  
When you create the list ➊, you assign a reference to it in the spam variable. But the next line ➋ copies only the list reference in spam to cheese, not the list value itself. This means the values stored in spam and cheese now both refer to the same list. There is only one underlying list because the list itself was never actually copied. So when you modify the first element of cheese ➌, you are modifying the same list that spam refers to.  
当你创建列表时,你定义了一个指向变量spam的引用,下一行仅仅是复制了spam的引用到cheese,并不是列表值本身.这就意味着存储在spam和cheese的值都指向了同一个列表.这里最底层仅有一个列表因为列表不能复制列表自己.所以当你改变cheese的元素时也改变了spam指向的同一个列表.  

Remember that variables are like boxes that contain values. The previous figures in this chapter show that lists in boxes aren’t exactly accurate because list variables don’t actually contain lists—they contain references to lists. (These references will have ID numbers that Python uses internally, but you can ignore them.) Using boxes as a metaphor for variables, Figure 4-4 shows what happens when a list is assigned to the spam variable.  
记住变量就像一个存储了值的盒子.在这一章前面指出列表在盒子中并不完全正确,因为列表变量实际上并不包含你列表,他们只是包含了列表的引用.这些引用会产生ID号在python内部使用.你可以忽略他们.使用盒作为变量的一个比喻，图4-4显示了一个列表被分配到spam变量会发生什么。  
[图4-4](https://automatetheboringstuff.com/images/000081.jpg)

Then, in Figure 4-5, the reference in spam is copied to cheese. Only a new reference was created and stored in cheese, not a new list. Note how both references refer to the same list.  
在图4-5，在spam中的引用复制到cheese。仅一个新的引用被创建并存储在cheese中，而不是一个新的列表。注意两个引用如何引用相同的列表。  
[图4-5](https://automatetheboringstuff.com/images/000082.jpg)

When you alter the list that cheese refers to, the list that spam refers to is also changed, because both cheese and spam refer to the same list. You can see this in Figure 4-6.  
当你改变cheese指向的列表，spam是指向的列表也被改变，因为这两个变量cheese和spam指相同列表。您可以在图4-6看到这一点。
[图4-6](https://automatetheboringstuff.com/images/000071.jpg)

Variables will contain references to list values rather than list values themselves. But for strings and integer values, variables simply contain the string or integer value. Python uses references whenever variables must store values of mutable data types, such as lists or dictionaries. For values of immutable data types such as strings, integers, or tuples, Python variables will store the value itself.  
变量包含引用列表值，而不是列表值本身。但是对于字符串和整数值，变量仅仅包含字符串或整数值。每当变量必须存储可变数据类型的值时，Python使用引用来存储可变数据类型的值,如列表或字典。对于字符串，整数或元组这样不可改变的数据类型的值，Python的变量将存储值本身。 

Although Python variables technically contain references to list or dictionary values, people often casually say that the variable contains the list or dictionary.  
虽然Python中的变量在技术上采用引用来存储列表或字典中的值，但人们常常说的变量包含列表或字典。  

##Passing References引用传递

References are particularly important for understanding how arguments get passed to functions. When a function is called, the values of the arguments are copied to the parameter variables. For lists (and dictionaries, which I’ll describe in the next chapter), this means a copy of the reference is used for the parameter. To see the consequences of this, open a new file editor window, enter the following code, and save it as passingReference.py:  
引用对理解参数是如何被传递给函数的尤为重要。当一个函数被调用，参数的值复制到参数变量。对于列表（字典，我将在下一章中描述）,这意味着引用的副本被用于参数。为了看到这样的意义，打开一个新的文件编辑器窗口，输入以下代码，并保存为passingReference.py：

	def eggs(someParameter):
		someParameter.append('Hello')

	spam = [1, 2, 3]
	eggs(spam)
	print(spam)

Notice that when eggs() is called, a return value is not used to assign a new value to spam. Instead, it modifies the list in place, directly. When run, this program produces the following output:  
注意当函数eggs()被调用时,返回值不是分配一个新的值给spam.相反,直接在原处修改了其值.当运行这个程序输出结果如下:

	[1, 2, 3, 'Hello']

Even though spam and someParameter contain separate references, they both refer to the same list. This is why the append('Hello') method call inside the function affects the list even after the function call has returned.  
尽管spam和someParameter包含单独的引用，但它们都指向相同的列表。这就是为什么append('Hello')方法在函数中调用返回会影响到列表中的值。  
Keep this behavior in mind: Forgetting that Python handles list and dictionary variables this way can lead to confusing bugs.  
在脑海中牢记这种行为记：忘记了Python处理列表和字典变量这种方式可能会导致奇怪的错误。  

##The copy Module’s copy() and deepcopy() Functions
##浅表复制和深度复制  

Although passing around references is often the handiest way to deal with lists and dictionaries, if the function modifies the list or dictionary that is passed, you may not want these changes in the original list or dictionary value. For this, Python provides a module named copy that provides both the copy() and deepcopy() functions. The first of these, copy.copy(), can be used to make a duplicate copy of a mutable value like a list or dictionary, not just a copy of a reference. Enter the following into the interactive shell:  
虽然引用传递往往是处理列表和字典最方便的方式，如果函数修改传递的列表或字典时,你不希望在原来的列表或字典值引起这些变化要怎么办。为此，Python提供了一个名为copy()的模块,同时提供浅表复制copy()和深度复制deepcopy()函数。首先,copy.copy（），可以用来制作一个可变值的列表或字典副本，而不仅仅是一个引用的副本。输入以下内容到交互窗体：

	>>> import copy
	>>> spam = ['A', 'B', 'C', 'D']
	>>> cheese = copy.copy(spam)
	>>> cheese[1] = 42
	>>> spam
	['A', 'B', 'C', 'D']
	>>> cheese
	['A', 42, 'C', 'D']

Now the spam and cheese variables refer to separate lists, which is why only the list in cheese is modified when you assign 42 at index 1. As you can see in Figure 4-7, the reference ID numbers are no longer the same for both variables because the variables refer to independent lists.    
现在，spam和cheese变量是单独的列表，这就是为什么当你对索引1分配值42时只有cheese列表被修改。正如你在图4-7中看到的，两个变量的引用ID号不再是相同的，因为变量是指独立的列表。  
[图 4-7](https://automatetheboringstuff.com/images/000084.jpg)
 
 If the list you need to copy contains lists, then use the copy.deepcopy() function instead of copy.copy(). The deepcopy() function will copy these inner lists as well.  
如果您需要复制的列表包含列表，请使用copy.deepcopy()函数，而不是copy.copy()。deepcopy()函数将复制这些内在的列表。  

##Summary总结

Lists are useful data types since they allow you to write code that works on a modifiable number of values in a single variable. Later in this book, you will see programs using lists to do things that would be difficult or impossible to do without them.   
列表是一种非常有用的数据类型,它可以让你的代码实现在一个单一变量中修改值的数量.在本书的后面你会看到一些使用列表的程序,如果不使用列表这些程序是非常困难甚至于是无法完成的. 

Lists are mutable, meaning that their contents can change. Tuples and strings, although list-like in some respects, are immutable and cannot be changed. A variable that contains a tuple or string value can be overwritten with a new tuple or string value, but this is not the same thing as modifying the existing value in place—like, say, the append() or remove() methods do on lists.  
列表是可变的，这意味着它们的内容可以改变。元组和字符串，虽然在某些方面与列表类似，但是他们是不可变的，并且不能被改变。包含元组或字符串值的变量可以用一个新的元组或字符串值覆盖，但这和使用append()或remove() 方法在原处修改列表的值是不一样的.  

Variables do not store list values directly; they store references to lists. This is an important distinction when copying variables or passing lists as arguments in function calls. Because the value that is being copied is the list reference, be aware that any changes you make to the list might impact another variable in your program. You can use copy() or deepcopy() if you want to make changes to a list in one variable without modifying the original list.  
变量不直接存储列表中的值;它们存储列表的引用.复制变量或传递列表作为函数调用的参数时这是非常重要的区别.因为复制的值是列表的引用，请注意，您对列表中的任何值的修改可能影响到程序中另一个变量.如果你仅想改变一个变量列表而不需要修改原来的列表可以使用copy()或deepcopy().

###Practice Questions 练习题


Q:1. What is []? 

Q:2. How would you assign the value 'hello' as the third value in a list stored in a variable named spam? (Assume spam contains [2, 4, 6, 8, 10].)
For the following three questions, let’s say spam contains the list ['a', 'b', 'c', 'd'].   

Q:3. What does spam[int(int('3' * 2) // 11)] evaluate to?  

Q:4. What does spam[-1] evaluate to?

Q:5. What does spam[:2] evaluate to?
For the following three questions, let’s say bacon contains the list [3.14, 'cat', 11, 'cat', True].

Q:6. What does bacon.index('cat') evaluate to?

Q:7. What does bacon.append(99) make the list value in bacon look like?

Q:8. What does bacon.remove('cat') make the list value in bacon look like?

Q:9. What are the operators for list concatenation and list replication?

Q:10. What is the difference between the append() and insert() list methods?

Q:11. What are two ways to remove values from a list?

Q:12. Name a few ways that list values are similar to string values.

Q:13. What is the difference between lists and tuples?

Q:14. How do you type the tuple value that has just the integer value 42 in it?

Q:15. How can you get the tuple form of a list value? How can you get the list form of a tuple value?

Q:16. Variables that “contain” list values don’t actually contain lists directly. What do they contain instead?

Q:17. What is the difference between copy.copy() and copy.deepcopy()?

##Practice Projects 练习项目

For practice, write programs to do the following tasks.  
练习,编写程序来执行以下任务。  

###Comma Code 逗号码

Say you have a list value like this: spam = ['apples', 'bananas', 'tofu', 'cats']  
假设你有一个这样的列表spam = ['apples', 'bananas', 'tofu', 'cats']   
 
Write a function that takes a list value as an argument and returns a string with all the items separated by a comma and a space, with and inserted before the last item. For example, passing the previous spam list to the function would return 'apples, bananas, tofu, and cats'. But your function should be able to work with any list value passed to it.   
编写一个函数，接受一个列表值作为参数并返回全部由逗号分隔的字符串并在最后
一个元素之前插入and.例如前面的列表spam会返回'apples, bananas, tofu, and cats'但是你的函数需要对任何列表都适用.  

###Character Picture Grid 字符图片

Say you have a list of lists where each value in the inner lists is a one-character string, like this:  
假设有一个列表，其内部有多个列表,每行都是一个由字符组成的列表，就像这样： 

	grid = [['.', '.', '.', '.', '.', '.'],
			['.', 'O', 'O', '.', '.', '.'],
			['O', 'O', 'O', 'O', '.', '.'],
			['O', 'O', 'O', 'O', 'O', '.'],
			['.', 'O', 'O', 'O', 'O', 'O'],
			['O', 'O', 'O', 'O', 'O', '.'],
			['O', 'O', 'O', 'O', '.', '.'],
			['.', 'O', 'O', '.', '.', '.'],
			['.', '.', '.', '.', '.', '.']]
			
You can think of grid[x][y] as being the character at the x- and y-coordinates of a “picture” drawn with text characters. The (0, 0) origin will be in the upper-left corner, the x-coordinates increase going right, and the y-coordinates increase going down.
Copy the previous grid value, and write code that uses it to print the image.  
你可以把这个想象成X和Y组成的坐标网格.利用x行和y列的字符来绘制图片.把左上角当成坐标原点(0,0),x坐标往右增长,y往下增长.复制网格的值,并写出代码打印出下面的图片.  

	..OO.OO..
	.OOOOOOO.
	.OOOOOOO.
	..OOOOO..
	...OOO...
	....O....
	
Hint: You will need to use a loop in a loop in order to print grid[0][0], then grid[1][0], then grid[2][0], and so on, up to grid[8][0]. This will finish the first row, so then print a newline. Then your program should print grid[0][1], then grid[1][1], then grid[2][1], and so on. The last thing your program will print is grid[8][5].    
小提示:你需要用循环内循环来实现打印如下值.grid[0][0],接着grid[1][0],接着grid[2][0]直到grid[8][0].这样可以完成第一行,接下来打印下一行.你的程序应该先打印grid[0][1],接着grid[1][1],接着grid[2][1],最后打印grid[8][5].

Also, remember to pass the end keyword argument to print() if you don’t want a newline printed automatically after each print() call.  
此外，如果你不希望每次打印后自动打印一个换行符请记住传递结束关键字参数给print()。

