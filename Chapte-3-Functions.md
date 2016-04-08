# Functions
## [相关视频教程](https://youtu.be/WB4hJJkfhLU)

 You’re already familiar with the print(), input(), and len() functions from the previous chapters. 
 Python provides several builtin functions like these, but you can also write your own functions. 
 A function is like a mini-program within a program.  
 在前面的章节你已经熟悉的print()，input()和len()函数。  
 Python提供了一些这样的内建函数，你也可以编写自己的函数。  
 函数就像一个程序中的一个小程序。  

 To better understand how functions work, let’s create one. Type this program into the file editor and save it as helloFunc.py:
 理解函数的工作原理的最好方法是我们创建一个试试。在文件编辑器里面输入这段代码到并保存为helloFunc.py：  
 
	def hello():  
		print('Howdy!')  
		print('Howdy!!!')  
		print('Hello there.')  
	hello()  
	hello()  
	hello()

 The first line is a def statement [1], which defines a function named hello().  
 The code in the block that follows the def statement[2]， is the body of the function.   
 This code is executed when the function is called, not when the function is first defined.  
 第一行的def我们成为函数声明语句。def为函数声明关键词。我们将这个函数名称定义为hello.  
 紧跟着函数声明语句的代码块我们成为函数体。  
 当函数被调用的时候函数的代码才会执行，而不是在首次定义函数的时候执行该代码。  
 
 The hello() lines after the function are function calls. In code,  a function call is  just the  function’s name 
 followed by  parentheses, possibly with some number of arguments in between the parentheses.  When the  program execution
 reaches these  calls, it  will jump  to the  top line  in the function and begin executing the code there. When it reaches the end 
 of the function, the execution eturns to the line  that called the function  and continues moving through  the code as before. 
 Since  this program calls hello()  three times, the code  in the hello() function is executed three times. When you run this program,
 the  output looks like this:  
	Howdy!  
	Howdy!!!  
	Hello there.  
	Howdy!  
	Howdy!!!  
	Hello there.  
	Howdy!  
	Howdy!!!  
	Hello there.  
 最后三行的hello()我们称之为函数调用。函数调用仅仅需要函数名和紧跟着的括号，括号里面包含几个这个函数所定义的参数。当程序执行到
 函数调用的时候会自动跳转到这个函数声明的位置并开始执行函数代码。当函数功能的结束时，执行返回到调用函数位置，并继续执行下面的代码.
 因为这段代码调用了三次hello()函数所以hello()函数被执行了三次。当你运行这段代码时输出结果如下：  
	Howdy!    
	Howdy!!!    
	Hello there.  
	Howdy!  
	Howdy!!!  
	Hello there.  
	Howdy!  
	Howdy!!!  
	Hello there.  
 
 A major purpose of functions is to group code that gets executed multiple times. Without a function defined, you would have to  copy and paste this code each time, and the program would look like this:  
定义函数功能的主要目的把需要多次执行的代码遍成一个组。如果没有定义一个函数，你就必须复制和粘贴此代码，刚才的程序就会变成这样：  

	print('Howdy!')
	print('Howdy!!!')
	print('Hello there.')
	print('Howdy!')
	print('Howdy!!!')
	print('Hello there.')
	print('Howdy!')
	print('Howdy!!!')
	print('Hello there.')

In general, you always want to avoid duplicating code, because if you ever decide to update the code—if, for example, you find a bug you need to fix—you’ll have to remember to change the code everywhere you copied it.  
一般情况下，你总是希望避免重复的代码。举个例子，当你发现程序片段中有bug需要修复，你需要记得把你到处复的所有代码中的错误都进行修复。这是很痛苦的。  

## def Statements with Parameters
## 带参数的函数声明语句 def

 When you call the print() or len() function, you pass in values, called arguments in this context, by typing them between the parentheses. You can also define your own functions that accept arguments. Type this example into the file editor and save it as helloFunc2.py:  
当你调用print（）或LEN（）函数时在括号中输入的内容我们称为函数车参数。你也可以定义自己的函数可以接受的参数。在文件编辑器输入如下示例程序并保存为helloFunc2.py  
	
	def hello(name):  
		print('Hello ' + name)  
	hello('Alice')  
	hello('Bob')  
When you run this program, the output looks like this:  
当你运行这个程序时可以获得如下结果：  
	Hello Alice  
	Hello Bob  

The definition of the hello() function in this program has a parameter called name .A parameter is a variable that an argument is stored in when a function is called. The first time the hello() function is called, it’s with the argument 'Alice'. The program execution enters the function, and the variable name is automatically set to 'Alice', which is what gets printed by the print() statement.  
我们在这段代码中定义Hello（）函数有一个参数叫name。当函数被调用时该参数被当成一个变量存储在函数中。当第一次调用Hello（）函数时它被赋值为‘Alice'.当程序执行时，变量name就被自动赋值为'Alice'并且能够传递给print()函数。  
 
One special thing to note about parameters is that the value stored in a parameter is forgotten when the function returns. For example, if you added print(name) after hello('Bob') in the previous program, the program would give you a NameError because there is no variable named name. This variable was destroyed after the function call hello('Bob') had returned, so print(name) would refer to a name variable that does not exist.  
需要注意的是参数有一个特别之处，当函数返回时存储在一个参数的值将被清空。举例，在前面的程序中如果你在hello('Bob')后添加代码print（name)，程序会报NameError错误，因为变量name没有被赋值。name的值在函数调用hello('Bob')返回后就被清空了。所以print(name)将指向一个不存在值的变量name。  

