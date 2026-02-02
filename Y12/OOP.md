## Object Orientated Programming (OOP)

To define an object, we must use a **Class** (It is the generic representation for all objects of the same type)

```python
class Person:
```

When we have an attribute that we want  to store ( or state ) then we will use a variable to represent it
<br><br>

To create a person, we first need a **constructor**

This is a function which is called when you create a person

```python
def __init__(self): #Must be called this
  self.name = input()
  self.age = int(input())
  self.height = int(input())
```
<br><br>

To make a new person you would:

```python
person1 = Person()
me = Person()
```
<br><br>

To get a value from that var you can:

```python
print(me.name)
print(me.age)
etc
```
<br><br>
<br><br>

### Inheritance

It is a way to re-use code, where one class can access the properties and methods of a **Parent** class.

So, this means you could have a pet class, and under that have a Dog and Cat class.

Things that’s both dogs and cats can do, would then be stored in the pet class.

Things that dogs and cats do differently the get stored in the **Dog** or **Cat** class

```python
class Cat(Pet)

# The parent = Pet
```

| Advantages | Disadvantages |
| -------------- | --------------- |
| Enhanced maintainability | Fragile - changes to base class may have side effects |
| Allows for code re-use | Data leak - Vulnerable if superclass is compromised (single point of attack) |
| More efficient (Saves time and storage places) |  |

<br><br>

### Modifiers

#### Public Modifier:

- This means that they can be accessed from outside the class directly

- They are public knowledge such as `person.age`

- Leave as is

#### Private Modifier:

- This means they can only be accessed from within the instance of that class

- Theyre effectively hidden from all the other objects `Person.__age`

- Double underscore

#### Protected Modifier:

- This is the same as private, except any subclasses that inherit from this class

- Can also use the variable or method, `Person._age`

- Single underscore

<br><br>
----------

**Getter** = Gets a value

```python
def getName(self):
  return self.__name
```

**Setter** = Sets a value

----------
<br><br>
### Mantra Of The OOP Programmer (Principles):

- Always **encapsulate** what varies

- Favour **composition** over Inheritance

- Program to interfaces, not implementation (**Polymorphism**)
<br><br>
<br><br>
### Composition

Where an object contains other instances of objects, but these other objects are created and exist only inside of the container (When container is destroyed, the composed classes are also destroyed)

### Aggregation

It is a type of composition. You have an Aggregation relationship when an object is created, and exists, a container class will also exist, but a link will be put inbetween the 2 classes.
<br><br>

### Polymorphism

The ability of a method to behave differently depending on the object on which the method is involved with

**Static Methods:**

Related to the class theyre in but dont require access to any class specific data. Can be utilised without instantiating the class, represented with `@staticmethod`

Advantages: You may want to group a collection of related functions which will Impact or be part of a class which do not depend on the data held within the class as they are used w/o instantiation

**Virtual Method:**

A method that you are designing to be overwritten within your code which has a base functionality

When you want sub-classes to have a behaviour which will be consistent and shared but where the implementation in the sub-classes could behave differently

**Abstract Method:**

A method which you are designing to be overwritten within your code which has no functionality
