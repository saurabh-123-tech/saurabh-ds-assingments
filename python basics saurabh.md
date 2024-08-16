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


# 3. Describe how to access, modify and delete elements in a list with examples.

Accessing, modifying, and deleting elements in a Python list are fundamental operations that are quite straightforward. Here’s a detailed explanation with examples:

### Accessing Elements

Elements in a list are accessed using their index, with the first element having an index of `0`. Python supports both positive and negative indexing. Positive indices start from `0` and go up, while negative indices start from `-1` and go down.

#### Example

```python
my_list = ['apple', 'banana', 'cherry', 'date']

# Accessing elements using positive index
print(my_list[0])  # Output: 'apple'
print(my_list[2])  # Output: 'cherry'

# Accessing elements using negative index
print(my_list[-1])  # Output: 'date'
print(my_list[-3])  # Output: 'banana'
```

### Modifying Elements

You can modify elements in a list by accessing them via their index and then assigning a new value. Lists are mutable, so this operation directly alters the original list.

#### Example

```python
my_list = ['apple', 'banana', 'cherry', 'date']

# Modifying an element at a specific index
my_list[1] = 'blueberry'
print(my_list)  # Output: ['apple', 'blueberry', 'cherry', 'date']

# Modifying an element using a negative index
my_list[-2] = 'coconut'
print(my_list)  # Output: ['apple', 'blueberry', 'coconut', 'date']
```

### Deleting Elements

Elements can be removed from a list using several methods:

1. **Using `del` Statement**: Removes an element at a specific index.
2. **Using `remove()` Method**: Removes the first occurrence of a specific value.
3. **Using `pop()` Method**: Removes and returns an element at a specific index. If no index is provided, it removes and returns the last element.
4. **Using `clear()` Method**: Removes all elements from the list.

#### Examples

1. **Using `del` Statement**

   ```python
   my_list = ['apple', 'banana', 'cherry', 'date']
   del my_list[1]  # Removes the element at index 1
   print(my_list)  # Output: ['apple', 'cherry', 'date']
   ```

2. **Using `remove()` Method**

   ```python
   my_list = ['apple', 'banana', 'cherry', 'banana']
   my_list.remove('banana')  # Removes the first occurrence of 'banana'
   print(my_list)  # Output: ['apple', 'cherry', 'banana']

   # If the value is not in the list, it raises a ValueError
   # my_list.remove('grape')  # Uncommenting this line will raise a ValueError
   ```

3. **Using `pop()` Method**

   ```python
   my_list = ['apple', 'banana', 'cherry']
   removed_element = my_list.pop(1)  # Removes and returns the element at index 1
   print(removed_element)  # Output: 'banana'
   print(my_list)  # Output: ['apple', 'cherry']

   last_element = my_list.pop()  # Removes and returns the last element
   print(last_element)  # Output: 'cherry'
   print(my_list)  # Output: ['apple']
   ```

4. **Using `clear()` Method**

   ```python
   my_list = ['apple', 'banana', 'cherry']
   my_list.clear()  # Removes all elements from the list
   print(my_list)  # Output: []
   ```


# 4. Compare and contrast tuples and lists with examples.

Tuples and lists are both fundamental data structures in Python used for storing collections of items. However, they have different properties and use cases. Here’s a detailed comparison between the two, with examples to illustrate their features:

### 1. **Mutability**

- **Lists**: Mutable. You can modify, add, or remove elements after creation.
- **Tuples**: Immutable. Once a tuple is created, its elements cannot be changed, added, or removed.

#### Example

```python
# List example
my_list = [1, 2, 3]
my_list[1] = 20  # Modify element
my_list.append(4)  # Add element
print(my_list)  # Output: [1, 20, 3, 4]

# Tuple example
my_tuple = (1, 2, 3)
# my_tuple[1] = 20  # This will raise a TypeError
# my_tuple.append(4)  # This will raise an AttributeError
print(my_tuple)  # Output: (1, 2, 3)
```

### 2. **Syntax**

- **Lists**: Defined using square brackets `[]`.
- **Tuples**: Defined using parentheses `()`.

#### Example

