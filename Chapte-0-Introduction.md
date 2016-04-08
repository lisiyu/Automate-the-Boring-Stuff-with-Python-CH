##Introduction
##引言

“You’ve just done in two hours what it takes the three of us two days to do.” My college roommate was working at a retail electronics store in the early 2000s. Occasionally, the store would receive a spreadsheet of thousands of product prices from its competitor. A team of three employees would print the spreadsheet onto a thick stack of paper and split it among themselves. For each product price, they would look up their store’s price and note all the products that their competitors sold for less. It usually took a couple of days.

"我们三个人需要两天才能完成的工作，你两个小时就搞定了。"2000年那会儿，我的大学室友在一家电器零售店工作。有时候，这家商店会从竞争对手哪里获取一份包含成百上千产品价格的电子表格。一个由三个雇员组成的团队会把这个表格打印成厚厚的一摞纸，然后把它们平分给每个人。对于每一个产品，它们会去查看自己商店的价格，然后纪录所有竞争对手售价更低的产品。通常这需要花费几天的时间。

“You know, I could write a program to do that if you have the original file for the printouts,” my roommate told them, when he saw them sitting on the floor with papers scattered and stacked around them.
当看到他们坐在地板上，旁边散乱堆放着纸张的时候，我的室友对他们讲，"你们懂的，我可以写一个程序去做这类事情，如果你有这些打印版的原文件的话。"


After a couple of hours, he had a short program that read a competitor’s price from a file, found the product in the store’s database, and noted whether the competitor was cheaper. He was still new to programming, and he spent most of his time looking up documentation in a programming book. The actual program took only a few seconds to run. My roommate and his co-workers took an extra-long lunch that day.

几个小时之后，他写了一个简短的程序，可以从一个文件读入竞争对手的售价信息，在商店数据库里面找到某个产品，并且标记该产品对手的售价是否更低。他才刚开始接触编程，花费了大量的时间在编程书籍中查找文档。真正的程序运行只需要

This is the power of computer programming. A computer is like a Swiss Army knife that you can configure for countless tasks. Many people spend hours clicking and typing to perform repetitive tasks, unaware that the machine they’re using could do their job in seconds if they gave it the right instructions.
花费几秒钟。我的室友和他的同事那天吃了一个非常长的午餐。这就是电脑程序的威力。一台电脑，就好像是一把瑞士军刀，你可以用它来做不计其数的工作。很多人花费大量的时间，通过点击和输入来完成重复性的工作，没有意识到，如果你可以下达正确的指令，他们正在使用的机器可以在几秒钟内完成他们的工作。



##Whom Is This Book For?
##本文的受众是哪些人？
Software is at the core of so many of the tools we use today: Nearly everyone uses social networks to communicate, many people have Internet-connected computers in their phones, and most office jobs involve interacting with a computer to get work done. As a result, the demand for people who can code has skyrocketed. Countless books, interactive web tutorials, and developer boot camps promise to turn ambitious beginners into software engineers with six-figure salaries.
This book is not for those people. It’s for everyone else.

软件是我们当今使用的很多工具的核心：几乎所有人都在使用社交网络来沟通交流，很多人有联网的手机，以及大多数的办公工作涉及到使用电脑完成工作。因此，对于那些能够编程的人的需求一飞冲天。无数的书，交互式在线教程，开发者训练营承诺可以把充满野心的新手变成拥有6位数薪水的软件工程师。
本文不是为这些人写的。而是为了除此之外的所有人。


On its own, this book won’t turn you into a professional software developer any more than a few guitar lessons will turn you into a rock star. But if you’re an office worker, administrator, academic, or anyone else who uses a computer for work or fun, you will learn the basics of programming so that you can automate simple tasks such as the following:
就其本身而言，这本书并不是要把你变成一个专业的软件开发者，就像几节吉他课不能把你变成摇滚明星一样。但是如果你是一个办公室白领，管理者，学者，或是其他使用电脑进行工作或娱乐的人，你可以学到编程的基本知识，这样你就可以使下面这些现代的工作变得自动化：