This is similar to how a program’s variables are forgotten when the program terminates. I’ll talk more about why that happens later in the chapter, when I discuss what a function’s local scope is.  
这类似于程序终止时，程序的变量被清空。在后面的章节中讲到函数的局部范围时我们在做更多地讨论。  

## Return Values and return Statements  
## 返回值和返回语句  

When you call the len() function and pass it an argument such as 'Hello', the function call evaluates to the integer value 5, which is the length of the string you passed it. In general, the value that a function call evaluates to is called the return value of the function.  When creating a function using the def statement, you can specify what the return value should be with a return statement. A return statement consists of the following:  
- The return keyword  
- The value or expression that the function should return  
当你把hello作为参数传递给函数len()时，函数调用的计算结果为整型值5，刚好这就是你传递参数hello字符串的长度。通常我们把该函数调用后的计算结果值称为被调用的函数的返回值。  
当使用def语句创建一个新函数时，我们可以用return声明语句定义函数的返回值应该是什么。return声明语句句法如下：  
- 关键字 return  
- 希望函数返回的值或者表达式  

When an expression is used with a return statement, the return value is what this expression evaluates to. For example, the following program defines a function that returns a different string depending on what number it is passed as an argument. Type this code into the file editor and save it as magic8Ball.py:  
当用表达式来定义返回语句时，返回值就是表达式的运算结果。举例，下面程序不同的数字作为参数时将返回不同的字符串。在文件编辑器中编写下面的代码并保存为magic8Ball.py:  
		
	import random  
	def getAnswer(answerNumber):  
		if answerNumber == 1:
			return 'It is certain'  
		elif answerNumber == 2:  
			return 'It is decidedly so'  
		elif answerNumber == 3:  
			return 'Yes'  
		elif answerNumber == 4:  
			return 'Reply hazy try again'
		elif answerNumber == 5:  
			return 'Ask again later'  
		elif answerNumber == 6:  
			return 'Concentrate and ask again'  
		elif answerNumber == 7:  
			return 'My reply is no'  
		elif answerNumber == 8:  
			return 'Outlook not so good'  
		elif answerNumber == 9:  
			return 'Very doubtful'  
	r = random.randint(1, 9)  
	fortune = getAnswer(r)  
	print(fortune)  

When this program starts, Python first imports the random module ➊. Then the getAnswer() function is defined ➋. Because the function is being defined (and not called), the execution skips over the code in it. Next, the random.randint() function is called with two arguments, 1 and 9 ➍. It evaluates to a random integer between 1 and 9 (including 1 and 9 themselves), and this value is stored in a variable named r.  
当程序执行时先导入random模块。然后定义 getAnswer()函数。因为该函数刚被定义（没调用），执行时会跳过它的代码。接下来random.randint()函数调用并使用了两个参数1和9.它的计算结果为1和9之间的随机整数（包括1和9本身）并且该值被存储在一个变量名r中。  
 
The getAnswer() function is called with r as the argument ➎. The program execution moves to the top of the getAnswer() function ➌, and the value r is stored in a parameter named answerNumber. Then, depending on this value in answerNumber, the function returns one of many possible string values. The program execution returns to the line at the bottom of the program that originally called getAnswer() ➎. The returned string is assigned to a variable named fortune, which then gets passed to a print() call ➏ and is printed to the screen.  
getAnswer（）函数被调用并把变量r作为参数。程序执行将跳转到getAnswer()函数的第一行，并且r值存储在参数answerNumber中。然后根据 answerNumber被赋予的不同值函数返回多个字符串中的某一个值。程序执行返回到原来调用的getAnswer()函数的的底部。他返回的字符串被分配到一个名为fortune的变量，然后把它传递给打印函数print()并将结果打印到屏幕上。  
 
Note that since you can pass return values as an argument to another function call, you could shorten these three lines:  
需要注意的是，因为可以通过返回值作为参数传递给另一个函数调用，所以您可以把三行缩短成一行：  
	
	r = random.randint(1, 9)  
	fortune = getAnswer(r)  
	print(fortune)  
	
to this single equivalent line: 
	
	print(getAnswer(random.randint(1, 9)))  

Remember, expressions are composed of values and operators. A function call can be used in an expression because it evaluates to its return value.  
请记住，表达式是由值和运算符组成。函数调用可以在表达式中使用，因为表达式的计算结果就是它的返回值。  

## The None Value
## 空值

In Python there is a value called None, which represents the absence of a value. None is the only value of the NoneType data type. (Other programming languages might call this value null, nil, or undefined.) Just like the Boolean True and False values, None must be typed with a capital N.  
在python中有一个表示不存在的值，NoneType数据类型的唯一值，我们称其为空值。在其他编程语言中可能叫做空或者未定义值。这个值就像布尔True和False值，空值必须以大写N开头写为None.  

This value-without-a-value can be helpful when you need to store something that won’t be confused for a real value in a variable. One place where None is used is as the return value of print(). The print() function displays text on the screen, but it doesn’t need to return anything in the same way len() or input() does. But since all function calls need to evaluate to a return value, print() returns None. To see this in action, enter the following into the interactive shell:  
当你需要在变量中存储一个无法定义的数值时，空值就会变得非常有用。空值有一个常用的地方就是作为print()函数执行后的返回值。print()函数的功能是把字符打印到屏幕上，但是他又不能像len()或input()函数一样执行后返回一个真实存在的值。但所有函数执行完成后都需要一个返回值，print()函数返回为空值。想看到空值的作用请在交互窗口中输入如下代码：  
	
	spam = print('Hello!')
	Hello!
	None == spam
	True

