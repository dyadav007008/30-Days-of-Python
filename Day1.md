# Introduction to Python

Python is a general-purpose programming language that was named after Monty Python. It is simple and incredibly readable since it closely resembles the English language. Unlike other languages Python program works on an Interpreter so to run a code all you have to do is type it out. Python language runs line by line, so incase you want to update a piece of code all you have to do is update the line.

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
*
**
***
****
*****

** Modified triangle
```python
print("*")
print("*"*2)
print("*"*3)
print("*"*4)
print("*"*5)
```
Output:
*
**
***
****
*****

print("*"*2): This is taking * as a string and will copy it will the mentioned number. This will happen as python wont be consider * as an operator . Instead it is considering it as a string. We can perform various function on string.

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
Enter your age :  30
You are  303030303030303030303030  months old

**Note: Input command will always take input from user in String. If we have to take input in other data type. We have to convert string to desired data type. This conversion is known as TYPE Casting.


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

<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>

## Type Casting in python:

```python
a=1
print(int(a))
print(float(a))
print(str(a))
print(bool(a))
```
Output:
1
1.0
1
True


## Data types in python: 
Python offers multiple data types. We'll learn each in details later.

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


