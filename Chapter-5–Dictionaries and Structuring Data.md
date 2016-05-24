#Chapter 5 �C Dictionaries and Structuring Data �ֵ�ͽṹ������
[�����Ƶ�̳�](https://youtu.be/o3m8XhnVDWs)

In this chapter, I will cover the dictionary data type, which provides a flexible way to access and organize data. Then, combining dictionaries with your knowledge of lists from the previous chapter, you��ll learn how to create a data structure to model a tic-tac-toe board.  
�ڱ����У��ҽ������ֵ��������ͣ����ṩ��һ�����ķ�ʽ�����ʺ���֯���ݡ��ֵ���֮ǰ�½�ѧϰ��֪ʶ����ѧϰ��δ���һ�����ݽṹ��ʵ�־���������.

##The Dictionary Data Type �ֵ���������

Like a list, a dictionary is a collection of many values. But unlike indexes for lists, indexes for dictionaries can use many different data types, not just integers. Indexes for dictionaries are called keys, and a key with its associated value is called a key-value pair.  
���б�һ�����ֵ������ֵ�ļ��ϡ��������б��������ͬ���ֵ����������ʹ����಻ͬ���������ͣ������������������ֵ���������Ϊ�����������������ֵһ���Ϊ��-ֵ�ԡ�  

In code, a dictionary is typed with braces, {}. Enter the following into the interactive shell:  
�ڴ����У�һ���ֵ������ô�����{}��ʾ�������������ݵ��������壺

	myCat = {'size': 'fat', 'color': 'gray', 'disposition': 'loud'}
	
This assigns a dictionary to the myCat variable. This dictionary��s keys are 'size', 'color', and 'disposition'. The values for these keys are 'fat', 'gray', and 'loud', respectively. You can access these values through their keys:  
���ﶨ����һ����myCat���ֵ����ͱ���.����ֵ�ļ���'size','color'��'disposition'.����Щ��f�ֱ��Ӧ��ֵ��'fat','gray'��'loud',

	>>> myCat['size']
	'fat'
	>>> 'My cat has ' + myCat['color'] + ' fur.'
	'My cat has gray fur.'
	
Dictionaries can still use integer values as keys, just like lists use integers for indexes, but they do not have to start at 0 and can be any number.  
�ֵ���Ȼ����ʹ������ֵ��Ϊ���������б�ʹ�������������������ǲ���Ҫ��0��ʼ���������κ����֡�  

	>>> spam = {12345: 'Luggage Combination', 42: 'The Answer'}
	
##Dictionaries vs. Lists �ֵ���ʵ�

Unlike lists, items in dictionaries are unordered. The first item in a list named spam would be spam[0]. But there is no ��first�� item in a dictionary. While the order of items matters for determining whether two lists are the same, it does not matter in what order the key-value pairs are typed in a dictionary. Enter the following into the interactive shell:  
���б�һ��,�ֵ��е�Ԫ���������.���б�spam�еĵ�һ��Ԫ��Ӧ����spam[0].�������ֵ���û�е�һ��Ԫ�صĸ���.�б���Ԫ�ص�����˳���Ӱ�쵽�Ƚ������б��Ƿ���ͬ.�������ֵ��м�ֵ�Ե�����˳�������Ƚ�û��Ӱ��.�����������ݵ���������:

	>>> spam = ['cats', 'dogs', 'moose']
	>>> bacon = ['dogs', 'moose', 'cats']
	>>> spam == bacon
	False
	>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
	>>> ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}
	>>> eggs == ham
	True
	
Because dictionaries are not ordered, they can��t be sliced like lists.  
��Ϊ�ֵ�������ģ����ǲ������б�һ������Ƭ��

