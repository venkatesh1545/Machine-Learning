- [Inheritance](#python-inheritance)
    - [Benefits and Types of Inheritance](#benefits-of-inheritance)
    - [Inheritance in Python Example](#example-inheritance-in-python)
    - [Example of Single Inheritance](#single-inheritance)
    - [Example of Multi-Level Inheritance](#multilevel-inheritance)
    - [Example of Multiple Inheritance](#multiple-inheritance)
    - [Example of Hierarchical Inheritance](#hierarchical-inheritance)
    - [The **super()** Function](#the-super-function)
    - [Adding Properties with the help of super() method](#adding-properties-with-the-help-of-super-method)
- [Polymorphism]()
# Python Inheritance

Inheritance is a key feature of Python's object-oriented programming (OOP) that allows one class to inherit the properties and methods of another class.

---

## Key Concepts:

1. **Base Class (Parent Class)**:  
   The class whose properties and methods are inherited by another class.

2. **Derived Class (Child Class)**:  
   The class that inherits properties and methods from the base class.

---

### Benefits of Inheritance:
- Represents real-world relationships effectively.
- Promotes **code reusability** by allowing the same code to be reused in multiple places.
- Enables **extensibility**: new features can be added without modifying the base class.
- **Transitive nature**: If class B inherits from class A, all subclasses of B also inherit from A.

---

## Types of Inheritance:
1. **Single Inheritance**:  
   A derived class inherits from a single base class.

2. **Multilevel Inheritance**:  
   A derived class inherits from an immediate parent class, which in turn inherits from another class.

3. **Hierarchical Inheritance**:  
   Multiple derived classes inherit from a single base class.

4. **Multiple Inheritance**:  
   A derived class inherits from more than one base class.

---

## Example: Inheritance in Python

This example demonstrates inheritance where the `Employee` class (child) inherits from the `Person` class (parent).

### Code:
```python
# Python code to demonstrate how parent constructors are called.

# Parent class
class Person(object):
    # Constructor (__init__ method)
    def __init__(self, name, idnumber):
        self.name = name
        self.idnumber = idnumber

    def display(self):
        print(self.name)
        print(self.idnumber)
        
    def details(self):
        print("My name is {}".format(self.name))
        print("IdNumber: {}".format(self.idnumber))
    
# Child class
class Employee(Person):
    def __init__(self, name, idnumber, salary, post):
        self.salary = salary
        self.post = post

        # Invoking the constructor of the parent class
        Person.__init__(self, name, idnumber)
        
    # Overriding the details method
    def details(self):
        print("My name is {}".format(self.name))
        print("IdNumber: {}".format(self.idnumber))
        print("Post: {}".format(self.post))


# Creating an object (instance) of the Employee class
a = Employee('Rahul', 886012, 200000, "Intern")

# Calling methods of the class
a.display()
a.details()
```
### Output:
```
Rahul
886012
My name is Rahul
IdNumber: 886012
Post: Intern
```

- ### Single Inheritance:
A child class inherits from a single parent class.

```python
# Parent class
class Animal:
    def speak(self):
        print("I am an animal")

# Child class
class Dog(Animal):
    def bark(self):
        print("Woof! Woof!")

# Example usage
dog = Dog()
dog.speak()  # Inherited method
dog.bark()   # Method of Dog class
```
### Output:
```
I am an animal
Woof! Woof!
```

- ### Multilevel Inheritance:
A child class inherits from a parent class, and another class inherits from the child class.

```
# Grandparent class
class Animal:
    def speak(self):
        print("I am an animal")

# Parent class
class Mammal(Animal):
    def walk(self):
        print("I can walk")

# Child class
class Dog(Mammal):
    def bark(self):
        print("Woof! Woof!")

# Example usage
dog = Dog()
dog.speak()  # Inherited from Animal
dog.walk()   # Inherited from Mammal
dog.bark()   # Method of Dog class
```
### Output:
```
I am an animal
I can walk
Woof! Woof!
```
- ### Hierarchical Inheritance:
Multiple child classes inherit from a single parent class.
```python
# Parent class
class Animal:
    def speak(self):
        print("I am an animal")

# Child classes
class Dog(Animal):
    def bark(self):
        print("Woof! Woof!")

class Cat(Animal):
    def meow(self):
        print("Meow!")

# Example usage
dog = Dog()
cat = Cat()

dog.speak()  # Inherited method
dog.bark()   # Method of Dog class

cat.speak()  # Inherited method
cat.meow()   # Method of Cat class
```
### Output:
```
I am an animal
Woof! Woof!
I am an animal
Meow!
```
- ### Multiple Inheritance:
A child class inherits from more than one parent class.
```python
# Parent classes
class LandAnimal:
    def walk(self):
        print("I can walk on land")

class WaterAnimal:
    def swim(self):
        print("I can swim in water")

# Child class
class Frog(LandAnimal, WaterAnimal):
    def jump(self):
        print("I can jump")

# Example usage
frog = Frog()
frog.walk()  # Inherited from LandAnimal
frog.swim()  # Inherited from WaterAnimal
frog.jump()  # Method of Frog class
```
### Output:
```
I can walk on land
I can swim in water
I can jump
```
### The **super()** Function
The super() function is a built-in function that returns the objects that represent the parent class. It allows to access the parent class’s methods and attributes in the child class.

#### Example: super() function with simple Python inheritance

&rarr; In this example, we created the object ‘obj’ of the child class. When we called the constructor of the child class ‘Student’, it initialized the data members to the values passed during the object creation. Then using the super() function, we invoked the constructor of the parent class.

```python
# parent class
class Person():
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def display(self):
    print(self.name, self.age)

# child class
class Student(Person):
  def __init__(self, name, age):
    self.sName = name
    self.sAge = age
    # inheriting the properties of parent class
    super().__init__("venkat", age)

  def displayInfo(self):
    print(self.sName, self.sAge)

obj = Student("nani", 19)
obj.display()
obj.displayInfo()
```
### Output:
```
venkat 23
nani 23
```
### Adding Properties with the help of super() method
One of the features that inheritance provides is inheriting the properties of the parent class as well as adding new properties of our own to the child class. Let us see this with an example:

### Program:
```python
# parent class
class Person():
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def display(self):
    print(self.name, self.age)

# child class
class Student(Person):
  def __init__(self, name, age, dob):
    self.sName = name
    self.sAge = age
    self.dob = dob
    # inheriting the properties of parent class
    super().__init__("Rahul", age)

  def displayInfo(self):
    print(self.sName, self.sAge, self.dob)

obj = Student("Mayank", 23, "16-03-2000")
obj.display()
obj.displayInfo()
```
### Output:
```
Rahul 23
Mayank 23 16-03-2000
```
