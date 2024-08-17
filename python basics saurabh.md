# 1. Write a code reverse a string.

def reverse_string(s):
    return s[::-1]

# Example usage
string = "hello"
reversed_string = reverse_string(string)
print(reversed_string)  # Output: "olleh"


# 2. Write a code to count the number of vowels in a string.

def count_vowels(s):
    vowels = "aeiouAEIOU"
    count = sum(1 for char in s if char in vowels)
    return count

# Example usage
string = "hello"
vowel_count = count_vowels(string)
print(vowel_count)  # Output: 2


# 3. Write a code to check if a given string is a palindrome or not.

def is_palindrome(s):
    # Remove any spaces and convert to lowercase for uniformity
    s = s.replace(" ", "").lower()
    # Check if the string is equal to its reverse
    return s == s[::-1]

# Example usage
input_string = input("Enter a string: ")
if is_palindrome(input_string):
    print(f'"{input_string}" is a palindrome.')
else:
    print(f'"{input_string}" is not a palindrome.')


# 4. Write a code to check if two given strings are anagrams of each other.

def are_anagrams(str1, str2):
    # Remove any spaces and convert to lowercase for uniformity
    str1 = str1.replace(" ", "").lower()
    str2 = str2.replace(" ", "").lower()
    
    # Check if sorted characters of both strings are the same
    return sorted(str1) == sorted(str2)

# Example usage
string1 = input("Enter the first string: ")
string2 = input("Enter the second string: ")

if are_anagrams(string1, string2):
    print(f'"{string1}" and "{string2}" are anagrams.')
else:
    print(f'"{string1}" and "{string2}" are not anagrams.')


# 5. Write a code to find all occurrences of a given substring within another string.

def find_substring_occurrences(main_string, substring):
    occurrences = []
    start = 0
    
    while True:
        # Find the substring starting from 'start' index
        start = main_string.find(substring, start)
        
        # If no more occurrences are found, break the loop
        if start == -1:
            break
        
        # Append the starting index of the found substring
        occurrences.append(start)
        
        # Move past the current occurrence
        start += len(substring)
    
    return occurrences

# Example usage
main_string = input("Enter the main string: ")
substring = input("Enter the substring to find: ")

indices = find_substring_occurrences(main_string, substring)

if indices:
    print(f'The substring "{substring}" occurs at indices: {indices}')
else:
    print(f'The substring "{substring}" is not found in the main string.')


# 6. Write a code to perform basic string compression using the counts of repeated characters.

def compress_string(s):
    # Initialize variables
    compressed = []
    count = 1
    
    # Iterate through the string
    for i in range(1, len(s)):
        # Compare current character with the previous one
        if s[i] == s[i - 1]:
            count += 1
        else:
            # Append previous character and its count to the result
            compressed.append(s[i - 1] + str(count))
            count = 1
    
    # Append the last character and its count
    compressed.append(s[-1] + str(count))
    
    # Join the list into a single string
    compressed_string = ''.join(compressed)
    
    # Return the compressed string if it's shorter, otherwise return the original string
    return compressed_string if len(compressed_string) < len(s) else s

# Example usage
input_string = input("Enter a string to compress: ")
compressed_string = compress_string(input_string)
print(f'Compressed string: {compressed_string}')


# 7. Write a code to determine if a string has all unique characters.

Method 1: Using a Set
The idea is to use a set to track characters as you iterate through the string. Since sets do not allow duplicate elements, you can check if the length of the set is the same as the length of the string.
def has_all_unique_characters(s):
    # Use a set to track characters
    seen = set()
    
    for char in s:
        # If the character is already in the set, it's a duplicate
        if char in seen:
            return False
        # Add the character to the set
        seen.add(char)
    
    return True

# Example usage
input_string = input("Enter a string: ")
if has_all_unique_characters(input_string):
    print("The string has all unique characters.")
else:
    print("The string does not have all unique characters.")

Method 2: Using an Array (for ASCII Characters)
If you know that the string only contains ASCII characters, you can use a boolean array to track occurrences of characters. This method is particularly efficient for fixed character sets.
def has_all_unique_characters(s):
    # ASCII characters range from 0 to 127
    if len(s) > 128:  # There are only 128 unique ASCII characters
        return False
    
    # Create a boolean array of size 128 (for ASCII characters)
    char_seen = [False] * 128
    
    for char in s:
        # Get ASCII value of the character
        val = ord(char)
        
        # If the character has been seen before, return False
        if char_seen[val]:
            return False
        
        # Mark the character as seen
        char_seen[val] = True
    
    return True

