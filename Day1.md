# Introduction to Python


Python is a versatile, high-level programming language known for its simplicity and readability. Developed by Guido van Rossum and first released in 1991, Python has become one of the most popular programming languages, thanks to its ease of use and vast ecosystem of libraries.

#### Key Features of Python
- Simple and Readable Syntax: Python’s syntax resembles English, making it beginner-friendly and easy to read and understand.
- Interpreted Language: Python code is executed line by line, which simplifies debugging and reduces development time.
- Dynamic Typing: You don’t need to declare variable types explicitly, as Python infers them automatically.
- Vast Library Support: Python has libraries for almost everything—data analysis, web development, machine learning, and more.
- Cross-Platform Compatibility: Python runs on various platforms (Windows, Mac, Linux), making it very versatile.

## First Python Program

**Hello World**

```python
print("Hello World")
```

Output: Hello World

**Make a triangle

```Python
print("*")
print("**")
print("***")
print("****")
print("*****")
```
Output:


<br/>*<br/>
** <br/>
*** <br/>
**** <br/>
***** <br/>

** Modified triangle
```python
print("*")
print("*"*2)
print("*"*3)
print("*"*4)
print("*"*5)
```
Output:
<br/>*<br/>
** <br/>
*** <br/>
**** <br/>
***** <br/>

print("*" * 2): This expression treats `"*"` as a string and multiplies (or repeats) it by the specified number, in this case, `2`. As a result, Python outputs `"**"`. Here, the `*` operator functions as a repetition operator rather than an arithmetic operator, which is why it works with strings. This feature is specific to Python’s handling of strings, allowing various string operations, such as concatenation, repetition, slicing, and more.


## Variables: 
Python variables are a container that can store any type of value and of any particular size. Unlike other languages such as C, Java - Variables in Python don't need initialization. Let's create a variable to see how do they work


**input: To get an input from user. We use input() function.

```Python
a = input("Enter Your Name?")
print(a)
```
Output:Enter Your Name?Deepak

**Variable_Initialization:


```python
var1 = "Deepak"
print(var1)
```
Output:Deepak
```python
var2 = 6
print(var2)
```
Output:6

```python
number = input("What's your favourite number? ")
print(number)
```
Output: 5

```python
name = input("Enter your name : ")
print("Welcome", name)
```
Output: Welcome Deepak

```python
#That was helpful, could I also perform operation on input received?
age = input("Enter your age : ")
print("You are " , age*12 , " months old")
```
Output:
Enter your age :  30 <br/>
You are  303030303030303030303030  months old

**Note: The input() function in Python always takes input from the user as a string. If we need to use the input as a different data type (e.g., integer or float), we must convert (or cast) the string to the desired data type. This process is known as type casting.

Examples of Type Casting:

- To convert a user input to an integer, use int().
- To convert it to a float, use float().
- To ensure the input is stored as a boolean, use bool().


```python
age = input("enter your age ")
age = int(age)
print("You are " , age*12 , " months old")
```
Output:enter your age  30
You are  360  months old

**Find out the data type of particular variable, We use type(variable_name)

```python
integer_num = 1
floating_num = 1.3
string = 'Deepak'
boolean = True

print (type(integer_num))
print (type(floating_num))
print (type(string))
print (type(boolean))
```

<class 'int'>  <br/>
<class 'float'> <br/>
<class 'str'> <br/>
<class 'bool'> <br/>

## Type Casting in python:

```python
a=1
print(int(a))
print(float(a))
print(str(a))
print(bool(a))
```
Output:
<br/>1<br/>
1.0<br/>
1<br/>
True<br/>


## Data types in python: 
Data types define the kind of values that can be stored in a variable. Python supports several built-in data types, each with its own properties and usage

| Assigning Data Type                          | Data Type  |
|----------------------------------------------|------------|
| x = "Hello World"                            | str        |
| x = 20                                       | int        |
| x = 20.5                                     | float      |
| x = 1j                                       | complex    |
| x = ["apple", "banana", "cherry"]            | list       |
| x = ("apple", "banana", "cherry")            | tuple      |
| x = range(6)                                 | range      |
| x = {"name" : "John", "age" : 36}            | dict       |
| x = {"apple", "banana", "cherry"}            | set        |
| x = frozenset({"apple", "banana", "cherry"}) | frozenset  |
| x = True                                     | bool       |
| x = b"Hello"                                 | bytes      |
| x = bytearray(5)                             | bytearray  |
| x = memoryview(bytes(5))                     | memoryview |
| x = None                                     | NoneType   |