Behind the scenes, Python adds return None to the end of any function definition with no return statement. This is similar to how a while or for loop implicitly ends with a continue statement. Also, if you use a return statement without a value (that is, just the return keyword by itself), then None is returned.  
在幕后，python在任何未定义返回参数的函数末尾增加了返回空值语句。这就好像for循环和whlie循环在末尾隐藏了一个continue语句。另外，如果使用return语句没有返回值（即，只返回关键字本身）这个时候就会返回空值。  

## Keyword Arguments and print()
## 关键字参数和print()函数

Most arguments are identified by their position in the function call. For example, random.randint(1, 10) is different from random.randint(10, 1). The function call random.randint(1, 10) will return a random integer between 1 and 10, because the first argument is the low end of the range and the second argument is the high end (while random.randint(10, 1) causes an error).  
大多数参数都是由它们在函数调用位置来识别。例如，random.randint（1，10和random.randint（10，1）不同。函数调用random.randint（1，10）将返回1和10之间的随机整数，因为第一个参数是random函数的最小值，第二个参数是最大值。如果写成random.randint(10, 1)就会出错。  

However, keyword arguments are identified by the keyword put before them in the function call. Keyword arguments are often used for optional parameters. For example, the print() function has the optional parameters end and sep to specify what should be printed at the end of its arguments and between its arguments (separating them), respectively.  
If you ran the following program:  
但是关键字参数是在他们函数调用之前通过关键字进行定义和区分的。关键字参数通常是可选参数。例如，print()函数具有可选参数end和spe两个可选参数.end这个参数可以指定在其结尾换行或继续打印。spe参数则可以在多个参数之间打印一些特殊字符如逗号等。当你运行下面的程序：  
	
	print('Hello')  
	print('World')  

the output would look like this:  
运行结果如下：  
	Hello  
	World  

The two strings appear on separate lines because the print() function automatically adds a newline character to the end of the string it is passed. However, you can set the end keyword argument to change this to a different string. For example, if the program were this:  
这两个字符串出现在不同的行上，因为print（）函数会自动添加一个换行符在字符串的结尾。但是，您可以将end关键字参数更改为不同的字符串。
例如，如果程序是这样的:  
	
	print('Hello', end='')    
	print('World')    
	
the output would look like this:  
程序运行结果是两个字符在同一行。  
	HelloWorld  

The output is printed on a single line because there is no longer a new-line printed after 'Hello'. Instead, the blank string is printed. This is useful if you need to disable the newline that gets added to the end of every print() function call.  
输出显示在一行，因为不再有换行符在“Hello”打印之后。取而代之的是空字符串。如果你需要禁用每一个print（）函数调用结束的换行符，这是非常有用的。  

Similarly, when you pass multiple string values to print(), the function will automatically separate them with a single space. Enter the following into the interactive shell:  
同样，当你使用print（）函数打印多个字符串值，该功能会自动将这些用一个空格分开。输入以下内容：  
	
	print('cats', 'dogs', 'mice')    
	cats dogs mice  

But you could replace the default separating string by passing the sep keyword argument. Enter the following into the interactive shell:  
但是你可以通过传递sep关键字参数替换默认的分隔字符串。在交互窗体输入以下代码：  
	
	print('cats', 'dogs', 'mice', sep=',')    
	cats,dogs,mice  

You can add keyword arguments to the functions you write as well, but first you’ll have to learn about the list and dictionary data types in the next two chapters. For now, just know that some functions have optional keyword arguments that can be specified when the function is called.  
您可以添加关键字参数给你写的函数，但首先你必须在接下来的两个章节学习列表类型和字典数据类型。现在你只需要知道一些函数在被调用时可以指定可选关键字参数。  

## Local and Global Scope  
## 局部和全局范围  
## [相关视频教程](https://youtu.be/M-CoVBK_bLE)  

Parameters and variables that are assigned in a called function are said to exist in that function’s local scope. Variables that are assigned outside all functions are said to exist in the global scope. A variable that exists in a local scope is called a local variable, while a variable that exists in the global scope is called a global variable. A variable must be one or the other; it cannot be both local and global.  
在函数被调用时才赋值的参数和变量其作用范围为局部范围，这样的参数和变量我们称为局部参数和局部变量。在全部函数外部被赋值的变量其作用范围为全局范围，这样的变量我们称为全局变量。一个变量的作用范围必须是全局或局部的一种，一个变量不能既是全局变量又是局部变量。  
  
Think of a scope as a container for variables. When a scope is destroyed, all the values stored in the scope’s variables are forgotten. There is only one global scope, and it is created when your program begins. When your program terminates, the global scope is destroyed, and all its variables are forgotten. Otherwise, the next time you ran your program, the variables would remember their values from the last time you ran it.  
思考一下变量的作用范围。当一个作用范围被破坏，储存在范围内的变量的所有值都清空了。Python中只有一个全局范围，在你的程序开始时生成。当你的程序终止时全局范围被破坏，它的所有变量将清空。否则，你程序下一次运行时，变量就会调出它最后一次运行时被赋值它们的值。  

A local scope is created whenever a function is called. Any variables assigned in this function exist within the local scope. When the function returns, the local scope is destroyed, and these variables are forgotten. The next time you call this function, the local variables will not remember the values stored in them from the last time the function was called.  
每当函数被调用时都会创建局部作用范围。任何在函数内部被赋值的变量都是局部范围。当函数返回时，局部范围被破坏，这些变量就被清空。当你下次调用这个函数的时候局部变量不会记得上次函数调用时存储的值。  

