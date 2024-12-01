- [Object Oriented Programming in Python](#object-oriented-programming-oop-in-python)
    
    - [What is OOP in Python](#what-is-object-oriented-programming-in-python)
    - [Key OOP Concepts in Python](#key-oop-concepts-in-python)
    - [Python Classes](#python-class)
    - [Python Objects](#python-objects)
        - [Components of an Object](#components-of-an-object)
        - [Creating an Object](#creating-an-object) 
    - [Self in Python Classes](#self-in-python-classes)
        - [What is the use of self in python](#what-is-the-use-of-self-in-python)
        - [Python Class self Constructor](#python-class-self-constructor)
        - [Is self a Keyword in Python?](#is-self-a-keyword-in-python)
        - [Characteristics of self](#characteristics-of-self)
        - [Example: Creating Class with Attributes and Methods](#example-creating-class-with-attributes-and-methods)
        - [Self in Constructors and Methods](#self-in-constructors-and-methods)
        - [Self: Convention, Not Keyword](#self-convention-not-keyword)
    - [The `__init__` Method in Python](#the-python-init-method)
        - [Creating a class and object with class and instance attributes](#creating-a-class-and-object-with-class-and-instance-attributes) 
    - [Creating Classes and objects with methods](#creating-classes-and-objects-with-methods)

# Object-Oriented Programming (OOP) in Python

**Object-Oriented Programming (OOP)** is a fundamental concept in Python that empowers developers to build modular, maintainable, and scalable applications. By understanding core OOP principles—such as **classes**, **objects**, **inheritance**, **encapsulation**, **polymorphism**, and **abstraction**—programmers can design elegant and efficient solutions to complex problems.

---

## What is Object-Oriented Programming in Python?

In Python, **Object-Oriented Programming (OOP)** is a programming paradigm that uses **objects** and **classes**. It models real-world entities like **inheritance**, **polymorphism**, and **encapsulation** in programming. 

The main idea behind OOP is to bind **data** and **functions** into a single unit (class), ensuring better modularity and security. By doing so, no external part of the code can access the class's private data.


---

## Key OOP Concepts in Python

- **Class** in Python
- **Objects** in Python
- **Self** Method in Python
- **init** Method in Python
- **Polymorphism** in Python
- **Encapsulation** in Python
- **Inheritance** in Python
- **Data Abstraction** in Python

---

## Python Class

A **class** is a blueprint for creating objects. It is a logical entity that contains attributes (variables) and methods (functions).

### Why Use Classes?
Imagine tracking the details of multiple dogs, each with attributes like breed and age. Using a list, you could store these attributes, but it would lack organization and scalability:
- Which element represents the breed? 
- Which element is the age? 
- How do you add more attributes efficiently?

Using a class solves these issues by organizing attributes and methods into a structured format.

### Key Points About Python Classes:
1. Classes are created using the `class` keyword.
2. **Attributes** are variables belonging to a class.
3. Attributes are **public** by default and can be accessed using the `.` operator (e.g., `ClassName.Attribute`).

---

### Syntax for Defining a Class:

```python
class ClassName:
    # Statement-1
    # Statement-2
    ...
    # Statement-N
```

### Creating an Empty Class in Python
To define an empty class, use the `pass` keyword.

#### Example:
```python
# Python3 program to demonstrate defining a class

class Dog:
    pass
```

# Python Objects

In **Object-Oriented Programming (OOP)** in Python, an **object** is an entity that has a **state** and **behavior** associated with it. Objects can represent real-world entities like a mouse, keyboard, chair, or pen. In Python, everything is an object—integers, strings, floating-point numbers, lists, dictionaries, etc.

For example:
- The number `12` is an object.
- The string `"Hello, world"` is an object.
- A list is an object that can hold other objects.

---

## Components of an Object:

1. **State**:
   - Represented by the **attributes** of an object.
   - Reflects the properties of the object.
   
2. **Behavior**:
   - Represented by the **methods** of an object.
   - Reflects how the object interacts with other objects or responds to actions.

3. **Identity**:
   - A unique identifier for the object.
   - Allows objects to interact with one another.

---

### Example: Understanding State, Behavior, and Identity

Consider the `Dog` class:
- **Identity**: The dog's name.
- **State (Attributes)**: Properties like breed, age, and color.
- **Behavior**: Actions like eating or sleeping.

---

## Creating an Object

To create an object in Python, you instantiate a class. 

### Syntax:
```python
obj = ClassName()
```

#### Example:
```python
class Dog:
    pass

# Creating an object of the Dog class
obj = Dog()
```
Here:
- `Dog` is the class.
- `obj` is an object of the Dog class.

## `self` in Python Classes

In Python, `self` represents the **instance of the class**. By using `self`, you can access the attributes and methods of the class. It binds the attributes to the provided arguments. Python uses `self` instead of the `@` syntax used in some other programming languages to refer to instance attributes.

---

## What is the Use of `self` in Python?

- The term `self` refers to the **instance of the class** that is currently being used.
- It is customary to use `self` as the first parameter in instance methods of a class.
- Whenever you call a method of an object, the object itself is automatically passed as the first argument to the method using `self`.
- This allows modifying the object’s properties and executing tasks unique to that particular instance.

---

## Example:
```python
class Mynumber:
    def __init__(self, value):
        self.value = value  # Bind the attribute to the instance
    
    def print_value(self):
        print(self.value)

obj1 = Mynumber(17)  # Create an instance of the class
obj1.print_value()   # Call the method
```
### Output:
```
17
```

### Python Class self Constructor
- The __init__ method is a constructor in Python.
- It is automatically called when you create an object of a class.
- The self parameter in the constructor refers to the instance being created and allows you to initialize its attributes.

### Example:
```python
class Subject:
    def __init__(self, attr1, attr2):
        self.attr1 = attr1  # Assign attribute 1
        self.attr2 = attr2  # Assign attribute 2

obj = Subject('Maths', 'Science')  # Create an instance
print(obj.attr1)  # Access attribute 1
print(obj.attr2)  # Access attribute 2
```

### Output:
```
Maths
Science
```
### Is self a Keyword in Python?
- No, self is not a keyword in Python. It is a convention used in instance methods to refer to the instance itself.

### Characteristics of self:
- `Self:` Pointer to the Current Object
The self parameter always points to the current object. When you create an instance of a class, you create an object with its own set of attributes and methods.
### Example:
```python
class Check:
    def __init__(self):
        print("Address of self = ", id(self))

obj = Check()  # Create an object
print("Address of class object = ", id(obj))  # Compare with the address of self
```
### Output:
```
Address of self =  140273244381008
Address of class object =  140273244381008
```

&rarr; Here, the `id(self)` and `id(obj)` are the same, demonstrating that self refers to the current object.

### Example: Creating Class with Attributes and Methods

This code defines a Python class car representing cars with attributes **‘model’** and **‘color’**. The `_init_` constructor initializes these attributes for each instance. The show method displays model and color, while direct attribute access and method calls demonstrate instance-specific data retrieval.

### Program:
```python:
class Car():
    
    # init method or constructor
    def __init__(self, model, color):
        self.model = model
        self.color = color
        
    def show(self):
        print("Model is", self.model )
        print("color is", self.color )
        
# both objects have different self which contain their attributes
audi = Car("audi a4", "blue")
ferrari = Car("ferrari 488", "green")

audi.show()     # same output as car.show(audi)
ferrari.show()  # same output as car.show(ferrari)

print("Model for audi is ",audi.model)
print("Colour for ferrari is ",ferrari.color)
```
### Output:
```
Model is audi a4
color is blue
Model is ferrari 488
color is green
Model for audi is  audi a4
Colour for ferrari is  green
```

### Self in Constructors and Methods
Self is the first argument to be passed in Constructor and Instance Method. Self must be provided as a First parameter to the Instance method and constructor. If you don’t provide it, it will cause an error.

### Program:
```python
# Self is always required as the first argument
class Check:
    def __init__():
        print("This is Constructor")

object = Check()
print("Worked fine")
```
### Output:
```
# Following Error is produced if Self is not passed as an argument
Traceback (most recent call last):
  File "/home/c736b5fad311dd1eb3cd2e280260e7dd.py", line 6, in <module>
    object = Check()
TypeError: __init__() takes 0 positional arguments but 1 was given
```

### Self: Convention, Not Keyword
Self is a convention and not a Python keyword. Self is a parameter in Instance Method and the user can use another parameter name in place of it. But it is advisable to use self because it increases the readability of code, and it is also a good programming practice.

### Program:
```python
class This_is_class: 
    def __init__(in_place_of_self): 
        print("we have used another "
        "parameter name in place of self") 
        
object = This_is_class()
```

### Output:
```
we have used another parameter name in place of self
```

## The Python __init__ Method 
The `_init_` method is similar to constructors in C++ and Java. It is run as soon as an object of a class is instantiated. The method is useful to do any initialization you want to do with your object. Now let us define a class and create some objects using the self and `_init_` method.

#### Creating a class and object with class and instance attributes

### Program:
```python
class Dog:

    # class attribute
    attr1 = "mammal"

    # Instance attribute
    def __init__(self, name):
        self.name = name

# Driver code
# Object instantiation
Rodger = Dog("Rodger")
Tommy = Dog("Tommy")

# Accessing class attributes
print("Rodger is a {}".format(Rodger.__class__.attr1))
print("Tommy is also a {}".format(Tommy.__class__.attr1))

# Accessing instance attributes
print("My name is {}".format(Rodger.name))
print("My name is {}".format(Tommy.name))
```

### Output:
```
Rodger is a mammal
Tommy is also a mammal
My name is Rodger
My name is Tommy
```

### Creating Classes and objects with methods

The `Dog` class is defined with the following attributes and methods:

---

### Attributes:

1. **`attr1`**:  
   - A **class attribute** set to the value `"mammal"`.  
   - Class attributes are shared by all instances of the class.

2. **`__init__`**:  
   - A special method (**constructor**) that initializes an instance of the `Dog` class.  
   - Takes two parameters:  
     - `self`: Refers to the instance being created.  
     - `name`: Represents the name of the dog.  
   - The `name` parameter is used to assign a `name` attribute to each instance.

---

### Methods:

- **`speak`**:  
  - Prints a string that includes the name of the dog instance.

---

## Example:

### Code:
```python
class Dog:

    # Class attribute
    attr1 = "mammal"

    # Instance attribute
    def __init__(self, name):
        self.name = name
        
    def speak(self):
        print("My name is {}".format(self.name))

# Driver code
# Object instantiation
Rodger = Dog("Rodger")
Tommy = Dog("Tommy")

# Accessing class methods
Rodger.speak()
Tommy.speak()
```
### Output:
```
My name is Rodger
My name is Tommy
```
