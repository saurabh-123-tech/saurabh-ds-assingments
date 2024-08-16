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