```python
# List syntax
my_list = [1, 2, 3, 4]

# Tuple syntax
my_tuple = (1, 2, 3, 4)
```

### 3. **Performance**

- **Lists**: Generally slower than tuples due to their mutable nature and additional overhead for dynamic resizing.
- **Tuples**: Generally faster than lists for iteration and access, and require less memory due to their immutability.

#### Example

```python
import time

# List performance
start_time = time.time()
my_list = [x for x in range(10000)]
end_time = time.time()
print("List time:", end_time - start_time)

# Tuple performance
start_time = time.time()
my_tuple = tuple(x for x in range(10000))
end_time = time.time()
print("Tuple time:", end_time - start_time)
```

### 4. **Methods**

- **Lists**: Support many methods, such as `append()`, `remove()`, `pop()`, `sort()`, `reverse()`, etc.
- **Tuples**: Support fewer methods, mainly `count()` and `index()`.

#### Example

```python
# List methods
my_list = [1, 2, 3]
my_list.append(4)
my_list.sort(reverse=True)
print(my_list)  # Output: [4, 3, 2, 1]

# Tuple methods
my_tuple = (1, 2, 3, 2, 2)
print(my_tuple.count(2))  # Output: 3
print(my_tuple.index(3))  # Output: 2
```

### 5. **Use Cases**

- **Lists**: Ideal for collections of items that may need to be modified, such as dynamic data or collections where elements are frequently added or removed.
- **Tuples**: Ideal for fixed collections of items that should not change, such as coordinates or function return values where immutability is desired.

#### Example

```python
# List use case
shopping_list = ['milk', 'eggs', 'bread']
shopping_list.append('butter')
print(shopping_list)  # Output: ['milk', 'eggs', 'bread', 'butter']

# Tuple use case
coordinates = (40.7128, -74.0060)  # Latitude and longitude of New York City
print(coordinates)  # Output: (40.7128, -74.0060)
```

### 6. **Unpacking**

- **Lists**: Can be unpacked, but usually not used as a fixed structure.
- **Tuples**: Often used to return multiple values from a function and are commonly unpacked.

#### Example

```python
# Unpacking a list
my_list = [1, 2, 3]
a, b, c = my_list
print(a, b, c)  # Output: 1 2 3

# Unpacking a tuple
my_tuple = (1, 2, 3)
x, y, z = my_tuple
print(x, y, z)  # Output: 1 2 3
```


# 5. Describe the key features of sets and provide examples of thier use.

Sets are a built-in data structure in Python that represent unordered collections of unique items. They are particularly useful for operations involving membership testing, removing duplicates, and performing mathematical set operations. Here are the key features of sets, along with examples of their use:

### Key Features of Sets

1. **Unordered Collection**
   - Sets do not maintain any order of elements. The order in which elements are added is not necessarily the order in which they are stored or iterated over.

2. **Unique Elements**
   - Sets automatically remove duplicate items. Each element in a set is unique, which means no two elements can have the same value.

3. **Mutable**
   - Sets are mutable, so you can add or remove elements after the set is created. However, the elements themselves must be immutable (e.g., numbers, strings, tuples).

4. **No Indexing**
   - Unlike lists or tuples, you cannot access elements in a set by index, as sets are unordered.

5. **Mathematical Set Operations**
   - Sets support operations like union, intersection, difference, and symmetric difference, which are useful for various types of mathematical and logical operations.

6. **Performance**
   - Sets are optimized for membership testing and set operations, making these operations generally faster than similar operations on lists.

### Examples of Sets and Their Use

#### Creating a Set

```python
my_set = {1, 2, 3, 4}
print(my_set)  # Output: {1, 2, 3, 4}
```

#### Adding and Removing Elements

```python
my_set = {1, 2, 3}

# Adding elements
my_set.add(4)
print(my_set)  # Output: {1, 2, 3, 4}

# Removing elements
my_set.remove(2)  # Raises KeyError if element is not found
print(my_set)  # Output: {1, 3, 4}

# Safe removal with discard
my_set.discard(5)  # Does nothing if element is not found
print(my_set)  # Output: {1, 3, 4}

# Popping elements (removes and returns an arbitrary element)
element = my_set.pop()
print(element)  # Output: (could be 1, 3, or 4)
print(my_set)  # Output: {remaining elements}
```

