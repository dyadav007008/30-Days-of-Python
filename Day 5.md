# Python for Data Analyst


## Numpy

Why NumPy is an important library for working with data?
NumPy, an acronym for the term ‘Numerical Python’, is a library in Python which is used extensively for efficient mathematical computing. 
This library allows users to store large amounts of data using less memory and perform extensive operations efficiently. 
It provides optimised and simpler functionalities to perform aforementioned operations using homogenous, one-dimensional and multidimensional arrays


Session Contains:
- Create NumPy arrays,
- Convert lists and tuples to NumPy arrays,
- Inspect the structure and content of arrays, and
- Subset, slice, index and iterate through arrays.


### Basics of NumPy

- The basic data structure of NumPy is an array. 
- A NumPy array is a collection of values stored together, similar to a list. 

### Two different advantages that NumPy arrays have over lists. These include: 

1. Ability to operate on individual elements in the array without using loops or list comprehension
2. Speed of execution 

### What are NumPy Arrays?
- A NumPy array is a powerful data structure for numerical computations in Python, provided by the NumPy library.
- It allows element-wise operations across the entire dataset, unlike Python lists.

###  Creating NumPy Arrays
There are two primary methods to create NumPy arrays:

1. Converting Existing Lists or Tuples:

Use the np.array() function to convert Python lists or tuples into NumPy arrays.

Example:
```python
import numpy as np
my_list = [1, 2, 3]
array_from_list = np.array(my_list)
print(array_from_list)  # Output: [1 2 3]
```

2. Initializing Arrays Using NumPy Functions:
Predefined functions can create arrays with specific patterns or fixed lengths:

- Zeros Array: np.zeros(shape) creates an array filled with zeros.
- Ones Array: np.ones(shape) creates an array filled with ones.
- Empty Array: np.empty(shape) creates an array with uninitialized values.
- Range Array: np.arange(start, stop, step) generates evenly spaced values.
- Linear Space Array: np.linspace(start, stop, num) creates a specified number of evenly spaced values between two limits.

### Key Features of NumPy Arrays

1. Uniform Structure:
A NumPy array is homogeneous; all elements must be of the same data type (integer, float, string, etc.).
Example:
```python

arr = np.array([1, 2.5, 3])  # Data type: float, as one element is a float.
```

2. Representation:

In a NumPy array, elements are separated by spaces, unlike Python lists where they are separated by commas.
Example:
```python
arr = np.array([1, 2, 3])
print(arr)  # Output: [1 2 3]
```

3. Multidimensional Capability:
Arrays can be one-dimensional, two-dimensional, or multi-dimensional.


4. Element-wise Operations:

Arrays allow operations across the entire dataset simultaneously.
Example:
```python
arr = np.array([1, 2, 3])
print(arr + 2)  # Output: [3 4 5]
```

### Key Differences Between NumPy Arrays and Lists

| Feature        | NumPy Arrays                            | Python Lists                         |
|----------------|-----------------------------------------|--------------------------------------|
| Homogeneity    | Elements must be of the same data type. | Elements can be of mixed data types. |
| Operations     | Element-wise operations are supported.  | Requires iteration for operations.   |
| Speed          | Faster due to vectorization.            | Slower due to overhead.              |
| Memory Usage   | More memory-efficient.                  | Less memory-efficient.               |
| Representation | Elements separated by spaces.           | Elements separated by commas.        |


### Operations Over 1-D Arrays

NumPy arrays support a variety of operations, allowing us to perform computations and manipulations efficiently. Below is a comprehensive guide to the common operations on 1-dimensional (1-D) arrays.

1. Basic Arithmetic Operations
Arithmetic operations are applied element-wise to all elements of the array.

| Operation      | Example  | Explanation                            |
|----------------|----------|----------------------------------------|
| Addition       | arr + 5  | Adds 5 to each element of the array.   |
| Subtraction    | arr - 3  | Subtracts 3 from each element.         |
| Multiplication | arr * 2  | Multiplies each element by 2.          |
| Division       | arr / 4  | Divides each element by 4.             |
| Power          | arr ** 2 | Raises each element to the power of 2. |