# Example usage
input_string = input("Enter a string: ")
if has_all_unique_characters(input_string):
    print("The string has all unique characters.")
else:
    print("The string does not have all unique characters.")


# 8. Write a code to convert a given string to uppercase or lowercase.

def convert_case(s, to_uppercase=True):
    """
    Convert the given string to uppercase or lowercase.
    
    Parameters:
    s (str): The input string to be converted.
    to_uppercase (bool): If True, convert to uppercase. If False, convert to lowercase.
    
    Returns:
    str: The converted string.
    """
    if to_uppercase:
        return s.upper()
    else:
        return s.lower()

# Example usage
input_string = input("Enter a string: ")
conversion_choice = input("Type 'upper' to convert to uppercase or 'lower' to convert to lowercase: ").strip().lower()

if conversion_choice == 'upper':
    converted_string = convert_case(input_string, to_uppercase=True)
elif conversion_choice == 'lower':
    converted_string = convert_case(input_string, to_uppercase=False)
else:
    print("Invalid choice. Please type 'upper' or 'lower'.")
    converted_string = None

if converted_string is not None:
    print(f'Converted string: {converted_string}')


# 9. Write a code to count the number of words in a string.

def count_words(s):
    # Split the string by whitespace and filter out any empty strings
    words = s.split()
    return len(words)

# Example usage
input_string = input("Enter a string: ")
word_count = count_words(input_string)
print(f'The number of words in the string is: {word_count}')


# 10. Write a code to concatenate two strings without using the + operator.

### Method 1: Using `join()`

```python
def concatenate_strings(str1, str2):
    # Use join() to concatenate strings
    return ''.join([str1, str2])

# Example usage
string1 = input("Enter the first string: ")
string2 = input("Enter the second string: ")
result = concatenate_strings(string1, string2)
print(f'Concatenated string: {result}')
```

### Method 2: Using String Formatting

```python
def concatenate_strings(str1, str2):
    # Use string formatting to concatenate
    return '{}{}'.format(str1, str2)

# Example usage
string1 = input("Enter the first string: ")
string2 = input("Enter the second string: ")
result = concatenate_strings(string1, string2)
print(f'Concatenated string: {result}')
```

### Method 3: Using f-strings (Python 3.6+)

```python
def concatenate_strings(str1, str2):
    # Use f-strings to concatenate
    return f'{str1}{str2}'

# Example usage
string1 = input("Enter the first string: ")
string2 = input("Enter the second string: ")
result = concatenate_strings(string1, string2)
print(f'Concatenated string: {result}')
```

### Method 4: Using `str.join()` with a List

```python
def concatenate_strings(str1, str2):
    # Use join() with a list to concatenate strings
    return ''.join([str1, str2])

# Example usage
string1 = input("Enter the first string: ")
string2 = input("Enter the second string: ")
result = concatenate_strings(string1, string2)
print(f'Concatenated string: {result}')
```


# 11. Write a code to remove all occurrences of a specific element from a list.

### Method 1: Using List Comprehension

```python
def remove_occurrences(lst, element):
    # Use list comprehension to create a new list without the specified element
    return [x for x in lst if x != element]

# Example usage
input_list = [1, 2, 3, 4, 2, 5, 2, 6]
element_to_remove = 2
result_list = remove_occurrences(input_list, element_to_remove)
print(f'List after removing all occurrences of {element_to_remove}: {result_list}')
```

### Method 2: Using `filter()`

```python
def remove_occurrences(lst, element):
    # Use filter() to create a new list without the specified element
    return list(filter(lambda x: x != element, lst))

# Example usage
input_list = [1, 2, 3, 4, 2, 5, 2, 6]
element_to_remove = 2
result_list = remove_occurrences(input_list, element_to_remove)
print(f'List after removing all occurrences of {element_to_remove}: {result_list}')
```


# 12. Implement a code to find the second largest number in a given list of integers.

