# Assignment_Week4_2024
##  Questions Review
*1). Write a Python program to check whether a string is a palindrome or not using a stack.*

A palindromes are words, phrases, numbes, or other sequence of characters that reads the same forward and backward, ignoring spaces, punctuation, and capitalization.

*2). Explain the concept of list comprehension in Python with at least three examples.*
List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list. Without list comprehension you will have to write a for statement with a conditional test inside.

**Example 1**
- Square Numbers
- Filtering Even Numbers
- String Transformation.

*3). Explain what a compound datatype is in Python with three examples.*

A compound datatype in python is a datatype that has capability to hold multiple values or elements of different types by only using a single name. The values are usually stored in an order whereby the compound datatype provides the order of which the values are accessed, modified or managed.

**Examples:**

**Lists**
Python lists are used to store elements of text inside a square bracket separated by commas. List contains characteristics namely;
- Lists are mutable and dynamic;
- List items can be added, removed or changed after the list is defined. 
- Lists are ordered; newly added items will be placed at the end of the list. 
- Lists use zero-based indexing; every list item has an associated index, and the first item's index is 0.

**Tuples**
Python tuples are a type of data structure that is very similar to lists. The main difference between the two is that tuples are immutable, meaning they cannot be changed once they are created. This makes them ideal for storing data that should not be modified, such as database records.

**Dictionary**

Dictionaries are used to store data values in key:value pairs. A dictionary is a collection which is ordered*, changeable and do not allow duplicates.

*4. Write a function that takes a string and returns a list of bigrams.*

When we are dealing with text classification, sometimes we need to do certain kind of natural language processing and hence sometimes require to form bigrams of words for processing.

*5.Given a dictionary with keys as letters and values as lists of letters, write a function closest_key to find the key with the input value closest to the beginning of the list.*

To find the closest key in a Python dictionary, you can use a combination of dictionary methods and functions like min() with a custom key function. Here are two common Methods.

**Method 1** ***Using Lambda Function***

`def closest_key(test_dict, search_key):
    return min(test_dict.keys(), key=lambda k: abs(k - search_key))`

#### Example usage

`test_dict = {13: 'Hi', 15: 'Hello', 16: 'Gfg'}
search_key = 15.6
closest = closest_key(test_dict, search_key)
print(f"The closest key to {search_key} is {closest}, with value '{test_dict[closest]}'")`

**Method 2:** ***Using bisect with OrderedDict**

This method uses binary search for a more efficient lookup in an ordered dictionary.


`from collections`

`import OrderedDict`

`import bisect`

`def closest_key(test_dict, search_key):`

    keys = list(test_dict.keys())
    
    pos = bisect.bisect_left(keys, search_key)
    
    if pos == 0:
    
        return keys[0]
        
    if pos == len(keys):
    
        return keys[-1]
        
    before = keys[pos - 1]
    
    after = keys[pos]
    
    if after - search_key < search_key - before:
    
        return after
        
    else:
        return before`
        

#### Example usage

`test_dict = OrderedDict({13: 'Hi', 15: 'Hello', 16: 'Gfg'})`

`search_key = 15.6`

`closest = closest_key(test_dict, search_key)`

`print(f"The closest key to {search_key} is {closest}, with value '{test_dict[closest]}'")`