Scopes matter for several reasons:
Code in the global scope cannot use any local variables.
However, a local scope can access global variables.
Code in a function’s local scope cannot use variables in any other local scope.
You can use the same name for different variables if they are in different scopes. That is, there can be a local variable named spam and a global variable also named spam.  
他们之间有以下关系：  
全局范围内的代码不能使用任何局部变量。    
但是，局部变量可以范围全局变量。  
一个函数内部的代码不能使用另外的局部变量。  
如果变量的作用范围是不一样的那么你可以使用相同的名字来命名不同的变量。也就是说允许一个局部变量命名为spam和一个全局变量也命名为spam。  

The reason Python has different scopes instead of just making everything a global variable is so that when variables are modified by the code in a particular call to a function, the function interacts with the rest of the program only through its parameters and the return value. This narrows down the list code lines that may be causing a bug. If your program contained nothing but global variables and had a bug because of a variable being set to a bad value, then it would be hard to track down where this bad value was set. It could have been set from anywhere in the program—and your program could be hundreds or thousands of lines long! But if the bug is because of a local variable with a bad value, you know that only the code in that one function could have set it incorrectly.    
python使用不同作用范围来代替把所有变量都定义成全局的原因是，当一个变量被特定的函数调用赋值后，这个函数与其他代码的交互和作用只能通过参数和其返回值进行。在python中不当的代码缩进可能造成Bug。如果你的程序中只有一个因为全局变量被错误赋值造成的Bug，那么要找出这个错误赋值出现在什么地方是很困难的。因为你的程序有成百上千行代码这个赋值可能在任何地方出现。相反地，如果是局部变量被错误赋值造成的Bug，你只需要去调用这个局部变量所在函数的地方进行修正就可以了。  

While using global variables in small programs is fine, it is a bad habit to rely on global variables as your programs get larger and larger.  
在小程序中使用全局变量是不会有什么问题的，当您的程序变得越来越长时依靠全局变量就是一个坏习惯了。  

### Local Variables Cannot Be Used in the Global Scope
### 局部变量不能用在全局范围  

Consider this program, which will cause an error when you run it:  
思考下运行下面这个程序时，将出现什么错误：  
	
	def spam():  
		eggs = 31337  
		spam()  
	print(eggs)   

If you run this program, the output will look like this:  
如果你运行这个程序会输出如下的错误提示：  
Traceback (most recent call last):  
  File "C:/test3784.py", line 4, in <module>  
    print(eggs)  
NameError: name 'eggs' is not defined  

The error happens because the eggs variable exists only in the local scope created when spam() is called. Once the program execution returns from spam, that local scope is destroyed, and there is no longer a variable named eggs. So when your program tries to run print(eggs), Python gives you an error saying that eggs is not defined. This makes sense if you think about it; when the program execution is in the global scope, no local scopes exist, so there can’t be any local variables. This is why only global variables can be used in the global scope.  
因为变量eggs只能在spam()被调用时创建，他的作用范围是局部范围所以会发生错误。当程序运返回spam时，局部作用范围已经破坏。在变量eggs中不存在任何值。所以尝试用print(eggs)来打印python会报告eggs没有被定义的错误。，如果你仔细想想，这是有道理的。当程序在全局范围内运行时，无局部范围存在，所以不能有任何局部变量。这就是为什么全局变量只可以在全局范围内使用。  

###　Local Scopes Cannot Use Variables in Other Local Scopes
### 局部作用范围不能使用其他函数局部变量  

A new local scope is created whenever a function is called, including when a function is called from another function. Consider this program:  
每当函数被调是将创建一个新的局部范围建，包括一个函数从另一个函数调用时。思考下面的程序：  
	
	def spam():  
		eggs = 99  
		bacon()  
		print(eggs)  
	def bacon():  
		ham = 101  
		eggs = 0  
	pam()  