#### Membership Testing

```python
my_set = {1, 2, 3, 4}

print(2 in my_set)  # Output: True
print(5 in my_set)  # Output: False
```

#### Mathematical Set Operations

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# Union (elements in either set)
union_set = set_a | set_b
print(union_set)  # Output: {1, 2, 3, 4, 5, 6}

# Intersection (elements in both sets)
intersection_set = set_a & set_b
print(intersection_set)  # Output: {3, 4}

# Difference (elements in set_a but not in set_b)
difference_set = set_a - set_b
print(difference_set)  # Output: {1, 2}

# Symmetric Difference (elements in either set but not both)
symmetric_difference_set = set_a ^ set_b
print(symmetric_difference_set)  # Output: {1, 2, 5, 6}
```

#### Removing Duplicates

Sets are often used to remove duplicates from a list.

```python
my_list = [1, 2, 2, 3, 4, 4, 4]
unique_elements = set(my_list)
print(unique_elements)  # Output: {1, 2, 3, 4}

# Converting back to a list if needed
unique_list = list(unique_elements)
print(unique_list)  # Output: [1, 2, 3, 4] (order may vary)
```

#### Set Comprehensions

You can create sets using comprehensions similar to list comprehensions.

```python
squares = {x**2 for x in range(5)}
print(squares)  # Output: {0, 1, 4, 9, 16}
```



# 6. Discuss the use cases of tuples and sets in python programming.

Tuples and sets are both fundamental data structures in Python, each with specific use cases due to their unique properties. Here’s a detailed look at the typical use cases for tuples and sets:

### Use Cases of Tuples

1. **Immutable Data Storage**
   - **Tuples** are ideal for storing data that should not be modified after creation. This immutability makes tuples a good choice for constants or fixed collections of items.
   - **Example**: Storing coordinates, RGB values, or fixed configuration settings.

   ```python
   coordinates = (40.7128, -74.0060)  # Latitude and longitude of New York City
   rgb_color = (255, 0, 0)  # Red color in RGB
   ```

2. **Function Return Values**
   - Tuples are commonly used to return multiple values from a function. They allow you to bundle several values together and return them in a single return statement.
   - **Example**: A function that returns the minimum, maximum, and average of a list of numbers.

   ```python
   def min_max_avg(numbers):
       return (min(numbers), max(numbers), sum(numbers) / len(numbers))

   result = min_max_avg([10, 20, 30, 40])
   print(result)  # Output: (10, 40, 25.0)
   ```

3. **Data Integrity and Hashing**
   - **Tuples** can be used as keys in dictionaries and elements in sets because they are immutable and hashable. This is useful when you need to use complex keys or store immutable collections.
   - **Example**: Using tuples as keys in a dictionary to store data associated with specific coordinates.

   ```python
   locations = {(40.7128, -74.0060): "New York", (34.0522, -118.2437): "Los Angeles"}
   print(locations[(40.7128, -74.0060)])  # Output: New York
   ```

4. **Structuring Data**
   - Tuples can be used to represent complex data structures, such as records or rows in a database.
   - **Example**: Representing a person's information as a tuple of name, age, and address.

   ```python
   person = ("Alice", 30, "123 Main St")
   ```

5. **Unpacking**
   - Tuples are used for unpacking, allowing you to assign values from a tuple to multiple variables in a single statement.
   - **Example**: Unpacking a tuple to extract values.

   ```python
   point = (1, 2)
   x, y = point
   print(x, y)  # Output: 1 2
   ```

### Use Cases of Sets

1. **Removing Duplicates**
   - **Sets** are often used to remove duplicates from a collection. By converting a list to a set, you automatically eliminate any repeated items.
   - **Example**: Removing duplicate items from a list of user IDs.

   ```python
   user_ids = [101, 102, 103, 101, 104, 102]
   unique_ids = set(user_ids)
   print(unique_ids)  # Output: {101, 102, 103, 104}
   ```

2. **Membership Testing**
   - **Sets** are optimized for membership testing. Checking whether an item is in a set is generally faster than in a list due to the underlying hash-based implementation.
   - **Example**: Checking if a user is part of a group.

   ```python
   authorized_users = {"Alice", "Bob", "Charlie"}
   print("Alice" in authorized_users)  # Output: True
   print("David" in authorized_users)  # Output: False
   ```

3. **Mathematical Set Operations**
   - Sets support mathematical operations like union, intersection, difference, and symmetric difference. This makes them useful for tasks involving comparisons and combinations of collections.
   - **Example**: Finding common elements between two lists or determining the unique elements across multiple collections.

   ```python
   set_a = {1, 2, 3, 4}
   set_b = {3, 4, 5, 6}

   union_set = set_a | set_b  # Union
   intersection_set = set_a & set_b  # Intersection
   difference_set = set_a - set_b  # Difference
   symmetric_difference_set = set_a ^ set_b  # Symmetric Difference

   print(union_set)  # Output: {1, 2, 3, 4, 5, 6}
   print(intersection_set)  # Output: {3, 4}
   print(difference_set)  # Output: {1, 2}
   print(symmetric_difference_set)  # Output: {1, 2, 5, 6}
   ```

4. **Efficient Data Lookup**
   - **Sets** can be used for efficient data lookup and for checking the existence of items in large datasets. They are ideal for scenarios where performance in checking membership is critical.
   - **Example**: Quickly checking if a value exists in a large set of data.

   ```python
   large_data_set = set(range(1000000))  # Large set of numbers from 0 to 999999
   print(999999 in large_data_set)  # Output: True
   ```

5. **Set Operations in Data Analysis**
   - Sets can be useful in data analysis tasks where you need to handle unique items or perform set-based operations on data.
   - **Example**: Finding unique categories in a dataset or determining distinct values in a column.

   ```python
   categories = {"Electronics", "Books", "Clothing", "Books"}
   print(categories)  # Output: {'Electronics', 'Books', 'Clothing'}
   ```



# 7. Describe how to add, modify and delete items in a disctionary with examples.

Dictionaries in Python are versatile data structures that store key-value pairs. You can easily add, modify, and delete items in a dictionary using various methods. Here's a detailed guide on how to perform these operations with examples:

### Adding Items

To add items to a dictionary, you simply assign a value to a new key. If the key already exists, this operation will update the existing key's value.

#### Example

```python
# Creating a dictionary
my_dict = {'name': 'Alice', 'age': 25}