- Moving and renaming thousands of files and sorting them into folders
- Filling out online forms, no typing required
- Downloading files or copy text from a website whenever it updates
- Having your computer text you custom notifications
- Updating or formatting Excel spreadsheets
- Checking your email and sending out prewritten responses


- 移动和重命名上千的文件，并在文件夹中进行排序
- 填写在线表格，不需要进行输入。
- 当内容更新时，从一个网站下载文件或者复制文本
- 让你的电脑发送定制的提示信息
- 更新或格式化你的Excel表格
- 查看你的邮箱并且发送事先写好的回复


These tasks are simple but time-consuming for humans, and they’re often so trivial or specific that there’s no ready-made software to perform them. Armed with a little bit of programming knowledge, you can have your computer do these tasks for you.

这些工作非常简单，但是对人来讲很耗时，同时因为它们通常十分琐碎又没有特定的内容，所以并不存在已经写好的程序来处理它们。当你有了一点编程知识后，你可以让你的电脑为你完成这些任务。

##Conventions
##约定
This book is not designed as a reference manual; it’s a guide for beginners. The coding style sometimes goes against best practices (for example, some programs use global variables), but that’s a trade-off to make the code simpler to learn. This book is made for people to write throwaway code, so there’s not much time spent on style and elegance. 
本书并不是一份参考手册；它为初学者提供指导。这里的编程有时并不符合最佳实践（比如，有些程序使用了全局变量），但是这是为了让代码变的简单易学的一种折中办法。本书针对那些代码用完随手就丢掉的人，因此在编程风格和优雅上面不需要花费太多时间。

Sophisticated programming concepts—like object-oriented programming, list comprehensions, and generators—aren’t covered because of the complexity they add. Veteran programmers may point out ways the code in this book could be changed to improve efficiency, but this book is mostly concerned with getting programs to work with the least amount of effort.

老生常谈的编程概念——比如面相对象编程，列表推到式和生成器——本书并没有介绍，因为这会增加本书对复杂性。编程老手可能会指出本书中的一些代码可以改写来提升性能，但是本书最关心的是花费最少的力气让程序运行起来。

##What Is Programming?
##什么是编程？
Television shows and films often show programmers furiously typing cryptic streams of 1s and 0s on glowing screens, but modern programming isn’t that mysterious. Programming is simply the act of entering instructions for the computer to perform. These instructions might crunch some numbers, modify text, look up information in files, or communicate with other computers over the Internet.
All programs use basic instructions as building blocks. Here are a few of the most common ones, in English:

电视节目和电影通常会这样演，程序员在闪光的屏幕上疯狂的输入难以理解的1和0字符流，但其实现代程序并没有这么神秘。编程其实就是一门输入指令让电脑执行的艺术。这些指令可能会是处理一些数字，修改一些文本，在文件中查找信息，或是和其他互联网上的电脑通信。所有的程序都把基本的指令作为基础素材。下面列出一些最常见的指令，用中文来描述就是：

- “Do this; then do that.”
- “If this condition is true, perform this action; otherwise, do that action.”
- “Do this action that number of times.”
- “Keep doing that until this condition is true.”

- “做这个；然后再做那个。”
- “如果这个条件是真，执行这个操作；否则就执行这个操作。”
- “把这件事，重复那个数字表示的次数。”
- “一直做下去，直到条件变为真。”

You can combine these building blocks to implement more intricate decisions, too. For example, here are the programming instructions, called the source code, for a simple program written in the Python programming language. Starting at the top, the Python software runs each line of code (some lines are run only if a certain condition is true or else Python runs some other line) until it reaches the bottom.

你也可以结合这些基本模块来实现更加复杂的指令。比如，下面有一段程序指令，叫做源代码，它是用Python编写的一个简单的程序。从上面开始，Python软件执行每一行代码（有一些行只有在特定条件为真时才执行，除此之外Python会去执行另外的行）直到达到最底部。

