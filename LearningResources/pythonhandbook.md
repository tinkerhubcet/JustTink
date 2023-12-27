
# An introduction to Python

## Session 1:

- [Printing values](#Printing-values)
- [Using variables](#Using-variables)
- [Simple data types](#Simple-data-types): [Booleans](#Booleans), [Integers](#Integers), [Floating point numbers](#Floating-point-numbers), and [Strings](#Strings)
- [Comments](#Comments)
- [Exercises 1.1.1](#Exercises-1.1.1)
- [Arithmetic](#Arithmetic)
- [Exercises 1.1.2](#Exercises-1.1.2)

## My Mantra of how to learn a new programming language

- Learn Data Types
- Learn Control Structures
- Practice

## Printing values

The first bit of python syntax we're going to learn is the <tt>print</tt> statement. This command lets us print messages to the user, and also to see what Python thinks is the value of some expression (very useful when debugging your programs).

We will go into details later on, but for now just note that to print some text you have to enclose it in  "quotation marks". 

We will go into detail on the arithmetic operations supported in python shortly, but you can try exploring python's calculating abilities.


```python
print (sys.version)
```

    3.6.2 |Anaconda, Inc.| (default, Sep 30 2017, 18:42:57) 
    [GCC 7.2.0]



```python
print("Hello from python!")
```

    Hello from python!



```python
print(34)
```

    34



```python
print(2 + 3)
```

    5


You can print  multiple expressions you need to seperate them with commas. Python will insert a space between each element, and a newline at the end of the message (though you can suppress this behaviour by leaving a trailing comma at the end of the command).


```python
print("The answer:", 42)
```

    The answer: 42


## Using variables

In the <tt>print</tt> commands above we have directly operated on values such as text strings and numbers. When programming we will typically want to deal with rather more complex expressions where it is useful to be able to assign a name to an expression, especially if we are trying to deal with multiple values at the same time.

We can give a name to a value using _variables_, the name is apt because the values stored in a variable can _vary_. Unlike some other languages, the type of value assigned to a variable can also change (this is one of the reasons why python is known as a _dynamic_ language).

A variable can be assigned to a simple value...


```python
x = 3
print(x)
```

    3


... or the outcome of a more complex expression.


```python
x = 2 + 2
print(x)
```

    4


A variable can be called whatever you like (as long as it starts with a character, it does not contain space and is meaningful) and you assign a value to a variable with the **`=` operator**. Note that this is different to mathematical equality (which we will come to later...)

You can <tt>print</tt> a variable to see what python thinks its current value is.


```python
name = "Iron man"
print(name, "is his name")
```

    Iron man is his name


In the interactive interpreter you don't have to <tt>print</tt> everything, if you type a variable name (or just a value), the interpreter will automatically print out what python thinks the value is. Note though that this is not the case if your code is in a file.


```python
3 + 4
```




    7




```python
x = 5
3 * x
```




    15



Variables can be used on the right hand side of an assignment as well, in which case they will be evaluated before the value is assigned to the variable on the left hand side.


```python
x = 5
y = x * 3
print(y)
```

    15


or just `y` in the interpreter and in Jupyter notebook


```python
y
```




    15



You can use the current value of a variable itself in an assignment


```python
y = y + 1
y
```




    16



In fact this is such a common idiom that there are special operators that will do this implicitly (more on these later)


```python
y += 1
y
```




    17



## Simple data types

Python (and computers in general) treats different types of data differently. Python has 5 main basic data types. Types are useful to constrain some operations to a certain category of variables. For example it doesn't really make sense to try to divide a string.

We will see some examples of these in use shortly, but for now let's see all of the basic types available in python.

### Booleans

Boolean values represent truth or falsehood, as used in logical operations, for example. Not surprisingly, there are only two values, and in Python they are called <tt>True</tt> and <tt>False</tt>.


```python
a = True
b = False
print(a, b)

x = 10 < 5
print(x)
```

    True False
    False


### Integers

Integers represent whole numbers, as you would use when counting items, and can be positive or negative.


```python
i = -7
j = 123
print(i, j)
```

    -7 123


### Floating point numbers

Floating point numbers, often simply referred to as <tt>float</tt>s, are numbers expressed in the decimal system, i.e. 2.1, 999.998, -0.000004 etc. The value 2.0 would also be interpreted as a floating point number, but the value 2, without the decimal point will not; it will be interpreted as an integer.


```python
x = 3.14159
y = -42.3
print(x * y)
```

    -132.889257


Floating point numbers can also carry an <tt>e</tt> suffix that states which power of ten they operate at.


```python
k = 1.5e3
l = 3e-2
print(k)
print(l)
```

    1500.0
    0.03


### Strings

Strings represent text, i.e. "strings" of characters. They can be delimited by single quotes <tt>‘</tt> or double quotes <tt>“</tt>, but you have to use the same delimiter at both ends. Unlike some programming languages, such as Perl, there is no difference between the two types of quote, although using one type does allow the other type to appear inside the string as a regular character.

Normally a python statement ends at the end of the line, but if you want to type a string over several lines you can enclose it in triple quotation marks.


```python
s = "String with double quotes"
t = 'String with single quotes'
u = "It's a string with apostrophes"
"""A string that extends
over multiple lines"""
```




    'A string that extends\nover multiple lines'



### The <tt>None</tt> object

The None object is special built-in value which can be thought of as **representing nothingness or that something is undefined**. For example, it can be used to indicate that a variable exists, but has not yet been set to anything specific.


```python
z = None
print(z)
```

    None


### Object type

You can check what type python thinks an expression is with the <tt>type</tt> function, which you can call with the name <tt>type</tt> immediately followed by parentheses enclosing the expression you want to check (either a variable or a value), e.g. <tt>type(3)</tt>. (This is the general form for calling functions, we'll see lots more examples of functions later...)


```python
a = True
print(a, "is of", type(a))
```

    True is of <class 'bool'>



```python
i = -7
print(i, "is of", type(i))
```

    -7 is of <class 'int'>



```python
x = 12.7893
print(x, "is of", type(x))
```

    12.7893 is of <class 'float'>



```python
s = "Workshop"
print(s, "is of", type(s))
```

    Workshop is of <class 'str'>



```python
z = None
print(z, "is of", type(z))
```

    None is of <class 'NoneType'>


## Comments

When you are writing a program it is often convenient to annotate your code to remind you what you were (intending) it to do. In programming these annotations are known as _comments_. You can include a comment in python by prefixing some text with a <tt>#</tt> character. All text following the <tt>#</tt> will then be ignored by the interpreter. You can start a comment on its own line, or you can include it at the end of a line of code.

It is also often useful to temporarily remove some code from a script without deleting it. This is known as _commenting out_ some code.


```python
print("Hi") # this will be ignored
# as will this
print("Bye")
# print "Never seen"
```

## Exercises 1.1.1

To start the Python interpreter, open a terminal window, type the command `python`, then enter Python commands after the prompt `>>>` and press `Enter` when you're done. 

Python will run the code you typed, and might display some output on the line below, before leaving you with another prompt which looks like `>>>`.

If you want to exit the interactive interpreter you can type the command `quit()` or type `Ctrl-D`.

In the interpreter:

1. Create a variable and assign it the string value of your first name, assign your age to another variable (you are free to lie!), print out a message saying how old you are
2. Use the addition operator to add 10 to your age and print out a message saying how old you will be in 10 years time

## Arithmetic

Python supports all the standard arithmetical operations on numerical types, and mostly uses a similar syntax to several other computer languages:


```python
x = 4.5
y = 2

print('x = ', x, 'y = ', y)
print('addition x + y =', x + y) 
print('subtraction x - y =', x - y) 
print('multiplication x * y =', x * y) 
print('division x / y =', x / y) 
```

    x =  4.5 y =  2
    addition x + y = 6.5
    subtraction x - y = 2.5
    multiplication x * y = 9.0
    division x / y = 2.25



```python
x = 4.5
y = 2

print('x = ', x, 'y = ', y)
print('division x / y =', x / y)
print('floored division x // y =', x // y)
print(type(x//y))
print('modulus (remainder of x/y) x % y =', x % y) 
print('exponentiation x ** y =', 10 ** 2)
```

    x =  4.5 y =  2
    division x / y = 2.25
    floored division x // y = 2.0
    <class 'float'>
    modulus (remainder of x/y) x % y = 0.5
    exponentiation x ** y = 100


As usual in maths, division and multiplication have higher precedence than addition and subtraction, but arithmetic expressions can be grouped using parentheses to override the default precedence


```python
x = 13
y = 5

print('x * (2 + y) =', x * (2 + y))
print('(x * 2) + y =', (x * 2) + y)
print('x * 2 + y =', x * 2 + y)
```

You can mix (some) types in arithmetic expressions and python will apply rules as to the type of the result



```python
int(13 + 5.0)
```




    18



You can force python to use a particular type by converting an expression explicitly, using helpful named functions: <tt>float</tt>, <tt>int</tt>, <tt>str</tt> etc.


```python
float(3) + float(7)
```




    10.0




```python
int(3.14159) + 1

+1+1
```




    2



The addition operator `+` allows you also to concatenate strings together.


```python
print('number' + str(3))
```

    number3


Division in Python 2 sometimes trips up new (and experienced!) programmers. If you divide 2 integers you will only get an integer result. If you want a floating point result you should explicitly cast at least one of the arguments to a <tt>float</tt>.


```python
print("3/4 =", 3/4)
print("3.0/4 =", 3.0/4)
print("float(3)/4 =", float(3)/4)
```

    3/4 = 0.75
    3.0/4 = 0.75
    float(3)/4 = 0.75


There are a few shortcut assignment statements to make modifying variables directly faster to type


```python
x = 3
x += 1 # equivalent to x = x + 1
x
```




    4




```python
x = 2
y = 10
y *= x
y
```




    20



These shortcut operators are available for all arithmetic and logical operators.

## Exercises 1.1.2

In the interpreter:

1. Assign numerical values to 2 variables, calculate the mean of these two variables and store the result in another variable. Print out the result to the screen.


# An introduction to Python

## Session 1.2: Collections

- [Tuples](#Tuples), [Lists](#Lists) and [Manipulating tuples and lists](#Manipulating-tuples-and-lists) | [Exercise 1.2.1](#Exercise-1.2.1)
- [String manipulations](#String-manipulations) | [Exercise 1.2.2](#Exercise-1.2.2)
- [Sets](#Sets) |
- [Dictionnaries](#Dictionnaries) |

As well as the basic data types we introduced above, very commonly you will want to store and operate on collections of values, and python has several _data structures_ that you can use to do this. The general idea is that you can place several items into a single collection and then refer to that collection as a whole. Which one you will use will depend on what problem you are trying to solve.

## Tuples

- Can contain any number of items
- Can contain different types of items
- __Cannot__ be altered once created (they are immutable)
- Items have a defined order

A tuple is created by using round brackets around the items it contains, with commas seperating the individual elements.


```python
a = (123, 54, 92) # tuple of 4 integers
b = () # empty tuple
c = ("Ala",) # tuple of a single string (note the trailing ",")
d = (2, 3, False, "Arg", None) # a tuple of mixed types

print(a)
print(b)
print(c)
print(d)
```

You can of course use variables in tuples and other data structures


```python
x = 1.2
y = -0.3
z = 0.9
t = (x, y, z)

print(t)
```

Tuples can be _packed_ and _unpacked_ with a convenient syntax. The number of variables used to unpack the tuple must match the number of elements in the tuple.


```python
t = 2, 3, 4 # tuple packing
print('t is', t)
x, y, z = t # tuple unpacking
print('x is', x)
print('y is', y)
print('z is', z)
```

## Lists

- Can contain any number of items
- Can contain different types of items
- __Can__ be altered once created (they are _mutable_)
- Items have a particular order

Lists are created with square brackets around their items:


```python
a = [1, 3, 9, 'Py', 217.213]
b = ["Python"]
c = []

print(a)
print(b)
print(c)
```

    [1, 3, 9, 'Py', 217.213]
    ['Python']
    []


Lists and tuples can contain other list and tuples, or any other type of collection:


```python
matrix = [[input(),input()], [input(),input()]]
print(matrix)
```

    r
    ff
    fd
    sd
    [['r', 'ff'], ['fd', 'sd']]


You can convert between tuples and lists with the <tt>tuple</tt> and <tt>list</tt> functions. Note that these create a new collection with the same items, and leave the original unaffected.


```python
a = (1, 4, 9, 16)     # A tuple of numbers
b = ['A','B','C','d'] # A list of characters

print(a)
print(b)

l = list(a)   # Make a list based on a tuple 
print(l)

t = tuple(b)  # Make a tuple based on a list
print(t)
```

## Manipulating tuples and lists

Once your data is in a list or tuple, python supports a number of ways you can access elements of the list and manipulate the list in useful ways, such as sorting the data.

Tuples and lists can generally be used in very similar ways.

### Index access

You can access individual elements of the collection using their _index_, note that the first element is at index 0. Negative indices count backwards from the end.


```python
t = (123, 54, 92, 87, 33)
x = [123, 54, 92, 87, 33]

print('t is', t)
print('t[0] is', t[0])
print('t[2] is', t[2])

print('x is', x)
print('x[-1] is', x[-1])
```

### Slices

You can also access a range of items, known as _slices_, from inside lists and tuples using a colon `:` to indicate the beginning and end of the slice inside the square brackets. **Note that the slice notation `[a:b]` includes positions from `a` up to _but not including_ `b`**.


```python
t = (123, 54, 92, 87, 33)
x = [123, 54, 92, 87, 33]
print('t[1:3] is', t[1:3])
print('x[2:] is', x[2:])
print('x[:-1] is', x[:-1])
```

    t[1:3] is (54, 92)
    x[2:] is [92, 87, 33]
    x[:-1] is [123, 54, 92, 87]


### `in` operator
You can check if a value is in a tuple or list with the <tt>in</tt> operator, and you can negate this with <tt>not</tt>


```python
t = (123, 54, 92, 87, 33)
x = [123, 54, 92, 87, 33]
print('123 in', x, 123 in x)
print('234 in', t, 234 in t)
print('999 not in', x, 999 not in x)
```

    123 in [123, 54, 92, 87, 33] True
    234 in (123, 54, 92, 87, 33) False
    999 not in [123, 54, 92, 87, 33] True



```python
a = [1, 2, 3, 4, 5]

a[2:]
```




    [3, 4, 5]



### `len()` and `count()` functions
You can get the length of a list or tuple with the in-built <tt>len()</tt> function, and you can count the number of particular elements contained in a list with the <tt>.count()</tt> function.


```python
t = (123, 54, 92, 87, 33)
x = [123, 54, 92, 87, 33]
print("length of t is", len(t))
print("number of 33s in x is", x.count(33))
```

    length of t is 5
    number of 33s in x is 1


### Modifying lists
You can alter lists in place, but not tuples


```python
x = [123, 54, 92, 87, 33]
print(x)
x[2] = 33
print(x)
```

    [123, 54, 92, 87, 33]
    [123, 54, 33, 87, 33]


Tuples _cannot_ be altered once they have been created, if you try to do so, you'll get an error.


```python
t = (123, 54, 92, 87, 33)
print(t)
t[1] = 4
```

    (123, 54, 92, 87, 33)



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-1-7204a6fa6a43> in <module>()
          1 t = (123, 54, 92, 87, 33)
          2 print(t)
    ----> 3 t[1] = 4
    

    TypeError: 'tuple' object does not support item assignment


You can add elements to the end of a list with <tt>append()</tt>


```python
x = [123, 54, 92, 87, 33]
x.append(101)
print(x)
```

    [123, 54, 92, 87, 33, 101]


or insert values at a certain position with <tt>insert()</tt>, by supplying the desired position as well as the new value


```python
x = [123, 54, 92, 87, 33]
x.insert(3, 1111)
print(x)
```

    [123, 54, 92, 1111, 87, 33]


You can remove values with <tt>remove()</tt>


```python
x = [123, 54, 92, 87, 33]
x.remove(123)
print(x)
```

    [54, 92, 87, 33]


and delete values by index with <tt>del</tt>


```python
x = [123, 54, 92, 87, 33]
print(x)
del x[0]
print(x)
```

    [123, 54, 92, 87, 33]
    [54, 92, 87, 33]


It's often useful to be able to combine arrays together, which can be done with <tt>extend()</tt> (as <tt>append</tt> would add the whole list as a single element in the list)


```python
a = [1,2,3]
b = [4,5,6]
a.extend(b)
print(a)
a.append(b)
print(a)
```

    [1, 2, 3, 4, 5, 6]
    [1, 2, 3, 4, 5, 6, [4, 5, 6]]


The plus symbol <tt>+</tt> is shorthand for the extend operation when applied to lists:


```python
a = [1, 2, 3]
b = [4, 5, 6]
a = a + b
print(a)
```

    [1, 2, 3, 4, 5, 6]


Slice syntax can be used on the left hand side of an assignment operation to assign subregions of a list


```python
a = [1, 2, 3, 4, 5, 6]
a[1:3] = [9, 9, 9, 9]
print(a)
```

    [1, 9, 9, 9, 9, 4, 5, 6]


You can change the order of elements in a list


```python
a = [1, 3, 5, 4, 2]
a.reverse()
print(a)
#print(a[::2])
a.sort()
print(a)
```

    [2, 4, 5, 3, 1]
    [1, 2, 3, 4, 5]


Note that both of these change the list, if you want a sorted copy of the list while leaving the original untouched, use <tt>sorted()</tt>


```python
a = [2, 5, 7, 1]
b = sorted(a)
print(a)
print(b)
```

## String manipulations

Strings are a lot like tuples of characters, and individual characters and substrings can be accessed and manipulated using similar operations we introduced above.



```python
text = "ABCDEFGH"
print(text[0])
print(text[-2])
print(text[0:6])
print("EFG" in text)
print("ABC" in text)
print(len(text))
```

    A
    G
    ABCDEF
    True
    True
    8


Just as with tuples, trying to assign a value to an element of a string results in an error


```python
text = "ABCDEFGH"
text[0:2] = "CCC" 
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-3-6c7e51bd134e> in <module>()
          1 text = "ABCDEFGH"
    ----> 2 text[0:2] = "CCC"
    

    TypeError: 'str' object does not support item assignment


Python provides a number of useful functions that let you manipulate strings

The <tt>in</tt> operator lets you check if a substring is contained within a larger string, but it does not tell you where the substring is located. This is often useful to know and python provides the <tt>.find()</tt> method which returns the index of the first occurrence of the search string, and the <tt>.rfind()</tt> method to start searching from the end of the string.

If the search string is not found in the string both these methods return -1.


```python
string = "ABCDEDCBA"
index = string.find("CDE")
print("CDE is at position:", index)
index = string.rfind('C')
print("The last C is at position:", index)
```

    CDE is at position: 2
    The last C is at position: 6


When we are reading text from files  (which we will see later on), often there is unwanted whitespace at the start or end of the string. We can remove leading whitespace with the <tt>.lstrip()</tt> method, trailing whitespace with <tt>.rstrip()</tt>, and whitespace from both ends with <tt>.strip()</tt>.

All of these methods return a copy of the changed string, so if you want to replace the original you can assign the result of the method call to the original variable.


```python
s = "     My name is Python     "
print(len(s), s, ".")
print(len(s.rstrip()), s.rstrip(), ".")
print(len(s.lstrip()), s.lstrip(), ".")
print(len(s.strip()), s.strip(),".")
```

    27      My name is Python      .
    22      My name is Python .
    22 My name is Python      .
    17 My name is Python .


You can split a string into a list of substrings using the <tt>.split()</tt> method, supplying the delimiter as an argument to the method. If you don't supply any delimiter the method will split the string on whitespace by default (which is very often what you want!)

To split a string into its component characters you can simply _cast_ the string to a list 


```python
string = "My name is Python"
words = string.split(" ")
print(words)

letters = list(string) # a tuple of character converted into a list
print(letters)
```

    ['My', 'name', 'is', 'Python']
    ['M', 'y', ' ', 'n', 'a', 'm', 'e', ' ', 'i', 's', ' ', 'P', 'y', 't', 'h', 'o', 'n']


<tt>.split()</tt> is the counterpart to the <tt>.join()</tt> method that lets you join the elements of a list into a string only if all the elements are of type String:


```python
string = "My name is Python"
words = string.split(" ")
print(words)
print("|".join(words))
```

    ['My', 'name', 'is', 'Python']
    My|name|is|Python


We also saw earlier that the <tt>+</tt> operator lets you concatenate strings together into a larger string.

Note that this operator only works on variables of the same type. If you want to concatenate a string with an integer (or some other type), first you have to cast the integer to a string with the <tt>str()</tt> function.


```python
language = "Python"
version = 3.6
print(language + str(version))
```

    Python3.6


## Exercise 1.2.2

1. Create a string variable with your full name in it, with your first and last name (and any middle names) seperated by a space. Split the string into a list, and print out your surname.
2. Check if your surname contains the letter "E", and print out the position of this letter in the string. Try a few other letters.

### Optional exercise
- Use a format string to print out your first name and the length of your first name by looking into the python library for String formating https://docs.python.org/3/library/stdtypes.html#str.format and https://docs.python.org/3/library/string.html#formatstrings using `str.format()`

## Sets

- Sets contain unique elements, i.e. no repeats are allowed
- The elements in a set do not have an order
- Sets cannot contain elements which can be internally modified (e.g. lists and dictionaries)


```python
l = [1, 2, 3, 2, 3] # list of 5 values
s = set(l) # set of 3 unique values
print(s)
e = set() # empty set
print(e)
```

Sets are very similar to lists and tuples and you can use many of the same operators and functions, except they are **inherently unordered**, so they don't have an index, and can only contain _unique_ values, so adding a value already in the set will have no effect


```python
s = set([1, 2, 3, 2, 3])
print(s)
print("number in set:", len(s))
s.add(4)
print(s)
s.add(3)
print(s)
```

You can remove specific elements from the set.


```python
s = set([1, 2, 3, 2, 3])
print(s)
s.remove(3)
print(s)
```

You can do all the expected logical operations on sets, such as taking the union or intersection of 2 sets with the <tt>|</tt> _or_ and <tt>&</tt> _and_ operators 


```python
s1 = set([2, 4, 6, 8, 10])
s2 = set([4, 5, 6, 7])

print("Union:", s1 | s2)
print("Intersection:", s1 & s2)
```

## Dictionaries

Lists are useful in many contexts, but often we have some data that has no inherent order and that we want to access by some useful name rather than an index. For example, as a result of some experiment we may have a set of genes and corresponding expression values. We could put the expression values in a list, but then we'd have to remember which index in the list corresponded to which gene and this would quickly get complicated.

For these situations a _dictionary_ is a very useful data structure.

Dictionaries:

- Contain a mapping of keys to values (like a word and its corresponding definition in a dictionary)
- The keys of a dictionary are unique, i.e. they cannot repeat
- The values of a dictionary can be of any data type
- The keys of a dictionary cannot be an internally modifiable type (e.g. lists, but you can use tuples)
- Dictionaries do not store data in any particular order


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
print(sports)

sports['C']
```

    {'A': 'Cricket', 'B': 'Football', 'C': 'Hockey', 'D': 'Badminton'}





    'Hockey'



You can access values in a dictionary using the key inside square brackets


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
print("A represents", sports["A"])
print("G represents", sports["G"])
```

An error is triggered if a key is absent from the dictionary:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
print("What about N?", sports["N"])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-25-422dcfa53292> in <module>()
          1 sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
    ----> 2 print("What about N?", sports["N"])
    

    KeyError: 'N'


You can access values safely with the <tt>get</tt> method, which gives back <tt>None</tt> if the key is absent and you can also supply a default values


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
print("What about N?", sports.get("N"))
print("With a default value:", sports.get("N", "asfasfasf"))
```

    What about N? None
    With a default value: asfasfasf


You can check if a key is in a dictionary with the <tt>in</tt> operator, and you can negate this with <tt>not</tt>


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
"T" in sports
```




    False




```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
"Y" not in sports
```




    True



The <tt>len()</tt> function gives back the number of (key, value) pairs in the dictionary:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
print(len(sports))
```

    4


You can introduce new entries in the dictionary by assigning a value with a new key:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton"}
sports['E'] = 'Kabaddi'
print(sports)
```

    {'A': 'Cricket', 'B': 'Football', 'C': 'Hockey', 'D': 'Badminton', 'E': 'Kabaddi'}


You can change the value for an existing key by reassigning it:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi"}
sports['F'] = 'Volley Ball'
print(sports)
```

    {'A': 'Cricket', 'B': 'Football', 'C': 'Hockey', 'D': 'Badminton', 'E': 'Kabaddi', 'F': 'Volley Ball'}


You can delete entries from the dictionary:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi", 'F': 'Volley Ball'}
del sports['F']
print(sports)
```

    {'A': 'Cricket', 'B': 'Football', 'C': 'Hockey', 'D': 'Badminton', 'E': 'Kabaddi'}


You can get a list of all the keys (in arbitrary order) using the inbuilt <tt>.keys()</tt> function


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi"}
print(list(sports.keys()))
```

    ['A', 'B', 'C', 'D', 'E']


And equivalently get a list of the values:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi"}
print(list(sports.values()))
```

    ['Cricket', 'Football', 'Hockey', 'Badminton', 'Kabaddi']


And a list of tuples containing (key, value) pairs:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi"}
print(list(sports.items()))
```

    [('A', 'Cricket'), ('B', 'Football'), ('C', 'Hockey'), ('D', 'Badminton'), ('E', 'Kabaddi')]



# An introduction to Python

## Session 1.3: Conditional execution

- [Code blocks](#Code-blocks)
- [Conditional execution](#Conditional-execution)
- [Exercises 1.3.1](#Exercises-1.3.1)

## Program control and logic

A program will normally run by executing the stated commands, one after the other in sequential order. Frequently however, you will need the program to deviate from this. There are several ways of diverting from the line-by-line paradigm:

- With conditional statements. Here you can check if some statement or expression is true, and if it is then you continue on with the following block of code, otherwise you might skip it or execute a different bit of code.

- By performing repetitive loops through the same block of code, where each time through the loop different values may be used for the variables.

- Through the use of functions (subroutines) where the program’s execution jumps from a particular line of code to an entirely different spot, even in a different file or module, to do a task before (usually) jumping back again. Functions are covered in the next session, so we will not discuss them yet.

- By checking if an error or exception occurs, i.e. something illegal has happened, and executing different blocks of code accordingly

## Code blocks

With all of the means by which Python code execution can jump about we naturally need to be aware of the boundaries of the block of code we jump into, so that it is clear at what point the job is done, and program execution can jump back again. In essence it is required that the end of a function, loop or conditional statement be defined, so that we know the bounds of their respective code blocks.

Python uses indentation to show which statements are in a block of code, other languages use specific `begin` and `end` statements or curly braces `{}`. It doesn't matter how much indentation you use, but the whole block must be consistent, i.e., if the first statement is indented by four spaces, the rest of the block must be indented by the same amount. The Python style guide recommends using 4-space indentation. Use spaces, rather than tabs, since different editors display tab characters with different widths.

The use of indentation to delineate code blocks is illustrated in an abstract manner in the following scheme: 

Statement 1:

    Command A – in the block of statement 1
    Command B – in the block of statement 1
  
    Statement 2:
        Command C – in the block of statement 2
        Command D – in the block of statement 2
  
    Command E – back in the block of statement 1

Command F – outside all statement blocks


## Conditional execution

### The <tt>if</tt> statement

A conditional <tt>if</tt> statement is used to specify that some block of code should only be executed if some associated test is upheld; a conditional expression evaluates to <tt>True</tt>. This might also involve subsidiary checks using the <tt>elif</tt> statement to use an alternative block if the previous expression turns out to be False. There can even be a final <tt>else</tt> statement to do something if none of the checks are passed. 

The following uses statements that test whether a number is less than zero, greater than zero or otherwise equal to zero and will print out a different message in each case:


```python
x = -3

if x > 0:
    print("Value is positive")

elif x < 0:
    print("Value is negative")

else:
    print("Value is zero")
```

    Value is negative


The general form of writing out such combined conditional statements is as follows:

<pre>
if conditionalExpression1:
    # codeBlock1

elif conditionalExpression2:
    # codeBlock2

elif conditionalExpressionN:
    # codeBlockN
    +any number of additional elif statements, then finally:

else:
    # codeBlockE
</pre>


The <tt>elif</tt> block is optional, and we can use as many as we like. The <tt>else</tt> block is also optional, so will only have the <tt>if</tt> statement, which is a fairly common situation. It is often good practice to include <tt>else</tt> where possible though, so that you always catch cases that do not pass, otherwise values might go unnoticed, which might not be the desired behaviour.

Placeholders are needed for “empty” code blocks:


```python
name = "luttapi"
mark = 30

if mark < 45:
    print(name, "has failed in the exam")
        
elif geneExpression > 0:
    print(name, "has passed in the exam")
        
else:
    pass
```

    luttapi has failed in the exam


For very simple conditional checks, you can write the `if` statement on a single line as a single expression, and the result will be the expression before the `if` if the condition is true or the expression after the `else` otherwise.




```python
x = 11

if x < 10:
    s = "Yes"
else:
    s = "No"
print(s)

# Could also be written onto one line
s = "Yes" if x < 10 else "No"
print(s)
```

### Comparisons and truth

With conditional execution the question naturally arises as to which expressions are deemed to be true and which false. For the python boolean values <tt>True</tt> and <tt>False</tt> the answer is (hopefully) obvious. Also, the logical states of truth and falsehood that result from conditional checks like “Is x greater than 5?” or “Is y in this list?” are also clear. When comparing values Python has the standard comparison (or relational) operators, some of which we have already seen:

|Operator |	Description |	Example |
|---------|-------------|-----------|
|`==`  |	    equality |	1 == 2 # False |
|`!=`  |	    non equality |	1 != 2 # True |
| `<`  |	    less than |	1 < 2 # True |
| `<=` |	    equal or less than |	2 <= 2 # True |
| `>`  |	    greater then |	1 > 2 # False |
| `>=` |	    equal or greater than |	1 >= 1 # True |

It is notable that comparison operations can be combined, for example to check if a value is within a range.


```python
x = 5

#if x > 0 and x < 10:
if 0 < x < 10: #is also possible
    print("In range A")
else:
    print("Not in range")
    
#elif x < 0 or x > 10:
#    print("In range B")
```

    In range A


Python has two additional comparison operators <tt>is</tt> and <tt>is not</tt>. These compare whether two objects are the same object, whereas <tt>==</tt> and <tt>!=</tt> compare whether values are the same.

As an example in Python:


```python
x = [123, 54, 92, 87, 33]
y = x[:] # y is a copy of x
z = x
print(x)
print("Are values of y and x the same?", y == x)
print("Are objects y and x the same?", y is x)
print("Are values of z and x the same?", z == x)
print("Are objects z and x the same?", z is x)
# Let's change x
x[1] = 23
print(x)
print("Are values of y and x the same?", y == x)
print("Are objects y and x the same?", y is x)
print("Are values of z and x the same?", z == x)
print("Are objects z and x the same?", z is x)
```

In Python even expressions that do not involve an obvious boolean value can be assigned a status of "truthfulness";  the value of an item itself can be forced to be considered as either True or False inside an if statement. For the Python built-in types discussed in this chapter the following are deemed to be False in such a context:

| False value | Description | 
|-------------|-------------|
| `None` |	numeric equality |
| `False` |	False boolean |
| `0`	| 0 integer |
| `0.0` |	0.0 floating point |
| `""` |	empty string |
| `()` |	empty tuple |
| `[]` |	empty list |
| `{}` |	empty dictonary |
| `set()` |	empty set |

And everything else is deemed to be True in a conditional context.


```python
x = ''      # An empty string
y = ['a']   # A list with one item

if x:
    print("x is true")
else: 
    print("x is false")     

if y:
    print("y is true")
else:
    print("y is false")
```

## Exercises 1.3.1

Create a `if..elif..else` block that will compare a variable containing your age to another variable containing another person's age and print a statement which says if you are younger, older or the same age as that person.


# An introduction to Python

## Session 1.4: Loops

- [The <tt>for</tt> loop](#The-for-loop)
- [The <tt>while</tt> loop](#The-while-loop)
- [Skipping and breaking loops](#Skipping-and-breaking-loops)
- [More looping using range and enumerate](#More-looping)
- [Filtering in loops](#Filtering-in-loops)

## Loops

When an operation needs to be repeated multiple times, for example on all of the items in a list, we
avoid having to type (or copy and paste) repetitive code by creating a loop. There are two ways of creating loops in Python, the <tt>for</tt> loop and the <tt>while</tt> loop.

## The <tt>for</tt> loop

The for loop in Python iterates over each item in a sequence (such as a list or tuple) in the order that they appear in the sequence. What this means is that a variable (<tt>code</tt> in the below example) is set to each item from the sequence of values in turn, and each time this happens the indented block of code is executed again.


```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]

for x in numbers:
    print(x)
    #print(number, end = '-')
```

    1
    2
    3
    4
    5
    6
    7
    8
    9


A <tt>for</tt> loop can iterate over the individual characters in a string:


```python
name = 'Kochi Python'

for character in name:
    print(character)
```

    K
    o
    c
    h
    i

    P
    y
    t
    h
    o
    n


And also over the keys of a dictionary:


```python
sports = {"A": "Cricket", "B": "Football", "C": "Hockey", "D": "Badminton", "E": "Kabaddi"}

for x in sports:
    print(x, sports[x])
```

    A Cricket
    B Football
    C Hockey
    D Badminton
    E Kabaddi


Any variables that are defined before the loop can be accessed from inside the loop. So for example to calculate the summation of the items in a list of values we could define the total initially to be zero and add each value to the total in the loop:


```python
total = 0
values = [1, 2, 4, 8, 16]

for v in values:
    total = total + v
    # total += v
    print(total)

print(total)
```

Naturally we can combine a <tt>for</tt> loop with an <tt>if</tt> statement, noting that we need two indentation levels, one for the outer loop and another for the conditional blocks:


```python
markList = {
    'Tintumon': 22,
    'Dundumol': 86,
    'Dingan': 69,
    'Luttapi': 45
}

for person in markList:
    if markList.get(person) < 45:
        print(person, " : Failed")

    elif markList.get(person) > 45:
        print(person, " : Passed")

    else:
        print(person, ' : Just Pass' )
```

    Tintumon  : Failed
    Dundumol  : Passed
    Dingan  : Passed
    Luttapi  : Just Pass


## The <tt>while</tt> loop

In addition to the <tt>for</tt> loop that operates on a collection of items, there is a <tt>while</tt> loop that simply repeats while some statement evaluates to True and stops when it is False. Note that if the tested expression never evaluates to False then you have an “infinite loop”, which is not good.

In this example we generate a series of numbers by doubling a value after each iteration, until a limit is reached:


```python
value = 0.25
while value < 8:
    value = value * 2
    print(value)

print("final value:", value)
```

    0.5
    1.0
    2.0
    4.0
    8.0
    final value: 8.0


Whats going on here is that the value is doubled in each iteration and once it gets to 8 the while test fails (8 is not less than 8) and that last value is preserved. Note that if the test were instead value `<= 8` then we would get one more doubling and the value would reach 16.

## Skipping and breaking loops

Python has two ways of affecting the flow of the <tt>for</tt> or <tt>while</tt> loop inside the block. The <tt>continue</tt> statement means that the rest of the code in the block is skipped for this particular item in the collection, i.e. jump to the next iteration. In this example negative numbers are left out of a summation:


```python
#Sum of positive integers in a list
values = [10, -5, 3, -1, 7]

total = 0
for v in values:
    if v < 0:
        continue # Skip this iteration   
    total += v

print(total)
```

    20


The other way of affecting a loop is with the <tt>break</tt> statement. In contrast to the <tt>continue</tt> statement, this immediately causes all looping to finish, and execution is resumed at the next statement _after_ the loop.


```python
#Print from 1 - 7
for n in range(1,10):
    if n % 8 == 0:
        break            # Quit looping at this point
    else:
        print(n)
```

    1
    2
    3
    4
    5
    6
    7


## Looping gotchas

An internal counter is used to keep track of which item is used next, and this is incremented on each iteration. When this counter has reached the length of the sequence the loop terminates. This means that if you delete the current item from the sequence, the next item will be skipped (since it gets the index of the current item which has already been treated). Likewise, if you insert an item in a sequence before the current item, the current item will be treated again the next time through the loop. This can lead to nasty bugs that can be avoided by making a temporary copy using a slice of the whole sequence.

<div class="alert-warning">
**When looping, never modify the collection!** Always create a copy of it first.
</div>

## More looping

### Using range

If you would like to iterate over a numeric sequence then this is possible by combining the `range()` function and a for loop.


```python
print(list(range(10)))

print(list(range(5, 10)))

print(list(range(0, 10, 3)))

print(list(range(7, 2, -1)))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    [5, 6, 7, 8, 9]
    [0, 3, 6, 9]
    [7, 6, 5, 4, 3]


### Looping through ranges


```python
for x in range(8):
    print(x*x)
```

    0
    1
    4
    9
    16
    25
    36
    49



```python
squares = []
for x in range(8):
    s = x*x
    squares.append(s)

print(squares)
```

    [0, 1, 4, 9, 16, 25, 36, 49]


#### Looping through list ndices


```python
alphabets = ['A', 'B', 'C', 'D', 'E']

for index in range(len(alphabets)):
    print(index, alphabets[index])
```

    0 A
    1 B
    2 C
    3 D
    4 E


#### Looping through indices for two lists


```python
alphabets = ['A', 'B', 'C', 'D', 'E']
more_alphabets = ['F', 'G', 'H', 'I', 'J']

for index in range(len(alphabets)):
    print(index, alphabets[index], more_alphabets[index])
```

    0 A F
    1 B G
    2 C H
    3 D I
    4 E J


### Using enumerate

Given a sequence, `enumerate()` allows you to iterate over the sequence generating a tuple containing each value along with a corresponding index.


```python
letters = ['A','B','C','D']
for index, letter in enumerate(letters):
    print(index, letter)
```

    0 A
    1 B
    2 C
    3 D



```python
numbered_letters = list(enumerate(letters))
print(numbered_letters)
```

    [(0, 'A'), (1, 'B'), (2, 'C'), (3, 'D')]


## Filtering in loops


```python
city_pops = {
    'London': 8200000,
    'Cambridge': 130000,
    'Edinburgh': 420000,
    'Glasgow': 1200000
}

big_cities = []
for city in city_pops:
    if city_pops[city] >= 1000000:
         big_cities.append(city)

print(big_cities)
```

    ['London', 'Glasgow']



```python
total = 0
for city in city_pops:
    total += city_pops[city]
print("total population:", total)
```

    total population: 9950000



```python
pops = list(city_pops.values())
print("total population:", sum(pops))
```

    total population: 9950000



# An introduction to Python

- Python website: https://www.python.org/
- [Python 3 Standard Library](https://docs.python.org/3/library/index.html])

## Learning objectives

- **Basics** how to print, create variables and save Python code in files
- **List** the most common data types in Python
- **Explain** how to write conditions and loops in Python
- **Use and compare** these concepts in different code examples
- **Propose and create** solutions using these concepts in different exercises

- **Session 2.1** - Functions
- **Session 2.2** - Modules
- **Session 2.3** - Files

## What we've learned so far

- Simple data types, Collections
- Conditional execution
- Loops
- Functions used so far...

## Collections


```python
## Tuple - immutable
example_tuple = (2, 3, 4, 5)
print('A tuple:', example_tuple)
print('First element of tuple:', example_tuple[0])
```

    A tuple: (2, 3, 4, 5)
    First element of tuple: 2



```python
## List
example_list = [2, 3, 4, 5]
print('A list:', example_list)
print('First element of list:', example_list[0])
example_list.append(12)
print('Appended list:', example_list)
example_list[0] = 45
print('Modified list:', example_list)
```

    A list: [2, 3, 4, 5]
    First element of list: 2
    Appended list: [2, 3, 4, 5, 12]
    Modified list: [45, 3, 4, 5, 12]



```python
## String - immutable, tuple of characters
text = "ABCDEFGH"
print('Here is a string:', text)
print('First character:', text[0])
print('Number of characters in text', len(text))
```

    Here is a string: ABCDEFGH
    First character: A
    Number of characters in text 8



```python
## Set - unique unordered elements
example_set = set([1,2,2,2,2,4,5,6,6,6])
print('A set:', example_set)
```

    A set: {1, 2, 4, 5, 6}



```python
## Dictionary
example_dictionary = {"A": "APPLE",
                      "B": "BALL",
                      "C": "CAT",
                      "D": "DOLL"}
print('A dictionary:', example_dictionary)
print('Value associated to key C:', example_dictionary['C'])
```

    A dictionary: {'A': 'APPLE', 'B': 'BALL', 'C': 'CAT', 'D': 'DOLL'}
    Value associated to key C: CAT


## Conditional execution


```python
x = 2
print('Is 2 < 5?', x < 5)
print('Is 2 == 5?', x == 5)
print('Is 2 < 5 and 2 > 1?', (x < 5) & (x > 1))

if x == 2:
    print('x is equal to 2')
```

    Is 2 < 5? True
    Is 2 == 5? False
    Is 2 < 5 and 2 > 1? True
    x is equal to 2


## Loops


```python
example_list = ['A', 'B', 'C', 'D', 'E']

## Looping through a list
for element in example_list:
    print("The element in list is:", element)
```

    The element in list is: A
    The element in list is: B
    The element in list is: C
    The element in list is: D
    The element in list is: E


## Exercise 2.0.1

- Create a string variable with the lyrics of Imagine by John Lennon, 1971. Split into words. Print the total number of words, and the number of unique words. Calculate the frequency of each word and store the result into a dictionary. Print each unique word along with its frequency. Find the most frequent word in the song, print it with its frequency.

<center><img src="https://upload.wikimedia.org/wikipedia/en/1/1d/John_Lennon_-_Imagine_John_Lennon.jpg"/></center>


```python
lyrics = """
Imagine there's no Heaven
It's easy if you try
No Hell below us
Above us only sky

Imagine all the people
Living for today
Aaa haa

Imagine there's no countries
It isn't hard to do
Nothing to kill or die for
And no religion too

Imagine all the people
Living life in peace
Yoo hoo

You may say I'm a dreamer
But I'm not the only one
I hope someday you'll join us
And the world will be as one

Imagine no possessions
I wonder if you can
No need for greed or hunger
A brotherhood of man

Imagine all the people
Sharing all the world
Yoo hoo

You may say I'm a dreamer
But I'm not the only one
I hope someday you'll join us
And the world will live as one
"""
```


# An introduction to Python

## Session 2.1: Functions

- [Function definition syntax](#Function-definition-syntax)
- [Excercises 2.1.1](#Excercises-2.1.1)
- [Return value](#Return-value)
- [Exercises 2.1.2](#Exercises-2.1.2)
- [Function arguments](#Function-arguments)
- [Exercises 2.1.3](#Exercises-2.1.3)
- [Variable scope](#Variable-scope)

## Function basics

We have already seen a number of functions built into python that let us do useful things to strings, collections and numbers etc. For example `print()` or `len()` which is passed some kind of sequence object and returns the length of the sequence.

This is the general form of a function; it takes some input _arguments_ and returns some output based on the supplied arguments.

The arguments to a function, if any, are supplied in parentheses and the result of the function _call_ is the result of evaluating the function.



```python
x = abs(-3.0)
print(x)

l = len("ABCDEF")
print(l)
```

    3.0
    6


As well as using python's built in functions, you can write your own. Functions are a nice way to **encapsulate some code that you want to reuse** elsewhere in your program, rather than repeating the same bit of code multiple times. They also provide a way to name some coherent block of code and allow you to structure a complex program.

## Function definition syntax

Functions are defined in Python using the `def` keyword followed by the name of the function. If your function takes some arguments (input data) then you can name these in parentheses after the function name. If your function does not take any arguments you still need some empty parentheses. Here we define a simple function named `sayHello` that prints a line of text to the screen:


```python
def sayHello():
    print('Hello world!')
    
sayHello()
```

    Hello world!


Note that the code block for the function (just a single print line in this case) is indented relative to the `def`. The above definition just decalares the function in an abstract way and nothing will be printed when the definition is made. To actually use a function you need to invoke it (call it) by using its name and a pair of round parentheses:


```python
sayHello() # Call the function to print 'Hello world'
```

If required, a function may be written so it accepts input. Here we specify a variable called `name` in the brackets of the function definition and this variable is then used by the function. Although the input variable is referred to inside the function the variable does not represent any particular value. It only takes a value if the function is actually used in context.


```python
def sayHello(name):
    print('Hello', name)
```

When we call (invoke) this function we specify a specific value for the input. Here we pass in the value `User`, so the name variable takes that value and uses it to print a message, as defined in the function. 


```python
sayHello('User')  # Prints 'Hello User'
```

When we call the function again with a different input value we naturally get a different message. Here we also illustrate that the input value can also be passed-in as a variable (text in this case).


```python
text = 'Mary'
sayHello(text)     # Prints 'Hello Mary'
```

A function may also generate output that is passed back or returned to the program at the point at which the function was called. For example here we define a function to do a simple calculation of the square of input (`x`) to create an output (`y`):


```python
def square(x):
  y = x*x
  return y
```

Once the `return` statement is reached the operation of the function will end, and anything on the return line will be passed back as output. Here we call the function on an input number and catch the output value as result. Notice how the names of the variables used inside the function definition are separate from any variable names we may choose to use when calling the function.
  


```python
number = 7
result = square(number) # Call the square() function which returns a result
print(result)           # Prints: 49
```

The function `square` can be used from now on anywhere in your program as many times as required on any (numeric) input values we like.


```python
print(square(1.2e-3))   # Prints: 1.4399999999999998e-06
```

A function can accept multiple input values, otherwise known as arguments. These are separated by commas inside the brackets of the function definition. Here we define a function that takes two arguments and performs a calculation on both, before sending back the result.



```python
def calcFunc(x, y):
  z = x*x + y*y
  return z


result = calcFunc(1.414, 2.0)
print(result)  #  5.999396
```

Note that this function does not check that x and y are valid forms of input. For the function to work properly we assume they are numbers. Depending on how this function is going to be used, appropriate checks could be added.

Functions can be arbitrarily long and can peform very complex operations. However, to make a function reusable, it is often better to assign it a single responsibility and a descriptive name.
Let's define now a function to calculate the [Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance) between two vectors:


```python
def calcDistance(vec1, vec2):    
    dist = 0
    for i in range(len(vec1)):
        delta = vec1[i] - vec2[i]
        dist += delta*delta
    dist = dist**(1/2) # square-root
    return dist
```

For the record, the [prefered way to calcule a square-root](https://docs.python.org/3/library/math.html#math.sqrt) is by using the built-in function `sqrt()` from the `math` library:
```python
import math
math.sqrt(x)
```

Let's experiment a little with our function.


```python
w1 = ( 23.1, 17.8, -5.6 )
w2 = ( 8.4, 15.9, 7.7 )
calcDistance( w1, w2 )
```

Note that the function is general and handles any two vectors (irrespective of their representation) as long as their dimensions are compatible:


```python
calcDistance( ( 1, 2 ), ( 3, 4 ) ) # dimension: 2
```


```python
calcDistance( [ 1, 2 ], [ 3, 4 ] ) # vectors represented as lists
```


```python
calcDistance( ( 1, 2 ), [ 3, 4 ] ) # mixed representation
```

## Return value

There can be more than one `return` statement in a function, although typically there is only one, at the bottom. Consider the following function to get some text to say whether a number is positive or negative. It has three return statements: the first two return statements pass back text strings but the last, which would be reached if the input value were zero, has no explicit return value and thus passes back the Python `None` object. Any function code after this final return is ignored. 
The `return` keyword immediately exits the function, and no more of the code in that function will be run once the function has returned (as program flow will be returned to the call site)


```python
def getSign(value):
    
    if value > 0:
        return "Positive"
    
    elif value < 0:
        return "Negative"
    
    return # implicit 'None'

    print("Hello world") # execution does not reach this line
    
print("getSign( 33.6 ):", getSign( 33.6 ))
print("getSign( -7 ):", getSign( -7 ))
print("getSign( 0 ):", getSign( 0 ))
```

    getSign( 33.6 ): Positive
    getSign( -7 ): Negative
    getSign( 0 ): None


All of the examples of functions so far have returned only single values, however it is possible to pass back more than one value via the `return` statement. In the following example we define a function that takes two arguments and passes back three values. The return values are really passed back inside a single tuple, which can be caught as a single collection of values. 


```python
def myFunction(value1, value2):
    
    total = value1 + value2
    difference = value1 - value2
    product = value1 * value2
    
    return total, difference, product

values = myFunction( 3, 7 )  # Grab output as a whole tuple
print("Results as a tuple:", values)

x, y, z = myFunction( 3, 7 ) # Unpack tuple to grab individual values
print("x:", x)
print("y:", y)
print("z:", z)
```

## Function arguments

### Mandatory arguments

The arguments we have passed to functions so far have all been _mandatory_, if we do not supply them or if supply the wrong number of arguments python will throw an error also called an exception:


```python
def square(number):
    # one mandatory argument
    y = number*number
    return y
```


```python
square(2)
```

**Mandatory arguments are assumed to come in the same order as the arguments in the function definition**, but you can also opt to specify the arguments using the argument names as _keywords_, supplying the values corresponding to each keyword with a `=` sign.


```python
square(number=3)
```


```python
def repeat(seq, n):
    # two mandatory arguments
    result = ''
    for i in range(0,n):
        result += seq
    return result

print(repeat("abc", 3))
print(repeat(n=4, seq="XYZ"))
```

    abcabcabc
    XYZXYZXYZXYZ


<div class="alert-warning">**NOTE** Unnamed (positional) arguments must come before named arguments, even if they look to be in the right order.</div>


```python
print(repeat(seq="LMN", n=3))
```

    LMNLMNLMN


### Arguments with default values
Sometimes it is useful to give some arguments a default value that the caller can override, but which will be used if the caller does not supply a value for this argument. We can do this by assigning some value to the named argument with the `=` operator in the function definition.


```python
def runSimulation(nsteps=1000):
    print("Running simulation for", nsteps, "steps")

runSimulation(500)
runSimulation()
```

    Running simulation for 500 steps
    Running simulation for 1000 steps


<div class="alert-warning">**CAVEAT**: default arguments are defined once and keep their state between calls. This can be a problem for *mutable* objects:</div>


```python
def myFunction(parameters=[]):
    parameters.append( 100 )
    print(parameters)
    
myFunction()
myFunction()
myFunction()
myFunction([])
myFunction([])
myFunction([])
```

    [100]
    [100, 100]
    [100, 100, 100]
    [100]
    [100]
    [100]


... or avoid modifying *mutable* default arguments.


```python
def myFunction(parameters):
    # one mandatory argument without default value
    parameters.append( 100 )
    print(parameters)
    
my_list = []
myFunction(my_list)
myFunction(my_list)
myFunction(my_list)
my_new_list = []
myFunction(my_new_list)
```

### Position of mandatory arguments
Arrange function arguments so that *mandatory* arguments come first:


```python
def runSimulation(initialTemperature, nsteps=1000):
    # one mandatory argument followed by one with default value
    print("Running simulation starting at", initialTemperature, "K and doing", nsteps, "steps")
    
runSimulation(300, 500)
runSimulation(300)
```

As before, no positional argument can appear after a keyword argument, and all required arguments must still be provided.


```python
runSimulation( nsteps=100, initialTemperature=300 )
```


```python
runSimulation( initialTemperature=300 )
```


```python
runSimulation( nsteps=100 ) # Error: missing required argument 'initialTemperature'
```


```python
runSimulation( nsteps=100, 300 ) # Error: positional argument follows keyword argument
```

Keyword names must naturally match to those declared:


```python
runSimulation( initialTemperature=300, numSteps=100 ) # Error: unexpected keyword argument 'numSteps'
```

Function cannot be defined with mandatory arguments after default ones.


```python
def badFunction(nsteps=1000, initialTemperature):
    pass
```

## Variable scope

Every variable in python has a _scope_ in which it is defined. Variables defined at the outermost level are known as _globals_ (although typically only for the current module). In contrast, variables defined within a function are local, and cannot be accessed from the outside.


```python
def mathFunction(x, y):
    math_func_result = ( x + y ) * ( x - y )
    return math_func_result
```


```python
answer = mathFunction( 4, 7 )
print(answer)
```


```python
answer = mathFunction( 4, 7 )
print(math_func_result)
```

Generally, variables defined in an outer scope are also visible in functions, but you should be careful manipulating them as this can lead to confusing code and python will actually raise an error if you try to change the value of a global variable inside a function. Instead it is a good idea to avoid using global variables and, for example, to pass any necessary variables as parameters to your functions.


```python
counter = 1
def increment(): 
    print(counter)
    counter += 1

increment()
print(counter)
```

If you really want to do this, there is a way round this using the `global` statement. Any variable which is changed or created inside of a function is local, if it hasn't been declared as a global variable. To tell Python that we want to use the global variable, we have to explicitly state this by using the keyword `global`.


```python
counter = 1
def increment(): 
    global counter
    print(counter)
    counter += 1

increment()
print(counter)
```

<div class="alert-warning">**NOTE** It is normally better to avoid global variables and passing through arguments to functions instead.</div>


```python
def increment(counter): 
    return counter + 1

counter = 0
counter = increment( counter ) 
print(counter)
```


# An introduction to Python

## Session 2.2: Modules
- [Modules](#Modules)
- [Be creative and create a module for what you love](#Create)

## Modules

So far we have been writing Python code in files as executable scripts without knowning that they are also modules from which we are able to call the different functions defined in them.

A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. Create a file called `my_first_module.py` in the current directory with the following contents:


```python
def say_hello(user):
    print('hello', user, '!')
```

Now enter the Python interpreter from the directory you've created `my_first_module.py` file and import the `say_hello` function from this module with the following command:

```bash
python3
Python 3.5.2 (default, Jun 30 2016, 18:10:25)
[GCC 4.2.1 Compatible Apple LLVM 7.0.2 (clang-700.1.81)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from my_first_module import say_hello
>>> say_hello('Anne')
hello Anne !
>>>
```

There is one module already stored in the course directory called `my_first_module.py`, if you wish to import it into this notebook, below is what you need to do. If you wish to edit this file and change the code or add another function, you will have to restart the notebook to have these changes taken into account using the restart the kernel button in the menu bar.


```python
from my_first_module import say_hello
say_hello('Anne')
```

A module can contain executable statements as well as function definitions. These statements are intended to initialize the module. They are executed only the first time the module name is encountered in an import statement.
They are also run if the file is executed as a script.

Do comment out these executable statements if you do not wish to have them executed when importing your module.

For more information about modules, https://docs.python.org/3/tutorial/modules.html.

## Create

Now that you know functions, lists, dictionaries, loops and a lot more why don't you try to build something on your own.

Maybe a module with some mathematical functions.

I'll leave this part to you!

Good luck!


# An introduction to Python

## Session 2.3: Files

- [Using files](#Using-files)
- [Data formats](#Data-formats)
- [Importing modules and libraries](#Importing-modules-and-libraries)
- [Using the `csv` module](#Using-the-csv-module)
- [Python file library](#Python-file-library)

# Data input and output (I/O)

So far, all that data we have been working with has been written by us into our scripts, and the results of out computation has just been displayed in the terminal output. In the real world data will be supplied by the user of our programs (who may be you!) by some means, and we will often want to save the results of some analysis somewhere more permanent than just printing it to the screen. In this session we cover 2 widely used ways of reading data into our programs, via the command line and by reading files from dish, we also discuss writing out data to files. 

There are, of course, many other ways of accessing data, such as querying a database or retrieving data from a network such as the internet. We don't cover these here, but python has excellent support for interacting with databases and networks either in the standard library or using external modules.

## Using files

Frequently the data we want to operate on or analyse will be stored in files, so in our programs we need to be able to open files, read through them (perhaps all at once, perhaps not), and then close them. 

We will also frequently want to be able to print output to files rather than always printing out results to the terminal.

Python supports all of these modes of operations on files, and provides a number of useful functions and syntax to make dealing with files straightforward.

### Opening files

To open a file, python provides the `open` function, which takes a filename as its first argument and returns a _file object_ which is python's internal representation of the file.


```python
path = "data/datafile.txt"
fileObj = open( path )
```

`open` takes an optional second argument specifying the _mode_ in which the file is opened, either for reading, writing or appending.

It defaults to `'r'` which means open for reading in text mode. Other common values are `'w'` for writing (truncating the file if it already exists) and `'a'` for appending.


```python
open( "data/myfile.txt", "r" ) # open for reading, default
```


```python
open( "data/myfile.txt", "w" ) # open for writing (existing files will be overwritten)
```


```python
open( "data/myfile.txt", "a" ) # open for appending
```

### Closing files

To close a file once you finished with it, you can call the `.close` method on a file object.


```python
fileObj.close()
```

### Mode modifiers

These mode strings can include some extra modifier characters to deal with issues with files across multiple platforms.

`'b'`: binary mode, e.g. `'rb'`. No translation for end-of-line characters to platform specific setting value.

|Character | Meaning |
|----------|---------|
|`'r'` |	open for reading (default) |
|`'w'` |	open for writing, truncating the file first |
|`'x'` |	open for exclusive creation, failing if the file already exists |
|`'a'` |	open for writing, appending to the end of the file if it exists |
|`'b'` |	binary mode |
|`'t'` |	text mode (default) |
|`'+'` |	open a disk file for updating (reading and writing) |

### Reading from files

Once we have opened a file for reading, file objects provide a number of methods for accessing the data in a file. The simplest of these is the `.read` method that reads the entire contents of the file into a string variable.




```python
fileObj = open( "data/datafile.txt" )
print(fileObj.read()) # everything
fileObj.close()
```

Note that this means the entire file will be read into memory. If you are operating on a large file and don't actually need all the data at the same time this is rather inefficient.

Frequently, we just need to operate on individual lines of the file, and you can use the `.readline` method to read a line from a file and return it as a python string.

File objects internally keep track of your current location in a file, so to get following lines from the file you can call this method multiple times.

It is important to note that the string representing each line will have a trailing newline `"\n"` character, which you may want to remove with the `.rstrip` string method.

Once the end of the file is reached, `.readline` will return an empty string `''`. This is different from an apparently empty line in a file, as even an empty line will contain a newline character. Recall that the empty string is considered as `False` in python, so you can readily check for this condition with an `if` statement etc.


```python
# one line at a time
fileObj = open( "data/datafile.txt" )
print("1st line:", fileObj.readline())
print("2nd line:", fileObj.readline())
print("3rd line:", fileObj.readline())
print("4th line:", fileObj.readline())
fileObj.close()
```

To read in all lines from a file as a list of strings containing the data from each line, use the `.readlines` method (though note that this will again read all data into memory).


```python
# all lines
fileObj = open( "data/datafile.txt" )

lines = fileObj.readlines()

print("The file has", len(lines), "lines")

fileObj.close()
```

Looping over the lines in a file is a very common operation and python lets you iterate over a file using a `for` loop just as if it were an array of strings. This does not read all data into memory at once, and so is much more efficient that reading the file with `.readlines` and then looping over the resulting list.


```python
# as an iterable
fileObj = open( "data/datafile.txt" )

for line in fileObj:
    print(line.rstrip().upper())

fileObj.close()
```

### The with statement

It is important that files are closed when they are no longer required, but writing ``fileObj.close()`` is tedious (and more importantly, easy to forget). An alternative syntax is to open the files within a ``with`` statement, in which case the file will automatically be closed at the end of the `with` block.


```python
# fileObj will be closed when leaving the block
with open( "data/datafile.txt" ) as fileObj:
    for ( i, line ) in enumerate( fileObj, start = 1 ):
        print("%s: %r" % ( i, line ))
```

### Writing to files

Once a file has been opened for writing, you can use the `.write()` method on a file object to write data to the file.

The argument to the `.write()` method must be a string, so if you want to write out numerical data to a file you will have to convert it to a string somehow beforehand.

<div class="alert-warning">**Remember** to include a newline character `\n` to separate lines of your output, unlike the `print()` statement, `.write()` does not include this by default.</div>


```python
marks = {
    'Luttapi': 43,
    'Dagini': 32,
    'Mayavi': 34
}

with open( "out.txt", "w" ) as output:
    output.write("Name\tMark\n")

    for mark in marks:
        line = "\t".join( [ mark, str(marks[mark]) ] )
        output.write(line + "\n")
```

To view the output file, open a terminal window, go to the directory where the file has been written, and print the content of the file using `cat` command or open it using your favourite editor:

```bash
cat out.txt
```

Be cautious when opening a file for writing, as python will happily let you overwrite any existing data in the file. 

## Data formats

JSON, XML, CSV, txt are a few common Data formats. You can learn more about those from various websites. Go on and search and read about them. 

Delimited file example:
```
X 169008682 1 111267453 1.0976
2 8265484 5 69763543 4.9825
MT 10924 MT 81934 7.2357
3 127 8 10908776 1.2509
```

### Reading delimited files

We can use the various string manipulation techniques covered earlier to process delimited files in a fairly straightforward way. Here we loop through a file with columns delimited by spaces, reading the data for each row into a list, and storing each of these lists into a main results list.

To view the an example of a delimited file, open a terminal window, go to the course directory, and print the content of the file using `cat` command or open it using your favourite editor:

```bash
cat data/mydata.txt
```

```
Index Organism Score
1 Human 1.076
2 Mouse 1.202
3 Frog 2.2362
4 Fly 0.9853
```


```python
results = []

with open("data/mydata.txt", "r") as data:
    header = data.readline()
    for line in data:
        line = line.strip()
        results.append(line.split(" "))
        
print(results)
```

Here we show a slightly more complicated example where we are reading the results into a more convenient data structure, a list of dictionaries with the dictionary keys corresponding to the column headers and the values to the values from each line. We also convert the columns to an appropriate type as we go.


```python
results = []

with open("data/mydata.txt", "r") as data:
    header = data.readline()
    for line in data:
        idx, org, score = line.strip().split(" ")
        row = {'Index': int(idx), 'Organism': org, 'Score': float(score)}
        results.append(row)
        
print(results)
print('Score of first row:', results[0]['Score'])
```

### Writing delimited files

Writing out a delimited file is also straightforward using the `join` method. Here, as an example we will recreate our original file from above, but this time we will delimit the columns with a comma.


```python
mydata = [{'Organism': 'Human', 'Index': 1, 'Score': 1.076}, 
          {'Organism': 'Mouse', 'Index': 2, 'Score': 1.202}, 
          {'Organism': 'Frog', 'Index': 3, 'Score': 2.2362}, 
          {'Organism': 'Fly', 'Index': 4, 'Score': 0.9853}]

with open('data/mydata.csv', 'w') as output:
    # write a header
    header = ",".join(['Index', 'Organism', 'Score'])
    output.write(header + "\n")
    for row in mydata:
        line = ",".join([str(row['Index']), row['Organism'], str(row['Score'])])
        output.write(line + "\n")
```

To view the output file, open a terminal window, go to the course directory, and print the content of the file using `cat` command or open it using your favourite editor:

```bash
cat data/mydata.csv
```

```
Index,Organism,Score
1,Human,1.076
2,Mouse,1.202
3,Frog,2.2362
4,Fly,0.9853
```

<div class="alert-warning">**NOTE** that there is actually a module in the standard library called `csv` which can also be used to read and write delimited files. There is example code reading this same file using this library towards the end of this notebook.</div>

## Importing modules and libraries

Like other laguages, Python has the ability to import external modules (or libraries) into the current program. These modules may be part of the standard library that is automatically included with the Python installation, they may be extra libraries which you install separately or they may be other Python programs you have written yourself. Whatever the source of the module, they are imported into a program via an <tt>import</tt> command.

For example, if we wish to access the mathematical constants pi and e we can use the import keyword to get [the module named `math`](https://docs.python.org/3/library/math.html) and access its contents with the dot notation:


```python
import math
print(math.pi, math.e)
```

Also we can use the `as` keyword to give the module a different name in our code, which can be useful for brevity and avoiding name conflicts:


```python
import math as m
print(m.pi, m.e)
```

Alternatively we can import the separate components using the `from … import` keyword combination, like we've seen in the [previous session](Introduction_to_python_day_2_session_2.ipynb#Modules):


```python
from math import pi, e
print(pi, e)
```

We can import multiple components from a single module, either on one line like as seen above or on separate lines:


```python
from math import pi
from math import e
```

### Listing module contents

Using the [method `dir()`](https://docs.python.org/3/library/functions.html?highlight=dir#dir) and passing the module name:


```python
import math
dir(math)
```

or directly using an instance, like with this String:


```python
dir("mystring")
```

or using the object type


```python
dir(str)
```

### Getting quick help on method

After listing all contents, you may wish to display specific information on a method using [`help()`](https://docs.python.org/3/library/functions.html?highlight=help#help)


```python
help(str.title)
```

### Getting help from the official Python documentation

The most useful information is online on https://www.python.org/ website and should  be used as a reference guide.

- [Python 3.5.2 documentation](https://docs.python.org/3/) is the starting page with links to tutorials and libraries' documentation for Python 3
    - [The Python Tutorial](https://docs.python.org/3/tutorial/index.html)
        - [Modules](https://docs.python.org/3/tutorial/modules.html)
        - [Brief Tour of the Standard Library: Mathematics](https://docs.python.org/3/tutorial/stdlib.html#mathematics)
    - [The Python Standard Library Reference](https://docs.python.org/3/library/index.html) is the documentation of all libraries included within Python as well as built-in functions and data types like:
        - [Text Sequence Type — `str`](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)
        - [`math` — Mathematical functions](https://docs.python.org/3/library/math.html)
        - [`csv` — CSV File Reading and Writing](https://docs.python.org/3/library/csv.html)
        - [`os` — Miscellaneous operating system interfaces](https://docs.python.org/3/library/os.html)
        - [`os.path` — Common pathname manipulations](https://docs.python.org/3/library/os.path.html)

## Using the `csv` module

The so-called CSV (Comma Separated Values) format is the most common import and export format for spreadsheets and databases. The csv module implements methods to read and write tabular data in CSV format.

The csv module’s `reader()` and `writer()` methods read and write CSV files. You can also read and write data into dictionary form using the `DictReader()` and `DictWriter()` methods.

For more information about this built-in Python library about [CSV File Reading and Writing documentation](https://docs.python.org/3/library/csv.html).

Let's now read our `data/mydata.txt` file using the `csv` module.


```python
import csv
with open("data/mydata.txt") as f:
    reader = csv.reader(f, delimiter = " ") # default delimiter is ","
    for row in reader:
        print(row)
```

Change the `csv.reader()` by the `csv.DictReader()` and it builds up a dictionary automatically based on the column headers.


```python
with open("data/mydata.txt") as f:
    reader = csv.DictReader(f, delimiter = " ")
    for row in reader:
        print(row)
```


```python
# Write tab delimited files using the csv module
import csv

mydata = [
    ['1', 'Human', '1.076'], 
    ['2', 'Mouse', '1.202'], 
    ['3', 'Frog', '2.2362'], 
    ['4', 'Fly', '0.9853']
]

with open("csvdata.tsv", "w") as f:
    writer = csv.writer(f, delimiter='\t' )
    writer.writerow( [ "Index", "Organism", "Score" ] ) # write header
    for record in mydata:
        writer.writerow( record )

# Open the output file and print out its content
with open("csvdata.tsv") as f:
    print(f.read())
```


```python
# Write delimited files using the csv module from a list of dictionaries 
import csv

mydata = [
    {'Index': '1', 'Score': '1.076', 'Organism': 'Human'}, 
    {'Index': '2', 'Score': '1.202', 'Organism': 'Mouse'}, 
    {'Index': '3', 'Score': '2.2362', 'Organism': 'Frog'}, 
    {'Index': '4', 'Score': '0.9853', 'Organism': 'Fly'}
]

with open("csvdictdata.tsv", "w") as f:
    writer = csv.DictWriter(f, mydata[0].keys(), delimiter='\t')
    writer.writeheader() # write header

    for record in mydata:
        writer.writerow( record )

# Open the output file and print out its content
with open("csvdictdata.tsv") as f:
    print(f.read())
```

## Python file library

### [`os.path` — Common pathname manipulations](https://docs.python.org/3/library/os.path.html)

- `exists(path)` : returns whether path exists
- `isfile(path)` : returns whether path is a “regular” file (as opposed to a directory)
- `isdir(path)` : returns whether path is a directory
- `islink(path)` : returns whether path is a symbolic link
- `join(*paths)` : joins the paths together into one long path
- `dirname(path)` : returns directory containing the path
- `basename(path)` : returns the path minus the dirname(path) in front
- `split(path)` : returns (dirname(path), basename(path))

### [`os` — Miscellaneous operating system interfaces](https://docs.python.org/3/library/os.html)

- `chdir(path)` : change the current working directory to be path
- `getcwd()` : return the current working directory
- `listdir(path)` : returns a list of files/directories in the directory path
- `mkdir(path)` : create the directory path
- `rmdir(path)` : remove the directory path
- `remove(path)` : remove the file path
- `rename(src, dst)` : move the file/directory from src to dst

Building the path to your file from a list of directory and filename makes your script able to run on any platforms.


```python
import os.path
os.path.join("data", "mydata.txt")
# data/mydata.txt - Unix
# data\mydata.txt - Windows
```

Check if a file exists before opening it:


```python
import os.path
data_file = os.path.join("data", "mydata.txt")
if os.path.exists(data_file):
    print("file", data_file, "exists")
    with open(data_file) as f:
        print(f.read())
else:
    print("file", data_file, "not found!")
```

## Congratulation! You reached the end of the tutorial! 