Trying to access a key that does not exist in a dictionary will result in a KeyError error message, much like a list��s ��out-of-range�� IndexError error message. Enter the following into the interactive shell, and notice the error message that shows up because there is no 'color' key:  
��ͼ���ʲ��ֵ��д��ڵļ��ᵼ��KeyError�쳣�Ĵ�����Ϣ�������б�ġ�out-of-range��IndexError������Ϣ�������������ݵ���������,��Ϊ����û�м�'color'���������Ϣ.  

	>>> spam = {'name': 'Zophie', 'age': 7}
	>>> spam['color']
	Traceback (most recent call last):
	  File "<pyshell#1>", line 1, in <module>
		spam['color']
	KeyError: 'color'
	
Though dictionaries are not ordered, the fact that you can have arbitrary values for the keys allows you to organize your data in powerful ways. Say you wanted your program to store data about your friends�� birthdays. You can use a dictionary with the names as keys and the birthdays as values. Open a new file editor window and enter the following code. Save it as birthdays.py.  
��Ϊ�ֵ�����û��˳��֮��,��ʵ�����������ͨ���������ǿ�����ķ�ʽ��֯�������.  ��������дһ���������洢�����ѵ�������Ϣ.��������ֵ��в���������Ϊ����������Ϊֵ��ʵ��.��һ���µ��ļ��༭�����ڣ����������´��롣��������Ϊbirthdays.py��  

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
����Գ�ʼ��һ���ֵ�洢������Ϣ.����Կ�������������������Ϊ�����ֵ��еĹؼ����еļ�,������б����һ��.����������ֵ��У���ʹ�÷����ŷ�����ص�ֵ.���û�У������ʹ����ͬ�ķ����Ÿ�ֵ��������.

When you run this program, it will look like this:  
��������������������������ģ�

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

Of course, all the data you enter in this program is forgotten when the program terminates. You��ll learn how to save data to files on the hard drive in Chapter 8.  
��Ȼ��������ֹʱ��������������������������ݻᶪʧ���ڵ�8������ѧϰ��ν����ݱ��浽Ӳ���������ϵ��ļ��С�  

##The keys(), values(), and items() Methods ��,ֵ��Ԫ�ط���

There are three dictionary methods that will return list-like values of the dictionary��s keys, values, or both keys and values: keys(), values(), and items(). The values returned by these methods are not true lists: They cannot be modified and do not have an append() method. But these data types (dict_keys, dict_values, and dict_items, respectively) can be used in for loops. To see how these methods work, enter the following into the interactive shell:  
�������ֵ�keys(), values(), and items()�����������ֵ�ļ���ֵ���ֵ��.����Щ���������ص�ֵ���б����ǲ��ܱ��޸ģ�����ʹ��append()����������Щ���ص��������Ϳ�������ѭ����.Ҫ�˽���Щ�����Ĺ���ģʽ���������´��뵽�������壺  

	spam = {'color': 'red', 'age': 42}
	for v in spam.values():
			print(v)

	red
	42

Here, a for loop iterates over each of the values in the spam dictionary. A for loop can also iterate over the keys or both keys and values:  
������forѭ�����Ա����ֵ�spam�е�ֵ.forѭ�����Ա����������ֵ:  

	for k in spam.keys():
			print(k)

	color
	age

	for i in spam.items():
			print(i)

	('color', 'red')
	('age', 42)

Using the keys(), values(), and items() methods, a for loop can iterate over the keys, values, or key-value pairs in a dictionary, respectively. Notice that the values in the dict_items value returned by the items() method are tuples of the key and value.  
 ��keys(), values(), ��items()�������Ա�����,ֵ,��ֵ��.ע�⣬����items()�������ص�dict_itemsֵ��ֵ�Ǽ���ֵ��Ԫ��
 
If you want a true list from one of these methods, pass its list-like return value to the list() function. Enter the following into the interactive shell:  
����������Щ��������������б����԰ѷ���ֵ���ݸ�list()�����������������ݵ��������壺  

	spam = {'color': 'red', 'age': 42}
	spam.keys()
	dict_keys(['color', 'age'])
	list(spam.keys())
	['color', 'age']
	
The list(spam.keys()) line takes the dict_keys value returned from keys() and passes it to list(), which then returns a list value of ['color', 'age'].  
��list(spam.keys())������dict_keys��ֵ���ݵ�list()��Ȼ�󷵻�['color', 'age']�б�  