You might not know anything about programming, but you could probably make a reasonable guess at what the previous code does just by reading it. First, the file SecretPasswordFile.txt is opened ➊, and the secret password in it is read ➋. Then, the user is prompted to input a password (from the keyboard) ➌. These two passwords are compared ➍, and if they’re the same, the program prints Access granted to the screen ➎. Next, the program checks to see whether the password is 12345 ➏ and hints that this choice might not be the best for a password ➐. If the passwords are not the same, the program prints Access denied to the screen ➑.
你可能对编程一无所知，但是你也许只要读一下它就可以猜测那段代码会做哪些事情。熟悉，文件SecretPasswordFile.txt被打开了➊，然后它里面存放着的机密密码被读取 ➋。再然后，用户被提示输入一个密码（从键盘） ➌。对比这两个密码➍，如果它们相同的话，程序在屏幕打印“Access granted”➎。然后程序查看密码是不是12345 ➏，然后提示这个密码可能并不是一个好的选择 ➐。如果密码不相同，程序会在屏幕上打印“Access denied” ➑。

##What Is Python?
##什么是Python？
Python refers to the Python programming language (with syntax rules for writing what is considered valid Python code) and the Python interpreter software that reads source code (written in the Python language) and performs its instructions. The Python interpreter is free to download from http://python.org/, and there are versions for Linux, OS X, and Windows.
Python指的是Python编程语言（它有固定的语法规则来判断是否是有效的Python代码）以及读取源代码（使用Python语言编写）并执行指令的Python解释器软件。Python解释器可以从http://python.org/ 免费下载，它有Linux, OS X, 和Windows版本。

The name Python comes from the surreal British comedy group Monty Python, not from the snake. Python programmers are affectionately called Pythonistas, and both Monty Python and serpentine references usually pepper Python tutorials and documentation.

Python语言的名字来自荒诞的英国喜剧团Monty Python，而不是蛇。Python程序员被亲切的称为Pythonistas，Monty Python和大蟒蛇在各种Python教程和文档中都会被提及。


##Programmers Don’t Need to Know Much Math
##程序员不需要懂太多数学知识
The most common anxiety I hear about learning to program is that people think it requires a lot of math. Actually, most programming doesn’t require math beyond basic arithmetic. In fact, being good at programming isn’t that different from being good at solving Sudoku puzzles.
To solve a Sudoku puzzle, the numbers 1 through 9 must be filled in for each row, each column, and each 3×3 interior square of the full 9×9 board. You find a solution by applying deduction and logic from the starting numbers. For example, since 5 appears in the top left of the Sudoku puzzle shown in Figure 1, it cannot appear elsewhere in the top row, in the leftmost column, or in the top-left 3×3 square. Solving one row, column, or square at a time will provide more number clues for the rest of the puzzle.

关于学习编程，我听到最多常见的顾虑是人们认为它需要很多数学知识。实际上，大多数编程都只需要基础数学。事实上，擅长编程和擅长数独并没有太多的不同。解决数独问题，数字1到9必须被填在每行和每列，还有9×9棋盘中的每一个3×3到小方块内.你通过对起始数字进行逻辑推理来找到解决问题的办法。比如，因为5出现在了左上角，如图1，它就不能出现在顶行，最左边列以及左上角3x3点方格内。一次解决一行，一列或一个方块可以提供位接下来提供更多的线索。

Just because Sudoku involves numbers doesn’t mean you have to be good at math to figure out the solution. The same is true of programming. Like solving a Sudoku puzzle, writing programs involves breaking down a problem into individual, detailed steps. Similarly, when debugging programs (that is, finding and fixing errors), you’ll patiently observe what the program is doing and find the cause of the bugs. And like all skills, the more you program, the better you’ll become.