def find_second_largest(numbers):
    if len(numbers) < 2:
        raise ValueError("List must contain at least two distinct numbers.")

    # Initialize the largest and second largest numbers
    largest = second_largest = float('-inf')

    for number in numbers:
        if number > largest:
            # Update both largest and second largest
            second_largest = largest
            largest = number
        elif number > second_largest and number != largest:
            # Update only the second largest
            second_largest = number

    if second_largest == float('-inf'):
        raise ValueError("There is no second distinct largest number.")

    return second_largest

# Example usage
input_list = [10, 5, 20, 20, 30, 30, 40]
try:
    result = find_second_largest(input_list)
    print(f'The second largest number is: {result}')
except ValueError as e:
    print(e)


# 13. Create a code to count the occurrences of each element in a list and return a dictionary with elements as keys and thier count as values.

def count_occurrences(lst):
    # Initialize an empty dictionary to store the counts
    count_dict = {}
    
    # Iterate through the list and count each element
    for item in lst:
        if item in count_dict:
            count_dict[item] += 1
        else:
            count_dict[item] = 1
    
    return count_dict

# Example usage
input_list = [1, 2, 2, 3, 1, 4, 1, 2, 3, 3]
result = count_occurrences(input_list)
print(f'Occurrences: {result}')


# 14. Write a code to reverse a list in-place without using any built-in reverse functions.

def reverse_list(lst):
    # Initialize two pointers
    left = 0
    right = len(lst) - 1
    
    # Swap elements until the pointers meet in the middle
    while left < right:
        # Swap the elements at the left and right pointers
        lst[left], lst[right] = lst[right], lst[left]
        # Move the pointers towards the center
        left += 1
        right -= 1

# Example usage
input_list = [1, 2, 3, 4, 5]
reverse_list(input_list)
print(f'Reversed list: {input_list}')


# 15. Implement a code to find and remove duplicates from a list while preserving the original order of elements.

def remove_duplicates(lst):
    seen = set()       # Set to track seen elements
    result = []        # List to store unique elements in original order

    for item in lst:
        if item not in seen:
            seen.add(item)  # Add the item to the set of seen elements
            result.append(item)  # Append the item to the result list

    return result

# Example usage
input_list = [1, 2, 2, 3, 4, 1, 5, 3]
unique_list = remove_duplicates(input_list)
print(f'List with duplicates removed: {unique_list}')


# 16. Create a code to check if a given list is sorted (either in ascending or descending order) or not.

def is_sorted(lst):
    if len(lst) <= 1:
        return True  # A list with 0 or 1 element is trivially sorted

    ascending = True
    descending = True

    # Check if the list is sorted in ascending order
    for i in range(1, len(lst)):
        if lst[i] < lst[i - 1]:
            ascending = False
            break

    # Check if the list is sorted in descending order
    for i in range(1, len(lst)):
        if lst[i] > lst[i - 1]:
            descending = False
            break

    return ascending or descending

# Example usage
input_list = [1, 2, 2, 3, 4]
if is_sorted(input_list):
    print("The list is sorted (either ascending or descending).")
else:
    print("The list is not sorted.")


# 17. Write a code to merge two sorted lists into a single sorted list.

def merge_sorted_lists(list1, list2):
    merged_list = []
    i = 0  # Pointer for list1
    j = 0  # Pointer for list2

    # Traverse both lists and merge them
    while i < len(list1) and j < len(list2):
        if list1[i] <= list2[j]:
            merged_list.append(list1[i])
            i += 1
        else:
            merged_list.append(list2[j])
            j += 1

    # If there are remaining elements in list1, add them to merged_list
    while i < len(list1):
        merged_list.append(list1[i])
        i += 1

    # If there are remaining elements in list2, add them to merged_list
    while j < len(list2):
        merged_list.append(list2[j])
        j += 1

    return merged_list

# Example usage
list1 = [1, 3, 5, 7]
list2 = [2, 4, 6, 8]
result = merge_sorted_lists(list1, list2)
print(f'Merged sorted list: {result}')


# 18. Implement a code to find the intersection of two given lists.

def intersection_of_lists(list1, list2):
    # Convert both lists to sets to find the intersection
    set1 = set(list1)
    set2 = set(list2)
    
    # Find the intersection of the two sets
    intersection = set1 & set2
    
    # Convert the intersection set back to a list (if needed)
    return list(intersection)

# Example usage
list1 = [1, 2, 3, 4, 5]
list2 = [4, 5, 6, 7, 8]
result = intersection_of_lists(list1, list2)
print(f'Intersection of the two lists: {result}')


