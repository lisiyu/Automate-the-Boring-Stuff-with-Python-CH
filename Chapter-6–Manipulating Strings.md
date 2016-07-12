#Manipulating Strings 字符串操作
[视频教程](https://youtu.be/0gybjpkN-UY)

Text is one of the most common forms of data your programs will handle. You already know how to concatenate two string values together with the + operator, but you can do much more than that. You can extract partial strings from string values, add or remove spacing, convert letters to lowercase or uppercase, and check that strings are formatted correctly. You can even write Python code to access the clipboard for copying and pasting text.  
文字是程序将处理的最常见数据形式之一。你已经知道如何将两个字符串值用+操作联在一起，但你可以做的远不止于此。您可以从字符串中提取部分字符，添加或删除空格，转换字母大写或小写，或检查字符串格式是否正确。你也可以编写Python代码访问剪贴板复制和粘贴文本。  

In this chapter, you’ll learn all this and more. Then you’ll work through two different programming projects: a simple password manager and a program to automate the boring chore of formatting pieces of text.  
在本章中，你会通过两个不同的编程项目:一个简单的密码管理程序和自动格式化文本程序,来了解这一切。

##Working with Strings
##处理字符串

Let’s look at some of the ways Python lets you write, print, and access strings in your code.  
让我们来看看Python代码执行写入，打印和访问字符串的方法。  

###String Literals
###字符串表示

Typing string values in Python code is fairly straightforward: They begin and end with a single quote. But then how can you use a quote inside a string? Typing 'That is Alice's cat.' won’t work, because Python thinks the string ends after Alice, and the rest (s cat.') is invalid Python code. Fortunately, there are multiple ways to type strings.  
在python代码中表示字符串非常简单:在开头和结尾以单引号标识.但是如果字符串中有单引号需要怎么表示? 'That is Alice's cat.'是无法工作的.Python编译器会认为Alice后面的单引号就表示字符串结束了.后面的 (s cat.')是无效代码.好在这里有多种方式来表示字符串.

###Double Quotes
###双引号

Strings can begin and end with double quotes, just as they do with single quotes. One benefit of using double quotes is that the string can have a single quote character in it. Enter the following into the interactive shell:  
字符串可以以双引号开头和结尾来表示,就像用单引号括起来一样.这样字符串中间的单引号就可以正确的被识别为单引号了.在交互窗体输入以下内容:

	spam = "That is Alice's cat."

Since the string begins with a double quote, Python knows that the single quote is part of the string and not marking the end of the string. However, if you need to use both single quotes and double quotes in the string, you’ll need to use escape characters.  
因为开始是双引号,所有Python知道中间的单引号食欲字符串的一部分,双引号才是结尾.如果你需要在一个字符串中同时使用单引号和双引号就需要使用转义字符了.  

###Escape Characters
###转义字符

An escape character lets you use characters that are otherwise impossible to put into a string. An escape character consists of a backslash (\) followed by the character you want to add to the string. (Despite consisting of two characters, it is commonly referred to as a singular escape character.) For example, the escape character for a single quote is \'. You can use this inside a string that begins and ends with single quotes. To see how escape characters work, enter the following into the interactive shell:  
转义字符可以帮助你输入一些不可能输入到一个字符串中的字符.转义字符是在反斜杠(\)后面紧跟你想输入的字符.(尽管包含两个字符,他们通常被称为单转义字符).例如,单引号的转义字符是 \'. 你可以在字符串中使用这个转义字符,字符串开头和结尾使用单引号.想了解转义字符怎么工作,在交互窗体输入以下内容:

	spam = 'Say hi to Bob\'s mother.'
	
Python knows that since the single quote in Bob\'s has a backslash, it is not a single quote meant to end the string value. The escape characters \' and \" let you put single quotes and double quotes inside your strings, respectively.  
Python知道以在Bob\'s 有一个反斜杠表示这个单引号不是字符串结束的意思.转义字符\'和\"让你可以在字符串中输入单引号或双引号.
Table 6-1 lists the escape characters you can use.  
表6-1列出可以使用的转义字符。