尽管数独和数字有关，但是这并不意味着你需要擅长数学才能解决这个问题。就像解决数独问题一样，写程序涉及到把问题分割为独立的，更细致的步骤。同样的，当你debug的时候（指的是，发现和修复错误），你会耐心的观察程序在做什么并找到导致这些bug的原因。如同其他所有技能一样，你编写的程序越多，你就会写的越好。

##Programming Is a Creative Activity
##编程是一个创造性的活动
Programming is a creative task, somewhat like constructing a castle out of LEGO bricks. You start with a basic idea of what you want your castle to look like and inventory your available blocks. Then you start building. Once you’ve finished building your program, you can pretty up your code just like you would your castle.

编程是一个创造性的活动，有点像是使用LEGO积木来建造一个城堡。你首先会有一些基本的想法，关于要把这个城堡建成什么样，你有哪些可以使用积木。然后你开始建造。当你完成构建你的程序之后，你可以美化你的程序，就像美化你的城堡一样。

The difference between programming and other creative activities is that when programming, you have all the raw materials you need in your computer; you don’t need to buy any additional canvas, paint, film, yarn, LEGO bricks, or electronic components. When your program is written, it can easily be shared online with the entire world. And though you’ll make mistakes when programming, the activity is still a lot of fun.

编程和其他创造性活动的区别是，当你编程的时候，你所需的全部原材料都在你的电脑中；你不需要去买额外的画布，颜料，胶片，棉线，LEGO积木或是电子元器件。当你的程序写好后，它可以通过网络很方便的雨全世界分享。尽管你在编程的过程中会犯错误，这个活动依旧非常有趣。

##About This Book
##关于本书
The first part of this book covers basic Python programming concepts, and the second part covers various tasks you can have your computer automate. Each chapter in the second part has project programs for you to study. Here’s a brief rundown of what you’ll find in each chapter:

本书的第一部分包含了基本的Python编程概念，第二部分包含了一些你可以让你电脑自动完成的工作。第二部分的每一章都有一个项目程序供你学习。这里我们简单浏览一下每个章节的内容：

**Part I**
**第一部分**

- Chapter 1. Covers expressions, the most basic type of Python instruction, and how to use the Python interactive shell software to experiment with code.
- Chapter 2. Explains how to make programs decide which instructions to execute so your code can intelligently respond to different conditions.
- Chapter 3. Instructs you on how to define your own functions so that you can organize your code into more manageable chunks.
- Chapter 4. Introduces the list data type and explains how to organize data.
- Chapter 5. Introduces the dictionary data type and shows you more powerful ways to organize data.
Chapter 6. Covers working with text data (called strings in Python).

- 第一章. 包含了表达式，这是Python指令中最基本的内容，以及如何使用Python交互式shell程序来试验代码。
- 第二章. 解释了如何让程序决定执行哪些指令，这样你的代码就能够智能的应对不同的情况。
- 第三章. 教你如何定义自己的函数，这样你可以把你的代码以更易管理的代码块形式组织起来。
- 第四章. 介绍了列表数据类型还解释了如何组织数据。
- 第五章. 介绍了字典数据类型并且展示了组织数据更加强大的方法。
- 第六章. 包含了操作文本数据的内容（在Python中我们称之为字符串）

**Part II**
**第二部分**

- Chapter 7. Covers how Python can manipulate strings and search for text patterns with regular expressions.
- Chapter 8. Explains how your programs can read the contents of text files and save information to files on your hard drive.
- Chapter 9. Shows how Python can copy, move, rename, and delete large numbers of files much faster than a human user can. It also explains compressing and decompressing files.
- Chapter 10. Shows how to use Python’s various bug-finding and bug-fixing tools.
- Chapter 11. Shows how to write programs that can automatically download web pages and parse them for information. This is called web scraping.

- 第七章. 包含Python如何操作字符串，查找通过正则表达式查找模式文本。
- 第八章. 解释了如何让你的程序读取文本文件的内容并保存信息到你硬盘上的文件中。
- 第九章. 展示了Python如何以比人类快的多的速度复制，移动，重命名和删除大量文件。同样也解释了加速和解压缩文件。
- 第十章. 展示了如何使用Python众多的bug查找和bug修复工具。
- 第十一章. 展示了如何写一个自动下载网页病解析它们获取信息的程序。我们称之*爬取网页*。