# 19. Create a code to find the union of two lists without duplicates.

def union_of_lists(list1, list2):
    # Convert both lists to sets to remove duplicates and perform union
    set1 = set(list1)
    set2 = set(list2)
    
    # Find the union of the two sets
    union = set1 | set2
    
    # Convert the union set back to a list (if needed)
    return list(union)

# Example usage
list1 = [1, 2, 3, 4, 5]
list2 = [4, 5, 6, 7, 8]
result = union_of_lists(list1, list2)
print(f'Union of the two lists: {result}')


# 20. Write a code to shuffle a given list randomly without using any built-in shuffle functions.

import random

def fisher_yates_shuffle(lst):
    # Loop through the list from the last element to the second element
    for i in range(len(lst) - 1, 0, -1):
        # Generate a random index from 0 to i
        j = random.randint(0, i)
        
        # Swap the elements at index i and index j
        lst[i], lst[j] = lst[j], lst[i]

# Example usage
input_list = [1, 2, 3, 4, 5]
fisher_yates_shuffle(input_list)
print(f'Shuffled list: {input_list}')


# 21. Write a code that takes two tuples as input and returns a new tuple containing elements that are common to both input tuples.

def common_elements(tuple1, tuple2):
    # Convert tuples to sets to find the intersection
    set1 = set(tuple1)
    set2 = set(tuple2)
    
    # Find the intersection of the two sets
    common_set = set1 & set2
    
    # Convert the set back to a tuple
    common_tuple = tuple(common_set)
    
    return common_tuple

# Example usage
tuple1 = (1, 2, 3, 4, 5)
tuple2 = (4, 5, 6, 7, 8)
result = common_elements(tuple1, tuple2)
print(f'Common elements: {result}')


# 22. Create a code that prompts the user to enter two sets of integers separated by commas. Then, print the intersection of these two sets.

def get_set_from_input(prompt):
    # Prompt the user for input
    user_input = input(prompt)
    
    # Split the input string by commas and convert to a set of integers
    # Strip removes any leading/trailing whitespace, and map applies int conversion
    return set(map(int, user_input.split(',')))

def main():
    # Get the first set of integers from the user
    set1 = get_set_from_input("Enter the first set of integers separated by commas: ")
    
    # Get the second set of integers from the user
    set2 = get_set_from_input("Enter the second set of integers separated by commas: ")
    
    # Find the intersection of the two sets
    intersection = set1 & set2
    
    # Print the result
    print(f'The intersection of the two sets is: {intersection}')

# Example usage
main()


# 23. Write a code to concatenate two tuples. The function should take two tuples as input and return a new tuple containing elements from both input tuples.

def concatenate_tuples(tuple1, tuple2):
    # Concatenate the two tuples using the + operator
    concatenated_tuple = tuple1 + tuple2
    return concatenated_tuple

# Example usage
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
result = concatenate_tuples(tuple1, tuple2)
print(f'Concatenated tuple: {result}')


# 24. Develop a code that prompts the user to input two sets of strings. Then, print the elements that are present in the first set but not in the second set.

def get_set_from_input(prompt):
    # Prompt the user for input
    user_input = input(prompt)
    
    # Split the input string by commas, strip whitespace, and convert to a set of strings
    return set(word.strip() for word in user_input.split(','))

def main():
    # Get the first set of strings from the user
    set1 = get_set_from_input("Enter the first set of strings separated by commas: ")
    
    # Get the second set of strings from the user
    set2 = get_set_from_input("Enter the second set of strings separated by commas: ")
    
    # Find the elements that are in set1 but not in set2
    difference = set1 - set2
    
    # Print the result
    print(f'Elements in the first set but not in the second set: {difference}')

# Example usage
main()


# 25. Create a code that takes a tuple and two integers as input. The function should return a new tuple containing elements from the original tuple within the specified range of indices.

def slice_tuple(original_tuple, start_index, end_index):
    # Ensure indices are within the bounds of the tuple
    if start_index < 0:
        start_index = 0
    if end_index > len(original_tuple):
        end_index = len(original_tuple)
    
    # Return the sliced tuple
    return original_tuple[start_index:end_index]