You can also use the multiple assignment trick in a for loop to assign the key and value to separate variables. Enter the following into the interactive shell:  
��Ҳ����ʹ�ö��ظ�ֵ������forѭ���ж������ֵ�������ı�����  

	spam = {'color': 'red', 'age': 42}
	for k, v in spam.items():
			print('Key: ' + k + ' Value: ' + str(v))

	Key: age Value: 42
	Key: color Value: red
	
##Checking Whether a Key or Value Exists in a Dictionary
##���һ������ֵ�Ƿ�����ֵ���

Recall from the previous chapter that the in and not in operators can check whether a value exists in a list. You can also use these operators to see whether a certain key or value exists in a dictionary. Enter the following into the interactive shell:  
��ǰ����½��е��У�������in���������Լ���б����Ƿ����ĳ��ֵ����Ҳ����ʹ��in�������鿴���ֵ���ĳ������ֵ�Ƿ���ڡ��ڽ�������������������:  

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
	
In the previous example, notice that 'color' in spam is essentially a shorter version of writing 'color' in spam.keys(). This is always the case: If you ever want to check whether a value is (or isn��t) a key in the dictionary, you can simply use the in (or not in) keyword with the dictionary value itself.  
��ǰ��������У�'color' in spam ��������'color' in spam.keys()�ļ�д��ͨ��Ӧ���������ĳ���:����������ѯһ������ֵ�Ƿ�����ֵ��ж���������������Ǽ�����ֵ�Ϳ���ʹ��.

##The get() Method
##get()����

It��s tedious to check whether a key exists in a dictionary before accessing that key��s value. Fortunately, dictionaries have a get() method that takes two arguments: the key of the value to retrieve and a fallback value to return if that key does not exist.
Enter the following into the interactive shell:  
����ڷ���һ������ֵ֮ǰ��Ҫ�ȼ����Ƿ�����ֵ��о�̫�鷳��.�Һ����ֵ�����һ����������������get()�ķ���:��������ֵ�ļ�,������ʱ�ķ���ֵ.�ڽ�������������������:

	picnicItems = {'apples': 5, 'cups': 2}
	'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'
	'I am bringing 2 cups.'
	'I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.'
	'I am bringing 0 eggs.'
	
Because there is no 'eggs' key in the picnicItems dictionary, the default value 0 is returned by the get() method. Without using get(), the code would have caused an error message, such as in the following example:  
��Ϊ�ֵ�picnicItems��û��'egs'����Ĭ��ֵ0��get()�������ء������ʹ��get()���������ɴ�����Ϣ������������ӣ�

	picnicItems = {'apples': 5, 'cups': 2}
	'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'
	Traceback (most recent call last):
	  File "<pyshell#34>", line 1, in <module>
		'I am bringing ' + str(picnicItems['eggs']) + ' eggs.'
	KeyError: 'eggs'
	
##The setdefault() Method

You��ll often have to set a value in a dictionary for a certain key only if that key does not already have a value. The code looks something like this:  
��ͨ����Ҫ���ֵ���ĳЩû��ֵ�ļ��趨һ��ֵ���ô��뿴�����������ģ�

	spam = {'name': 'Pooka', 'age': 5}
	if 'color' not in spam:
		spam['color'] = 'black'
		
The setdefault() method offers a way to do this in one line of code. The first argument passed to the method is the key to check for, and the second argument is the value to set at that key if the key does not exist. If the key does exist, the setdefault() method returns the key��s value. Enter the following into the interactive shell:  
setdefault()�����ṩ��һ�ֵ��д���ʵ��������ܵ�;��.���ݸ������ĵ�һ�������Ǽ����Ƿ���ڣ��ڶ�������������ü�������ֵʱ���øü���ֵ�������������setdefault()�������ظü���ֵ.�ڽ��������������´���:  

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
��һ�ε���setdefault()���ֵ�spam���{'color': 'black', 'age': 5, 'name': 'Pooka'}.��Ϊ����ֵͨ����'color'���������÷������÷���ֵ'black'.���ڶ��ε���spam.setdefault('color', 'white')ʱ,����Ӧ��ֵ��û�б��'white',��Ϊspam�Ѿ��м�'color'����.