- Chapter 12. Covers programmatically manipulating Excel spreadsheets so that you don’t have to read them. This is helpful when the number of documents you have to analyze is in the hundreds or thousands.
- Chapter 13. Covers programmatically reading Word and PDF documents.
- Chapter 14. Continues to explain how to programmatically manipulate documents with CSV and JSON files.
- Chapter 15. Explains how time and dates are handled by Python programs and how to schedule your computer to perform tasks at certain times. This chapter also shows how your Python programs can launch non-Python programs.
- Chapter 16. Explains how to write programs that can send emails and text messages on your behalf.
- Chapter 17. Explains how to programmatically manipulate images such as JPEG or PNG files.
- Chapter 18. Explains how to programmatically control the mouse and keyboard to automate clicks and keypresses.

- 第十二章. 包括如何用编程的方式操作Excel表格，这样你就不需要去读它们了。当你需要分析成百上千的电子表格的时候，特别有用。
- 第十三章. 包括如何使用编程的方式读取Word和PDF文件。
- 第十四章. 继续解释如何用编程的方法来操作CSV和JSON文件。
- 第十五章. 解释了Python如何处理时间和日期以及如何为你的电脑安排计划在某个时间执行任务。本章同样向你展示了你的Python程序如何启动非Python程序。
- 第十六章. 解释了如何编写可以代替你发送电子邮件和短信的程序。
- 第十七章. 解释了如何用编程的方式操作图片，例如JPGE或PNG。
- 第十八章. 解释了如何通过编程的方式来控制鼠标和键盘，来自动点击和按键。

