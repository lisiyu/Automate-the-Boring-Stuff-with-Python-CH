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
|Augmented assignment statement|Equivalent assignment statement|
|spam += 1|spam = spam + 1|
|spam -= 1|spam = spam - 1|
|spam *= 1|spam = spam * 1|
|spam /= 1|spam = spam / 1|
|spam %= 1|spam = spam % 1|

The += operator can also do string and list concatenation, and the *= operator can do string and list replication. Enter the following into the interactive shell:  
+ =运算符也可以做字符串连接列表，而* =运算符可以做字符串和列表复制。输入以下内容交互的shell：

	>>> spam = 'Hello'
	>>> spam += ' world!'
	>>> spam
	'Hello world!'

	>>> bacon = ['Zophie']
	>>> bacon *= 3
	>>> bacon
	['Zophie', 'Zophie', 'Zophie']
	Methods  
	
##Methods 方法