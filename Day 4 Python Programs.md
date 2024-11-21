# Python Programs

## Beginner-Level Questions:
- Write a Python program to check if a Number is Even or Odd.
- Write a Python program to Count Words in a Sentence.
- Write a Python program to Reverse a String.
- Write a Python program to Count Vowels in a String.
- Write a Python program to check for Leap Year.
- Write a Python program to convert Celsius to Fahrenheit.
- Write a Python program to Remove Duplicates from a String.
- Write a Python program to check for Pangram.
- Write a Python program to find the Minimum Element in a List.
- Write a Python program to find the Maximum Element in a List.
- Write a Python program to check if a Number is a Prime Factor.
- Write a Python program to find the Maximum Difference between Two Elements in a List.
- Write a Python program to Convert Decimal to Binary.
- Write a Python program to Find Second Largest Element in a List.
## Intermediate-Level Questions:
- Write a Python program to Merge Two Sorted Lists.
- Write a Python program to Reverse Words in a String.
- Write a Python program to Check for Perfect Numbers.
- Write a Python program to Find the Fibonacci Sequence.
- Write a Python program to find Anagram Check.
- Write a Python program to Find the Average Numbers in a List.
- Write a Python program to calculate the Sum of Digits in a Number.
- Write a Python program to check for Armstrong Number.
- Write a Python program to Check Palindrome.
- Write a Python program to calculate Factorial without Recursion.
- Write a Python program to Check Prime Numbers.
- Write a Python program to calculate LCM (Least Common Multiple) of Two Numbers.
## Advanced-Level Questions:
- Write a Python program to find Factorial with Recursion.
- Write a Python program to find the Fibonacci Sequence with Recursion.
- Write a Python program to perform basic Data Structure Operations (e.g., list manipulation, string manipulation).
- Write a Python program to check if a Number is a Power of Two.
- Write a Python program to find the Armstrong Number.
- Write a Python program to Merge Two Sorted Lists.
- Write a Python program to find the Maximum Element in a List with a User-Defined Function.
- Write a Python program to calculate Sum of Digits using Recursion.
- Write a Python program to calculate the Sum of Numbers using the Map function.
- Write a Python program to calculate the Fibonacci Series using Recursion.

## Write a Python program to check if a Number is Even or Odd.
```python
num = int(input("Enter the number to check if it is even or odd"))
if(num%2 == 0):
    print("Number is even")
else:
    print("Number is odd")
```

## Write a Python program to Count Words in a Sentence.

```python
str = "Hi! I am Deepak. I am learning data science"
words = len(str.split())
words
```

- Write a Python program to Reverse a String.
```python
str_1 = "Ninja"
def reverse(str_1):
    return str_1[::-1]
new_str = reverse(str_1)
print("The reverse of "+ str_1 , "is " +new_str)
```

- Write a Python program to Count Vowels in a String.
```python
str_1 = "Ninja"
def is_char(str_1):
    return str_1.lower() in 'aeiou'

str_2 = list(map(is_char,str_1))
vowel_count = sum(str_2)
vowel_count
```
  
- Write a Python program to check for Leap Year.
```python
a = 1994
if ((a % 4 == 0 and a % 100 !=0) or (a % 4 == 0 and a % 400 == 0)):
    print("This is a leap Year")
else:
    print("This is not a leap Year")
```
  
- Write a Python program to convert Celsius to Fahrenheit.
```python
# °F = °C * 1.8 + 32
cel = int(input("Enter the celsius"))
def farenheit(cel):
    return cel * 1.8 + 32
faren = farenheit(cel)
print(faren)
```

- Write a Python program to Remove Duplicates from a String.

Using Set 
  ```python
  # Write a Python program to Remove Duplicates from a String.

a = input("enter a string")
b = set(a)
c = list(b)
d =''.join(c)
d
```

Using Function
```python

def remove_duplicates(input_string):
    seen = set()
    result = []
    for char in input_string:
        if char not in seen:
            seen.add(char)
            result.append(char)
    return ''.join(result)
input_string = "Hello World"
print(remove_duplicates(input_string))
   ```         


 
- Write a Python program to check for Pangram.
  ```python
  # Write a Python program to check for Pangram.
# Pangram should contain all letters of alphabet at least once


using for looop:
```python
# pangram

def pangramm(str_n,alpha):
    for char in alpha:
        if char not in str_n:
            return False
    return True

str_n = input("enter a string").lower()
alpha = 'abcdefghijklmnopqrstuvwxyz'
if (pangramm(str_n,alpha) == False):
    print("The string is not Pangram")
else:
    print("The string is Pangram:")
```
Output: enter a string asljkfdasd
The string is not Pangram

enter a string The quick brown fox jumps over a lazy dog
The string is Pangram:    

using string library

```python
import string