** Setting Specific data type:

| Example                                      | Data Type  |
|----------------------------------------------|------------|
| x = str("Hello World")                       | str        |
| x = int(20)                                  | int        |
| x = float(20.5)                              | float      |
| x = complex(1j)                              | complex    |
| x = list(("apple", "banana", "cherry"))      | list       |
| x = tuple(("apple", "banana", "cherry"))     | tuple      |
| x = range(6)                                 | range      |
| x = dict(name="John", age=36)                | dict       |
| x = set(("apple", "banana", "cherry"))       | set        |
| x = frozenset(("apple", "banana", "cherry")) | frozenset  |
| x = bool(5)                                  | bool       |
| x = bytes(5)                                 | bytes      |
| x = bytearray(5)                             | bytearray  |
| x = memoryview(bytes(5))                     | memoryview |


## Operations in Python

Python divides the operators in the following groups:

Arithmetic operators
Assignment operators
Comparison operators
Logical operators
Identity operators
Membership operators
Bitwise operators


**Arithmetic Operators:

| Operator | Name           | Example |
|----------|----------------|---------|
| +        | Addition       | x + y   |
| -        | Subtraction    | x - y   |
| *        | Multiplication | x * y   |
| /        | Division       | x / y   |
| %        | Modulus        | x % y   |
| **       | Exponentiation | x ** y  |
| //       | Floor division | x // y  |



```python
a = 6
b = 7
print("Addition  = ", a + b)  
print("Substraction = ", a - b) 
print("Multiplication = ", a * b) 
print("Division = ", a / b)
print("Floor Division = ", a // b) 
print("Modulus or remainder",a % b) 
print("Exponential = ", a ** b)
```

Output:
Addition  =  13
Substraction =  -1
Multiplication =  42
Division =  0.8571428571428571
Floor Division =  0
Modulus or remainder 6
Exponential =  279936


**Assignment Operators

| Operator | Example       | Same As    |
|----------|---------------|------------|
| =        | x = 5         | x = 5      |
| +=       | x += 3        | x = x + 3  |
| -=       | x -= 3        | x = x - 3  |
| *=       | x *= 3        | x = x * 3  |
| /=       | x /= 3        | x = x / 3  |
| %=       | x %= 3        | x = x % 3  |
| //=      | x //= 3       | x = x // 3 |
| **=      | x **= 3       | x = x ** 3 |
| &=       | x &= 3        | x = x & 3  |
| |=       | x |= 3        | x = x | 3  |
| ^=       | x ^= 3        | x = x ^ 3  |
| >>=      | x >>= 3       | x = x >> 3 |
| <<=      | x <<= 3       | x = x << 3 |
| :=       | print(x := 3) | x = 3      |
|          | print(x)      |            |

**Comparison Operators

| Operator | Name                     | Example |
|----------|--------------------------|---------|
| ==       | Equal                    | x == y  |
| !=       | Not equal                | x != y  |
| >        | Greater than             | x > y   |
| <        | Less than                | x < y   |
| >=       | Greater than or equal to | x >= y  |
| <=       | Less than or equal to    | x <= y  |


**Logical Operators

| Operator | Description                                             | Example               |
|----------|---------------------------------------------------------|-----------------------|
| and      | Returns True if both statements are true                | x < 5 and  x < 10     |
| or       | Returns True if one of the statements is true           | x < 5 or x < 4        |
| not      | Reverse the result, returns False if the result is true | not(x < 5 and x < 10) |

**Bitwise Operators

| Operator | Name                 | Description                                                                                             | Example |
|----------|----------------------|---------------------------------------------------------------------------------------------------------|---------|
| &        | AND                  | Sets each bit to 1 if both bits are 1                                                                   | x & y   |
| |        | OR                   | Sets each bit to 1 if one of two bits is 1                                                              | x | y   |
| ^        | XOR                  | Sets each bit to 1 if only one of two bits is 1                                                         | x ^ y   |
| ~        | NOT                  | Inverts all the bits                                                                                    | ~x      |
| <<       | Zero fill left shift | Shift left by pushing zeros in from the right and let the leftmost bits fall off                        | x << 2  |
| >>       | Signed right shift   | Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off | x >> 2  |