# Example usage
input_tuple = (10, 20, 30, 40, 50, 60)
start = 2
end = 5
result = slice_tuple(input_tuple, start, end)
print(f'Sliced tuple: {result}')


# 26. Write a code that prompts the user to input two sets of characters. Then, print the union of these two sets.

def get_set_from_input(prompt):
    # Prompt the user for input
    user_input = input(prompt)
    
    # Remove any extra spaces and convert the input into a set of characters
    return set(user_input.strip())

def main():
    # Get the first set of characters from the user
    set1 = get_set_from_input("Enter the first set of characters: ")
    
    # Get the second set of characters from the user
    set2 = get_set_from_input("Enter the second set of characters: ")
    
    # Find the union of the two sets
    union_set = set1 | set2
    
    # Print the result
    print(f'The union of the two sets is: {union_set}')

# Example usage
main()


# 27. Develop a code that takes a tuple of integers as input. The function should return the maximum and minimum values from the tuple using tuple unpacking.

def find_max_min(input_tuple):
    # Ensure the tuple is not empty
    if not input_tuple:
        raise ValueError("The input tuple is empty")
    
    # Find the maximum and minimum values using built-in functions
    max_value = max(input_tuple)
    min_value = min(input_tuple)
    
    # Return the values as a tuple (max_value, min_value)
    return max_value, min_value

# Example usage
input_tuple = (10, 20, 4, 45, 99, -12)
max_val, min_val = find_max_min(input_tuple)
print(f'Maximum value: {max_val}')
print(f'Minimum value: {min_val}')


# 28. Create a code that defines two sets of integers. Then, print the union, intersection, and difference of these two sets.

def print_set_operations(set1, set2):
    # Compute union
    union_set = set1 | set2
    
    # Compute intersection
    intersection_set = set1 & set2
    
    # Compute difference (elements in set1 but not in set2)
    difference_set = set1 - set2
    
    # Print the results
    print(f'Union of the two sets: {union_set}')
    print(f'Intersection of the two sets: {intersection_set}')
    print(f'Difference (elements in set1 but not in set2): {difference_set}')

# Define two sets of integers
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

# Call the function with the defined sets
print_set_operations(set1, set2)


# 29. Write a code that takes a tuple and an element as input. The function should return the count of occurrences of the given element in the tuple.

def count_occurrences(input_tuple, element):
    # Count the occurrences of the element in the tuple
    count = input_tuple.count(element)
    return count

# Example usage
input_tuple = (1, 2, 3, 4, 2, 2, 5)
element = 2
result = count_occurrences(input_tuple, element)
print(f'The element {element} appears {result} times in the tuple.')


# 30. Develop a code that prompts the user to input two sets of strings. Then, print the symmetric difference of these two sets.

def get_set_from_input(prompt):
    # Prompt the user for input
    user_input = input(prompt)
    
    # Convert the input string into a set of strings
    return set(user_input.strip().split(','))

def main():
    # Get the first set of strings from the user
    set1 = get_set_from_input("Enter the first set of strings separated by commas: ")
    
    # Get the second set of strings from the user
    set2 = get_set_from_input("Enter the second set of strings separated by commas: ")
    
    # Find the symmetric difference of the two sets
    symmetric_difference = set1 ^ set2
    
    # Print the result
    print(f'The symmetric difference of the two sets is: {symmetric_difference}')

# Example usage
main()


# 31. Write a code that takes a list of words as input and returns a dictionary where the keys are unique words and the values are the frequencies of those words in the input list.

from collections import Counter

def count_word_frequencies(word_list):
    # Use Counter to count frequencies of each word in the list
    word_count = Counter(word_list)
    return dict(word_count)

# Example usage
def main():
    # Prompt the user to enter a list of words separated by spaces
    input_string = input("Enter a list of words separated by spaces: ")
    
    # Split the input string into a list of words
    word_list = input_string.split()
    
    # Get the word frequencies as a dictionary
    frequencies = count_word_frequencies(word_list)
    
    # Print the result
    print(f'Word frequencies: {frequencies}')

# Example usage
main()


# 32. Write a code that takes two dictionaries as input and merges them into a single dictionary. If there are common keys, the values should be added together.

