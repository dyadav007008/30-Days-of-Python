# Day 3


## 1.Control structures
-  If-elif-else
-  For loop
-  While loop
-  List comprehensions
-  Dictionary comprehensions

## 2.Functions
## 3.Map
## 4.Filter
##  5.Reduce

## Control Structures and Functions
Control structures are the essence of programming; they help computers do what they do best: automate repetitive tasks intelligently. The most common control structures are if-else statements, for and while loops, and list and dictionary comprehensions. This session will cover all these concepts.


## Relational Operators:

- Compares the values on either side of the operator and returns and boolean value as True or False.

- ##### ' = ' is an assignment operator; it is used to assign value to a variable on the left.

- ##### '==' is a relational operator; it is used for comparision of equality.


| Operator | Name                     | Example | Result if, x=10, y = 10 | Result if, x=10, y = 11 |
|----------|--------------------------|---------|-------------------------|-------------------------|
| ==       | Equal                    | x == y  | TRUE                    | FALSE                   |
| !=       | Not equal                | x != y  | FALSE                   | TRUE                    |
| >        | Greater than             | x > y   | FALSE                   | FALSE                   |
| <        | Less than                | x < y   | FALSE                   | TRUE                    |
| >=       | Greater than or equal to | x >= y  | TRUE                    | FALSE                   |
| <=       | Less than or equal to    | x <= y  | TRUE                    | TRUE                    |



## Decision Making: If else Statements

If a condition is met then the action is executed.
Relational operators are used to test equality or inequality of a condition and that condition might change based on your preference.

Example -
If its raining == True:
  THEN I'll get an umbrella

SYNTAX:

```python
if condition:
    # Code to execute if the condition is True
else:
    # Code to execute if the condition is False
```

### Check if the number entered from the user is greater than 99 or not:

```python
### Check if the number entered from the user is greater than 99 or not:
num = int(input("Enter the number"))
if(num > 99):
    print("Number is Greater than 99")
else:
    print("Number is smaller than 99")
```
![image](https://github.com/user-attachments/assets/1f359a62-2c70-4e1e-9bf0-1fc9afac7c57)


## Decision Making: If else Statements

- ### Check if the number entered from the user is greater than 100,1000 or not:

```python
# elif Statement
num = int(input("Enter the number"))
if(num == 1000):
    print("Number is Equal to 1000")
elif(num > 1000):
    print("Number is Greater than 1000")
elif(num == 100):
    print("Number is Equal to 100")
elif(num > 100):
    print("Number is Greater than 100")
else:
    print("Number is smaller than 100")
```

![image](https://github.com/user-attachments/assets/357bd1c8-d0ee-4c5d-8233-4d121edc9839)

**Logical Operators**

| Operator | Description                                             | Example               |
|----------|---------------------------------------------------------|-----------------------|
| and      | Returns True if both statements are true                | x < 5 and  x < 10     |
| or       | Returns True if one of the statements is true           | x < 5 or x < 4        |
| not      | Reverse the result, returns False if the result is true | not(x < 5 and x < 10) |


**Bitwise Operators**

| Operator | Name                 | Description                                                                                             | Example |
|----------|----------------------|---------------------------------------------------------------------------------------------------------|---------|
| &        | AND                  | Sets each bit to 1 if both bits are 1                                                                   | x & y   |
| |        | OR                   | Sets each bit to 1 if one of two bits is 1                                                              | x | y   |
| ^        | XOR                  | Sets each bit to 1 if only one of two bits is 1                                                         | x ^ y   |
| ~        | NOT                  | Inverts all the bits                                                                                    | ~x      |
| <<       | Zero fill left shift | Shift left by pushing zeros in from the right and let the leftmost bits fall off                        | x << 2  |
| >>       | Signed right shift   | Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off | x >> 2  |


- # Write a program to record the age of visitor and allows him to an exclusive children's day party hosted by Mr Obama only if he or she is above 60 years or below 18 years of age
```python
# Logical Operators
# Write a program to record the age of visitor and allows him to an exclusive children's day party hosted by Mr Obama only 
## if he or she is above 60 years or below 18 years of age

age = int(input("Enter the age of Visitor"))
if(age < 18 or age > 60):
    print("Welcome to the party. Have Fun!")
else:
    print("Sorry, You are not eligible for the party")
```

![image](https://github.com/user-attachments/assets/4252ad61-91ef-4ac8-832c-deeaa02b7a62)

- # Write a program which offers various discount on purchase bills.

  ```python
shoppinng_total = 550

if shoppinng_total >= 500:
    print("You won a discount voucher of flat 15% on next purchase")
elif shoppinng_total >= 250:
    print("You won a discount voucher of flat 10% on next purchase")
elif shoppinng_total >= 100:
    print("You won a discount voucher of flat 5% on next purchase")    
else:
    print("OOPS!! no discount for you!!!")
  ```

shoppinng_total = 550

if shoppinng_total >= 500:
    print("You won a discount voucher of flat 1000 on next purchase")
elif shoppinng_total >= 250:
    print("You won a discount voucher of flat 500 on next purchase")
elif shoppinng_total >= 100:
    print("You won a discount voucher of flat 100 on next purchase")    
else:
    print("OOPS!! no discount for you!!!")

```

## Loops and Iteration and Python

### While Loop


Syntax:
while condition:
    # Code to execute as long as the condition is True

```python
x = 0

while x < 5:
    print(x)
    x += 1  # Increment x by 1 each time
```

## Check if the pin entered by the user is valid or not. If not let the user try again

```python
pin = input("Enter the 4 digit pin")
while pin != '1234':
    pin = input("!Invalid Pin. Try again")
print("Pin validation Successful")
```



## Lets try to add max of 3 tries and if user fails to identify . we will print a message of attempted tries
```python
attempt = 0
max_attempt = 3
correct_pin = '1234'
while attempt < max_attempt:
    pin = input("Enter the 4 digit pin: ")
    if(pin == correct_pin):
        print("Pin Validation Successfull")
        break
    else:
        attempt += 1
        if attempt < max_attempt:
            print(f"!Invalid Pin. You have {max_attempt - attempt} tries left.")
        else:
            print("Maximum attempts reached. You have been locked out.")
```


## for loop:

```python
# for loop
# iterate over a list of string
a = "One Piece is the best anime in the world"
for var in a:
    print(var,end=':')
```

```python
# for loop
# iterate over a list of string
a = "One Piece is the best anime in the world"
for var in a:
    print(var)
```

```python
# Iterating over dictionary

student_data = {1:["deepak",10],2:["Juhi",15],3:["Harshita",29],4:["Kalpana",40],5:["Robert Downy Jr",3000]}
student_data
for key, val in student_data.items():
    print(key, val)

```

Output:
1 ['deepak', 10]
2 ['Juhi', 15]
3 ['Harshita', 29]
4 ['Kalpana', 40]
5 ['Robert Downy Jr', 3000]


Range:

```python
# range
for i in range(1,5):
    print(i,end = ',')
```
Output: 1,2,3,4,5
```python
list1 = [1,4,2,6,4,7,8]

for i in range(len(list1)):
    print(list1[i])
```

Output :
1
4
2
6
4
7
8

```python
print(list(range(1,100,2))) # print range of 1 to 100 with a skip step of 2
```

Output: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]

## check if a number is prime or not:

```python
# Function to check if a number is prime
def is_prime(num):
    if num <= 1:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

# List to store prime numbers
prime_numbers = []

# Loop through numbers from 1 to 20
for number in range(1, 21):
    if is_prime(number):
        prime_numbers.append(number)

print("Prime numbers between 1 and 20:", prime_numbers)
```

Prime numbers between 1 and 20: [2, 3, 5, 7, 11, 13, 17, 19]


## Comprehensions

li = ["Arun","Deepak","Joker","Mohit","Shubham","Chahat"]


## List Comprehensions:

```python
# Functional Approach:
# List Comprehension
L2 = [len(word) for word in li]
l2
```


```python
# iterating over li and l2 simutaneously

for i,j in zip(li,l2):
    print(i," - ", j)
```

Output:
Arun  -  4
Deepak  -  6
Joker  -  5
Mohit  -  5
Shubham  -  7
Chahat  -  6


## Dictionary Comprehension:

```python
## dicionary comrehension
d = {word:len(word) for word in li}
d
```
{'Arun': 4, 'Deepak': 6, 'Joker': 5, 'Mohit': 5, 'Shubham': 7, 'Chahat': 6}



## Set Comprehension
## Write a program which takes a word as input from user and returns vowels from the word 

```python
# Set Comprehension
# Write a program which takes a word as input from user and returns vowels from the word 
word = input("Enter a word: ")
vowels = {char for char in word if char in "aeiouAEIOU"}
vowels
```
Output:
Enter a word:  dEEPAK
{'A', 'E'}

## Funtions:

-Function is a block of reusable code that is used to perform a specific task. Functions help in organizing code, reducing redundancy, and improving the readability and maintainability of your programs.

### Defining a Function in Python
A function in Python is defined using the def keyword, followed by the function name and parentheses (optional parameters inside parentheses). The function body starts with an indentation level.

### Syntax:
```python
Copy code
def function_name(parameters):
    # Function body
    # Code to execute
    return result 
```
def: The keyword used to define a function.
function_name: The name of the function, which is called to execute the code inside it.
parameters: Optional values passed to the function (can be zero or more).
return: Optional statement used to send back a result from the function.


- Function are user defined and inbuilt function. input() is an example of built in Functions.

### Write a function which takes a values as a parameter and returns its factorial.

```python
# write a function that takes a value and return its factorial
def factorial_func(n):
    fact = 1
    for i in range(1,n+1):
        fact = fact*i
    return(fact)
factorial_func(5)
```
Output: 120


## Function Parameters in Python
- When defining functions in Python, we can specify parameters, which are placeholders for the values that will be passed to the function when it is called. These parameters allow us to pass data into a function and use that data within the function body. There are different types of parameters you can use depending on your needs.

## Types of Function Parameters in Python
- Positional Parameters
- Default Parameters
- Keyword Parameters
- Variable-Length Parameters (*args and **kwargs)

1. Default Parameters
We can assign default values to function parameters. If no argument is passed for that parameter when the function is called, the default value will be used.

```python
def greet(name, age=25):
    print(f"Hello, {name}. You are {age} years old.")

# Calling the function with one argument
greet("Bob")  # Outputs: Hello, Bob. You are 25 years old.

# Calling the function with both arguments
greet("Alice", 30)  # Outputs: Hello, Alice. You are 30 years old.
```

2. Keyword Parameters
Keyword parameters allow us to pass arguments to a function by explicitly specifying the parameter names. This can make our code more readable and allow arguments to be passed in any order.

```python
def greet(name, age):
    print(f"Hello, {name}. You are {age} years old.")

# Calling the function with keyword arguments
greet(age=30, name="Charlie")  # Outputs: Hello, Charlie. You are 30 years old.

```

3. Positional Parameters
These are the most common type of parameters. When you call a function, the arguments you provide are assigned to parameters in the order in which they appear in the function definition.
```python
def greet(name, age):
    print(f"Hello, {name}. You are {age} years old.")

# Calling the function with positional arguments
greet("Alice", 30)  # Outputs: Hello, Alice. You are 30 years old.
```

4. Variable-Length Parameters
*args (Non-keyword Variable-Length Arguments)
We can pass a variable number of positional arguments to a function using *args. args is a tuple that collects all additional positional arguments passed to the function.

```python
def add(*args):
    return sum(args)

# Calling the function with multiple arguments
print(add(1, 2, 3))  # Outputs: 6
print(add(10, 20, 30, 40, 50))  # Outputs: 150
```
```python
def var_func(*args):
  print(args)

var_func(1,2,3,4,"abs")
```

## Summary:

| Parameter Type             | Syntax             | Example Usage                                                      |
|----------------------------|--------------------|--------------------------------------------------------------------|
| Positional Parameters      | def func(a, b)     | func(10, 20) → a=10, b=20                                          |
| Default Parameters         | def func(a, b=5)   | func(10) → a=10, b=5                                               |
| Keyword Parameters         | def func(a, b)     | func(a=10, b=20) → a=10, b=20                                      |
| Variable-Length Positional | def func(*args)    | func(10, 20, 30) → args = (10, 20, 30)                             |
| Variable-Length Keyword    | def func(**kwargs) | func(name="Alice", age=25) → kwargs = {'name': 'Alice', 'age': 25} |

# Lambda Function:

In Python, lambda functions are small, anonymous (unnamed) functions that are defined using the lambda keyword. These functions can take any number of arguments but only contain a single expression. Lambda functions are primarily used when we need a simple function for a short duration, typically when working with functions like map(), filter(), or sorted().

- Syntax:  lambda arguments: expression
  
## Key Features of Lambda Functions:
- Anonymous: Lambda functions do not have a name.
- Single Expression: They can only contain one expression. No statements or multiple expressions are allowed.
- Return Value: Automatically returns the result of the expression without needing the return keyword.

## Limitations of Lambda Functions:
- Single Expression: Lambda functions can only have one expression. You cannot write complex logic or multiple statements inside a lambda function.
- Not Readable for Complex Operations: When the logic inside the lambda becomes complex, it is often better to define a regular function for clarity.

- Write a lambda function to check if a number is even or odd.

```python
f = lambda x: "Even" if x % 2 ==0 else "odd"
f(int(input("Enter the number :")))
```

## Map, Filter and Reduce Function:

### Map Function:

The map() function in Python allows you to apply a specified function to each item in an iterable (like a list, tuple, etc.), and it returns a map object (which is an iterator) that produces the transformed results. The map() function is particularly useful when you need to apply the same operation to every element of an iterable.

Syntax: map(function, iterable)

```python
# map Function
l1 = ["Deepak","Juhi","Harshita","Abhishek","Kalpana"]
def upper1(n):
     return n.upper()
l2 = map(upper1,l1)
print(list(l2))
```
['DEEPAK', 'JUHI', 'HARSHITA', 'ABHISHEK', 'KALPANA']

## The filter() Function in Python
The filter() function in Python is used to filter elements from an iterable (like a list, tuple, etc.) based on a function that tests each element. It returns an iterator that contains only the elements for which the function returns True.

Syntax: filter(function, iterable)

```print
# Filter function
natural_number = [1,3,24,5,65,4,3,12,3,4,6,7,5]
def iseven(n):
    return n%2==0
new = list(filter(iseven, natural_number))
new
```

## Write a program to count the students with age above 18

```python
## Write a program to count the students with age above 18
# lets define a dictionary
dict1 = {1:["Deepak",20],2:["Juhi",20],3:["Kalpana",19],4:["Gopal",5],5:["Abhishek",16],6:["Arun",18]}
values = [val[1] for val in dict1.values()]
def plus18(n):
    return n > 18
new = list(filter(plus18,values))
print(len(new))
```

# reduce() Function in Python
The reduce() function is part of the functools module in Python. It applies a binary function (a function that takes two arguments) cumulatively to the items of an iterable, from left to right, so as to reduce the iterable to a single value.

Syntax: 
from functools import reduce
reduce(function, iterable[, initializer])

```python
from functools import reduce
l5 = [1,4,2,3,5]
mul = reduce(lambda x,y : x*y,l5)
print(mul)
```