|Escape character |Prints as   |
|-----------------|------------|
|\'               |Single quote|
|\"               |Double quote|
|\t               |Tab         |
|\n               |Newline (line break)|
|\\               |Backslash   |

Enter the following into the interactive shell:  
输入以下内容到交互shell：

	print("Hello there!\nHow are you?\nI\'m doing fine.")
	Hello there!
	How are you?
	I'm doing fine.
	
###Raw Strings
###原始字符串

You can place an r before the beginning quotation mark of a string to make it a raw string. A raw string completely ignores all escape characters and prints any backslash that appears in the string. For example, type the following into the interactive shell:   
你可以把一个字母r放在字符串的开头引号之前，使之成为原始字符串。原始字符串完全忽略所有的转义字符并打印在字符串中的任何反斜线。例如，键入以下内容到交互窗体：  

	>>> print(r'That is Carol\'s cat.')
	That is Carol\'s cat.

Because this is a raw string, Python considers the backslash as part of the string and not as the start of an escape character. Raw strings are helpful if you are typing string values that contain many backslashes, such as the strings used for regular expressions described in the next chapter.  
因为这是一个原始字符串，Python认定反斜线作为字符串的一部分，而不是作为一个转义字符的开始。原始字符串是有用的，如果您键入包含许多反斜杠的字符，比如在下一章中将学习的正则表达式字符串就有很多反斜杠。  

###Multiline Strings with Triple Quotes
###用三重引号表示多行字符串

While you can use the \n escape character to put a newline into a string, it is often easier to use multiline strings. A multiline string in Python begins and ends with either three single quotes or three double quotes. Any quotes, tabs, or newlines in between the “triple quotes” are considered part of the string. Python’s indentation rules for blocks do not apply to lines inside a multiline string.  
虽然你可以在字符串中使用\n转义字符来实现换行,但是使用多行字符串往往 更容易.Python中的多行字符串以三个单引号或三个双引号标识开头和结束。任何在“三重引号”之间的引号，缩进，或者换行被认为是多行字符串的一部分。在多行字符串中Python不会对块缩进规则进行检测。  

Open the file editor and write the following:  
打开文件编辑器，编写如下代码：

	print('''Dear Alice,

	Eve's cat has been arrested for catnapping, cat burglary, and extortion.

	Sincerely,
	Bob''')
	
	
Save this program as catnapping.py and run it. The output will look like this:  
保存程序为catnapping.py并运行.输出结果如下:

	Dear Alice,

	Eve's cat has been arrested for catnapping, cat burglary, and extortion.

	Sincerely,
	Bob
	
Notice that the single quote character in Eve's does not need to be escaped. Escaping single and double quotes is optional in raw strings. The following print() call would print identical text but doesn’t use a multiline string:  
请注意，在Eve's中的单引号字符不需要进行转义。在原始字符串中单引号和双引号都是可以的.下面的print()函数将打印相同的文本，但不使用多行字符串：  

	print('Dear Alice,\n\nEve\'s cat has been arrested for catnapping, catburglary, and extortion.\n\nSincerely,\nBob')
	
###Multiline Comments
###多行注释