When the program starts, the spam() function is called ➎, and a local scope is created. The local variable eggs ➊ is set to 99. Then the bacon() function is called ➋, and a second local scope is created. Multiple local scopes can exist at the same time. In this new local scope, the local variable ham is set to 101, and a local variable eggs—which is different from the one in spam()’s local scope—is also created ➍ and set to 0.  
当程序运行时，函数spam()被调用，局部范围被创建。局部变量eggs被赋值99当函数bacon()b被调用是第二个局部范围被创建。两个局部范围同时存在。在新的局部范围内，局部变量ham被赋值101，第二个局部变量eggs不同于函数spam(）中的eggs并且被赋值0.  
When bacon() returns, the local scope for that call is destroyed. The program execution continues in the spam() function to print the value of eggs ➌, and since the local scope for the call to spam() still exists here, the eggs variable is set to 99. This is what the program prints.The upshot is that local variables in one function are completely separate from the local variables in another function.  
当bacon()函数返回时局部范围被破坏。程序继续执行spam()函数并打印eggs的值，因为最开始创建的局部范围还存在，所以eggs的被赋值99。这就是程序运行打印的结果。其结果是，在一个函数中的局部变量是和另一个函数中的局部变量完全独立。  

### Global Variables Can Be Read from a Local Scope  
### 全局变量可以被局部变量读取  

Consider the following program:  
思考下面的程序:  
	
	def spam():  
		print(eggs)  
	eggs = 42  
	spam()  
	print(eggs)  

Since there is no parameter named eggs or any code that assigns eggs a value in the spam() function, when eggs is used in spam(), Python considers it a reference to the global variable eggs. This is why 42 is printed when the previous program is run.  
由于参数eggs在函数spam()中没有任何定义，当在函数spam()中用到eggs参数时，Python会认为变量eggs是一个全局变量。这就是是为什么程序运行打印出来的值是42  

### Local and Global Variables with the Same Name
### 局部变量和全局变量可以具有相同的名称  

To simplify your life, avoid using local variables that have the same name as a global variable or another local variable. But technically, it’s perfectly legal to do so in Python. To see what happens, type the following code into the file editor and save it as sameName.py:  
为了让你代码可读性好，要避免使用相同的名称作为一个全局变量或其他局部变量的变量名。但在语法上讲，Python这样做这是完全合法的。想看看会发生什么，在文本编辑框输入下面的代码并保存为samName.py:  
	
	def spam():
		eggs = 'spam local' #1
		print(eggs) # prints 'spam local'
	def bacon():
		eggs = 'bacon local' #2
		print(eggs) # prints 'bacon local'
		spam()
		print(eggs) # prints 'bacon local'
	eggs = 'global' #3
	bacon()
	print(eggs) # prints 'global'
	
When you run this program, it outputs the following:  
当你运行这段代码时结果如下：  
	bacon local  
	spam local
	bacon local
	global  

There are actually three different variables in this program, but confusingly they are all named eggs. The variables are as follows:
➊ A variable named eggs that exists in a local scope when spam() is called.
➋ A variable named eggs that exists in a local scope when bacon() is called.
➌ A variable named eggs that exists in the global scope.
Since these three separate variables all have the same name, it can be confusing to keep track of which one is being used at any given time. This is why you should avoid using the same variable name in different scopes.   
其实这里有三个不同的变量，他们都被命名为eggs很容易使人误解。eggs变量如下：  
- 1、一个局部变量eggs在函数spam()中  
- 2、一个局部变量eggs在函数bacon()中
- 3、一个全局变量eggs
因为这三个独立的变量都具有相同的名称，要追踪其中一个变量在何时被使用将会十分混乱。这也是为什么建议大家不要用相同的名字命名不同的变量。

### The global Statement
### 全局声明语句  

If you need to modify a global variable from within a function, use the global statement. If you have a line such as global eggs at the top of a function, it tells Python, “In this function, eggs refers to the global variable, so don’t create a local variable with this name.” For example, type the following code into the file editor and save it as sameName2.py:  
如果你需要在一个函数中修改一个全局变量，需要用到全局声明语句。
如果你有一行代码类似于global eggs在一个函数顶部，它告诉Python，在这个函数中eggs是指全局变量，所以不要使用此名称创建一个局部变量。”例如在文本编辑框输入下面的代码并保存为samName2.py:

	def spam():
		global eggs
		eggs = 'spam'
	eggs = 'global'
	spam()
	print(eggs)
	
When you run this program, the final print() call will output this:  
当运行这个函数时最终输出如下：
spam  

Because eggs is declared global at the top of spam()，when eggs is set to 'spam' ， this assignment is done to the globally scoped eggs. No local eggs variable is created.  
There are four rules to tell whether a variable is in a local scope or global scope:
- If a variable is being used in the global scope (that is, outside of all functions), then it is always a global variable.
- If there is a global statement for that variable in a function, it is a global variable.
- Otherwise, if the variable is used in an assignment statement in the function, it is a local variable.
 -But if the variable is not used in an assignment statement, it is a global variable.
因为eggs在spam()函数的首行被声明全局变量eggs，当eggs被赋值为'spam"时，这个操作将全局变量的eggs进行了赋值。没有本地变量eggs被创建。  
这里有四个规则可以判断变量是全局变量还是局部变量：
- 当一个变量被用着全局范围（也就是说，在所有函数外面）那么这个变量就是全局变量。
- 当一个全局声明语句在函数中被使用，那么这个变量将指向全局变量。
- 如果变量是在函数内赋值语句中使用，那么这个是局部变量。
- 但是如果变量没有在赋值语句中使用，它是一个全局变量。  

To get a better feel for these rules, here’s an example program. Type the following code into the file editor and save it as sameName3.py:  
这里有一个例程帮你更好的理解这几个规则。键入下面的代码到文件编辑器并保存为sameName3.py：

	def spam():
		global eggs
    		eggs = 'spam' #全局
    	def bacon():
    		eggs = 'bacon' #局部
	def ham():
		print(eggs) #全局
	eggs = 42 #全局
	spam()
	print(eggs)
	
In the spam() function, eggs is the global eggs variable, because there’s a global statement for eggs at the beginning of the function ➊. In bacon(), eggs is a local variable, because there’s an assignment statement for it in that function ➋. In ham() ➌, eggs is the global variable, because there is no assignment statement or global statement for it in that function. 
在函数spam()函数中eggs是全局变量。因为在函数开始的地方用全局声明语句。在bacon()中eggs是局部变量，因为有赋值语句。在ham()中eggs是全局变量，因为没有任何赋值语句或全局声明语句。
If you run sameName3.py, the output will look like this:    
程序运行后结果如下： 
spam  

In a function, a variable will either always be global or always be local. There’s no way that the code in a function can use a local variable named eggs and then later in that same function use the global eggs variable.  
在函数中，变量要么始终是全局变量要么是局部变量。在同一个函数中没有办法先使用一个叫eggs的本地变量，然后在使用全局变量eggs。
### NOTE
If you ever want to modify the value stored in a global variable from in a function, you must use a global statement on that variable. 
如果你想在一个函数中修改存储在一个全局变量中的值，则必须在该变量前使用全局声明。  

If you try to use a local variable in a function before you assign a value to it, as in the following program, Python will give you an error. To see this, type the following into the file editor and save it as sameName4.py:  
如果你在函数中尝试使用一个未赋值的局部变量Python会给出错误。想看到这一点，键入以下到文件编辑器并保存为sameName4.py：  

	def spam():
		print(eggs) # ERROR!
		eggs = 'spam local'
	eggs = 'global
	spam()
	
If you run the previous program, it produces an error message.  
当你运行代码时会出现下面的错误：
	
	Traceback (most recent call last):
	File "C:/test3784.py", line 6, in <module>
	spam()
	File "C:/test3784.py", line 2, in spam
	print(eggs) # ERROR!
	UnboundLocalError: local variable 'eggs' referenced before assignment
	
This error happens because Python sees that there is an assignment statement for eggs in the spam() function and therefore considers eggs to be local. But because print(eggs) is executed before eggs is assigned anything, the local variable eggs doesn’t exist. Python will not fall back to using the global eggs variable   
错误发生是因为python看到在spam()函数中有一个赋值语句给eggs，他会认为eggs为局部变量，但是执行print(eggs)语句的时候eggs没有任何定义，局部变量eggs还不存在。python不会回去查找全局变量eggs的值。  

### FUNCTIONS AS “BLACK BOXES”
Often, all you need to know about a function are its inputs (the parameters) and output value; you don’t always have to burden yourself with how the function’s code actually works. When you think about functions in this high-level way, it’s common to say that you’re treating the function as a “black box.”
This idea is fundamental to modern programming. Later chapters in this book will show you several modules with functions that were written by other people. While you can take a peek at the source code if you’re curious, you don’t need to know how these functions work in order to use them. And because writing functions without global variables is encouraged, you usually don’t have to worry about the function’s code interacting with the rest of your program.  
通常情况下，你需要知道的函数输入（参数）后会有怎样的输出值，但是你并不是中需要知道代码具体是怎么执行的。当你站在更高的层面来看函数时，这些函数看起来就像一个黑盒子。这个想法是现代编程的基础。在这本书后面的章节会告诉你几个其他人编写的功能模块。虽然你好奇的时候可以看看源代码，但是你不需要知道这些函数是如何工作的就可以使用他们。而且因为我们鼓励编写函数时不用全局变量，所有你通常不必担心这些函数的代码影响到你程序的其余部分。

## Exception Handling
## 异常处理
## [相关视频教程](https://youtu.be/qS0UkqaYmfU)
Right now, getting an error, or exception, in your Python program means the entire program will crash. You don’t want this to happen in real-world programs. Instead, you want the program to detect errors, handle them, and then continue to run.  
运行你的Python程序得到一个错误，或异常，意味着整个程序会崩溃。你不希望这些错误在交付项目中发生。相反，你想要程序来检测错误，处理它们，然后继续运行。  
For example, consider the following program, which has a “divide-by-zero” error. Open a new file editor window and enter the following code, saving it as zeroDivide.py:  
例如，下面的程序，其中有一个“除以零”错误。打开一个新的文件编辑器窗口，然后输入以下代码，将其保存为zeroDivide.py：
	
	def spam(divideBy):
		return 42 / divideBy

	print(spam(2))
	print(spam(12))
	print(spam(0))
	print(spam(1))
	
We’ve defined a function called spam, given it a parameter, and then printed the value of that function with various parameters to see what happens. This is the output you get when you run the previous code:  
我们定义了一个名为spam的程序，给它一个参数，然后打印有不同参数的函数值，看看会发生什么。当你运行上面的代码中会输出如下内容：
	
	21.0
	3.5
	Traceback (most recent call last):
	File "C:/zeroDivide.py", line 6, in <module>
	print(spam(0))
	File "C:/zeroDivide.py", line 2, in spam
	return 42 / divideBy
	ZeroDivisionError: division by zero
	
A ZeroDivisionError happens whenever you try to divide a number by zero. From the line number given in the error message, you know that the return statement in spam() is causin　an　error.  
每当你尝试除以零值的时候ZeroDivisionError发生。从错误消息中给出的行号知道spam函数的return语句导致了错误. 

You can put the previous divide-by-zero code in a try clause and have an except clause contain code to handle what happens when this error occurs.    
你可以在除零语句前加上try语句，并且用有一个except语句指明可能发生的错误会是什么并指定这个错误发生时返回什么。
	
	def spam(divideBy):
		try:
			return 42 / divideBy
		except ZeroDivisionError:
        		print('Error: Invalid argument.')

	print(spam(2))
	print(spam(12))
	print(spam(0))
	print(spam(1))
		
When code in a try clause causes an error, the program execution immediately moves to the code in the except clause. After running that code, the execution continues as normal. The output of the previous program is as follows:  
当在try语句中发现错误，程序执行立即移动到代码中的except。运行的代码后，将继续正常执行。上面的程序的输出是如下：  
	
	21.0
	3.5
	Error: Invalid argument.
	None
	42.0

Note that any errors that occur in function calls in a try block will also be caught. Consider the following program, which instead has the spam() calls in the try block:  
需要注意的是发生在一个try块函数调用的任何错误都将被捕获。考虑下面的程序，spam()函数在try函数块中是如何调用：  
	
	def spam(divideBy):
		return 42 / divideBy
	try:
		print(spam(2))
		print(spam(12))
		print(spam(0))
		print(spam(1))
	except ZeroDivisionError:
		print('Error: Invalid argument.')
		
When this program is run, the output looks like this:  
当运行这个程序，输出如下：  

	21.0 
	3.5 
	Error: Invalid argument.      #错误：无效的参数。
	

The reason print(spam(1)) is never executed is because once the execution jumps to the code in the except clause, it does not return to the try clause. Instead, it just continues moving down as normal.  
print(spam(1))永远不会执行是因为一旦执行跳转到except句中的代码，它不会返回到try语句。相反，它只是继续向下执行。  

## A Short Program: Guess the Number
## 一个小程序：猜数字
## [相关视频教学](https://youtu.be/48WXHT0dfEY)

The toy examples I’ve show you so far are useful for introducing basic concepts, but now let’s see how everything you’ve learned comes together in a more complete program. In this section, I’ll show you a simple “guess the number” game. When you run this program, the output will look something like this:  
到目前为止我给你们举的玩具的例子对引入基本概念是非常有用的，但现在让我们来看看如何把你学到的一切结合在一起成为一个更完整的方案。在本节中，我会告诉你一个简单的“猜数字”游戏。当你运行这个程序，输出会是这个样子：
	I am thinking of a number between 1 and 20.
	Take a guess.
	10
	Your guess is too low.
	Take a guess.
	15
	Your guess is too low.
	Take a guess.
	17
	Your guess is too high.
	Take a guess.
	16
	Good job! You guessed my number in 4 guesses!

Type the following source code into the file editor, and save the file as guessTheNumber.py:  
键入下面的源代码到文件编辑器，并将该文件保存为guessTheNumber.py：
    
        #This is a guess the number game
        import random
        secretNumber = random.randint (1,20)
        print('I am thinking of a number betwen 1 and 20.')

        # Ask the player to guess 6 times
        for guessesTaken in range(1,7):
                print('Take a guess.')
                guess = int(input())
                if guess < secretNumber:
                        print('Your guess is too low.')
                elif guess > secretNumber:
                        print('Your guess is too high.')
                else:
                        break
        if guess == secretNumber:
                print('Good job!Yuou guessed my number in ' + str(guessesTaken) + ' guesses! ')
        else:
                print('Nope.The number I was thinking of was' + str(secertNumber))

First, a comment at the top of the code explains what the program does. Then, the program imports the random module so that it can use the random.randint() function to generate a number for the user to guess. The return value, a random integer between 1 and 20, is stored in the variable secretNumber.  
首先，在代码顶部的注释说明该程序的功能。然后，程序导入随机模块，以便它可以使用random.randint()函数来生成一个随机数，给用户猜测。随机函数返回1和20之间的随机整数，被存储在变量secretNumber中。  
	print('I am thinking of a number between 1 and 20.')

	# Ask the player to guess 6 times.
	for guessesTaken in range(1, 7):
		print('Take a guess.')
		guess = int(input())
The program tells the player that it has come up with a secret number and will give the player six chances to guess it. The code that lets the player enter a guess and checks that guess is in a for loop that will loop at most six times. The first thing that happens in the loop is that the player types in a guess. Since input() returns a string, its return value is passed straight into int(), which translates the string into an integer value. This gets stored in a variable named guess.  
该程序会告诉玩家，它想出了一个秘密号码，并给玩家6次机会来猜它。程序让玩家猜测一个数，并检查猜测的数字是否正确。这个猜测过程最多循环六次。这个循环中第一件发生的事情是玩家猜测输入的数据类型。因为input()函数返回为字符串，所以我们把值传递给用int()函数，并把字符串转换成数字。这个猜测的数据被存储在变量guess中。  

	if guess < secretNumber:
		print('Your guess is too low.')
	elif guess > secretNumber:
		print('Your guess is too high.')
		
These few lines of code check to see whether the guess is less than or greater than the secret number. In either case, a hint is printed to the screen.  
这几行代码用来检测玩家猜测的数字是大于还是小于程序随机产生的秘密数字。并将这两种情况下的提示打印到屏幕上。

	else:
		break    # This condition is the correct guess!

If the guess is neither higher nor lower than the secret number, then it must be equal to the secret number, in which case you want the program execution to break out of the for loop.  
如果猜测数字刚好等于秘密数字跳出猜测数字的for循环。  
	f guess == secretNumber:
		print('Good job! You guessed my number in ' + str(guessesTaken) + ' guesses!')
	else:
		print('Nope. The number I was thinking of was ' + str(secretNumber))
After the for loop, the previous if...else statement checks whether the player has correctly guessed the number and prints an appropriate message to the screen. In both cases, the program displays a variable that contains an integer value (guessesTaken and secretNumber). Since it must concatenate these integer values to strings, it passes these variables to the str() function, which returns the string value form of these integers. Now these strings can be concatenated with the + operators before finally bei...(line truncated)...  
猜测数字for循环结束后，用if～else语句检查玩家是否在循环次数中猜中数字并打印相应的提示消息到屏幕上。在这两种情况下，程序将显示包含一个整数值（guessesTaken和secretNumber）的变量。因为打印函数只能连接字符串类型的数据，所以我们需要用str()函数来把整数值类型转换成字符串类型。现在，这些字符串可以用+运算符连接起来并调用print()函数打印出来。  

## Summary
## 总结

Functions are the primary way to compartmentalize your code into logical groups. Since the variables in functions exist in their own local scopes, the code in one function cannot directly affect the values of variables in other functions. This limits what code could be changing the values of your variables, which can be helpful when it comes to debugging your code.  
函数是划分你的代码到逻辑组的主要方式。因为在函数中的变量有自己的作用域存在，在一个函数的代码不能直接影响的其他函数的变量的值。由于改变你变量值的代码有范围限制，所以在调试代码时非常有用。  
Functions are a great tool to help you organize your code. You can think of them as black boxes: They have inputs in the form of parameters and outputs in the form of return values, and the code in them doesn’t affect variables in other functions.  
函数是一个伟大的工具来帮助你组织你的代码。你可以把它们当作黑盒子：它们以参数和输出返回值的形式存在，并且它们代码不会影响到其他函数的变量。  
In previous chapters, a single error could cause your programs to crash. In this chapter, you learned about try and except statements, which can run code when an error has been detected. This can make your programs more resilient to common error cases.  
在前面的章节中，单个错误可能会导致程序崩溃。在这章我们学习了try和except声明，当检测到错误时代码还能运行。  

## Practice Questions
## 练习题

	Q:
	1. Why are functions advantageous to have in your programs?  
	   为什么函数对你的代码有用？
	Q:
	2. When does the code in a function execute: when the function is defined or when the function is called?  
	   函数中的代码什么时候执行：是函数被定义的时候还是函数被调用的时候？
	Q:
	3. What statement creates a function?  
	  什么语句可以创建一个函数？
	Q:
	4. What is the difference between a function and a function call?  
	  函数和函数调用之间有什么不同？
	Q:
	5. How many global scopes are there in a Python program? How many local scopes?  
	  在python中有几个全局作用范围？几个局部作用范围？
	Q:
	6. What happens to variables in a local scope when the function call returns?  
	  函数调用返回时在局部范围内的变量会发生什么？
	Q:
	7. What is a return value? Can a return value be part of an expression?  
	  什么是一个返回值？返回值可以是一个表达式的一部分吗？
	Q:
	8. If a function does not have a return statement, what is the return value of a call to that function?  
	  如果一个函数没有返回值，这个函数被调用的时候会返回什么？
	Q:
	9. How can you force a variable in a function to refer to the global variable?  
	  怎么将一个函数中的变量强制指向全局变量。
	Q:
	10. What is the data type of None?  
	  None是什么类型的数据。
	Q:
	11. What does the import areallyourpetsnamederic statement do?  
	  import areallyourpetsnamederic语句有什么作用？
	Q:
	12. If you had a function named bacon() in a module named spam, how would you call it after importing spam?  
	  如果有一个函数bacon()在一个叫spam的模块中，在导入模块spam之后如何调用。
	Q:
	13. How can you prevent a program from crashing when it gets an error?  
	  怎么防止程序在遇到错误时崩溃。
	Q:
	14. What goes in the try clause? What goes in the except clause?   
	  try语句什么是作用？except语句是什么作用？
	  
## Practice Projects
## 项目练习
For practice, write programs to do the following tasks.  
编写程序来执行以下任务作为练习  
### The Collatz Sequence
### 考拉兹猜想
> 又称为奇偶归一猜想、3n＋1猜想、冰雹猜想、角谷猜想、哈塞猜想、乌拉姆猜想或叙拉古猜想，是指对于每一个正整数，如果它是奇数，则对它乘3再加1，如果它是偶数，则对它除以2，如此循环，最终都能够得到1。

Write a function named collatz() that has one parameter named number. If number is even, then collatz() should print number // 2 and return this value. If number is odd, then collatz() should print and return 3 * number + 1.  
编写一个名为在Collat​​z()的函数他有一个参数叫number。如果number是偶数，那么Collat​​z()打印number//2并返回这个值。如果number为奇数，Collat​​z()打印并返回3 *number+ 1的值。  
Then write a program that lets the user type in an integer and that keeps calling collatz() on that number until the function returns the value 1. (Amazingly enough, this sequence actually works for any integer—sooner or later, using this sequence, you’ll arrive at 1! Even mathematicians aren’t sure why. Your program is exploring what’s called the Collatz sequence, sometimes called “the simplest impossible math problem.”)   
然后再写一个程序，让用户键入一个整数，并且不断调用Collat​​z（）直到函数返回值1。（令人吃惊的是无论输入什么样的整数在运行足够次数后最终都会得到1！甚至连数学家都不知道为什么。你的程序解决的问题叫着考拉赫兹猜想。有时也被称为“最简单的无解数学问题。”  
Remember to convert the return value from input() to an integer with the int() function; otherwise, it will be a string value.
Hint: An integer number is even if number % 2 == 0, and it’s odd if number % 2 == 1.  
记住用int()将input()值转换成整数。小提示：An integer number is even if number % 2 == 0, and it’s odd if number % 2 == 1.   
The output of this program could look something like this:  
程序运行后会像这样：
	Enter number:
	3
	10
	5
	16
	8
	4
	2
	1
	
### Input Validation
### 输入验证
Add try and except statements to the previous project to detect whether the user types in a noninteger string. Normally, the int() function will raise a ValueError error if it is passed a noninteger string, as in int('puppy'). In the except clause, print a message to the user saying they must enter an integer.  
尝试用except语句来提前检测用户输入是否为非整形数据类型。通常情况下，如果输入是非整数字符串int()函数将引发ValueError错误，例如int('puppy').在except语句，打印一个消息告诉用户说他们必须输入一个整数。  