# Adding a new key-value pair
my_dict['city'] = 'New York'
print(my_dict)  # Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}

# Updating an existing key's value
my_dict['age'] = 26
print(my_dict)  # Output: {'name': 'Alice', 'age': 26, 'city': 'New York'}
```

### Modifying Items

To modify an item in a dictionary, you update the value associated with an existing key. You use the key to access the item and then assign a new value to it.

#### Example

```python
# Creating a dictionary
my_dict = {'name': 'Alice', 'age': 25, 'city': 'New York'}

# Modifying an existing key's value
my_dict['age'] = 26
print(my_dict)  # Output: {'name': 'Alice', 'age': 26, 'city': 'New York'}

# Modifying another key's value
my_dict['city'] = 'Los Angeles'
print(my_dict)  # Output: {'name': 'Alice', 'age': 26, 'city': 'Los Angeles'}
```

### Deleting Items

There are several ways to delete items from a dictionary:

1. **Using `del` Statement**: Removes a specific key-value pair based on the key.
2. **Using `pop()` Method**: Removes a specific key and returns its value. If the key is not found, it raises a `KeyError`, unless a default value is provided.
3. **Using `popitem()` Method**: Removes and returns an arbitrary key-value pair (typically the last item in Python versions 3.7 and above).
4. **Using `clear()` Method**: Removes all key-value pairs from the dictionary.

#### Examples

1. **Using `del` Statement**

   ```python
   # Creating a dictionary
   my_dict = {'name': 'Alice', 'age': 26, 'city': 'Los Angeles'}

   # Deleting a specific key-value pair
   del my_dict['city']
   print(my_dict)  # Output: {'name': 'Alice', 'age': 26}
   ```

2. **Using `pop()` Method**

   ```python
   # Creating a dictionary
   my_dict = {'name': 'Alice', 'age': 26, 'city': 'Los Angeles'}

   # Removing a specific key and returning its value
   age = my_dict.pop('age')
   print(age)      # Output: 26
   print(my_dict)  # Output: {'name': 'Alice', 'city': 'Los Angeles'}

   # Removing a key with a default value (prevents KeyError)
   city = my_dict.pop('city', 'Not Found')
   print(city)     # Output: 'Los Angeles'
   print(my_dict)  # Output: {'name': 'Alice'}

   # Attempting to pop a non-existing key without default value raises KeyError
   # my_dict.pop('nonexistent_key')  # Uncommenting this line will raise KeyError
   ```

3. **Using `popitem()` Method**

   ```python
   # Creating a dictionary
   my_dict = {'name': 'Alice', 'age': 26, 'city': 'Los Angeles'}

   # Removing and returning an arbitrary key-value pair
   item = my_dict.popitem()
   print(item)     # Output: ('city', 'Los Angeles') (order may vary)
   print(my_dict)  # Output: {'name': 'Alice', 'age': 26}
   ```

4. **Using `clear()` Method**

   ```python
   # Creating a dictionary
   my_dict = {'name': 'Alice', 'age': 26, 'city': 'Los Angeles'}

   # Removing all key-value pairs
   my_dict.clear()
   print(my_dict)  # Output: {}
   ```



# 8. Discuss the importance of dictionary keys being immutable and provide examples.

In Python, dictionary keys must be immutable because dictionaries use hashing to quickly access values based on their keys. Here’s why immutability is crucial for dictionary keys and some examples to illustrate the concept:

### Importance of Immutable Keys

1. **Hashing Requirements**
   - **Hash Function**: Dictionaries in Python use a hash table to store key-value pairs. For this system to work correctly, the keys must be hashable, which means they need a consistent hash value throughout their lifetime. Immutable objects have a stable hash value, making them suitable as dictionary keys.
   - **Consistency**: If a key were mutable, its hash value could change if the object were modified, potentially breaking the dictionary’s ability to locate and retrieve the value efficiently.

2. **Integrity of Data Structure**
   - **Reliability**: Immutable keys ensure that the structure and integrity of the dictionary are maintained. Changing the key's value could lead to inconsistencies, where the dictionary might not be able to find or update entries correctly.
   - **Predictable Behavior**: With immutable keys, the behavior of dictionaries remains predictable, avoiding issues related to key collisions or data corruption.

### Examples

1. **Valid Dictionary Keys**

   - **Strings**: Strings are immutable and can be used as dictionary keys.

     ```python
     my_dict = {'name': 'Alice', 'age': 30}
     print(my_dict['name'])  # Output: Alice
     ```

   - **Numbers**: Integers and floating-point numbers are immutable and can be used as dictionary keys.

     ```python
     my_dict = {1: 'apple', 2: 'banana'}
     print(my_dict[1])  # Output: apple
     ```

   - **Tuples**: Tuples are immutable as long as their elements are also immutable. They can be used as dictionary keys.

     ```python
     my_dict = {(1, 2): 'point A', (3, 4): 'point B'}
     print(my_dict[(1, 2)])  # Output: point A
     ```

2. **Invalid Dictionary Keys**

   - **Lists**: Lists are mutable and cannot be used as dictionary keys because their hash value can change if the list is modified.

     ```python
     my_dict = {}
     # This will raise a TypeError because lists are unhashable
     # my_dict[[1, 2]] = 'list key'
     ```

   - **Dictionaries**: Dictionaries themselves are mutable and therefore cannot be used as keys.

     ```python
     my_dict = {}
     # This will raise a TypeError because dictionaries are unhashable
     # my_dict[{'key': 'value'}] = 'dict key'
     ```

   - **Sets**: Sets are mutable and cannot be used as dictionary keys.

     ```python
     my_dict = {}
     # This will raise a TypeError because sets are unhashable
     # my_dict[{1, 2}] = 'set key'
     ```
