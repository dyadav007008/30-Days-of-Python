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





