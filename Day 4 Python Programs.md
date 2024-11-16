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
 
- Write a Python program to check for Pangram.
- Write a Python program to find the Minimum Element in a List.
- Write a Python program to find the Maximum Element in a List.
- Write a Python program to check if a Number is a Prime Factor.
- Write a Python program to find the Maximum Difference between Two Elements in a List.
- Write a Python program to Convert Decimal to Binary.
- Write a Python program to Find Second Largest Element in a List.


















