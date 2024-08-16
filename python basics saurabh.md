# 1. Discuss string slicing and provide examples.

String slicing is a technique in programming languages like Python that allows you to extract a portion of a string by specifying a start and end index. This operation returns a new string that contains the specified subset of the original string.

### Basic Syntax

In Python, the syntax for slicing a string is:
```python
string[start:end:step]
```
- `start`: The index where the slice starts (inclusive).
- `end`: The index where the slice ends (exclusive).
- `step`: The interval between characters in the slice (optional).

### Examples

1. **Basic Slicing**

   ```python
   text = "Hello, World!"
   sliced_text = text[0:5]  # Slices from index 0 to 4
   print(sliced_text)  # Output: "Hello"
   ```

2. **Omitting Start and End**

   ```python
   text = "Hello, World!"
   sliced_text = text[:5]  # Omits the start, so it's from the beginning to index 4
   print(sliced_text)  # Output: "Hello"

   sliced_text = text[7:]  # Omits the end, so it's from index 7 to the end
   print(sliced_text)  # Output: "World!"
   ```

3. **Using Step**

   ```python
   text = "Hello, World!"
   sliced_text = text[::2]  # Slices the entire string with a step of 2
   print(sliced_text)  # Output: "Hlo ol!"
   ```

4. **Negative Indices**

   ```python
   text = "Hello, World!"
   sliced_text = text[-6:-1]  # Slices from index -6 to -2 (not including -1)
   print(sliced_text)  # Output: "World"
   ```

5. **Reversing a String**

   ```python
   text = "Hello, World!"
   reversed_text = text[::-1]  # Slices the entire string in reverse order
   print(reversed_text)  # Output: "!dlroW ,olleH"
   ```

6. **Empty Slices**

   ```python
   text = "Hello, World!"
   sliced_text = text[5:5]  # Slices from index 5 to 5 (an empty string)
   print(sliced_text)  # Output: ""

   sliced_text = text[5:5]  # Same result
   print(sliced_text)  # Output: ""
   ```

### Practical Use Cases

- **Extracting Substrings**: You can extract specific parts of a string, such as extracting a domain from an email address.
- **Reversing Strings**: By using a negative step, you can easily reverse a string.
- **Data Cleaning**: Removing unwanted characters or trimming strings.

String slicing is a powerful tool in string manipulation and can be used effectively for various tasks in programming.


# 2. Explain the key features of lists in python.

Lists in Python are one of the most versatile and widely used data structures. Here are some key features and characteristics of lists:

### 1. **Ordered Collection**

Lists maintain the order of elements as they are added. This means that the order in which items are inserted is preserved and can be accessed via indexing.

```python
my_list = [1, 2, 3, 4]
print(my_list[0])  # Output: 1
```

### 2. **Mutable**

Lists are mutable, which means you can change their content after they are created. You can modify, add, or remove elements.

```python
my_list = [1, 2, 3]
my_list[1] = 4  # Modifies the element at index 1
print(my_list)  # Output: [1, 4, 3]

my_list.append(5)  # Adds an element to the end
print(my_list)  # Output: [1, 4, 3, 5]

del my_list[0]  # Removes the element at index 0
print(my_list)  # Output: [4, 3, 5]
```

### 3. **Dynamic Size**

Lists can grow or shrink in size dynamically. You don't need to specify their size at the time of creation.

```python
my_list = [1, 2, 3]
print(len(my_list))  # Output: 3

my_list.append(4)
print(len(my_list))  # Output: 4
```

### 4. **Heterogeneous Elements**

Lists can contain elements of different types, including integers, strings, other lists, and more.

```python
my_list = [1, "hello", [2, 3], 4.5]
print(my_list)  # Output: [1, 'hello', [2, 3], 4.5]
```

### 5. **Indexing and Slicing**

You can access elements using their index, and you can use slicing to extract parts of the list.

```python
my_list = [10, 20, 30, 40, 50]
print(my_list[1])    # Output: 20
print(my_list[1:4])  # Output: [20, 30, 40]
```

### 6. **List Methods**

Lists come with a variety of built-in methods that provide functionality for manipulating the list.

- `append(item)`: Adds an item to the end of the list.
- `extend(iterable)`: Extends the list by appending elements from an iterable.
- `insert(index, item)`: Inserts an item at a specified index.
- `remove(item)`: Removes the first occurrence of an item.
- `pop([index])`: Removes and returns the item at the specified index.
- `sort(key=None, reverse=False)`: Sorts the list in place.
- `reverse()`: Reverses the list in place.
- `clear()`: Removes all items from the list.

```python
my_list = [3, 1, 4, 1, 5]
my_list.append(9)
print(my_list)  # Output: [3, 1, 4, 1, 5, 9]

my_list.remove(1)
print(my_list)  # Output: [3, 4, 1, 5, 9]

my_list.sort()
print(my_list)  # Output: [1, 3, 4, 5, 9]
```

### 7. **Nested Lists**

Lists can contain other lists, which can be useful for creating complex data structures like matrices.

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(matrix[1][2])  # Output: 6
```

### 8. **List Comprehensions**

Lists support a concise syntax for creating new lists by applying an expression to each item in an existing list or iterable.

```python
squares = [x**2 for x in range(10)]
print(squares)  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### Summary

Python lists are a fundamental and versatile data structure that support ordered, mutable collections of items. Their dynamic size, ability to hold heterogeneous elements, and rich set of built-in methods make them a powerful tool for various programming tasks.


# 3. Compare and contrast mutable and immutable objects in Python with examples.

## Mutable objects:-
Objects whose values can be changed after they are created. Examples include lists, dictionaries, and sets. 
## Immutable objects:-
Objects whose values cannot be changed after they are created. Examples include strings, numbers, and tuples.

Here's an example to illustrate the difference:-  
### [Open file "[Q-3].ipynb" for seeing example] 


# 4. Discuss the different types of operators in Python and provide examples of how they are used.
Python supports several types of operators, including:

## Arithmetic operators:
Used for performing mathematical operations, such as +, -, *, /, %, //, and **.

## Comparison operators:
Used for comparing values, such as ==, !=, >, <, >=, and <=.

## Logical operators:
Used for combining boolean expressions, such as and, or, and not.

## Assignment operators:
Used for assigning values to variables, such as =, +=, -=, *=, /=

Here are some examples:-
### [Open file "[Q-4].ipynb" for seeing example]

# 5. Explain the concept of type casting in Python with examples.
Type casting is the process of converting one data type to another. Python supports several built-in functions for type casting, such as int(), float(), str(), and bool().

Here are some examples:-
### [Open file "[Q-5].ipynb" for seeing example]

## 6. How do conditional statements work in Python? Illustrate with examples.
Conditional statements allow you to execute different code blocks based on whether a certain condition is true or false. Python supports the if, else, and elif (else if) statements.

Here's an example:-
### [Open file "[Q-6].ipynb" for seeing example]

# 7. Describe the different types of loops in Python and their use cases with examples.
Python supports two main types of loops: for loops and while loops.

## for loops:-
Used to iterate over a sequence of items, such as a list, tuple, or string.

## while loops:-
Used to execute code repeatedly as long as a condition is true.

Here are some examples:-
### [Open file "[Q-7].ipynb" for seeing example]