2. Mathematical Functions
NumPy provides a wide range of mathematical functions that operate element-wise.

| Function       | Example      | Explanation                               |
|----------------|--------------|-------------------------------------------|
| Square root    | np.sqrt(arr) | Computes the square root of each element. |
| Exponential    | np.exp(arr)  | Computes e power x   for each element.    |
| Logarithm      | np.log(arr)  | Computes the natural log of each element. |
| Sine           | np.sin(arr)  | Computes the sine of each element.        |
| Cosine         | np.cos(arr)  | Computes the cosine of each element.      |
| Absolute Value | np.abs(arr)  | Computes the absolute value.              |

```python
arr = np.array([1, 4, 9])
print(np.sqrt(arr))  # Output: [1. 2. 3.]
print(np.log(arr))   # Output: [0. 1.38629436 2.19722458]
```
3. Aggregation Functions
Aggregation functions compute a single result from an array.

| Function           | Example        | Explanation                             |
|--------------------|----------------|-----------------------------------------|
| Sum                | np.sum(arr)    | Computes the total sum of all elements. |
| Mean               | np.mean(arr)   | Computes the average of all elements.   |
| Median             | np.median(arr) | Finds the median value.                 |
| Standard Deviation | np.std(arr)    | Computes the standard deviation.        |
| Minimum            | np.min(arr)    | Finds the smallest value in the array.  |
| Maximum            | np.max(arr)    | Finds the largest value in the array.   |


```python
arr = np.array([10, 20, 30])
print(np.sum(arr))    # Output: 60
print(np.mean(arr))   # Output: 20.0
print(np.max(arr))    # Output: 30
```

4. Indexing and Slicing
Access elements or subarrays using indexing and slicing.

| Operation      | Example  | Explanation                                 |
|----------------|----------|---------------------------------------------|
| Access element | arr[2]   | Access the 3rd element (index starts at 0). |
| Access slice   | arr[1:4] | Access elements from index 1 to 3.          |
| Step slicing   | arr[::2] | Access every 2nd element.                   |

```python
arr = np.array([10, 20, 30, 40, 50])
print(arr[2])         # Output: 30
print(arr[1:4])       # Output: [20 30 40]
print(arr[::2])       # Output: [10 30 50]
```

5. Conditional Selection
Select elements based on conditions using Boolean indexing.

| Operation    | Example        | Explanation                      |
|--------------|----------------|----------------------------------|
| Greater than | arr[arr > 20]  | Select elements greater than 20. |
| Equal to     | arr[arr == 10] | Select elements equal to 10.     |
```python
arr = np.array([10, 20, 30, 40])
print(arr[arr > 20])  # Output: [30 40]
```
6. Array Manipulations
Manipulate arrays using various NumPy functions.
| Operation | Example        | Explanation                        |
|-----------|----------------|------------------------------------|
| Reverse   | arr[::-1]      | Reverse the array.                 |
| Sort      | np.sort(arr)   | Sort the array in ascending order. |
| Unique    | np.unique(arr) | Get unique elements in the array.  |

```python
arr = np.array([3, 1, 2, 2, 3])
print(np.sort(arr))     # Output: [1 2 2 3 3]
print(np.unique(arr))   # Output: [1 2 3]
```

7. Broadcasting
Perform operations between arrays of different shapes, where smaller arrays are "broadcasted" to match the shape of the larger array.
```python
arr = np.array([1, 2, 3])
print(arr + 10)         # Output: [11 12 13]
```

8. Copying and Views
Shallow Copy: A view of the original data; changes affect the original.
Deep Copy: A completely independent copy.
```python
arr = np.array([1, 2, 3])
view = arr[:]
copy = arr.copy()

view[0] = 10  # Changes arr
copy[0] = 100  # Does not change arr
```