**Membership Operators

| Operator | Description                                                                      | Example    |
|----------|----------------------------------------------------------------------------------|------------|
| in       | Returns True if a sequence with the specified value is present in the object     | x in y     |
| not in   | Returns True if a sequence with the specified value is not present in the object | x not in y |



**Operator Precedence

| Operator                                     | Description                                           |
|----------------------------------------------|-------------------------------------------------------|
| ()                                           | Parentheses                                           |
| **                                           | Exponentiation                                        |
| +x  -x  ~x                                   | Unary plus, unary minus, and bitwise NOT              |
| *  /  //  %                                  | Multiplication, division, floor division, and modulus |
| +  -                                         | Addition and subtraction                              |
| <<  >>                                       | Bitwise left and right shifts                         |
| &                                            | Bitwise AND                                           |
| ^                                            | Bitwise XOR                                           |
| |                                            | Bitwise OR                                            |
| ==  !=  >  >=  <  <=  is  is not  in  not in | Comparisons, identity, and membership operators       |
| not                                          | Logical NOT                                           |
| and                                          | AND                                                   |
| or                                           | OR                                                    |



## String Operations

- **Strings are immutable:** In Python, strings are immutable, meaning that once a string object is created, its value cannot be changed. If you try to modify a string directly, a new string object is created instead.
- **String delimiters:** Strings in Python can be enclosed in either single quotes (') or double quotes ("), and both are functionally equivalent. The choice between them often depends on personal preference or the need to avoid escaping quotes inside the string.
- **Multiline strings:** Strings can also be defined using triple quotes (''' or """), which allow for multi-line strings.

```python
name = "Deepak"
name_1 = 'Deepak'
print(name, ' ',name_1)
```
Output: Deepak   Deepak

**Escape Character \

```python
print('I don't know')
```
Output: SyntaxError: unterminated string literal (detected at line 1)

This error occurs when you have a string enclosed in single quotes (') and you try to use another single quote inside the string. Since Python treats the single quote as the string delimiter, it causes a syntax error.

There are two main ways to fix this:

Use double quotes (") to define the string: You can simply use double quotes to enclose the string, which allows the single quote (') to appear inside the string without any issue.
Example:

```python
str1 = "I don't know"  # Correct
```

Escape the single quote using a backslash (\): You can escape the special character (the single quote) inside the string by using a backslash (\). This tells Python to treat the quote as a character rather than a string delimiter.

```python
str2 = 'I don\'t know'  # Correct
```


### String Concatenation:

```python
first_name = input("Enter your first Name?")
Last_name = input("Enter your last Name?")
Full_name = 'Welcome to our Coffee Shop: ' + first_name + ' ' + Last_name
print(Full_name)
```
Output:

 <br/>Enter your first Name? Deepak  <br/>
Enter your last Name? Kumar  <br/>
Welcome to our Coffee Shop:  Deepak   Kumar

** TO calculate length of the string, we use len() function
```python
len(Full_name)
```
output: 40

### Indexing In Strings <br>
- Forward indexing starts with 0
- Reverse indexing starts with the last character as -1 in a python string
- Strings are immutable which, means they cannot be changed once created.
- Strings can be modified by slicing a part of it and concatenating with another

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
```

** print the 11th index string

```python
print(string[10])
```
output: o

** print the last 11th index string

```python
print(string[-11])
```
output: a

**Trying to change the character at index 2

```python
string[2] = 't'
```
output: 'str' object does not support item assignment

As string are mutable, we can't change them. Instead we can assign it again or in new variable.

```Python
string = "Wt may encounter many defeats, but we must not be defeated.— Maya Angelou"
print(string)
```
output:Wt may encounter many defeats, but we must not be defeated.— Maya Angelou

#### Slicing in Strings 
Syntax: string[start_step:end_step:skipstep]

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
sliced_string = string[0:21]
print(sliced_string)
```
Output: We may encounter many

skip 2 steps

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
sliced_string = string[0:21:2]
print(sliced_string)
```
Output: W a none ay

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
sliced_string = string[:21:2]
print(sliced_string)
```

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
sliced_string = string[0::2]
print(sliced_string)
```

#### Membership Operators

```Python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
print('May' in string)
print('new' in string)
```
Output:<br/>
True<br/>
False<br/>


#### String methods

All string methods return new values. They do not change the original string.

| Method         | Description                                                                                   |
|----------------|-----------------------------------------------------------------------------------------------|
| capitalize()   | Converts the first character to upper case                                                    |
| casefold()     | Converts string into lower case                                                               |
| center()       | Returns a centered string                                                                     |
| count()        | Returns the number of times a specified value occurs in a string                              |
| encode()       | Returns an encoded version of the string                                                      |
| endswith()     | Returns true if the string ends with the specified value                                      |
| expandtabs()   | Sets the tab size of the string                                                               |
| find()         | Searches the string for a specified value and returns the position of where it was found      |
| format()       | Formats specified values in a string                                                          |
| format_map()   | Formats specified values in a string                                                          |
| index()        | Searches the string for a specified value and returns the position of where it was found      |
| isalnum()      | Returns True if all characters in the string are alphanumeric                                 |
| isalpha()      | Returns True if all characters in the string are in the alphabet                              |
| isascii()      | Returns True if all characters in the string are ascii characters                             |
| isdecimal()    | Returns True if all characters in the string are decimals                                     |
| isdigit()      | Returns True if all characters in the string are digits                                       |
| isidentifier() | Returns True if the string is an identifier                                                   |
| islower()      | Returns True if all characters in the string are lower case                                   |
| isnumeric()    | Returns True if all characters in the string are numeric                                      |
| isprintable()  | Returns True if all characters in the string are printable                                    |
| isspace()      | Returns True if all characters in the string are whitespaces                                  |
| istitle()      | Returns True if the string follows the rules of a title                                       |
| isupper()      | Returns True if all characters in the string are upper case                                   |
| join()         | Joins the elements of an iterable to the end of the string                                    |
| ljust()        | Returns a left justified version of the string                                                |
| lower()        | Converts a string into lower case                                                             |
| lstrip()       | Returns a left trim version of the string                                                     |
| maketrans()    | Returns a translation table to be used in translations                                        |
| partition()    | Returns a tuple where the string is parted into three parts                                   |
| replace()      | Returns a string where a specified value is replaced with a specified value                   |
| rfind()        | Searches the string for a specified value and returns the last position of where it was found |
| rindex()       | Searches the string for a specified value and returns the last position of where it was found |
| rjust()        | Returns a right justified version of the string                                               |
| rpartition()   | Returns a tuple where the string is parted into three parts                                   |
| rsplit()       | Splits the string at the specified separator, and returns a list                              |
| rstrip()       | Returns a right trim version of the string                                                    |
| split()        | Splits the string at the specified separator, and returns a list                              |
| splitlines()   | Splits the string at line breaks and returns a list                                           |
| startswith()   | Returns true if the string starts with the specified value                                    |
| strip()        | Returns a trimmed version of the string                                                       |
| swapcase()     | Swaps cases, lower case becomes upper case and vice versa                                     |
| title()        | Converts the first character of each word to upper case                                       |
| translate()    | Returns a translated string                                                                   |
| upper()        | Converts a string into upper case                                                             |
| zfill()        | Fills the string with a specified number of 0 values at the beginning                         |



Samples:

```python
string = "We may encounter many defeats, but we must not be defeated.— Maya Angelou"
string.upper()
string.lower()
string.title()
```

'WE MAY ENCOUNTER MANY DEFEATS, BUT WE MUST NOT BE DEFEATED.— MAYA ANGELOU'
'we may encounter many defeats, but we must not be defeated.— maya angelou'
'We May Encounter Many Defeats, But We Must Not Be Defeated.— Maya Angelou'


```python
string1= '      new data in this      '
string1.strip()
```
Output: 'new data in this'

```python
string1= '      new data in this      '
string1.rstrip()
```
Output: 'new data in this      '

```python
string1= '      new data in this      '
string1.lstrip()
```
Output:'      new data in this'

```python
string1= '      new data in this      aaaa'
string1.rstrip('a')
```
Output: '      new data in this      '

```python
num_with_chars = '******444#######'
print(num_with_chars.rstrip('#').lstrip('*'))
```
Output: 444

### Count Method

```python
string = "This is a sample sentence"
print(string.count('i'))
print(string.count('i',5))
```

### Format Method

```python
A = "Data"
B = "Analysis"
C = "Pandas"

print("{0} {1} using {2}".format(A,B,C))
```

### Practice Questions:

#### Data Types:
1. What are the different data types in Python?
Ans. Python has int,string,bool,float,list,tuble,dict,none types of data types.

2. What is the difference between list and tuple in Python?
Ans. A list is mutable (its content can be changed), while a tuple is immutable (once created, its content cannot be modified).

3. How do you check the type of a variable in Python?
Ans. we use type(variable) to get the data type of variable

4. What is the difference between == and is operators in Python?
Ans. The == operator compares the values of two objects, while is checks whether two variables point to the same object in memory.

5. What are the mutable and immutable data types in Python?
Ans. list,dict,set are mutable data types in python and string, int,float,tuple and frozenset and immutable data types.

#### Variables:
1. What is a variable in Python, and how is it different from a constant?
Ans. A variable in Python is a name used to reference an object in memory, and it can be reassigned. Python doesn't have built-in support for constants, but by convention, uppercase variable names (e.g., PI = 3.14) are treated as constants.

2. Can you use a Python keyword as a variable name? Why or why not?
Ans. No, we cannot assign a variable using Python's reserved keywords (e.g., def, class, for), as they are predefined in the language syntax.

3. What will happen if you try to assign a variable with a name that is already used by a Python keyword?
Ans. We will be getting syntax error.

4. How do you assign multiple variables in a single line in Python?
Ans. 
```python
x, y, z = 5, 10, 15
print(x)  #Output: 5
print(y)  #Output: 10
print(z)  # Output: 15
```

5. What is the scope of a variable in Python?
Ans. The scope of a variable in Python refers to the region of the program where the variable can be accessed or modified. In Python, the scope of a variable is determined by where it is defined. There are four main types of variable scopes:
1. Local Scope:
Definition: Variables defined inside a function or block of code are said to have a local scope. These variables are only accessible within that function or block.

```python
def my_function():
    x = 10  # Local variable
    print(x)  # This works because x is in the local scope

my_function()
# print(x)  # This would raise a NameError because x is local to my_function
```

2. Enclosing (Nonlocal) Scope:
Definition: This scope exists when a function is nested inside another function. Variables in the outer function (but not global) are accessible in the inner function. These variables are referred to as nonlocal.

```python
def outer_function():
    x = 20  # Enclosing variable

    def inner_function():
        print(x)  # x is accessible here because it is in the enclosing scope
        
    inner_function()

outer_function()
```

3. Global Scope:
Definition: Variables defined outside of any function or class have a global scope. These variables are accessible throughout the entire program, and from any function, unless shadowed by a local variable.
```python
def outer_function():
    x = 20  # Enclosing variable

    def inner_function():
        print(x)  # x is accessible here because it is in the enclosing scope
        
    inner_function()

outer_function()
```

4. Built-in Scope:
Definition: This is the highest level of scope. Built-in scope contains the names of all Python's built-in objects, functions, and exceptions (e.g., print(), len(), int(), etc.). These are available throughout your program and can be accessed at any point.
```python
x = 50  # Global variable

def my_function():
    print(x)  # Global variable x can be accessed

my_function()  # Output: 50

```

#### String Methods:
1. How can you convert a string to lowercase in Python?
Ans. string.lower()

2. What is the use of the strip() method in Python?
Ans. When we have lots of junk space or continous character in a program. We use strip method.

3. How would you check if a string contains only numeric characters in Python?
Ans. We can use isnumeric()
```python
s = "12345"
print(s.isnumeric())  # Output: True
```

4. How can you replace a substring in a string with another substring in Python?
Ans. 
```python
s = "I love Python programming."
new_s = s.replace("Python", "Java")
print(new_s)  # Output: "I love Java programming."
```

5. What is the difference between find() and index() methods in Python strings?
Ans. The find() method returns the lowest index at which the substring is found in the string. If the substring is not found, it returns -1 whereas The index() method also returns the lowest index of the substring found within the string. If the substring is not found, it raises a ValueError exception.
   
#### String Indexing and Slicing:
1. What is string indexing in Python, and how does it work?
Ans. String indexing allows access to individual characters in a string using zero-based indices, with positive indices starting from the beginning and negative indices starting from the end.
2. How would you extract a substring from a string using slicing in Python?
Ans. using the syntax string[start:end], where start is the beginning index (inclusive) and end is the ending index (exclusive).
3. What happens if you try to index a string with an out-of-range index?
Ans. An IndexError will be raised if we try to access an index that is out of the valid range of the string.
4. What is the difference between negative indexing and regular indexing in Python strings?
Ans. Negative indexing allows us to access characters from the end of the string, with -1 referring to the last character, while regular indexing starts from 0 at the beginning of the string.
5. How do you reverse a string using slicing in Python?
Ans. string[::-1]
   
Bonus Questions:
1. What is the join() method in Python, and how does it work?
Ans. The join() method in Python concatenates elements of an iterable (e.g., list, tuple) into a single string, using the string on which it is called as a separator.
2. How does the format() method work in Python? Can you give an example of its usage?
Ans. The format() method allows us to insert variables into a string using curly braces {} as placeholders. For example, "Hello, {}".format(name).
3. What is the difference between the split() and join() methods in Python strings?
Ans. The split() method splits a string into a list of substrings, while join() combines elements of an iterable into a string.
4. How would you check if a string contains a specific substring in Python?
Ans. We can use in keyword, like 'substring' in string, to check if a string contains a specific substring.
5. What is the difference between string concatenation using + and using join()?
Ans. Using + for concatenation can be inefficient with large numbers of strings, while join() is more efficient as it avoids creating intermediate strings.

Coding Problems:

Question 1: Let us start by printing the word "Welcome to the practice exercise" in python.

```python
print("Welcome to the practice exercise")
```

Question 2: Create a string variable and print the string.
```python
string = "Welcome to the practice exercise"
print(string)
```

Question 3: Create a string by taking user input and print the string.


```python
string = input("Enter your name")
print(string)
```

Question 4: Print the pattern given below:
  1  
 234
56789

```python
print('  1  ')
print(' 234 ')
print('56789')
```

Question 5: Print the '#' symbol 15 times without having to type it for 15 times.
```python
print('#'*10)
```

Question 6: Take the user input to print the current date

```python
a_print = input("Enter the Date: ")
a_print
```

Question 7:Type cast the interger 1.8 into a string and print the result.

```python
a = 1.8
print(str(a))
```

Question 8: Find the product of two numbers input by the user.

```python
a = int(input("Enter the first numbers"))
b = int(input("Enter the second numbers"))
print(a * b)
```

Question 9: Calculate the remainder of the number 6 when divided by the number 4.

```python
a = 6
b = 4
print(a % b)
```

Question 10: Solve the error in code below and print the correct result.

print('I can't study any longer')

##### Corrected solution:
print('I can\'t study any longer')

Question 11: Print the following statement using only 1 print statement:

Hello

Good Morning

```python
print("Hello\n\nGood Morning")
```

Question 12: Concatenate the given strings and print the result:

```python
string1= 'Welcome to the'
string2= 'coding practice session.'
print(string1 + ' ' + string2)
```

Question 13: Find the length of string given below and print the result.

```python
a = "Welcome to the coding practice session."
print(len(a))
```

Question 14: Create a string of length=10. Obtain the fifth and seventh character of the string. Concatenate the characters and form a new string. Print the new string.

```python
# Create a string of length 12:
a = "We are venom"

# You can verify the length:
len(a)

# Obtain the fifth letter and store it into a new string:

b = a[4]

# Obtain the seventh letter and store it into a new string:

c = a[5]

# Concatenate the two strings:

d = b + c

# Print the result:
print(d)
```

Question 15: Given below is a string. Perform the following operations and print the results:

- Remove the extra spaces from the string and print the new string.
- Find the length of new string
- Remove the last 5 characters of the new string
- Find the 15th character of the new string
- Compute the result of concatenation of the first and last letter of the new string.

```python
# Given below is the string:
line= '     I hope you enjoyed this practice session.'

# Removing extra spaces:
line.strip()

# Print the result:
print(line.strip())

# Calculate the length:
print(len(line))

# Slice the string to remove the last 5 characters:
line1 = line[:-5]

# Print the result:
print(line1)

# Print the 15th character of the string:

print(line[15])

# Print the concatenation of first and last character of resulting string:
new = line1[0] + line1[-1]
print(new)
```