def merge_dictionaries(dict1, dict2):
    # Create a new dictionary to store the merged result
    merged_dict = {}
    
    # Add all key-value pairs from the first dictionary
    for key, value in dict1.items():
        if key in merged_dict:
            merged_dict[key] += value
        else:
            merged_dict[key] = value
    
    # Add all key-value pairs from the second dictionary
    for key, value in dict2.items():
        if key in merged_dict:
            merged_dict[key] += value
        else:
            merged_dict[key] = value
    
    return merged_dict

# Example usage
def main():
    # Prompt the user to enter two dictionaries in the form of string literals
    dict1_str = input("Enter the first dictionary (e.g., {'a': 1, 'b': 2}): ")
    dict2_str = input("Enter the second dictionary (e.g., {'b': 3, 'c': 4}): ")
    
    # Convert the input strings to dictionaries
    dict1 = eval(dict1_str)
    dict2 = eval(dict2_str)
    
    # Merge the dictionaries
    result = merge_dictionaries(dict1, dict2)
    
    # Print the result
    print(f'Merged dictionary: {result}')

# Example usage
main()


# 33. Write a code to access a value in a nested dictionary. The function should take the dictionary and a list of keys as input, and return the corresponding value. If any of the keys do not exist in the dictionary, the function should return None.

def get_nested_value(d, keys):
    """
    Access a value in a nested dictionary using a list of keys.

    :param d: The nested dictionary to search.
    :param keys: A list of keys representing the path to the value.
    :return: The value corresponding to the keys, or None if any key is not found.
    """
    current = d
    for key in keys:
        if isinstance(current, dict) and key in current:
            current = current[key]
        else:
            return None
    return current

# Example usage
def main():
    # Define a nested dictionary
    nested_dict = {
        'a': {
            'b': {
                'c': 42
            }
        },
        'x': {
            'y': 99
        }
    }

    # Prompt the user for a list of keys
    keys_input = input("Enter a list of keys separated by commas (e.g., a,b,c): ")
    keys = keys_input.split(',')
    
    # Get the value from the nested dictionary
    value = get_nested_value(nested_dict, keys)
    
    # Print the result
    if value is not None:
        print(f'The value corresponding to the keys {keys} is: {value}')
    else:
        print(f'No value found for the keys {keys}')

# Example usage
main()


# 34. Write a code that takes a dictionary as input and returns a sorted version of it based on the values. You can choose whether to sort in ascending or descending order.

def sort_dictionary_by_value(d, ascending=True):
    """
    Sort a dictionary by its values.

    :param d: The dictionary to be sorted.
    :param ascending: If True, sort in ascending order; otherwise, sort in descending order.
    :return: A dictionary sorted by values.
    """
    # Sort the dictionary items based on values
    sorted_items = sorted(d.items(), key=lambda item: item[1], reverse=not ascending)
    
    # Convert sorted items back to a dictionary
    sorted_dict = dict(sorted_items)
    
    return sorted_dict

# Example usage
def main():
    # Define a dictionary
    my_dict = {
        'apple': 10,
        'banana': 5,
        'cherry': 20,
        'date': 15
    }
    
    # Prompt the user to choose the sorting order
    order = input("Enter 'asc' for ascending or 'desc' for descending order: ").strip().lower()
    ascending = order == 'asc'
    
    # Get the sorted dictionary
    sorted_dict = sort_dictionary_by_value(my_dict, ascending)
    
    # Print the result
    print(f'Sorted dictionary: {sorted_dict}')

# Example usage
main()


# 35. Write a code that inverts a dictionary, swapping keys and values. Ensure that the inverted dictionary correctly handles cases where multiple keys have the same value by storing the keys as a list in the inverted dictionary.

def invert_dictionary(d):
    """
    Invert a dictionary by swapping keys and values. Handle cases where multiple keys have the same value
    by storing the original keys in a list.

    :param d: The dictionary to be inverted.
    :return: An inverted dictionary with values as keys and lists of original keys as values.
    """
    inverted_dict = {}
    
    for key, value in d.items():
        if value in inverted_dict:
            inverted_dict[value].append(key)
        else:
            inverted_dict[value] = [key]
    
    return inverted_dict

# Example usage
def main():
    # Define a dictionary
    my_dict = {
        'a': 1,
        'b': 2,
        'c': 1,
        'd': 3
    }
    
    # Invert the dictionary
    inverted_dict = invert_dictionary(my_dict)
    
    # Print the result
    print(f'Inverted dictionary: {inverted_dict}')

# Example usage
main()