## Multidimensional Arrays
1. Creating Multidimensional Arrays
You can create multidimensional arrays in NumPy using various methods:

From Nested Lists or Tuples:
```python
import numpy as np
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr)
# Output:
# [[1 2 3]
#  [4 5 6]]
```

2. Using Built-in Functions:

- np.zeros((rows, cols)): Creates an array filled with zeros.
- np.ones((rows, cols)): Creates an array filled with ones.
- np.eye(n): Creates an identity matrix.
- np.full((rows, cols), value): Creates an array filled with a specific value.
- np.random.rand(rows, cols): Generates an array with random values.

```python
zeros = np.zeros((2, 3))
print(zeros)
# Output:
# [[0. 0. 0.]
#  [0. 0. 0.]]
```
2. Attributes of Multidimensional Arrays

Multidimensional arrays have several key attributes:

shape: Returns the dimensions of the array.

```python
arr.shape  # Output: (2, 3)
```
ndim: Returns the number of dimensions.
```python
arr.ndim  # Output: 2
```

size: Returns the total number of elements.

```python
arr.size  # Output: 6
```
dtype: Returns the data type of the elements.

```python
arr.dtype  # Output: dtype('int32')
```

3. Indexing and Slicing

You can access and modify elements using indexing and slicing.

Accessing Elements:

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr[0, 1])  # Output: 2
```

Slicing Rows and Columns:

```python
print(arr[0, :])  # Output: [1 2 3] (First row)
print(arr[:, 1])  # Output: [2 5] (Second column)
```

Modifying Elements:

```python
arr[1, 2] = 10
print(arr)
# Output:
# [[ 1  2  3]
#  [ 4  5 10]]
```

4. Mathematical Operations

Mathematical operations are applied element-wise across the entire array.

Addition/Subtraction:

```python
arr + 2
# Adds 2 to every element
```
Matrix Multiplication:

```python
arr1 = np.array([[1, 2], [3, 4]])
arr2 = np.array([[5, 6], [7, 8]])
result = np.dot(arr1, arr2)
print(result)
# Output:
# [[19 22]
#  [43 50]]
```

5. Reshaping and Flattening

Reshaping: Change the shape of an array without altering its data.

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
reshaped = arr.reshape(3, 2)
print(reshaped)
# Output:
# [[1 2]
#  [3 4]
#  [5 6]]
```

Flattening: Convert a multidimensional array into a one-dimensional array.

```python
flat = arr.flatten()
print(flat)
# Output: [1 2 3 4 5 6]
```

6. Broadcasting

Broadcasting allows NumPy to perform operations between arrays of different shapes.

Example:

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
scalar = 10
result = arr + scalar
print(result)
# Output:
# [[11 12 13]
#  [14 15 16]]
```

7. Aggregation Functions

Aggregation functions operate over a specific axis in multidimensional arrays.

Function	Example	Description

| Function | Example              | Description                           |
|----------|----------------------|---------------------------------------|
| Sum      | np.sum(arr, axis=0)  | Sum across rows (axis=0).             |
| Mean     | np.mean(arr, axis=1) | Mean across columns (axis=1).         |
| Min/Max  | np.min(arr, axis=0)  | Minimum/Maximum values along an axis. |

Example:

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(np.sum(arr, axis=0))  # Output: [5 7 9]
print(np.mean(arr, axis=1))  # Output: [2. 5.]
```
8. Stacking and Splitting

Stacking: Combine arrays vertically (vstack) or horizontally (hstack).

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
print(np.vstack((a, b)))
# Output:
# [[1 2 3]
#  [4 5 6]]
```
Splitting: Split an array into multiple smaller arrays.

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(np.hsplit(arr, 3))
# Output: [array([[1], [4]]), array([[2], [5]]), array([[3], [6]])]
```
9. Copying and Views

Deep Copy: A new independent copy of the array.

```python
arr_copy = arr.copy()
```
View: A shallow copy; changes to the view affect the original array.

```python
arr_view = arr.view()
```











