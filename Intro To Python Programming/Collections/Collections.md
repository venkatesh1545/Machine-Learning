- [Python Collections: Lists](#python-collections-lists)
    - [Key Features of Lists](#key-features-of-lists)
    - [Creating and Modifying Lists](#creating-and-modifying-lists)
    - [Example Problem on adding elements into empty list](#example-problem-you-are-given-an-empty-list-named-names-you-have-to-insert-robin-aman-rahul-at-the-end-of-list-one-after-other)

- [Python Collections: Tuples](#python-collections-tuples)
    - [Tuple Overview](#tuple-overview)
    - [Creating a tuple](#creating-a-tuple)
    - [Accessing Tuple Elements](#accessing-tuple-elements)
    - [changing Tuple values](#changing-tuple-values)
    - [Single Item Tuples](#single-item-tuples)
    - [Joing Tuples](#joining-tuples)
    - [Example Problem on changing value at index 0 of both tuple to string "number"](#example-problem-change-value-at-index-0-of-both-tuple-to-string-number)
- [Python Collections: Dictionaries](#python-collections-dictionaries)
    - [Creating a Dictionary](#creating-a-dictionary)
    - [Accessing Items](#accessing-items)
    - [Changing Values](#changing-values)
    - [Looping through a adictionary](#looping-through-a-dictionary)
    - [Adding Items](#adding-items)
    - [Removing Items](#removing-items)
    - [Creating a Dictionary with dict()](#creating-a-dictionary-with-dict)
    - [Example Problem: Updating the value in dictioanry and Adding the Default value into Dictionary](#example-problem-updating-the-value-in-dictioanry-and-adding-the-default-value-into-dictionary)
- [Python Collections: Sets](#python-sets)
    - [Using Set()](#using-set)
    - [Accessing Items in a set](#accessing-items-in-a-set)
    - [Adding items to a set](#adding-items-to-a-set)
    - [Removing Items from a set](#removing-items-from-a-set)
    - [Example Problem on Adding and deleting elements from the set](#example-problem-add-some-elements-into-set-and-delete-some-elements-from-the-set)


# Python Collections: Lists

Lists in Python are similar to arrays. They can contain any type of variable and as many variables as needed. 

## Key Features of Lists

- **Ordered**: Elements in a list have a defined order.
- **Changeable**: Elements can be modified, added, or removed.
- **Allows Duplicates**: Lists can contain duplicate items.

---

## Creating and Modifying Lists

You can build a list and add elements using the `append()` method, which inserts elements at the end of the list:

```python
my_list = []
# Adding elements to the list
my_list.append(1)
my_list.append(2)
my_list.append(3)

# Accessing elements by index
print(my_list[0])  # Output: 1
print(my_list[1])  # Output: 2
print(my_list[2])  # Output: 3
```
### Example Problem: You are given an empty list named names, you have to insert “Robin”, “Aman”, “Rahul” at the end of list one after other.

```python
def main():
    names = []
    # YOUR CODE GOES HERE
    names.append('Robin')
    names.append('Aman')
    names.append('Rahul')
    print(names)
    return 0

if __name__ == '__main__':
    main()
```
### Output:
```
['Robin', 'Aman', 'Rahul']
```
# Python Collections: Tuples

Python provides four main collection data types:

- **List**: Ordered, changeable, allows duplicate members.
- **Tuple**: Ordered, unchangeable (immutable), allows duplicate members.
- **Set**: Unordered, unindexed, no duplicate members.
- **Dictionary**: Unordered, changeable, indexed, no duplicate members.

This document focuses on **Tuples**.

---

## Tuple Overview

A tuple is similar to a list, but it is **immutable**, meaning once created, the elements cannot be changed directly.

### Creating a Tuple

You can create a tuple by enclosing items in parentheses:

```python
my_tuple = ('one', 'two', 'three')
print(my_tuple)
# Output: ('one', 'two', 'three')
```
### Accessing Tuple Elements

```python
my_tuple = ('one', 'two', 'three')
print(my_tuple[1])
# Output: 'two'
```

### Changing Tuple Values
Tuples are immutable, meaning their elements cannot be changed after creation. However, there is a workaround:

- Convert the tuple into a list.
- Modify the list.
- Convert the list back into a tuple.

```python 
my_tuple = ('one', 'two', 'three')
my_list = list(my_tuple)
my_list[2] = 'two'
my_tuple = tuple(my_list)
print(my_tuple)
# Output: ('one', 'two', 'two')
```

### Single Item Tuples
To create a tuple with one item, add a comma after the item. Without the comma, Python will interpret it as a regular string:

```python
# Correct single-item tuple
my_tuple = ("one",)
print(type(my_tuple))
# Output: <class 'tuple'>

# NOT a tuple
my_tuple = ("one")
print(type(my_tuple))
# Output: <class 'str'>
```

## Joining Tuples
You can join two or more tuples using the + operator:

```python
my_tuple1 = ('one', 'two', 'three')
my_tuple2 = ('1', '2', '3')
my_tuple3 = my_tuple1 + my_tuple2
print(my_tuple3)
# Output: ('one', 'two', 'three', '1', '2', '3')
```
### Example Problem: change value at index 0 of both tuple to string "number"

```python
def main():
    tuple1 = tuple(("one", "two", "three"))
    tuple2 = tuple(("1", "2", "3"))
    # change value at index 0 of both tuple to string "number"
    # Your code goes here
    print('tuple1 before modifying:', tuple1)
    print('tuple2 before modifying: ', tuple2)
    
    tuple1 = ("number",) + tuple1[1:]
    tuple2 = ("number",) + tuple2[1:] 
    
    print('tuple1 after modifying:', tuple1[1:])
    print('tuple2 after modifying: ', tuple2[1:])
    
    print(tuple1)
    print(tuple2)
    
    return 0

if __name__ == '__main__':
    main()

```
### Output:
```
tuple1 before modifying: ('one', 'two', 'three')
tuple2 before modifying:  ('1', '2', '3')
tuple1 after modifying: ('two', 'three')
tuple2 after modifying:  ('2', '3')
('number', 'two', 'three')
('number', '2', '3')
```


# Python Collections: Dictionaries

A dictionary in Python is a collection that is:

- **Unordered**: Items do not have a defined order.
- **Changeable**: Items can be modified, added, or removed.
- **Indexed**: Items are accessed using keys, not numeric indices.

Dictionaries consist of **key-value pairs** and are written using curly brackets `{}`.

---

## Creating a Dictionary

Example of creating dictionaries:

```python
# Basic dictionary
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}
print(my_dict)

# Dictionary with mixed keys
my_dict = {'One': 'Robin', 2: 'Rahul'}
print(my_dict)
```
### Accessing items
You can access items with the help of their key

```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}

# Access using key
val = my_dict[2]
print(val)  # Output: 'Rahul'

# Access using get() method
val = my_dict.get(2)
print(val)  # Output: 'Rahul'
```
### Changing Values:
Change the value of an item by referring to its key:

```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}
my_dict[2] = 'Rohan'
print(my_dict[2])  # Output: 'Rohan'
```

## Looping through a dictionary
You can iterate over keys, values, or both in a dictionary:

```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}

# Loop through keys
for x in my_dict:
    print(x)  # Output: 1, 2, 3

# Loop through values
for x in my_dict.values():
    print(x)  # Output: 'Robin', 'Rahul', 'Aman'

# Loop through keys and values
for key, val in my_dict.items():
    print(key, val)
```

### Adding Items
Add items to a dictionary by assigning a value to a new key:
```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}
my_dict[4] = 'Shivam'
print(my_dict)
# Output: {1: 'Robin', 2: 'Rahul', 3: 'Aman', 4: 'Shivam'}
```
### Removing Items
There are multiple ways to remove items from a dictionary:

- Using pop(): Removes an item by its key.
```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}
my_dict.pop(2)
print(my_dict)
# Output: {1: 'Robin', 3: 'Aman'}
```
- Using del: Removes an item by its key.

```python
my_dict = {1: 'Robin', 2: 'Rahul', 3: 'Aman'}
del my_dict[2]
print(my_dict)
# Output: {1: 'Robin', 3: 'Aman'}
```

### Creating a Dictionary with **dict()**
You can use the **dict()*** constructor to create a dictionary:
```python
my_dict = dict(One='Robin', Two='Rahul', Three='Aman')
# Note: Use `=` instead of `:` for key-value assignment in `dict()`
print(my_dict)
# Output: {'One': 'Robin', 'Two': 'Rahul', 'Three': 'Aman'}
```

### Example Problem: Updating the value in dictioanry and Adding the Default value into Dictionary

```python
def main():
    my_dict = {
        "Monday": 1,
        "Tuesday": 2,
        "Wednesday": 3,
        "Thursday": 4,
        "Friday": 5,
        "Saturday": 6,
        "Sunday": 0
    }

    # Update value for key "Sunday" to 7
    my_dict["Sunday"] = 7
    
    # Add another item with key "Default" having value 0
    my_dict["Default"] = 0
    
    for i in sorted(my_dict):
        print ("(\'" + i + "\',", str(my_dict[i]) + ")")

    return 0

if __name__ == '__main__':
    main()
```

### Output:
```
('Default', 0)
('Friday', 5)
('Monday', 1)
('Saturday', 6)
('Sunday', 7)
('Thursday', 4)
('Tuesday', 2)
('Wednesday', 3)
```

# Python Sets

A **set** is a collection that is **unordered** and **unindexed**. In Python, sets are written with curly brackets, and they cannot contain duplicate elements.

```python
my_set = {'one', 'two', 'three'}
print(my_set)
```

### **Using set():**
Sets can also be created using the set() constructor:
```python
my_set = set(['one', 'two', 'three'])
print(my_set)
```
**Note:** Sets are unordered, so you cannot be sure in which order the items will appear.

### **Accessing Items in a Set**
You cannot access items in a set by referring to an index or a key. However, you can:

- Loop through the set using a for loop.
- Check if a specified value exists in a set using the in keyword.
```python
my_set = {'one', 'two', 'three'}
for val in my_set:
    print(val)
```
### Adding Items to a Set
Once a set is created, you cannot change its items, but you can add new items.

- **Using add():**
```python
my_set = {'one', 'two', 'three'}
my_set.add('four')
print(my_set)
```
- **Using update():**
The update() method can add multiple items to a set from another sequence:
```python
my_set = {'one', 'two', 'three'}
my_set.update(['four', 'five', 'six'])
print(my_set)
# Output: {'one', 'two', 'three', 'four', 'five', 'six'}
# No duplicates are added.
```

### Removing Items from a Set
Items can be removed using the remove() or discard() methods.

### Key Differences:
**remove():** Raises an error if the item does not exist.
**discard():** Does NOT raise an error if the item does not exist.
```python
my_set = {'one', 'two', 'three', 'four'}

# Using remove()
my_set.remove('one')  # Removes 'one' from my_set

# Using discard()
my_set.discard('three')  # Removes 'three' from my_set

# Error handling:
my_set.remove('five')  # Throws an error
my_set.discard('five')  # Will NOT throw an error
```
### Example Problem: Add some elements into set and delete some elements from the set.
```python
def main():
    my_set = set([1, 3, 2, 4, 1, 3, 3, 0])
    print("Before Adding elemets into the set", my_set)
    
    # add 10, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23 to my_set
    my_set.update([10,12,13,14,15,16,17,18,19,20,21,22,23])
    print("After adding elements into the set: ", my_set)
    
    # delete 2 and 3 from my_set
    
    my_set.remove(2)
    my_set.remove(3)
    
    print("After removing elements from the 2nd and 3rd index: ", my_set)
    
    li = list(my_set)
    li.sort()
    print("Elements in the sorted list format: ")
    print(li)
    return 0

if __name__ == '__main__':
    main()

```
### Output:
```
Before Adding elemets into the set {0, 1, 2, 3, 4}
After adding elements into the set:  {0, 1, 2, 3, 4, 10, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23}
After removing elements from the 2nd and 3rd index:  {0, 1, 4, 10, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23}
Elements in the sorted list format:
[0, 1, 4, 10, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23]
```