While the hash character (#) marks the beginning of a comment for the rest of the line, a multiline string is often used for comments that span multiple lines. The following is perfectly valid Python code:  
用符号#可以表示从这个符号开始这行后面的部分都是代码注释.而多行字符串也常常被用作多行注释.下面是完全有效的Python代码:

	"""This is a test Python program.
	Written by Al Sweigart al@inventwithpython.com

	This program was designed for Python 3, not Python 2.
	"""

	def spam():
		"""This is a multiline comment to help
		explain what the spam() function does."""
		print('Hello!')

###Indexing and Slicing Strings
###字符串切片和索引

Strings use indexes and slices the same way lists do. You can think of the string 'Hello world!' as a list and each character in the string as an item with a corresponding index.  
字符串可以和列表类似使用索引和切片功能.你可以把字符串'Hello world!'想象成一个列表.在字符串中每个字符都有对应的索引项.  

	'   H   e   l   l   o       w   o   r   l   d    !   '
		0   1   2   3   4   5   6   7   8   9   10   11

The space and exclamation point are included in the character count, so 'Hello world!' is 12 characters long, from H at index 0 to ! at index 11.
Enter the following into the interactive shell:  
空格和感叹号也包括在字符计数中,因此'Hello world'包含12个字符长度,从索引0的H到索引11的!  在交互窗体输入以下内容:

	>>> spam = 'Hello world!'
	>>> spam[0]
	'H'
	>>> spam[4]
	'o'
	>>> spam[-1]
	'!'
	>>> spam[0:5]
	'Hello'
	>>> spam[:5]
	'Hello'
	>>> spam[6:]
	'world!'

If you specify an index, you’ll get the character at that position in the string. If you specify a range from one index to another, the starting index is included and the ending index is not. That’s why, if spam is 'Hello world!', spam[0:5] is 'Hello'. The substring you get from spam[0:5] will include everything from spam[0] to spam[4], leaving out the space at index 5.  
如果你指定一个索引就能获得这个索引对应的字符.如果你指定一个索引到另一个索引的范围,包含索引开始不含索引结束值的字符就能被提取出来.如果spam是'Hello world!',spam[0:5]就是'Hello'.你从spam[0:5]获得的字符包含spam[0]到spam[4]不包含索引5的值.  

Note that slicing a string does not modify the original string. You can capture a slice from one variable in a separate variable. Try typing the following into the interactive shell:  
需要注意的是切片字符串不会修改原始字符串。可以另外指定一个单独的变量存储切片出来的数据。尝试输入以下内容到交互shell：  

	>>> spam = 'Hello world!'
	>>> fizz = spam[0:5]
	>>> fizz
	'Hello'

By slicing and storing the resulting substring in another variable, you can have both the whole string and the substring handy for quick, easy access.  
通过把切片数据存储在另一个子变量中，你可以同时拥有整个字符串和子变量.方便快速地访问。

###The in and not in Operators with Strings
###字符串in和not in运算符

The in and not in operators can be used with strings just like with list values. An expression with two strings joined using in or not in will evaluate to a Boolean True or False. Enter the following into the interactive shell:  
字符串可以和列表一样使用in和not in 运算符.两个字符串在运算符两端组成表达式,表达式的值为True或False的布尔值.在交互窗体输入以下内容:

	>>> 'Hello' in 'Hello World'
	True
	>>> 'Hello' in 'Hello'
	True
	>>> 'HELLO' in 'Hello World'
	False
	>>> '' in 'spam'
	True
	>>> 'cats' not in 'cats and dogs'
	False
	
These expressions test whether the first string (the exact string, case sensitive) can be found within the second string.  
这些表达式测试第一个字符串（字符串区分大小写）是否可在第二个字符串中找到。

##Useful String Methods
##有用的字符串方法
[视频教程](https://youtu.be/rODBsj5DfQ0)

Several string methods analyze strings or create transformed string values. This section describes the methods you’ll be using most often.  
有许多字符串方法可以分析字符串或创造转化字符串的值。本节将介绍最常用的方法。  

###The upper(), lower(), isupper(), and islower() String Methods 
The upper() and lower() string methods return a new string where all the letters in the original string have been converted to uppercase or lower-case, respectively. Nonletter characters in the string remain unchanged. Enter the following into the interactive shell:  
upper() 和lower()字符串方法返回一个新的字符串，其中原字符串中的所有字母都被转换为大写或小写.字符串中非字母字符保持不变.输入以下内容到交互窗体:

	>>> spam = 'Hello world!'
	>>> spam = spam.upper()
	>>> spam
	'HELLO WORLD!'
	>>> spam = spam.lower()
	>>> spam
	'hello world!'

Note that these methods do not change the string itself but return new string values. If you want to change the original string, you have to call upper() or lower() on the string and then assign the new string to the variable where the original was stored. This is why you must use spam = spam.upper() to change the string in spam instead of simply spam.upper(). (This is just like if a variable eggs contains the value 10. Writing eggs + 3 does not change the value of eggs, but eggs = eggs + 3 does.)  
注意这些方法并不会改变字符串本身,但是会返回一个新的字符串值.如果你想改变原有的字符串，你必须在字符串上调用upper()或 lower()，然后将新的字符串存储原始变量位置。这就是为什么你必须使用垃圾spam=spam.upper（）来更改在spam中字符串，而不是简单地spam.upper（）.这也像变量eggs值为10,eggs+3并不会改变eggs的值但是eggs = eggs + 3会改变.  

The upper() and lower() methods are helpful if you need to make a case-insensitive comparison. The strings 'great' and 'GREat' are not equal to each other. But in the following small program, it does not matter whether the user types Great, GREAT, or grEAT, because the string is first converted to lowercase.  
如果你需要做一个区分大小写的字符串比较upper()和lower()方法很有用.字符串great和GREat是不一样的.但是下面的小程序不关心字符串是Great, GREAT或grEAT.因为他在比较之前全部转换成小写字母.
 
	print('How are you?')
	feeling = input()
	if feeling.lower() == 'great':
		print('I feel great too.')
	else:
		print('I hope the rest of your day is good.')
		
When you run this program, the question is displayed, and entering a variation on great, such as GREat, will still give the output I feel great too. Adding code to your program to handle variations or mistakes in user input, such as inconsistent capitalization, will make your programs easier to use and less likely to fail.    
当你运行该程序，显示问题，无论你输入great还是GREat，都会输出:I feel great too.把这段代码添加到程序中在处理用户输入异常,比如误按大写键,会让你的程序运行起来更加容易和顺畅.

	How are you?
	GREat
	I feel great too.
	
The isupper() and islower() methods will return a Boolean True value if the string has at least one letter and all the letters are uppercase or lowercase, respectively. Otherwise, the method returns False. Enter the following into the interactive shell, and notice what each method call returns:  
如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False，在交互窗体输入以下内容:

	>>> 'Hello'.upper()
	'HELLO'
	>>> 'Hello'.upper().lower()
	'hello'
	>>> 'Hello'.upper().lower().upper()
	'HELLO'
	>>> 'HELLO'.lower()
	'hello'
	>>> 'HELLO'.lower().islower()
	True 
	
###The isX String Methods

Along with islower() and isupper(), there are several string methods that have names beginning with the word is. These methods return a Boolean value that describes the nature of the string. Here are some common isX string methods:
isalpha() returns True if the string consists only of letters and is not blank.
isalnum() returns True if the string consists only of letters and numbers and is not blank.
isdecimal() returns True if the string consists only of numeric characters and is not blank.
isspace() returns True if the string consists only of spaces, tabs, and new-lines and is not blank.
istitle() returns True if the string consists only of words that begin with an uppercase letter followed by only lowercase letters.
Enter the following into the interactive shell:   
与islower()和isupper()类似,这里还有几个以is开头的字符串方法.这些方法的返回值是描述字符串属性的布尔值.以下是一些常见的字符串isX方法:
isalpha()如果字符串至少有一个字符并且所有字符都是字母则返回 True,否则返回 False.    
isalnum()如果字符串至少有一个字符并且所有字符都是字母或数字则返回 True,否则返回 False.   
isdecimal()如果字符串至少有一个字符并且所有字符都是数字则返回 True  
isspace()如果字符串至少有一个字符并且所有字符都是空格，制表符或换行则返回 True,否则返回 False.     
istitle()如果字符串中所有的单词首字母为大写，且其他字母为小写则返回 True，否则返回 False.  

Enter the following into the interactive shell:  
输入以下内容到交互shell：

	>>> 'hello'.isalpha()
	True
	>>> 'hello123'.isalpha()
	False
	>>> 'hello123'.isalnum()
	True
	>>> 'hello'.isalnum()
	True
	>>> '123'.isdecimal()
	True
	>>> '    '.isspace()
	True
	>>> 'This Is Title Case'.istitle()
	True
	>>> 'This Is Title Case 123'.istitle()
	True
	>>> 'This Is not Title Case'.istitle()
	False
	>>> 'This Is NOT Title Case Either'.istitle()
	False
	
The isX string methods are helpful when you need to validate user input. For example, the following program repeatedly asks users for their age and a password until they provide valid input. Open a new file editor window and enter this program, saving it as validateInput.py:    
当你需要验证用户输入信息时isX字符串方法是非常有用的.例如,下面的程序会反复询问用户的年龄和密码，直到他们提供有效的投入。打开新的编辑器输入以下代码并保存为validateInput.py:

	while True:
		print('Enter your age:')
		age = input()
		if age.isdecimal():
			break
		print('Please enter a number for your age.')

	while True:
		print('Select a new password (letters and numbers only):')
		password = input()
		if password.isalnum():
			break
		print('Passwords can only have letters and numbers.')
		
In the first while loop, we ask the user for their age and store their input in age. If age is a valid (decimal) value, we break out of this first while loop and move on to the second, which asks for a password. Otherwise, we inform the user that they need to enter a number and again ask them to enter their age. In the second while loop, we ask for a password, store the user’s input in password, and break out of the loop if the input was alphanumeric. If it wasn’t, we’re not satisfied so we tell the user the password needs to be alphanumeric and again ask them to enter a password.
When run, the program’s output looks like this:  
在第一个循环中我们询问用户的年龄并将他们的输入存储在变量age中.如果age的值是10进制数,则跳出第一个循环并进入第二个循环询问用户的密码.反之则告诉用户年龄需要输入一个数字并重新要求输入.在第二个循环中我们要求用户输入密码并存在变量password中,如果用户输入是数字加字符则跳出循环.如果用户输入不满足条件我们就告诉他需要输入字母加数字类型的密码并要求重新输入.程序运行起来输出如下所示:

	Enter your age:
	forty two
	Please enter a number for your age.
	Enter your age:
	42
	Select a new password (letters and numbers only):
	secr3t!
	Passwords can only have letters and numbers.
	Select a new password (letters and numbers only):
	secr3t

Calling isdecimal() and isalnum() on variables, we’re able to test whether the values stored in those variables are decimal or not, alphanumeric or not. Here, these tests help us reject the input forty two and accept 42, and reject secr3t! and accept secr3t.  
调用isdecimal（）和isalnum（），我们能够测试存储在这些变量的值是否为十进制,是否为字母和数字.在这里帮助于我们拒绝输入forty two，接受42，拒绝sec??r3t！并接受secr3t

###The startswith() and endswith() String Methods

The startswith() and endswith() methods return True if the string value they are called on begins or ends (respectively) with the string passed to the method; otherwise, they return False. Enter the following into the interactive shell:  
startswith（）和的endsWith（）方法返回True如果调用他们的字符串值开头或结束（分别）是这个值;否则，返回False。输入以下内容到交互窗体：  

	>>> 'Hello world!'.startswith('Hello')
	True
	>>> 'Hello world!'.endswith('world!')
	True
	>>> 'abc123'.startswith('abcdef')
	False
	>>> 'abc123'.endswith('12')
	False
	>>> 'Hello world!'.startswith('Hello world!')
	True
	>>> 'Hello world!'.endswith('Hello world!')
	True
	
These methods are useful alternatives to the == equals operator if you need to check only whether the first or last part of the string, rather than the whole thing, is equal to another string.  
如果你需要检查字符串的开头或结尾部分是不是等于另一个字符串,这是比==操作符更方便的方法.  

###The join() and split() String Methods

The join() method is useful when you have a list of strings that need to be joined together into a single string value. The join() method is called on a string, gets passed a list of strings, and returns a string. The returned string is the concatenation of each string in the passed-in list. For example, enter the following into the interactive shell:  
当你需要把一个元素全是字符串的列表连接成一个字符串,join（）方法是非常有用的。join()方法调用一个字符串,把列表中的字符串当参数传入,然后返回一个新的字符串.返回的字符串把列表中的字符串全部通过调用的字符串串联起来.例如,输入以下内容到交互窗体:

	>>> ', '.join(['cats', 'rats', 'bats'])
	'cats, rats, bats'
	>>> ' '.join(['My', 'name', 'is', 'Simon'])
	'My name is Simon'
	>>> 'ABC'.join(['My', 'name', 'is', 'Simon'])
	'MyABCnameABCisABCSimon'
	
Notice that the string join() calls on is inserted between each string of the list argument. For example, when join(['cats', 'rats', 'bats']) is called on the ', ' string, the returned string is ‘cats, rats, bats’.  
注意join()调用的参数会插入列表中每个字符串之间.如刚才的例子.join(['cats', 'rats', 'bats'])调用了字符','返回的字符串为‘cats, rats, bats’.   

Remember that join() is called on a string value and is passed a list value. (It’s easy to accidentally call it the other way around.) The split() method does the opposite: It’s called on a string value and returns a list of strings. Enter the following into the interactive shell:  
记住join()调用的是字符串值,传递的是列表值.这个很容易和其他方法搞混.split()方法则正好相反：调用字符串值，并返回一个字符串列表。输入以下内容到交互窗体:  

	>>> 'My name is Simon'.split()
	['My', 'name', 'is', 'Simon']
	
By default, the string 'My name is Simon' is split wherever whitespace characters such as the space, tab, or newline characters are found. These whitespace characters are not included in the strings in the returned list. You can pass a delimiter string to the split() method to specify a different string to split upon. For example, enter the following into the interactive shell:    
默认情况下， 'My name is Simon'按照空白字符进行分割，如空格，制表符，或换行字符.这些空白字符未包含在返回的列表中。你可以传递一个分隔符字符串给split（）方法来分割.例如,在交互窗体输入以下内容:

	>>> 'MyABCnameABCisABCSimon'.split('ABC')
	['My', 'name', 'is', 'Simon']
	>>> 'My name is Simon'.split('m')
	['My na', 'e is Si', 'on']
	
A common use of split() is to split a multiline string along the newline characters. Enter the following into the interactive shell:    split()的一个常见的??用途是用换行符把多行字符串变成一个列表。输入以下内容到交互窗体:

	>>> spam = '''Dear Alice,
	How have you been? I am fine.
	There is a container in the fridge
	that is labeled "Milk Experiment".

	Please do not drink it.
	Sincerely,
	Bob'''
	>>> spam.split('\n')
	['Dear Alice,', 'How have you been? I am fine.', 'There is a container in the
	fridge', 'that is labeled "Milk Experiment".', '', 'Please do not drink it.',
	'Sincerely,', 'Bob']
	
Passing split() the argument '\n' lets us split the multiline string stored in spam along the newlines and return a list in which each item corresponds to one line of the string.  通过给split()传递参数'\n'我们沿换行符把spam的多行字符串进行分割，返回其中每行对应的字符串的行的列表。

###Justifying Text with rjust(), ljust(), and center()

The rjust() and ljust() string methods return a padded version of the string they are called on, with spaces inserted to justify the text. The first argument to both methods is an integer length for the justified string. Enter the following into the interactive shell:   
rjust() and ljust()方法会返回一个用空格填充方式进行对齐的字符串.他们包含一个整形参数来定义返回字符串的总长度.在交互窗体输入以下内容:

	>>> 'Hello'.rjust(10)
	'     Hello'
	>>> 'Hello'.rjust(20)
	'               Hello'
	>>> 'Hello World'.rjust(20)
	'         Hello World'
	>>> 'Hello'.ljust(10)
	'Hello     '
	
'Hello'.rjust(10) says that we want to right-justify 'Hello' in a string of total length 10. 'Hello' is five characters, so five spaces will be added to its left, giving us a string of 10 characters with 'Hello' justified right.  
“Hello'.rjust（10）意思是，我们要右对齐”Hello“字符串总长度为10'Hello'是五个字符，所以五个空格将被添加到其左侧.  

An optional second argument to rjust() and ljust() will specify a fill character other than a space character. Enter the following into the interactive shell:  
增加第二个参数到rjust()和ljust()方法可以用其他字符来代替空格对原字符进行填充对齐.输入以下内容到交互窗体:

	>>> 'Hello'.rjust(20, '*')
	'***************Hello'
	>>> 'Hello'.ljust(20, '-')
	'Hello---------------'
	
The center() string method works like ljust() and rjust() but centers the text rather than justifying it to the left or right. Enter the following into the interactive shell:  
center()方法的原理和ljust()和rjust()类似.只不过他是把字符填充到原字符的左右两端来实现文字居中.在交互窗体输入以下内容:

	>>> 'Hello'.center(20)
	'       Hello       '
	>>> 'Hello'.center(20, '=')
	'=======Hello========'
	
These methods are especially useful when you need to print tabular data that has the correct spacing. Open a new file editor window and enter the following code, saving it as picnicTable.py:  
当你需要打印具有正确的间距表格数据，这些方法是非常有用的。打开一个新的文件编辑器窗口，然后输入以下代码，将其保存为picnicTable.py：  

	def printPicnic(itemsDict, leftWidth, rightWidth):
		print('PICNIC ITEMS'.center(leftWidth + rightWidth, '-'))
		for k, v in itemsDict.items():
			print(k.ljust(leftWidth, '.') + str(v).rjust(rightWidth))
	picnicItems = {'sandwiches': 4, 'apples': 12, 'cups': 4, 'cookies': 8000}
	printPicnic(picnicItems, 12, 5)
	printPicnic(picnicItems, 20, 6) 
	
In this program, we define a printPicnic() method that will take in a dictionary of information and use center(), ljust(), and rjust() to display that information in a neatly aligned table-like format.  
在这个程序中我们首先定义了一个printPicnic()方法从字典中获取信息并用center(), ljust(),和rjust()方法来对显示内容进行格式话让打印结果看起来像表格.

The dictionary that we’ll pass to printPicnic() is picnicItems. In picnicItems, we have 4 sandwiches, 12 apples, 4 cups, and 8000 cookies. We want to organize this information into two columns, with the name of the item on the left and the quantity on the right.    
字典内容传递给picnicItems.在picnicItems我们有如下内容,4 sandwiches, 12 apples, 4 cups, and 8000 cookies.我们想让里面的内容变成两列,名字在左边,数量靠右边.

To do this, we decide how wide we want the left and right columns to be. Along with our dictionary, we’ll pass these values to printPicnic().   
为了实现这个,我们还需要确定左边和右边的列宽度为多少.我们把宽度信息和字典一起传给函数printPicnic()

printPicnic() takes in a dictionary, a leftWidth for the left column of a table, and a rightWidth for the right column. It prints a title, PICNIC ITEMS, centered above the table. Then, it loops through the dictionary, printing each key-value pair on a line with the key justified left and padded by periods, and the value justified right and padded by spaces.  
printPicnic()获得字典内容,左边列的宽度,右边列的宽度.他先居中打印标题PICNIC ITEMS,在整个表格的最上方.接着通过循环遍历字典中的键值对,并按照格式添加空格或句号并且打印出来.  

After defining printPicnic(), we define the dictionary picnicItems and call printPicnic() twice, passing it different widths for the left and right table columns.  
在定义完函数printPicnic()之后我们在定义一个字典.用不同的参数调用printPicnic()两次,看看不同的宽度下打印出来的效果.

When you run this program, the picnic items are displayed twice. The first time the left column is 12 characters wide, and the right column is 5 characters wide. The second time they are 20 and 6 characters wide, respectively.  
当你运行这个程序，打印了两次picnic。第一次最左列宽度是12个字符，而右列宽度是5个字符。第二次分别是宽20和6，运行结果如下:

	---PICNIC ITEMS--
	sandwiches..    4
	apples......   12
	cups........    4
	cookies..... 8000
	-------PICNIC ITEMS-------
	sandwiches..........     4
	apples..............    12
	cups................     4
	cookies.............  8000
	
Using rjust(), ljust(), and center() lets you ensure that strings are neatly aligned, even if you aren’t sure how many characters long your strings are.  
使用rjust（），ljust（）和center（），即使你不知道字符串有多少个字符也能确保字符串被整齐地排列.

###Removing Whitespace with strip(), rstrip(), and lstrip()	

Sometimes you may want to strip off whitespace characters (space, tab, and newline) from the left side, right side, or both sides of a string. The strip() string method will return a new string without any whitespace characters at the beginning or end. The lstrip() and rstrip() methods will remove whitespace characters from the left and right ends, respectively. Enter the following into the interactive shell:  
有时候我们需要从字符串中剔除空白字符（空格，制表符和换行符）.这些空白字符可能在左侧,右侧或两边.strip()方法将去掉原字符串开始或结束位置的任何空格字符并返回一个新的字符串.lstrip（）和rstrip（）可以方法将从左或右端分别除去空白字符。在交互窗体输入以下内容:

	>>> spam = '    Hello World     '
	>>> spam.strip()
	'Hello World'
	>>> spam.lstrip()
	'Hello World '
	>>> spam.rstrip()
	'    Hello World'
	
Optionally, a string argument will specify which characters on the ends should be stripped. Enter the following into the interactive shell:  
指定字符串参数可以实现从原字符串中剔除一些指定字符.输入以下内容到交互窗体:

	>>> spam = 'SpamSpamBaconSpamEggsSpamSpam'
	>>> spam.strip('ampS')
	'BaconSpamEggs'
	
Passing strip() the argument 'ampS' will tell it to strip occurences of a, m, p, and capital S from the ends of the string stored in spam. The order of the characters in the string passed to strip() does not matter: strip('ampS') will do the same thing as strip('mapS') or strip('Spam').   
'ampS'四个字符作为参数传递个strip()意味着执行时会在原字符串两端剔除和a,m,p,S这是个字符相同的字符.剔除字符与参数中四个字符的顺序无关.strip('ampS')和strip('mapS')及strip('Spam')都实现了相同的功能.  

###Copying and Pasting Strings with the pyperclip Module 

The pyperclip module has copy() and paste() functions that can send text to and receive text from your computer’s clipboard. Sending the output of your program to the clipboard will make it easy to paste it to an email, word processor, or some other software.
Pyperclip does not come with Python. To install it, follow the directions for installing third-party modules in Appendix A. After installing the pyperclip module, enter the following into the interactive shell:  
pyperclip模块有copy()和paste()两个方法可以发送文本到电脑剪贴板或者从剪贴板接收文本.把程序的输出发送到剪贴板可以很容易将其粘贴到电子邮件，文字处理或其他一些软件。pyperclip不是python自带模块.需要额外安装.按照附录A提供的方法可以按照安装第三方模块.安装完成之后在交互窗体输入以下内容:

	>>> import pyperclip
	>>> pyperclip.copy('Hello world!')
	>>> pyperclip.paste()
	'Hello world!'
	
Of course, if something outside of your program changes the clipboard contents, the paste() function will return it. For example, if I copied this sentence to the clipboard and then called paste(), it would look like this:  
当然,如果你电脑上其他程序改变了剪贴板内容paste()函数也会返回他.例如,如果我们复制了下面这段内容然后调用paste(),程序输出是这样的.

	>>> pyperclip.paste()
	'For example, if I copied this sentence to the clipboard and then called
	paste(), it would look like this:'
	
####RUNNING PYTHON SCRIPTS OUTSIDE OF IDLE 

So far, you’ve been running your Python scripts using the interactive shell and file editor in IDLE. However, you won’t want to go through the inconvenience of opening IDLE and the Python script each time you want to run a script. Fortunately, there are shortcuts you can set up to make running Python scripts easier. The steps are slightly different for Windows, OS X, and Linux, but each is described in Appendix B. Turn to Appendix B to learn how to run your Python scripts conveniently and be able to pass command line arguments to them. (You will not be able to pass command line arguments to your programs using IDLE.)  
到目前为止，您已经学会使用交互shell和文件编辑器已运行自己编写的Python脚本。但是每次运行之前都要先打开IDLE还是有些不方便.幸运的是，你可以设置运行Python脚本更容易快捷方式。这些步骤是针对Windows，Mac OS X和Linux略有不同，在附录B中有详细描述.转到附录B以了解如何方便地运行Python脚本，并学习通过命令行参数传递给他们。(无法通过命令行传递参数给使用IDLE的程序)  

###Project: Password Locker

