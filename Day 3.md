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