def pangram(string1):
    low_case = string1.lower()
    alphabets = string.ascii_lowercase
    for char in alphabets:
        if char in low_case:
            return False
        return True

string1 = input("enter the string to check if the string is pangram or not")
result = pangram(string1)
if (result == True):
    print("The string is pangram")
else:
    print("The string is not pangram")
```
  
- Write a Python program to find the Minimum Element in a List.

```python
a = [7,43,21,56,78]
char = min(a)
char
```

  
- Write a Python program to find the Maximum Element in a List.

```python
a = [7,43,21,56,78]
char = max(a)
char
```
  
- Write a Python program to check if a Number is a Prime Factor.
```python
num = 13
list1 = []
for var in range(2,num//2):
    if(num%var == 0):
        list1.append(var)
        
if(len(list1)>1):
    print(list1)
else:
    print("There is no prime factor")
```
  
- Write a Python program to find the Maximum Difference between Two Elements in a List.

  using Loop:
  
```python
new_list = [5,4,2,5,6,78,8,2,3,4,5,6,89,87]
max_diff = 0
for var in new_list:
    for var2 in new_list:
        if var - var2 > max_diff:
            max_diff = var - var2
print(max_diff)
```

Short Method:

```python
new_list = [5,4,2,5,6,78,8,2,3,4,5,6,89,87]
max_diff = max(new_list) - min(new_list)
print(max_diff)
```

- Write a Python program to Convert Decimal to Binary.

```python
def binary_conv(a):
    binary_conversion = ''
    if a == 0:
        return 0
    else :
        while(a>0):
            binary_conversion = str(a % 2) + binary_conversion
            a = a//2
        return binary_conversion
a = 10
print("The Binary conversion of " + str(a) + " is " + binary_conv(a))
```
Short Method:

```python
decimal_num = 10
binary_num = bin(decimal_num)
binary_num[2:]
```
  
- Write a Python program to Find Second Largest Element in a List.
  
```python

m = [5,4,2,5,6,78,8,2,3,4,5,6,89,87]
n = sorted(set(m), reverse = True)
print("The Second largest element is: ",n[1])
```

## Intermediate-Level Questions:

- Write a Python program to Merge Two Sorted Lists.

```python
list_1 = [1,3,5,7,9,11]
list_2 = [2,4,6,8,10,12]
final_list = sorted(list_1 + list_2)
final_list
```

```python
# Long Method
list_1 = [1,3,5,7,9,11]
list_2 = [2,4,6,8,10,12]
i,j = 0,0
final_list = []
while i < len(list_1) and j < len(list_2):
    if(list_1[i] < list_2[j]):
        final_list.append(list_1[i])
        i+=1
    else:
        final_list.append(list_2[j])
        j+=1
final_list.extend(list_1[i:])
final_list.extend(list_2[j:])
print(final_list)

```

```python
list_1 = [1,3,5,7,9,11]
list_2 = [2,4,6,8,10,12]

final_list = list_1
final_list.extend(list_2[:])
final_list = sorted(final_list)
final_list
```

- Write a Python program to Reverse Words in a String.

```python
won = 'Python is fun'
new_string = won.split()
new_string
reverse_words = new_string[::-1]
reverse_words = ' '.join(reverse_words)
reverse_words
```

  
- Write a Python program to Check for Perfect Numbers.

```python
# perfect number: A number who is sum of all its prime factors excluding itself:

num1 = 28
fact = 1
for var in range(2,num1//2+1):
    if (num1 % var == 0):
        fact = fact+var

if ( fact == num1):
    print(str(num1) + " is a perfect number")
else:
    print(str(num1) + " is not a perfect number")
```
  
- Write a Python program to Find the Fibonacci Sequence.

  
- Write a Python program to find Anagram Check.

  
- Write a Python program to Find the Average Numbers in a List.

  
- Write a Python program to calculate the Sum of Digits in a Number.


- Write a Python program to check for Armstrong Number.

  
- Write a Python program to Check Palindrome.
- Write a Python program to calculate Factorial without Recursion.
- Write a Python program to Check Prime Numbers.
- Write a Python program to calculate LCM (Least Common Multiple) of Two Numbers.



### Python Programs(Part 2:

- Swapping 2 numbers
```python
  def swapping(a,b):
    c=0
    c=a
    a=b
    b=c
    return(a,b)

a = 10
b = 5
print(swapping(a,b))

```

```python
m = 5
n = 7
print(m,n)
m,n = n,m
print(m,n)
```

- print if the input is even or odd

```python
# print if the number is even or odd

def evenodd(num):
    if num%2==0:
        return True
    else:
        return False

num = int(input("Enter the number to check if it is even or odd"))
if (evenodd(num)== True):
    print("Number is Even")
else:
    print("Number is Odd")
```













