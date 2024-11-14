# Data Structures in Python

## Topics Covered : List, Tuple, Set and Dictionary

### Short Introduction

- **List** is a collection which is ordered and changeable. Allows duplicate members.
- **Tuple** is a collection which is ordered and unchangeable. Allows duplicate members.
- **Set** is a collection which is unordered, unchangeable*, and unindexed. No duplicate members.
- **Dictionary** is a collection which is ordered** and changeable. No duplicate members.


 ### A data structure is nothing but a collection of data values.

 ## List

- Lists are used to store multiple items in a single variable.
- Lists are an ordered sequnce of mixed data types.
- Lists are written as comma-separated elements within square brackets


```python
list_1 = ['Deepak', 30, 'Uttar Pradesh']
print(list_1)
print(type(list_1))
```

![image](https://github.com/user-attachments/assets/a344e072-6e75-4146-9194-a8c8a3a37706)

#### Nested List: List inside a list

```python
list_1 = ['Deepak', 30, [1994,2024], 'Uttar Pradesh']
print(list_1)
print(type(list_1))
```

![image](https://github.com/user-attachments/assets/2fa989c7-a312-46b8-8391-f48db7ec5a0e)


#### Ordered
- When we say that lists are ordered, it means that the items have a defined order, and that order will not change.
- If you add new items to a list, the new items will be placed at the end of the list.
- Note: There are some list methods that will change the order, but in general: the order of the items will not change.

#### Indexing

To access elements in list, we can use positive and negative indexing. Indexing start from 0 and negative indexing from -1.

##### Accessing list elements:

```python
list_1 = ['Deepak', 30, 'Uttar Pradesh']
print(list_1[1])
print(list_1[-1])
```
![image](https://github.com/user-attachments/assets/7219c824-fa12-4615-b37a-977f63a4242e)


##### Accessing nested list elements:

```python
list_1 = ['Deepak', 30, [1994,2024], 'Uttar Pradesh']
print(list_1[2][1])
print(list_1[2][0])
print(list_1[2])
print(list_1[2][-1])

```
![image](https://github.com/user-attachments/assets/c6aeccc7-df05-4650-8c82-13981c5e5c4f)

#### Slicing : To access subset of elements in a list, we use slicing:

```python
list_1 = ['Deepak', 30, [1994,2024], 'Uttar Pradesh']
print(list_1[0:2])
```
![image](https://github.com/user-attachments/assets/4f59ec94-d700-4f50-bc97-05a32da168cf)


##### To access subset of nested list

```python
list_1 = ['Deepak', 30, [1994,2024], 'Uttar Pradesh']
print(list_1[2][0:2])
```
![image](https://github.com/user-attachments/assets/6eac8763-f31d-4d0e-bd66-71a6b9e2632a)


#### Membership in list

```python
l = [1,2,3]
print(1 in l)
print(2 in l)
```
Output: True
False

#### List Concatenation

```python
L =  [1,2,3]
new_l = l + [4,5]
print(new_l)
```

Output: [1,2,3,4,5]

##### In nested lists

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2] = list_1[2] + [2025, 2026]
print(list_1)
```
['Deepak', 30, [1994, 2024, 2025, 2026], 'Uttar Pradesh']

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
new_list = list_1[:2] + list_1[2] + [2025, 2026] + list_1[3:]
print(new_list)
```
['Deepak', 30, [1994, 2024, 2025, 2026], 'Uttar Pradesh']

#### replace deepak with Arun
```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[0] = 'Arun'
print(list_1)
```
Output: ['Arun', 30, [1994, 2024], 'Uttar Pradesh']

##### Note. Lists are mutable, which means the elements of a list can be changed.

### Extend
To append elements from another list to the current list, use the extend() method. The elements will be added to the end of the list.

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1.extend(['Owner','Bike',75000])
print(list_1)
```
Output: ['Deepak', 30, [1994, 2024], 'Uttar Pradesh', 'Owner', 'Bike', 75000]

##### Extending the nested list

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].extend([2025, 2026])
print(list_1)
```
Output: ['Deepak', 30, [1994, 2024, 2025, 2026], 'Uttar Pradesh']


### Append

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].append([2025, 2026])
print(list_1)
```
Output: ['Deepak', 30, [1994, 2024, [2025, 2026]], 'Uttar Pradesh']

Append will take the exact list and will paste it at the end where as extend will add its member in the list end.

### Append vs extend

| Method   | Description                                                                                          | Effect on List                                               | Example                                |
|----------|------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|----------------------------------------|
| append() | Adds a single element to the end of the list. If the element is a list, it's added as a nested list. | Increases the list by one element (the whole object)         | list_1.append([1, 2]) → [1, 2, [1, 2]] |
| extend() | Adds each element from an iterable (like a list, string, etc.) to the end of the list.               | Increases the list by the number of elements in the iterable | list_1.extend([1, 2]) → [1, 2, 1, 2]   |



### del:
To delete an element from the list, we use del.

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].append([2025, 2026])
print(list_1)
del list_1[3]
print(list_1)
```

![image](https://github.com/user-attachments/assets/a10c2f98-0cf3-4263-ab40-4f281826caba)

- delete multiple elements from a list

```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].append([2025, 2026])
print(list_1)
del list_1[2:4]
print(list_1)
```
![image](https://github.com/user-attachments/assets/b4cae5d5-d01d-45ac-b417-945c6909ecbe)


### pop:
To remove last element from the list, we can use pop()

```python

list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].append([2025, 2026])
print(list_1)
list_1.pop()
list_1
```

![image](https://github.com/user-attachments/assets/6e2cb50c-c468-4e9d-bf2b-0ae0569885d2)

### remove


```python
list_1 = ['Deepak', 30, [1994, 2024], 'Uttar Pradesh']
list_1[2].append([2025, 2026])
print(list_1)
list_1.remove('Uttar Pradesh')
print(list_1)
```

![image](https://github.com/user-attachments/assets/3cfbfa99-a7d1-4eda-9858-6dac4fb848ed)

| Method   | Purpose                                                               | Return Value                        | Effect on List            | Raises Error                          | Example                                                 |
|----------|-----------------------------------------------------------------------|-------------------------------------|---------------------------|---------------------------------------|---------------------------------------------------------|
| pop()    | Removes and returns an element by index (or last element by default). | The element removed.                | List size decreases by 1  | IndexError if index is out of range.  | list_1.pop(2) → returns and removes element at index 2. |
| del      | Removes an element by index or deletes an entire list or slice.       | None (does not return the element). | List size decreases by 1. | IndexError if index is out of range.  | del list_1[1] → deletes element at index 1.             |
| remove() | Removes the first occurrence of a specific value from the list.       | None (does not return the element). | List size decreases by 1. | ValueError if the value is not found. | list_1.remove(20) → removes first occurrence of 20.     |



### Sorting lists:

Sort in ascending order:

```python
# Sorting lists: Ascending Order
L = [5,2,45,6,24,78,94]
L.sort()
prinnt(L)
```
Output: [2, 5, 6, 24, 45, 78, 94]

Sort in descending order:

```python
# Sorting lists: Descending Order
L = [5,2,45,6,24,78,94]
L.sort(reverse=True)
print(L)
```
Output: [94, 78, 45, 24, 6, 5, 2]


```python
A = ['Goku','Saitama','Luffy','Zoro','Itachi','Nezuko']
B = A.sort()
print(A)
print(B)
```
![image](https://github.com/user-attachments/assets/4c38653d-6ef8-4c2f-b904-45a8c34e9c6f)


### Sorted
```python
A = ['Goku','Saitama','Luffy','Zoro','Itachi','Nezuko']
c = sorted(A)
print(A)
print(B)
print(c)
```

![image](https://github.com/user-attachments/assets/a7b6714a-752b-45ab-928c-468eb965b16f)

| Feature                | sort()                              | sorted()                                 |
|------------------------|-------------------------------------|------------------------------------------|
| Purpose                | Sorts the list in place.            | Returns a new sorted list.               |
| Modifies Original List | Yes, modifies the original list.    | No, the original list remains unchanged. |
| Return Value           | None (modifies the list in place).  | Returns a new list.                      |
| Usage                  | list.sort()                         | sorted(list)                             |
| Sorting Order          | Default is ascending, can reverse.  | Default is ascending, can reverse.       |
| Custom Sort            | Can use key and reverse parameters. | Can use key and reverse parameters.      |


### Shallow Copying:

```python
# Shallow Copying
A = ['Goku','Saitama','Luffy','Zoro','Itachi','Nezuko']
B= A
print(A,B)
```

![image](https://github.com/user-attachments/assets/b8edbcb0-8222-4df3-9b55-3623d041d67d)

- Lets change Goku to Beerus in list A and check what will happen to list A and B

```python
A[0] = 'Beerus'
print(A,B)
```

![image](https://github.com/user-attachments/assets/05919a46-2932-4c81-94ee-8cdc84b0dde1)

The Element not only changed in list A but also on List B. This is called Shallow Copying.

```python
A = ['Goku','Saitama','Luffy','Zoro','Itachi','Nezuko']
B= A[ : ]
A[0] = 'Beerus'
print(A,B)
```

![image](https://github.com/user-attachments/assets/562d7b53-0f67-4d15-9877-23799232dd5f)


- As we saw, by assigning  B = A, we refer to the same list object in the memory, and the changes made to list A will be reflected in list B as well. 
- With A[:], we are creating a new object, and this new object is assigned to B; here, any changes in list A would not affect list B anymore. 


## Tuples

- Tuples are ordered sequence of mixed data type.
- Tuples allows duplicate values.
- Tuples are similar to lists in almost of their functionalities, but there is one significant difference in both the data structures lists are mutable and tuples are not. 
- Tuples are written as commans separated within paranthesis.


Syntax:
mytuple = ("apple", "banana", "cherry")