##Downloading and Installing Python
##下载和安装Python
You can download Python for Windows, OS X, and Ubuntu for free from [http://python.org/downloads/](http://python.org/downloads/). If you download the latest version from the website’s download page, all of the programs in this book should work.

你可以从[http://python.org/downloads/](http://python.org/downloads/)为Windows, OS X, and Ubuntu下载免费的Python。如果你从该网站下载了最新版本的Python，本书的所有程序都应该能够正常运行。

###WARNING
###警告
Be sure to download a version of Python 3 (such as 3.4.0). The programs in this book are written to run on Python 3 and may not run correctly, if at all, on Python 2.

确保你下载的是Python 3（例如3.4.0）。本书的程序针对Python 3而写，在Python 2上可能无法正确运行。

You’ll find Python installers for 64-bit and 32-bit computers for each operating system on the download page, so first figure out which installer you need. If you bought your computer in 2007 or later, it is most likely a 64-bit system. Otherwise, you have a 32-bit version, but here’s how to find out for sure:

在下载页面，你可以找到针对任何系统的64位和32位安装程序，所以首先请确定你需要哪一种。如果你的电脑是在2007年之后购买的，那么它很可能是64位系统。否则，应该是32位，但是下面是如何确认的方法。

- On Windows, select Start▸Control Panel▸System and check whether System Type says 64-bit or 32-bit.
- On OS X, go the Apple menu, select About This Mac▸More Info ▸ System Report▸Hardware, and then look at the Processor Name field. If it says Intel Core Solo or Intel Core Duo, you have a 32-bit machine. If it says anything else (including Intel Core 2 Duo), you have a 64-bit machine.
- On Ubuntu Linux, open a Terminal and run the command uname -m. A response of i686 means 32-bit, and x86_64 means 64-bit.

- Windows系统，选择开始菜单▸控制面板▸系统，并查看你的系统类型写的是64位还是32位。
- OS X系统，前往Apple菜单，选择关于本机▸系统报告▸硬件，查看处理器名这一栏。如果是Intel Core Solo 或 Intel Core Duo，你的就是32位机器。如果写的是其他的信息（包括including Intel Core 2 Duo），则你的是64位机器。
- Ubuntu Linux，打开终端并且运行命令`uname -m`,i686指的是32位系统，x86_64指的是64位系统。

On Windows, download the Python installer (the filename will end with .msi) and double-click it. Follow the instructions the installer displays on the screen to install Python, as listed here:

1. Select Install for All Users and then click Next.
2. Install to the C:\Python34 folder by clicking Next.
3. Click Next again to skip the Customize Python section.

在Windows上，下载Python安装程序（文件名以.msi结尾）并且双击它。按照屏幕上的指引来安装Python,正如下面列出的这样：

1. 选择为所有用户安装病点击下一步。
2. 点击下一步安装到C:\Python34文件夹。
3. 再次点击下一步跳过自定义Python。

On Mac OS X, download the .dmg file that’s right for your version of OS X and double-click it. Follow the instructions the installer displays on the screen to install Python, as listed here:
在Mac OS X上，下载符合你操作系统版本的.dmg文件并双击。安装屏幕上的指示来安装Python，正如下面列出的这样：

1. When the DMG package opens in a new window, double-click the Python.mpkg file. You may have to enter the administrator password.
2. Click Continue through the Welcome section and click Agree to accept the license.
3. Select HD Macintosh (or whatever name your hard drive has) and click Install.

1. 当新窗口打开DMG包后，双击Python.mpkg文件。你可能会被要求输入管理员密码。
2. 点击继续通过欢迎界面并点击同意接受许可。
3. 选择HD Macintosh（或者任意你硬盘的名字）并点击安装。

If you’re running Ubuntu, you can install Python from the Terminal by following these steps:

1. Open the Terminal window.
2. Enter `sudo apt-get install python3`.
3. Enter `sudo apt-get install idle3`.
4. Enter `sudo apt-get install python3-pip`.

如果你使用Ubuntu，你可以安装通过如下步骤在终端中安装Python

1. 打开终端.
2. 输入 `sudo apt-get install python3`.
3. 输入 `sudo apt-get install idle3`.
4. 输入 `sudo apt-get install python3-pip`.


##Starting IDLE
##启动IDLE
While the Python interpreter is the software that runs your Python programs, the interactive development environment (IDLE) software is where you’ll enter your programs, much like a word processor. Let’s start IDLE now.

Python解释器是运行你Python程序的软件，而交互式开发环境（IDLE）软件是你输入程序的地方，有点像是词处理器。让我们现在首先启动IDLE。

- On Windows 7 or newer, click the Start icon in the lower-left corner of your screen, enter IDLE in the search box, and select IDLE (Python GUI).
- On Windows XP, click the Start button and then select Programs ▸ Python 3.4▸IDLE (Python GUI).
- On Mac OS X, open the Finder window, click Applications, click Python 3.4, and then click the IDLE icon.
- On Ubuntu, select Applications▸Accessories▸Terminal and then enter idle3. (You may also be able to click Applications at the top of the screen, select Programming, and then click IDLE 3.)

- Windows 7或更高版本，点击左下角开始菜单按钮，在搜索框中输入IDLE，并且选择IDLE (Python GUI)。
- Windows XP，点击开始菜单按钮选择，然后选择程序▸Python 3.4▸IDLE (Python GUI)
- Mac OS X，打开Finder 窗口，点击应用程序，点击Python 3.4,然后点击IDLE按钮。
- Ubuntu，选择应用▸附件▸终端，然后输入idle3.（你可能也可以点击屏幕上方的应用程序，选择Programming，然后点击IDLE 3）

##The Interactive Shell
##交互式shell
No matter which operating system you’re running, the IDLE window that first appears should be mostly blank except for text that looks something like this:
不论你使用的是何种操作系统，IDLE第一次打开的时候应该白色的，除了里面的一些字，看上去像这样：

```
Python 3.4.0 (v3.4.0:04f714765c13, Mar 16 2014, 19:25:23) [MSC v.1600 64
bit (AMD64)] on win32Type "copyright", "credits" or "license()" for more
information.
>>>
```

This window is called the interactive shell. A shell is a program that lets you type instructions into the computer, much like the Terminal or Command Prompt on OS X and Windows, respectively. Python’s interactive shell lets you enter instructions for the Python interpreter software to run. The computer reads the instructions you enter and runs them immediately.
For example, enter the following into the interactive shell next to the >>> prompt:

这个窗口叫做交互式shell。shell是一个程序，让你可以给电脑下达命令，就像是OS X 和Windows上面的终端或者命令提示符。Python的交互式shell让你输入Python解释器要执行的命令。电脑读取这些指令并立即执行它们。
比如，在>>>提示符后面输入下面的指令：

```
>>> print('Hello world!')
```

After you type that line and press ENTER, the interactive shell should display this in response:
当你输入这些命令后，按下回车，交互式shell应该显示如下回应：

```
>>> print('Hello world!')
Hello world!
```

##How to Find Help
##如何寻求帮助
Solving programming problems on your own is easier than you might think. If you’re not convinced, then let’s cause an error on purpose: Enter '42' + 3 into the interactive shell. You don’t need to know what this instruction means right now, but the result should look like this:
自己去解决问题也许比你想象的更加简单。也许你不信，那么让我们故意犯下一个错误：在交互式shell中输入**'42' + 3**。你现在并不需要知道这些指令的意义，但是结果看上去应该是这样的。

```
  >>> '42' + 3
➊ Traceback (most recent call last):
    File "<pyshell#0>", line 1, in <module>
      '42' + 3
➋ TypeError: Can't convert 'int' object to str implicitly
  >>>
```

The error message ➋ appeared here because Python couldn’t understand your instruction. The traceback part ➊ of the error message shows the specific instruction and line number that Python had trouble with. If you’re not sure what to make of a particular error message, search online for the exact error message. Enter “TypeError: Can’t convert ‘int’ object to str implicitly” (including the quotes) into your favorite search engine, and you should see tons of links explaining what the error message means and what causes it, as shown in Figure 2.

错误信息➋ 出现时因为Python并不理解你的指令。回溯到错误信息中的➊，它显示了Python遇到问题的具体的指令和行号。如果你不确定是什么导致了这个问题，你可以在线搜索这条错误信息。在你最喜欢的搜索引擎中输入“TypeError: Can’t convert ‘int’ object to str implicitly”（包括引号），你就可以看到很多链接，解释了这条信息的含义以及是什么导致了它，如图2所示。

You’ll often find that someone else had the same question as you and that some other helpful person has already answered it. No one person can know everything about programming, so an everyday part of any software developer’s job is looking up answers to technical questions.

你会经常发现别人也会像你一样遇到类似的问题，而且有一些乐于主人的朋友已经回答了这些问题。没有人可以了解全部关于编程的问题，所以一个程序员每天工作的一部分就是搜索技术问题的答案。

##Asking Smart Programming Questions
##问出聪明的程序问题
If you can’t find the answer by searching online, try asking people in a web forum such as Stack Overlow [(http://stackoverflow.com/)](http://stackoverflow.com/) or the “learn programming” subreddit at [http://reddit.com/r/learnprogramming/](http://reddit.com/r/learnprogramming/). But keep in mind there are smart ways to ask programming questions that help others help you. Be sure to read the Frequently Asked Questions sections these websites have about the proper way to post questions.
When asking programming questions, remember to do the following:
如果你不能通过搜索来找到答案，可以尝试在论坛询问他人，例如Stack Overlow [(http://stackoverflow.com/)](http://stackoverflow.com/)或是“learn programming” subreddit[http://reddit.com/r/learnprogramming/](http://reddit.com/r/learnprogramming/)。但是请记住有一些聪明的提问方式，可以帮助别人更好的帮助你。请确保阅读了这些网站的常见问题(FAQ)来了解合适的提问方式。当你询问编程问题的时候，请记住按下面的方式进行：

- Explain what you are trying to do, not just what you did. This lets your helper know if you are on the wrong track.
- Specify the point at which the error happens. Does it occur at the very start of the program or only after you do a certain action?


- 解释你正在尝试做的事情，而不是你做过的事情。这让想帮助你的人能够了解你是不是走错了路。
- 明确这些错误发生的位置。是不是每次启动程序都发生还是在你做了某件事之后才发生？


- Copy and paste the entire error message and your code to [http://pastebin.com/](http://pastebin.com/) or [http://gist.github.com/.](http://gist.github.com/)
These websites make it easy to share large amounts of code with people over the Web, without the risk of losing any text formatting. You can then put the URL of the posted code in your email or forum post. For example, here some pieces of code I’ve posted: http://pastebin.com/SzP2DbFx/ and https://gist.github.com/asweigart/6912168/.
- 复制粘贴全部的错误信息和你的代码到[http://pastebin.com/](http://pastebin.com/) or [http://gist.github.com/.](http://gist.github.com/)
这些网站会让你可以更加简单的在网络上和别人分享大规模的代码，而不会丢失格式。然后你可以把这些代码的链接放在你的电子邮件或者论坛帖子中。例如，这里有一些我发的代码[http://pastebin.com/SzP2DbFx/](http://pastebin.com/SzP2DbFx/) 和 [https://gist.github.com/asweigart/6912168/](https://gist.github.com/asweigart/6912168/.)

- Explain what you’ve already tried to do to solve your problem. This tells people you’ve already put in some work to figure things out on your own.
- List the version of Python you’re using. (There are some key differences between version 2 Python interpreters and version 3 Python interpreters.) Also, say which operating system and version you’re running.
- If the error came up after you made a change to your code, explain exactly what you changed.
- Say whether you’re able to reproduce the error every time you run the program or whether it happens only after you perform certain actions. Explain what those actions are, if so.

Always follow good online etiquette as well. For example, don’t post your questions in all caps or make unreasonable demands of the people trying to help you.

- 解释你为了解决问题已经做出的尝试。这会告诉人们你已经为了解决问题做出了自己的努力。
- 列出你正在使用的Python版本。（在Python 2和Python 3解释器中存在一些关键性的不同。）同样，说明你正在使用的操作系统和它们的版本
- 如果错误是在你对代码进行了改动之后出现的，明确说明你进行了何种修改。
- 说明你是否能够在每次运行程序时重现错误或是在你做出某些操作后才会出现问题。如果是的话指明这些操作。

同样，始终遵守网络礼节。比如，不要把你的问题全部用大写字母书写，也不要向帮助你的人提出无理的请求。


##Summary
##总结
For most people, their computer is just an appliance instead of a tool. But by learning how to program, you’ll gain access to one of the most powerful tools of the modern world, and you’ll have fun along the way. Programming isn’t brain surgery—it’s fine for amateurs to experiment and make mistakes.
I love helping people discover Python. I write programming tutorials on my blog at http://inventwithpython.com/blog/, and you can contact me with questions at al@inventwithpython.com.
This book will start you off from zero programming knowledge, but you may have questions beyond its scope. Remember that asking effective questions and knowing how to find answers are invaluable tools on your programming journey.
Let’s begin!

对于大多数人，它们的的电脑指示一个电器，而不是一个工具。但是通过学习编程，你会得到机会掌握现代社会最强大的工具之一，而且在这条路上你会感到快乐。编程并不是一种脑手术——它允许新手尝试并犯错。
我乐于帮助人们了解Python。我在我的博客[http://inventwithpython.com/blog/](http://inventwithpython.com/blog/)上写了写了一些教程，而且你可以像我提问，通过al@inventwithpython.com联系到我。
这本书会带你从0编程基础启程，但是你可能会遇到一些问题超出了本书的范畴。记住，提出有效的问题，知道如何寻找答案是你编程之旅上的无价之宝。

让我们开始吧！
