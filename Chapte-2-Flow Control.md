# Flow Control 流程控制
## [相关教学视频](https://youtu.be/4XA9CKJJbr4)

So you know the basics of individual instructions and that a program is just a series of instructions. But the real strength of programming isn’t just running (or executing) one instruction after another like a weekend errand list. Based on how the expressions evaluate, the program can decide to skip instructions, repeat them, or choose one of several instructions to run. In fact, you almost never want your programs to start from the first line of code and simply execute every line, straight to the end. Flow control statements can decide which Python instructions to execute under which conditions.  
就你目前你所知的程序基本上是由各种基本语句和一系列指令组成的集合。但是真正的程序并不是像周末任务列表一样一个接一个运行。基于表达式的值，该程序可以决定跳过指令，重复运行某些指令，或选择几个指令来运行的。事实上，你几乎不会希望你的程序从第一行代码开始，顺序执行每一行，直奔终点。流程控制语句可以决定Python根据指示在不同条件下执行不同的逻辑。  

These flow control statements directly correspond to the symbols in a flowchart, so I’ll provide flowchart versions of the code discussed in this chapter. Figure 2-1 shows a flowchart for what to do if it’s raining. Follow the path made by the arrows from Start to End.  
这些流程控制语句直接对应流程图中的符号，我们将在本章讨论不同的代码流程图。
下图显示了如果下雨怎么办的流程图。按照从开始到结束的路径。  
![Figure](https://automatetheboringstuff.com/images/000105.jpg)  

In a flowchart, there is usually more than one way to go from the start to the end. The same is true for lines of code in a computer program. Flowcharts represent these branching points with diamonds, while the other steps are represented with rectangles. The starting and ending steps are represented with rounded rectangles.  
在一个流程中，通常从开始到结果有不止一种到达方式。在程序代码中也是这样。流程图中用菱形表示分支节点，而其他步骤用矩形表示。开始和结束的步骤被表示成具有圆角的矩形。  

But before you learn about flow control statements, you first need to learn how to represent those yes and no options, and you need to understand how to write those branching points as Python code. To that end, let’s explore Boolean values, comparison operators, and Boolean operators.  
但是在你学习流程控制语句之前，你首先需要学习如何表达yes和no选项，并且你需要了解在python代码中如何写那些分支点。为此，让我们来看看布尔值，比较运算符和布尔运算。  

## Boolean Values
## 布尔值

While the integer, floating-point, and string data types have an unlimited number of possible values, the Boolean data type has only two values: True and False. (Boolean is capitalized because the data type is named after mathematician George Boole.) When typed as Python code, the Boolean values True and False lack the quotes you place around strings, and they always start with a capital T or F, with the rest of the word in lowercase. Enter the following into the interactive shell. (Some of these instructions are intentionally incorrect, and they’ll cause error messages to appear.)  
整数，浮点和字符串数据类型具有数量不限的可能值,但是布尔类型的数据只有真和假两种值。(布尔是大写的，因为布尔数据类型是根据数学家乔治·布尔名字命名的。）在python代码中布尔变量的值都是以大写字母的T和F开头后面字母小写的Ture和
False来代表布尔值的真和假。在python交互窗体输入以下内容（其中的一些指令是故意写错的，他们会导致出现错误消息。）  

	>>> spam = True     # (1)
	>>> spam
	True
	>>> true            # (2)
	Traceback (most recent call last):
	  File "<stdin>", line 1, in <module>
	NameError: name 'true' is not defined
	>>> True = 2 + 2    # (3)
	  File "<stdin>", line 1
	SyntaxError: can't assign to keyword
	>>> 
	Connection to server timed out. Click run to reconne  

Like any other value, Boolean values are used in expressions and can be stored in variables ➊. If you don’t use the proper case ➋ or you try to use True and False for variable names ➌, Python will give you an error message.  
像任何其他值一样，布尔值可以在表达式中使用，并且可以存储在变量中（1）。如果你使用不正确（2）或试图使用True和False变量名（3），Python将会给你一个错误信息。  

## Comparison Operators
## 比较运算符

Comparison operators compare two values and evaluate down to a single Boolean value. Table 2-1 lists the comparison operators.    比较运算符比较两个值并最终获得一个单一的布尔值。下表2-1列出了比较操作符。    
Table 2-1. Comparison Operators  

|Operator |Meaning|
|---------|-------|
|== |Equal to|
|!= |Not equal to|
|< |Less than|
|> |Greater than|
|<= |Less than or equal to|
|>= |Greater than or equal to|

These operators evaluate to True or False depending on the values you give them. Let’s try some operators now, starting with == and !=.  
这些表达式的结果为真或假取决于你给他们的值。让我们从==和!=开始尝试一些运算表达式。  

	>>> 42 == 42
	True
	>>> 42 == 99
	False
	>>> 2 != 3
	True
	>>> 2 != 2
	False
	>>> 

As you might expect, == (equal to) evaluates to True when the values on both sides are the same, and != (not equal to) evaluates to True when the two values are different. The == and != operators can actually work with values of any data type.  
正如你所预料的，==（等于）计算结果为真时，两边的值是相同的，！=（不等于）时，这两个值是不同的。==和！=操作实际上可以在任何数据类型之间。  

	>>> 'hello' == 'hello'
	True
	>>> 'hello' == 'Hello'
	False
	>>> 'dog' != 'cat'
	True
	>>> True == True
	True
	>>> True != False
	True
	>>> 42 == 42.0
	True
	>>> 42 == '42'
	False
	>>> 
	
Note that an integer or floating-point value will always be unequal to a string value. The expression 42 == '42' ➊ evaluates to False because Python considers the integer 42 to be different from the string '42'.  
注意，整数或浮点值将始终不等于一个字符串值。表达式42=='42'➊计算为假，因为Python认为整数42和字符串'42'不同。 The <, >, <=, and >= operators, on the other hand, work properly only with integer and floating-point values.  
在另一方面<，>，<=，和> =运算符仅适用于整数和浮点值运算。  
	
	>>> 42 < 100
	True
	>>> 42 > 100
	False
	>>> 42 < 42
	False
	>>> eggCount = 42
	>>> eggCount <= 42
	True
	>>> myAge = 29
	>>> myAge >= 10
	True
	>>>    
		
### THE DIFFERENCE BETWEEN THE == AND = OPERATORS
You might have noticed that the == operator (equal to) has two equal signs, while the = operator (assignment) has just one equal sign. It’s easy to confuse these two operators with each other. Just remember these points:  
The == operator (equal to) asks whether two values are the same as each other.
The = operator (assignment) puts the value on the right into the variable on the left.
To help remember which is which, notice that the == operator (equal to) consists of two characters, just like the != operator (not equal to) consists of two characters.  
### ==和=运算符的区别  
你可能已经注意到了==运算符（等于）有两个等号，而=运算符（赋值）只有一个等号。这是很容易相互混淆的两个运算符。请记住以下几点：  

- ==运算符（等于）是询问两个值彼此是否相同。 
- =运算符（赋值）把右侧的值传递到左侧的变量。 

为了帮助记忆哪个是哪个，请注意==操作符（等于）由两个字符组成，就像！=运算符（不等于）一样也是两个字符。  

You’ll often use comparison operators to compare a variable’s value to some other value, like in the eggCount <= 42 ➊ and myAge >= 10 ➋ examples. (After all, instead of typing 'dog' != 'cat' in your code, you could have just typed True.) You’ll see more examples of this later when you learn about flow control statements.  
你会经常使用比较运算符比较两个变量的值，像eggCount <= 42和myAge> = 10的例子。 
（毕竟你在代码中只输入True，而比键入'狗'！='猫'方便多了。）当您了解流程控制语句后会看到更多的例子。  

## Boolean Operators
## 布尔运算符

The three Boolean operators (and, or, and not) are used to compare Boolean values. Like comparison operators, they evaluate these expressions down to a Boolean value. Let’s explore these operators in detail, starting with the and operator.  
三个布尔运算符（与，或，非）用于比较的布尔值。像比较运算符一样，他们计算表达式的值直到得到一个布尔值。让我们首先从与运算符开始来探究这些运算符。  

## Binary Boolean Operators
## 二元布尔运算符

The and and or operators always take two Boolean values (or expressions), so they’re considered binary operators. The and operator evaluates an expression to True if both Boolean values are True; otherwise, it evaluates to False. Enter some expressions using and into the interactive shell to see it in action.  
与和或运算符通常有两个布尔值或表达式，因此我们把它们成为二元运算符。如果两个布尔值是True的值进行和运算后结果为True，反之为False.在交互式窗口输入以下的表达式看看他们的运算结果。  

	>>> True and True
	True
	>>> True and False
	False

A truth table shows every possible result of a Boolean operator. Table 2-2 is the truth table for the and operator.
与运算符的真值表显示了布尔逻辑运算符的每一个可能的结果。表2-2是与运算符的真值表。  
Table 2-2. The and Operator’s Truth Table  

|Expression|Evaluates to|
|----------|------------|
|True and True|True|
|True and False|False|
|False and True|False|
|False and False|False|

On the other hand, the or operator evaluates an expression to True if either of the two Boolean values is True. If both are False, it evaluates to False
另一方面，如果两个布尔值其中一个为True则或运算符计算表达式值为True。如果两个都是假的，它的计算结果为False。 

You can see every possible outcome of the or operator in its truth table, shown in Table 2-3.   
如表2-3所示你可以看到在或运算符的每一个可能的结果。  
Table 2-3. The or Operator’s Truth Table  

|Expression|Evaluates to|
|----------|------------|
|True and True|True|
|True and False|True|
|False and True|True|
|False and False|False|

## The not Operator
## NOT运算符
Unlike and and or, the not operator operates on only one Boolean value (or expression). The not operator simply evaluates to the opposite Boolean value.  
和与和或表达式不同，非运算符运行在只有一个布尔值（或表达式）。非运算符计算结果为相反的布尔值。  

	>>> not True
	False
	>>> not not not not True    # (1)
	True
	
Much like using double negatives in speech and writing, you can nest not operators ➊, though there’s never not no reason to do this in real programs. Table 2-4 shows the truth table for not.  
（1）就像在语言和写作中使用双重否定，可以多次使用非表达式，虽然实际程序很少这样实现。表2-4显示了非运算符的真值表。  
Table 2-4. The not Operator’s Truth Table   

|Expression|Evaluates to|
|----------|------------|
|not True|False|
|not False|True|

## Mixing Boolean and Comparison Operators
##　混合布尔和比较运算符

Since the comparison operators evaluate to Boolean values, you can use them in expressions with the Boolean operators.Recall that the and, or, and not operators are called Boolean operators because they always operate on the Boolean values True and False. While expressions like 4 < 5 aren’t Boolean values, they are expressions that evaluate down to Boolean values. Try entering some Boolean expressions that use comparison operators into the interactive shell.　　　　
由于比较运算符计算结果为布尔值，你可以在表达式中使用布尔运算符。因为与，或，非的值总是布尔值的True和false，所以我们们把他们成为布尔运算符。就像表达式4<5，虽然不是布尔值，但是表达式的运算结果会获得一个布尔值。在交互窗口输入以下使用比较操作符的布尔运算式。

	>>> (4 < 5) and (5 < 6)
	True
	>>> (4 < 5) and (9 < 6)
	False
	>>> (1 == 2) or (2 == 2)
	True
	>>> 
	
The computer will evaluate the left expression first, and then it will evaluate the right expression. When it knows the Boolean value for each, it will then evaluate the whole expression down to one Boolean value. You can think of the computer’s evaluation process for (4 < 5) and (5 < 6) as shown in Figure 2-2.  
You can also use multiple Boolean operators in an expression, along with the comparison operators.  
计算机将会从左到右依次计算表达式的值。当得到每一个表达式的布尔值后，它计算评估整个表达式直到获得一个布尔值。你可以思考下计算机计算(4 < 5) and (5 < 6)的过程，如图 Figure2-2.您也可以在表达式中使用多个布尔运算符和比较运算符.

	>>> 2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2
	True
	
The Boolean operators have an order of operations just like the math operators do. After any math and comparison operators evaluate, Python evaluates the not operators first, then the and operators, and then the or operators.  
布尔运算符的操作顺序就像数学运算。先经进行各种数学运算和比较运算，Python的计算结果首先是非运算符，然后是和运算符，最后是或运算符。  

####   Figure2-2  
![Figure 2-2](https://automatetheboringstuff.com/images/000023.jpg)

## Elements of Flow Control
## 流程控制的原理

Flow control statements often start with a part called the condition, and all are followed by a block of code called the clause. Before you learn about Python’s specific flow control statements, I’ll cover what a condition and a block are.  
流程控制语句开始部分我们称为条件，后面跟着一个代码块叫做子句。在你学习Python的具体流程控制语句前，我将介绍什么是条件和什么是代码块。  

### Conditions
### 条件

The Boolean expressions you’ve seen so far could all be considered conditions, which are the same thing as expressions; condition is just a more specific name in the context of flow control statements. Conditions always evaluate down to a Boolean value, True or False. A flow control statement decides what to do based on whether its condition is True or False, and almost every flow control statement uses a condition.  
到目前为止我们在布尔表达式中考虑到的各种情况都是相同的表达式。条件只是在流程控制语句中更具体的名称而已。条件运算的结果最终为一个布尔值，真或假。而这几乎是每一个流量控制语句使用的条件。  

### Blocks of Code
### 代码块

Lines of Python code can be grouped together in blocks. You can tell when a block begins and ends from the indentation of the lines of code. There are three rules for blocks.  

-Blocks begin when the indentation increases.  
-Blocks can contain other blocks.  
-Blocks end when the indentation decreases to zero or to a containing block’s indentation.

Blocks are easier to understand by looking at some indented code, so let’s find the blocks in part of a small game program, shown here:  
Python代码行可以一起组成一个块。通过代码的缩进你可以知道每一个代码块的开始和结束。这里有针对代码分块的三个规则。

-缩进增加代表代码块开始。  
-代码块可以在其他代码块中间。
-当缩进减少到零或者遇到另一个代码块的缩进时代码块结束。  

通过观察代码缩进很容易理解代码块。让我们在下面这个小游戏代码中来寻找代码块吧。  

	name = 'Mary'
	password = 'swordfish'
	if name == 'Mary':
		print('Hello Mary')
		if password == 'swordfish':
			print('Access granted.')
		else:
			print('Wrong password.')
  
The first block of code starts at the line print('Hello Mary') and contains all the lines after it. Inside this block is another block , which has only a single line in it: print('Access Granted.'). The third block is also one line long: print('Wrong password.').  
第一个代码块开始于行print('Hello Marry')并且包含后面所有的部分。在这个代码块里面有另外一个代码块，仅仅包含一行代码：print('Access Granted').第三个代码块也仅仅有一行代码长：print('Wrong password').  

### Program Execution
### 程序执行

In the previous chapter’s hello.py program, Python started executing instructions at the top of the program going down, one after another. The program execution (or simply, execution) is a term for the current instruction being executed. If you print the source code on paper and put your finger on each line as it is executed, you can think of your finger as the program execution.  
在前面的章节中的hello.py程序，python开始执行的时候是从程序的第一行开始一直往下，一行接一行。程序执行（或简单地说，执行）是用于当前指令正在执行的一个术语。如果您在纸张上打印的源代码，把你手指过程序的每一行当着执行，你可以把你的手指作为程序执行。  
Not all programs execute by simply going straight down, however. If you use your finger to trace through a program with flow control statements, you’ll likely find yourself jumping around the source code based on conditions, and you’ll probably skip entire clauses.  
但并不是所有的程序都是这样简单从头到尾按顺序执行。如果你用你的手指跟随流程控制语句执行程序，你会发现你需要根据条件跳来跳去，有时候还会跳过整个子句。  

## Flow Control Statements
## 流控制语句
## [相关视频教程](https://youtu.be/lWeCgEbk-Ro)

Now, let’s explore the most important piece of flow control: the statements themselves. The statements represent the diamonds you saw in the flowchart in Figure 2-1, and they are the actual decisions your programs will make.  
现在，让我们来探索流程控制最重要的部分：该语句本身。该声明标识你在图2-1中看到的流程图中的钻石图形部分，他们将决定你程序如何运行。  

### if Statements
### if 语句

The most common type of flow control statement is the if statement. An if statement’s clause (that is, the block following the if statement) will execute if the statement’s condition is True. The clause is skipped if the condition is False.  
if语句是流程控制语句中最常见的类型。if语句的子句（也就是指if语句下面的程序块）将被执行，如果该if语句的条件为True。如果if条件的结果为False该子句被跳过.  
In plain English, an if statement could be read as, “If this condition is true, execute the code in the clause.” In Python, an if statement consists of the following:  
用简单的英语，if语句可以理解为，“如果这个条件为真，则执行该子句中的代码。” 在python中if语句包含以下内容：  

- The if keyword
- A condition (that is, an expression that evaluates to True or False)
- A colon
- Starting on the next line, an indented block of code (called the if clause)  

- if关键字
- 条件（也就是说，计算结果为真或假的表达式)
- 冒号
- 另起一行并且包含缩进的代码块(称为if子句)  

For example, let’s say you have some code that checks to see whether someone’s name is Alice. (Pretend name was assigned some value earlier.)  
例如，我们有一段用来检测别人的名字是否为Alice的代码。（假设名字提前赋值在一个变量中）  

	if name == 'Alice':
		print('Hi, Alice.')

All flow control statements end with a colon and are followed by a new block of code (the clause). This if statement’s clause is the block with print('Hi, Alice.'). Figure 2-3 shows what a flowchart of this code would look like.  
所有的流程控制语句都以冒号结束后面跟随一个新的代码块（子句）。这if语句的子句是代码块print('Hi,Alice').图2-3显示了此代码的流程图的样子。  

![Figure 2-3](https://automatetheboringstuff.com/images/000019.jpg)
> Figure 2-3. The flowchart for an if statement  

### else Statements
### else语句

An if clause can optionally be followed by an else statement. The else clause is executed only when the if statement’s condition is False. In plain English, an else statement could be read as, “If this condition is true, execute this code. Or else, execute that code.” An else statement doesn’t have a condition, and in code, an else statement always consists of the following:  

-The else keyword  
-A colon
-Starting on the next line, an indented block of code (called the else clause)  

Returning to the Alice example, let’s look at some code that uses an else statement to offer a different greeting if the person’s name isn’t Alice.  
一个if语句后面可跟着一个else语句。当if语句的条件为假else子句被执行。用简单的英语，一个else语句可以理解为，“如果这个条件为真，执行该代码。否则，执行其他代码“。else语句没有具体条件。在代码中，else语句以下面方式表示：  
- else关键字
- 一个冒号
- 另起一行并且包含缩进的代码块(称为else子句)

让我们回到Alice的例子，让我们来看看如果这个人的名字不是Alice使用else语句来提供不同的问候语的代码。

	name = 'Bob'
	if name == 'Alice':
		print('Hi, Alice.')
	else:
		print('Hello, stranger.')
		
Figure 2-4 shows what a flowchart of this code would look like.
图2-4显示了此代码的流程图的样子。
![Figure 2-4](https://automatetheboringstuff.com/images/000106.png)
> Figure 2-4. The flowchart for an else statement

### elif Statements
### ELIF语句

While only one of the if or else clauses will execute, you may have a case where you want one of many possible clauses to execute. The elif statement is an “else if” statement that always follows an if or another elif statement. It provides another condition that is checked only if any of the previous conditions were False. In code, an elif statement always consists of the following:  

- The elif keyword  
- A condition (that is, an expression that evaluates to True or False)
- A colon
- Starting on the next line, an indented block of code (called the elif clause)

Let’s add an elif to the name checker to see this statement in action.  
虽然仅有一个if或else就能执行，但是有的情况下可能有多个不同子句需要执行。elif语句，就是一个“else is”语句,始终跟随if语句或其他elif语句。当任何前面的所有条件都是假时它提供另一个条件进行判断。在代码中，else语句以下面方式表示：  

- elif关键字
- 一个条件（也就是，计算结果为真或假的表达式）
- 一个冒号
- 另起一行并且包含缩进的代码块(称为elif子句)

让我们把elif加到名字检查例程中看看这个语句如何执行。  

	name = 'Bob'
	age = 5
	if name == 'Alice':
		print('Hi, Alice.')
	elif age < 12:
		print('You are not Alice, kiddo.')
		
This time, you check the person’s age, and the program will tell them something different if they’re younger than 12. You can see the flowchart for this in Figure 2-5.  
这次，你检查人的年龄，如果他们小于12岁程序会告诉他们不同的东西。程序执行流程图 如图2-5
![Figure](https://automatetheboringstuff.com/images/000107.png)
> Figure 2-5. The flowchart for an elif statement

The elif clause executes if age < 12 is True and name == 'Alice' is False. However, if both of the conditions are False, then both of the clauses are skipped. It is not guaranteed that at least one of the clauses will be executed. When there is a chain of elif statements, only one or none of the clauses will be executed. Once one of the statements’ conditions is found to be True, the rest of the elif clauses are automatically skipped. For example, open a new file editor window and enter the following code, saving it as vampire.py:  
如果年龄小于12是真并且名字是Alice为假elif语句将会执行。如果这两个条件的结果都是假的，则这两个子句都会跳过。它并不保证所有子句中的至少一个将被执行。存在多个elif语句的程序中，只有一个或没有子句被执行。一旦这些语句的条件之一被发现是真，其余elif子句将被自动跳过。例如，打开一个新的文件编辑器窗口输入以下代码，保存为vampire.py：

	name = 'Dracula'
	age = 4000
	if name == 'Alice':
		print('Hi, Alice.')
	elif age < 12:
		print('You are not Alice, kiddo.')
	elif age > 2000:
		print('Unlike you, Alice is not an undead, immortal vampire.')
	elif age > 100:
    print('You are not Alice, grannie.')
	
Here I’ve added two more elif statements to make the name checker greet a person with different answers based on age. Figure 2-6 shows the flowchart for this.  
在这里，我增加了两个ELIF语句，以使名称检查同时基于年龄给不同的人不同的答案。图2-6显示了该流程图。
![Figure 2-6](https://automatetheboringstuff.com/images/000088.png)
> Figure 2-6. The flowchart for multiple elif statements in the vampire.py program

The order of the elif statements does matter, however. Let’s rearrange them to introduce a bug. Remember that the rest of the elif clauses are automatically skipped once a True condition has been found, so if you swap around some of the clauses in vampire.py, you run into a problem. Change the code to look like the following, and save it as vampire2.py:  
elif语句按照顺序完成事物。让我们重新排列它们引入的错误。请记住，elif子句发现一次条件为真时其余部分自动跳过。如果你在vampire2.py中换一些子句你会运行遇到错误。把你的代码改成下面的样子并保存为vampire2.py：  

	name = 'Dracula'
	age = 4000
	if name == 'Alice':
		print('Hi, Alice.')
	elif age < 12:
		print('You are not Alice, kiddo.')
	elif age > 100:
		print('You are not Alice, grannie.')
	elif age > 2000:
		print('Unlike you, Alice is not an undead, immortal vampire.')
		
Say the age variable contains the value 3000 before this code is executed. You might expect the code to print the string 'Unlike you, Alice is not an undead, immortal vampire.'. However, because the age > 100 condition is True (after all, 3000 is greater than 100) , the string 'You are not Alice, grannie.' is printed, and the rest of the elif statements are automatically skipped. Remember, at most only one of the clauses will be executed, and for elif statements, the order matters!   
假设代码执行之前把变量age赋值为3000。你期望代码输出'Unlike you, Alice is not an undead, immortal vampire.'.。但是age >100已经为真了。（尽管3000比100大很多），'You are not Alice, grannie.'被打印出来，剩下的elif语句都被跳过了。对于elif语句来说最多只有一个子句被执行这是确信无疑的事实。  

Figure 2-7 shows the flowchart for the previous code. Notice how the diamonds for age > 100 and age > 2000 are swapped.  
图2-7显示了前面的代码的流程图。请注意age > 100和age > 2000流程图的交换。  
![Figure 2-7](https://automatetheboringstuff.com/images/000089.png)
> Figure 2-7. The flowchart for the vampire2.py program. The crossed-out path will logically never happen, because if age were greater than 2000, it would have already been greater than 100.  
> 图2-7为vampire2.py程序的流程图。打叉的路径逻辑永远不会发生，因为如果年龄超过2000人时，它早已经大于100。  

Optionally, you can have an else statement after the last elif statement. In that case, it is guaranteed that at least one (and only one) of the clauses will be executed. If the conditions in every if and elif statement are False, then the else clause is executed. For example, let’s re-create the Alice program to use if, elif, and else clauses.    
你可以有在所有elif语句后面else语句。
在这种情况下，可以保证子句中的至少一个（并且仅一个）将被执行。如果所有if和elif的语句的条件都是假的，那么else子句被执行。例如，让我们重新创建一个使用if,elif和else子句的Alice程序。  

	name = 'Bob'
	age = 30
	if name == 'Alice':
		print('Hi, Alice.')
	elif age < 12:
		print('You are not Alice, kiddo.')
	else:
		print('You are neither Alice nor a little kid.')
		
Figure 2-8 shows the flowchart for this new code, which we’ll save as littleKid.py.  
图2-8展示了这个新的代码的流程图，我们将其保存为littleKid.py。  
In plain English, this type of flow control structure would be, “If the first condition is true, do this. Else, if the second condition is true, do that. Otherwise, do something else.” When you use all three of these statements together, remember these rules about how to order them to avoid bugs like the one in Figure 2-7. First, there is always exactly one if statement. Any elif statements you need should follow the if statement. Second, if you want to be sure that at least one clause is executed, close the structure with an else statement.   
简单的说，这种类型的流程控制结构是，“如果第一个条件为真，执行它。否则，如果第二条件为真，执行这个。否则，执行其他的事情。“当您同时使用这三个语句，记住以下的规则以避免出现图2-7中的bug。首先，总共只有一个if语句。任何 elif语句都在if语句后面。第二，如果你要确保至少有一个子句被执行，需要在代码块最后以else语句结束。  
![Figure 2-8](https://automatetheboringstuff.com/images/000090.png)
> Figure 2-8. Flowchart for the previous littleKid.py program

### while Loop Statements
### while循环语句
### [相关视频教学](https://youtu.be/885qKiiKisI)

You can make a block of code execute over and over again with a while statement. The code in a while clause will be executed as long as the while statement’s condition is True. In code, a while statement always consists of the following:  

- The while keyword  
- A condition (that is, an expression that evaluates to True or False) 
- A colon
- Starting on the next line, an indented block of code (called the while clause)

你可以通过while语句让一个代码块不停的来回执行。当while语句的条件为真while语句中的代码会一直不停的执行。在代码中whlie语句通过下面的形式表示：  

- whlie关键字
- 一个条件(也就是一个结果为真或假的表达式)
- 一个冒号
- 另起一行并且包含缩进的代码块(称为while子句)

You can see that a while statement looks similar to an if statement. The difference is in how they behave. At the end of an if clause, the program execution continues after the if statement. But at the end of a while clause, the program execution jumps back to the start of the while statement. The while clause is often called the while loop or just the loop.  
你会发现while语句和if语句很像。他们的区别在于执行方式不同，if语句结束后程序将继续往下执行。但是在while语句执行到结尾后又会跳到while语句的起始处继续执行。while语句通常被称为while循环或循环。  
Let’s look at an if statement and a while loop that use the same condition and take the same actions based on that condition. Here is the code with an if statement:    
让我们看一个使用相同条件的if语句和while循环语句执行后的结果。下面是if语句的代码：  

	spam = 0
	if spam < 5:
		print('Hello, world.')
		spam = spam + 1
		
Here is the code with a while statement:  
这里是while语句的代码：  

	spam = 0
	while spam < 5:
		print('Hello, world.')
		spam = spam + 1
		
These statements are similar—both if and while check the value of spam, and if it’s less than five, they print a message. But when you run these two code snippets, something very different happens for each one. For the if statement, the output is simply "Hello, world.". But for the while statement, it’s "Hello, world." repeated five times! Take a look at the flowcharts for these two pieces of code, Figure 2-9 and Figure 2-10, to see why this happens.  
这些语句都是相似的，if语句和while语句都是检查spam值，如果小于五，就打印一个信息。但是，当你运行这两个代码片段后有非常不同的输出结果。if语句的输出结果只有一个"Hello, world."，=。但是while语句的输出有五个"Hello, world." 让我们从图2-9个图2-10的流程图开看看这两个代码片段执行时发生了什么。
![图2-9](https://automatetheboringstuff.com/images/000091.png)
> Figure 2-9. The flowchart for the if statement code  
![图2-10](https://automatetheboringstuff.com/images/000094.png)
> Figure 2-10. The flowchart for the while statement code  
The code with the if statement checks the condition, and it prints Hello, world. only once if that condition is true. The code with the while loop, on the other hand, will print it five times. It stops after five prints because the integer in spam is incremented by one at the end of each loop iteration, which means that the loop will execute five times before spam < 5 is False.  
if语句代码检查条件并打印的Hello，world。只有一次如果该条件为真。另一方面while循环则打印了五次。它在执行五次打印后停止了是因为spam的整数值被后面的循环每次加1，这就意味着循环在spam < 5 为假之前执行了五次。  
In the while loop, the condition is always checked at the start of each iteration (that is, each time the loop is executed). If the condition is True, then the clause is executed, and afterward, the condition is checked again. The first time the condition is found to be False, the while clause is skipped.  
在while循环中，条件始终在每次执行开始检查（即，每次执行循环时）。如果条件为真，则该子句被执行，后来，条件再次检查。第一次发现条件为假，while子句跳出。  

### An Annoying while Loop
### 一个恼人的while循环

Here’s a small example program that will keep asking you to type, literally, your name. Select File▸New File to open a new file editor window, enter the following code, and save the file as yourName.py: (Click "Run" to begin the program.)  
这里有一个小程序，从字面上看是要求您输入你的名字。选择File-New文件打开一个新的文件编辑器窗口，输入以下代码，并保存文件为yourName.py： （点击“运行”开始程序）。  

	name = ''                           # (1)
	while name != 'your name':          # (2)
		print('Please type your name.')
		name = input()                  # (3)
	print('Thank you!')                 # (4)
	
First, the program sets the name variable (1) to an empty string. This is so that the name != 'your name' condition will evaluate to True and the program execution will enter the while loop’s clause (2).  
最初程序将变量name赋值为空(1)。这就是说the name != 'your name'这个条件是成立的程序将执行进入循环(2)。
The code inside this clause asks the user to type their name, which is assigned to the name variable (3). Since this is the last line of the block, the execution moves back to the start of the while loop and reevaluates the condition. If the value in name is not equal to the string 'your name', then the condition is True, and the execution enters the while clause again.  
程序代码要求用户输入他们的名字并将输入值传递给变量name(3)。由于这是该块的最后一行，执行移回到循环开始处并重新评估条件。如果变量name的值不等于字符串'Your name',条件成立，程序执行再次进入循环。  
But once the user types your name, the condition of the while loop will be 'your name' != 'your name', which evaluates to False. The condition is now False, and instead of the program execution reentering the while loop’s clause, it skips past it and continues running the rest of the program (4). Figure 2-11 shows a flowchart for the yourName.py program.  
但是，一旦用户输入'Your name'，while循环的条件“Your name”！=“Your name”的值为False.现在条件是假,
程序执行不会重新进入while循环的子句，它会跳过过去，并继续运行该程序的其余部分(4).图2-11显示了程序yourName.py的流程图。  
![图2-11](https://automatetheboringstuff.com/images/000097.png)
> Figure 2-11. A flowchart of the yourName.py program
Now, let’s see yourName.py in action. Press F5 to run it, and enter something other than your name a few times before you give the program what it wants.  
现在，我们来看看yourName.py如何运行。按F5键运行，在输入程序需要的值'Your name'之前输入几次非'Your name'值.  

	Please type your name.
	Al
	Please type your name.
	Albert
	Please type your name.
	%#@#%*(^&!!!
	Please type your name.
	your name
	Thank you!

If you never enter your name, then the while loop’s condition will never be False, and the program will just keep asking forever. Here, the input() call lets the user enter the right string to make the program move on. In other programs, the condition might never actually change, and that can be a problem. Let’s look at how you can break out of a while loop.  
如果一直不输入‘Your name‘，while循环的条件将永远不会是假。
程序将一直运行并永远问你的名字。这里，input()函数调用让用户输入正确的字符串，使程序继续运行。在其他程序中，条件可能永远不会改变，这可能会造成问题。让我们来看看如何跳出whlie循环。  

### break Statements
### 跳出语句

There is a shortcut to getting the program execution to break out of a while loop’s clause early. If the execution reaches a break statement, it immediately exits the while loop’s clause. In code, a break statement simply contains the break keyword.  
这里有一个快捷方式让程序执行提前跳出while循环的条款。如果执行到break语句，它会立即退出while循环。在代码中，break语句只包含关键字break。  
Pretty simple, right? Here’s a program that does the same thing as the previous program, but it uses a break statement to escape the loop. Enter the following code, and save the file as yourName2.py:  
很简单，不是吗？下面的程序与前面的程序是做同样的事情，但它使用了一个break语句跳出循环。输入以下代码，并保存文件为yourName2.py：  

	while True:                         # (1)
		print('Please type your name.')
		name = input()                  # (2)
		if name == 'your name':         # (3)
			break                       # (4)
	print('Thank you!')                 # (5)

The first line (1) creates an infinite loop; it is a while loop whose condition is always True. (The expression True, after all, always evaluates down to the value True.) The program execution will always enter the loop and will exit it only when a break statement is executed. (An infinite loop that never exits is a common programming bug.)  
第一行(1)创建了一个无限循环;它是一个条件总是为真的while循环。（表达式为真，计算结果也就永远为真）。该程序的执行将始终进入循环，仅在执行break语句时才能退出。（永远不会退出的无限循环是常见的​​编程错误。）  
Just like before, this program asks the user to type your name (2). Now, however, while the execution is still inside the while loop, an if statement gets executed (3) to check whether name is equal to your name. If this condition is True, the break statement is run(4), and the execution moves out of the loop to print('Thank you!') (5). Otherwise, the if statement’s clause with the break statement is skipped, which puts the execution at the end of the while loop. At this point, the program execution jumps back to the start of the while statement (6) to recheck the condition. Since this condition is merely the True Boolean value, the execution enters the loop to ask the user to type your name again. See Figure 2-12 for the flowchart of this program.  
和之前一样，这个程序要求用户输入Your name（2）。然而，while循环一直在循环内部执行中，if语句用来检查'name'是否等于'Your name'。一旦条件为真，break语句被执行，程序跳出循环并打印‘Thank you!’(5).否则，if语句与break语句子句被跳过，这使的程序执行到while循环的结束。在这个点，程序跳转到whlie循环的开始处并重新检查条件是否成立。由于条件仅仅是布尔值真，程序执行进入循环再次要求用户输入名称。图2-12显示了这个程序的流程图。  
Run yourName2.py, and enter the same text you entered for yourName.py. The rewritten program should respond in the same way as the original.
运行程序yourName2.py，并输入你在运行yourName.py时相同的文字。
这个重写的程序响应方式和之前的一致。  
![图2-12](https://automatetheboringstuff.com/images/000099.jpg)
> Figure 2-12. The flowchart for the yourName2.py program with an infinite loop. Note that the X path will logically never happen because the loop condition is always True.
> 图2-12 YourName2.py无限循环程序的流程图。由于循环的条件总是为真所以X路径永远不会发生。

### continue Statements
### 继续语句

Like break statements, continue statements are used inside loops. When the program execution reaches a continue statement, the program execution immediately jumps back to the start of the loop and reevaluates the loop’s condition. (This is also what happens when the execution reaches the end of the loop.)  
像跳出语句一样，继续语句也在循环内部使用。当程序执行到继续语句，程序执行立即跳回循环开始处并重新检查循环的条件。这也是程序执行到达循环结束时会发生的动作。  

#### TRAPPED IN AN INFINITE LOOP?
#### 被困在一个无限循环中怎么办？
If you ever run a program that has a bug causing it to get stuck in an infinite loop, press CTRL-C. This will send a KeyboardInterrupt error to your program and cause it to stop immediately. To try it, create a simple infinite loop in the file editor, and save it as infiniteloop.py.   
如果你运行一个有错误的程序导致其被卡在一个无限循环中，可以按下CTRL-C退出。这将发送一个KeyboardInterrupt错误的信息给你的程序并让其立即停止。尝试在文件编辑器中写一个简单的无限循环，并将其保存为infiniteloop.py。   

	while True:
		print('Hello world!')
	
When you run this program, it will print Hello world! to the screen forever, because the while statement’s condition is always True. In IDLE’s interactive shell window, there are only two ways to stop this program: press CTRL-C or select Shell>restart Shell from the menu. CTRL-C is handy if you ever want to terminate your program immediately, even if it’s not stuck in an infinite loop.  
当你运行这个程序的时候会一直不停份的打印Hello world!到屏幕上，因为循环的条件永远为真。在IDLE交互窗体中这里有两个办法停止程序运行：按下CTRL-C或从窗体菜单中选择Shell>restart。如果你想立即终止你的程序CTRL-C是最方便的，即使它不是在一个无限循环中。  

Let’s use continue to write a program that asks for a name and password. Enter the following code into a new file editor window and save the program as swordfish.py.  
让我们用继续语句写一个程序，要求输入用户名和密码。输入以下代码到一个新的文件编辑器窗口，并保存为swordfish.py  

	while True:
	  print('Who are you?')
	  name = input()
	  if name != 'Joe':       #(1)
		continue              #(2)
	  print('Hello, Joe. What is the password? (It is a fish.)') 
	  password = input()      #(3)
	  if password == 'swordfish':
		break                 #(4)
	print('Access granted.')  #(5)
	
If the user enters any name besides Joe(1) , the continue statement (2) causes the program execution to jump back to the start of the loop. When it reevaluates the condition, the execution will always enter the loop, since the condition is simply the value True. Once they make it past that if statement, the user is asked for a password (3). If the password entered is swordfish, then the break statement (4) is run, and the execution jumps out of the while loop to print Access granted (5). Otherwise, the execution continues to the end of the while loop, where it then jumps back to the start of the loop. See Figure 2-13 for this program’s flowchart.  
如果用户输入的名字不是Joe(1),继续语句让程序跳转到循环开始位置(2)。因为条件是简单的值Ture，当检查循环的条件时循环条件成立，程序再次进入循环。一旦if语句为False跳过继续语句程序执行询问密码。如果输入密码是swordfish，跳出语句(4)执行。程序跳出循环打印Access granted (5)。另一方面如果密码不是swordfish程序执行到whlie循环结尾，在这里又会跳转到循环开始位置。图2-13显示了这个程序的流程图。  
![图2-13](https://automatetheboringstuff.com/images/000100.jpg)
> Figure 2-13. A flowchart for swordfish.py. The X path will logically never happen because the loop condition is always True.
> 图2-13。swordfish.py的流程图。在逻辑上不会发生X路径，因为循环条件始终为true。

#### “TRUTHY” AND “FALSEY” VALUES
#### 非布尔类型真和假值
There are some values in other data types that conditions will consider equivalent to True and False. When used in conditions, 0, 0.0, and '' (the empty string) are considered False, while all other values are considered True. For example, look at the following program:   
还有其他数据类型的一些值作为条件会当成等同真和假。当条件是0，0.0，和‘’(空字符串)会被当成False,而所有其他值被认为是真。例如下面的程序：

	name = ''
	while not name: #(1)
		print('Enter your name:')
		name = input()
	print('How many guests will you have?')
	numOfGuests = int(input())
	if numOfGuests: #(2)
		print('Be sure to have enough room for all your guests.') #(3)
	print('Done')

If the user enters a blank string for name, then the while statement’s condition will be True (1), and the program continues to ask for a name. If the value for numOfGuests is not 0 (2), then the condition is considered to be True, and the program will print a reminder for the user (3).  
如果用户输入的名称空字符串，while语句的条件将是True(1)，并继续问名称。如果numOfGuests的值不是0(2)，则条件被认为是真，程序将打印提醒用户(3)  
You could have typed not name != '' instead of not name, and numOfGuests != 0 instead of numOfGuests, but using the truthy and falsey values can make your code easier to read.  
你可以键入not name ！=''，代替not name，并用numOfGuests！= 0代替numOfGuests，但是用非布尔类型真值和假值可以使你的代码更易于阅读。  

Run this program and give it some input. Until you claim to be Joe, it shouldn’t ask for a password, and once you enter the correct password, it should exit.   
运行此程序，并给它一些输入。直到你输入是Joe，它才会要求输入密码，一旦你输入正确的密码，程序应该退出。  

	Who are you?
	I'm fine, thanks. Who are you?
	Who are you?
	Joe
	Hello, Joe. What is the password? (It is a fish.)
	Mary
	Who are you?
	Joe
	Hello, Joe. What is the password? (It is a fish.)
	swordfish
	Access granted.

## for Loops and the range() Function
## for循环和range（）函数
## [相关教学视频](https://youtu.be/HFQGxh1jY3g)

The while loop keeps looping while its condition is True (which is the reason for its name), but what if you want to execute a block of code only a certain number of times? You can do this with a for loop statement and the range() function.  
In code, a for statement looks something like for i in range(5): and always includes the following:

- The for keyword
- A variable name
- The in keyword
- A call to the range() method with up to three integers passed to it
- A colon
- Starting on the next line, an indented block of code (called the for clause)

Let’s create a new program called fiveTimes.py to help you see a for loop in action.  
while循环但其条件为真时不断循环（这也是它的名字叫whlie的原因），但是如果你要代码块执行一定次数怎么办？你可以使用for循环和range（）函数。在代码中for循环看起来像这样for i in range(5):并且总是包含以下内容：

- for关键字
- 一个变量名
- in关键字
- 一个最多包含三个参数的range()函数调用方法
- 一个冒号
- 另起一行并且包含缩进的代码块（我们称为for子句）

让我们创建一个叫fiveTimes.py的新程序来帮子理解for循环。

	print('My name is')
	for i in range(5):
		print('Jimmy Five Times (' + str(i) + ')')

The code in the for loop’s clause is run five times. The first time it is run, the variable i is set to 0. The print() call in the clause will print Jimmy Five Times (0). After Python finishes an iteration through all the code inside the for loop’s clause, the execution goes back to the top of the loop, and the for statement increments i by one. This is why range(5) results in five iterations through the clause, with i being set to 0, then 1, then 2, then 3, and then 4. The variable i will go up to, but will not include, the integer passed to range(). Figure 2-14 shows a flowchart for the fiveTimes.py program.  
代码在for循环中运行了五次。第一次运行的时候变量i值为0.print()函数调用打印内容为Jimmy Five Times (0)。Python完成内部所有代码循环的子句后，执行返回到循环的顶部，for语句将i的值加1。这就是为什么range(5)通过参数5可以进行五次循环，其中i被设置为0，然后1，然后2，然后3，然后4。变量i会自增加但不包含range()参数定义的整数。图2-14显示了这个程序的流程图。
![图2-14](https://automatetheboringstuff.com/images/000102.png)
> Figure 2-14. The flowchart for fiveTimes.py
When you run this program, it should print Jimmy Five Times followed by the value of i five times before leaving the for loop.   
当你运行这个程序，它应该打印Jimmy五次加上i的离开循环前的5个值。

	My name is
	Jimmy Five Times (0)
	Jimmy Five Times (1)
	Jimmy Five Times (2)
	Jimmy Five Times (3)
	Jimmy Five Times (4)

#### NOTE
You can use break and continue statements inside for loops as well. The continue statement will continue to the next value of the for loop’s counter, as if the program execution had reached the end of the loop and returned to the start. In fact, you can use continue and break statements only inside while and for loops. If you try to use these statements elsewhere, Python will give you an error.  
你也可以在for循环中使用中断和继续语句。继续语句会从for循环计数器的下一个值开始，如果程序执行已经达到循环的结尾将返回到开始处。事实上，你仅可以在while和for循环语句内部使用中断和继续语句。如果试图在其他地方使用这些语句，Python将会报错。  
As another for loop example, consider this story about the mathematician Karl Friedrich Gauss. When Gauss was a boy, a teacher wanted to give the class some busywork. The teacher told them to add up all the numbers from 0 to 100. Young Gauss came up with a clever trick to figure out the answer in a few seconds, but you can write a Python program with a for loop to do this calculation for you.  
再举一个for循环例如，考虑数学家卡尔·弗里德里希·高斯的故事。当他还是一个小男孩的时候，他的老师给在班上布置了个非常麻烦的作业。年轻的高斯想出了一个很聪明的方法在几秒钟内给出答案，但你可以写一个有for循环的Python程序为你做这个计算。  

	total = 0               #(1)
	for num in range(101):  #(2)
	   total = total + num  #(3)
	print(total)            #(4)

The result should be 5,050. When the program first starts, the total variable is set to 0 (1). The for loop (2)then executes total = total + num (3) 100 times. By the time the loop has finished all of its 100 iterations, every integer from 0 to 100 will have been added to total. At this point, total is printed to the screen (4). Even on the slowest computers, this program takes less than a second to complete.
(Young Gauss figured out that there were 50 pairs of numbers that added up to 101: 1 + 100, 2 + 99, 3 + 98, 4 + 97, and so on, until 50 + 51. Since 50 × 101 is 5,050, the sum of all the numbers from 0 to 100 is 5,050. Clever kid!)  
结果应该是5050。当第一次启动该程序，变量total设置为0(1)。 for循环(2)执行 total=total + num (3) 100次。随着时间的推移for循环完成它的所有100次迭代，从0到100的每个整数将被添加到total。此时，total被输出到屏幕(4).即使在最慢的电脑，这个程序不到一秒钟即可完成。（高斯发现有50对数字的和加起来是101：1 + 100，2 + 99，3 + 98，4 + 97，依此类推，直到50 + 51总共50×101 5050，所有的数字从0到100的总和为5050。聪明的孩子！）  

### An Equivalent while Loop
### 一个等同whi​​le循环的循环

You can actually use a while loop to do the same thing as a for loop; for loops are just more concise. Let’s rewrite fiveTimes.py to use a while loop equivalent of a for loop.  
实际上，你可以使用一个while循环做同样的事情，作为for循环只是更简洁。让我们重写fiveTimes.py使用whil​​e循环来完成for循环同样的事情。  

	print('My name is')
	i = 0
	while i < 5:
		print('Jimmy Five Times (' + str(i) + ')')
		i = i + 1
		
If you run this program, the output should look the same as the fiveTimes.py program, which uses a for loop.  
如果你运行这个程序，输出应该和使用一个for循环的fiveTimes.py程序一样。  

## The Starting, Stopping, and Stepping Arguments to range()
## range()函数的启动，停止和步进参数

Some functions can be called with multiple arguments separated by a comma, and range() is one of them. This lets you change the integer passed to range() to follow any sequence of integers, including starting at a number other than zero.  
有些函数可以有多个用逗号分隔的参数。range()函数就是其中之一。这可以让你通过改变传递到range()范围内的整数，产生任何整数序列，包括从非零数字开始。  

	for i in range(12, 16):
		print(i)
		
	>>>12
	>>>13
	>>>14
	>>>15	
	
The first argument will be where the for loop’s variable starts, and the second argument will be up to, but not including, the number to stop at.  
第一个参数是代表for循环开始的变量值，第二个参数表示变量将达到的值，但不包括停止数字。  
The range() function can also be called with three arguments. The first two arguments will be the start and stop values, and the third will be the step argument. The step is the amount that the variable is increased by after each iteration.  
range()函数也可以用三个参数调用。前两个参数将是启动和停止值，第三个是步进值表示变量在每次迭代后增加量。  

	for i in range(0, 10, 2):
		print(i)
		
So calling range(0, 10, 2) will count from zero to eight by intervals of two.  
range(0，10，2)将以间隔2打印处从零到8的整数值。  

	0
	2
	4
	6
	8
	
The range() function is flexible in the sequence of numbers it produces for for loops. For example (I never apologize for my puns), you can even use a negative number for the step argument to make the for loop count down instead of up.    
用range()函数可以非常灵活的通过for循环参数数字序列。例如（我从来不会为我的双关语道歉），你甚至可以用一个负数做步进参数，使for循环逆向递减代替向上。  

	for i in range(5, -1, -1):
		print(i)

Running a for loop to print i with range(5, -1, -1) should print from five down to zero.  
运行这个程序将会打印出从5递减到0的几个数字。

	5
	4
	3
	2
	1
	0

## Importing Modules
## 导入模块
## [相关教学视频](https://youtu.be/xJLj6fWfw6k)

All Python programs can call a basic set of functions called built-in functions, including the print(), input(), and len() functions you’ve seen before. Python also comes with a set of modules called the standard library. Each module is a Python program that contains a related group of functions that can be embedded in your programs. For example, the math module has mathematics-related functions, the random module has random number–related functions, and so on.  
所有Python程序可以调用一些基本的函数,我们称为内置函数，包括以前见过print(), input(), and len()函数等.Python还带有一个称为标准库的模块组.每个模块是一个Python程序，它包含一组可以嵌入你程序的功能函数.
例如，数学运算模块具有数学相关的功能，随机数模块具有随机数产生相关功能，等等.  
Before you can use the functions in a module, you must import the module with an import statement. In code, an import statement consists of the following: 
 
- The import keyword
- The name of the module
- Optionally, more module names, as long as they are separated by commas

Once you import a module, you can use all the cool functions of that module. Let’s give it a try with the random module, which will give us access to the random.randint() function.  
Enter this code into the file editor, and save it as printRandom.py:  
在你使用模块中的功能之前，您必须使用导入语句导入模块。在代码中，导入语句包括以下内容:

- import关键字
- 模块的名字
- 可选，多个模块名，它们之前用逗号隔开

一旦你导入了一个模块，就可以使用该模块的酷功能。让我们试试随机模块，这将让我们获得了random.randint（）函数。将下面代码输入到文件编辑器，并保存为printRandom.py：  

	import random
	for i in range(5):
		print(random.randint(1, 10))

When you run this program, the output will look something like this:  
当米运行这个程序，输出会是这个样子：

	4
	1
	8
	4
	1
	
The random.randint() function call evaluates to a random integer value between the two integers that you pass it. Since randint() is in the random module, you must first type random. in front of the function name to tell Python to look for this function inside the random module   
该random.randint（）函数调用之后会给出你定义的两个整数之间的随机整数值。由于randint（）是随机模块中，您必须首先输入random.在函数前面的名字告诉Python寻找random模块内部此功能。  
Here’s an example of an import statement that imports four different modules:  
这里是导入4个不同模板的例子.  
	
	import random, sys, os, math
	
Now we can use any of the functions in these four modules. We’ll learn more about them later in the book.   
现在，我们使用这四个模块中的任何功能。在本书后面，我们将更多地了解他们.  

## from import Statements
## from import语句

An alternative form of the import statement is composed of the from keyword, followed by the module name, the import keyword, and a star; for example, from random import *.  
With this form of import statement, calls to functions in random will not need the random. prefix. However, using the full name makes for more readable code, so it is better to use the normal form of the import statement.  
import语句的另一种形式是由关键字from,跟随模块名称，关键字import *;例如，from random import *。  
用这种导入模块语句在random中调用函数不在需要书写random.但是，使用全称可以使得代码可读性更好，所以最好使用常规的import语句.  

## Ending a Program Early with sys.exit()
## 用sys.exit()函数提前结束程序

The last flow control concept to cover is how to terminate the program. This always happens if the program execution reaches the bottom of the instructions. However, you can cause the program to terminate, or exit, by calling the sys.exit() function. Since this function is in the sys module, you have to import sys before your program can use it.  
最后一个流程控制的概念讲述的是如何终止程序。如果程序执行到底部这总是会发生的。但是，您可以通过调用sys.exit（）函数使程序终止或退出。由于此功能是在sys模块中，你必须导入SYS模块你的程序才可以使用它.  
Open a new file editor window and enter the following code, saving it as exitExample.py:  
打开一个新的文件编辑器窗口，然后输入以下代码，将其保存为exitExample.py：  

	import sys

	while True:
		print('Type exit to exit.')
		response = input()
		if response == 'exit':
			sys.exit()
		print('You typed ' + response + '.')  


Run this program in IDLE. This program has an infinite loop with no break statement inside. The only way this program will end is if the user enters exit, causing sys.exit() to be called. When response is equal to exit, the program ends. Since the response variable is set by the input() function, the user must enter exit in order to stop the program.  
运行该程序。这个程序内部没有break语句会导致无限循环.终止程序的唯一方法是，如果用户输入exit将调用sys.exit（）当变量response等于字符串'exit'程序被终止.由于response变量是由input()函数来设置，用户必须输入exit使程序退出.  
### Summary
### 总结

By using expressions that evaluate to True or False (also called conditions), you can write programs that make decisions on what code to execute and what code to skip. You can also execute code over and over again in a loop while a certain condition evaluates to True. The break and continue statements are useful if you need to exit a loop or jump back to the start.  
These flow control statements will let you write much more intelligent programs. There’s another type of flow control that you can achieve by writing your own functions, which is the topic of the next chapter.  
通过计算结果为true或false（也称为条件）的表达式，你可以让程序决定哪些代码需要执行哪些代码需要跳过.您也可以在条件的计算结果为真时让代码一遍又一遍地循环执行。break和continue语句是非常有用的，如果你需要退出循环或跳转到循环开始.  
这些流程控制语句可以让你写出更智能的程序。你可以通过编写自己的函数实现另一种类型的流程控制，这是下一个章节的内容。  