The setdefault() method is a nice shortcut to ensure that a key exists. Here is a short program that counts the number of occurrences of each letter in a string. Open the file editor window and enter the following code, saving it as characterCount.py:  
setdefault����������һ���ܺõ�ȷ���ؼ����ڵĿ�ݷ�ʽ��������һ���̵ܶĳ������������ַ����е�ÿ����ĸ���ֵĴ��������ļ��༭�����ڣ����������´��룬���䱣��ΪcharacterCount.py��

	message = 'It was a bright cold day in April, and the clocks were striking thirteen.'
	count = {}

	for character in message:
		count.setdefault(character, 0)
		count[character] = count[character] + 1

	print(count)
	
The program loops over each character in the message variable��s string, counting how often each character appears. The setdefault() method call ensures that the key is in the count dictionary (with a default value of 0) so the program doesn��t throw a KeyError error when count[character] = count[character] + 1 is executed. When you run this program, the output will look like this:  
�ó����������message�ַ�����ÿ���ַ�������ÿ���ַ����ֵ�Ƶ�ʡ�����setdefault()����������Ĭ�ϲ���Ϊ0ȷ�����ڼ����ֵ���count[character] = count[character] + 1ʱ���򲻻ᱨ��.�����������,����������:  

	{' ': 13, ',': 1, '.': 1, 'A': 1, 'I': 1, 'a': 4, 'c': 3, 'b': 1, 'e': 5, 'd': 3, 'g': 2, 'i':
	6, 'h': 3, 'k': 2, 'l': 3, 'o': 2, 'n': 4, 'p': 1, 's': 3, 'r': 5, 't': 6, 'w': 2, 'y': 1}
	
From the output, you can see that the lowercase letter c appears 3 times, the space character appears 13 times, and the uppercase letter A appears 1 time. This program will work no matter what string is inside the message variable, even if the string is millions of characters long!  
������У�����Կ�����Сд��ĸc����3�Σ��ո��ַ�����13�Σ��Լ���д��ĸA����1�Ρ���������Ϣ����������ʲô�ַ�������ʹ���ַ��������԰���Ƶ��ַ���������򶼿�������.  

##Pretty Printing ������ӡ

If you import the pprint module into your programs, you��ll have access to the pprint() and pformat() functions that will ��pretty print�� a dictionary��s values. This is helpful when you want a cleaner display of the items in a dictionary than what print() provides. Modify the previous characterCount.py program and save it as prettyCharacterCount.py.  
�������pprintģ�鵽��ĳ����㽫���pprint������pformat��������������������ӡ�����ֵ��ֵ����������ȫ��ӡ�ֵ��Ԫ�����Ƿǳ��а����ġ��޸�ǰ��ĳ���characterCount.py�����䱣��ΪprettyCharacterCount.py��  

	import pprint
	message = 'It was a bright cold day in April, and the clocks were striking
	thirteen.'
	count = {}

	for character in message:
		count.setdefault(character, 0)
		count[character] = count[character] + 1

	pprint.pprint(count)
	
This time, when the program is run, the output looks much cleaner, with the keys sorted.  
��һ�γ�������ʱ��������������ɾ����ü�����������

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
���ֵ䱾�����Ƕ�׵��б���ֵ�ʱpprint.pprint���������ر����á���������������ı���Ϊһ���ַ���ֵ������������Ļ����ʾ���������Ե���pprint.pformat()���档�������д����Ǳ˴˵�Ч��  

	pprint.pprint(someDictionaryValue)
	print(pprint.pformat(someDictionaryValue))
	
#Using Data Structures to Model Real-World Things
#�����ݽṹģ����ʵ���������
[��ؽ�ѧ��Ƶ](https://youtu.be/mf28IhDfMGk)