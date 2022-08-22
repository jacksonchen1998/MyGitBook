# Advanced Topics

### Class

#### The \_\_init\_\_() Function

All classes have a function called \_\_init\_\_(), which is always executed when the class is being initiated.

#### The self Parameter

The `self` parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

It does not have to be named `self` , you can call it whatever you like, but it has to be the first parameter of any function in the class:

```python
class Person:
    def __init__(mysillyobject, name, age):
        mysillyobject.name = name
        mysillyobject.age = age
    
    def myfunc(abc):
        print("Hello my name is " + abc.name)

p1 = Person("John", 36)
p1.myfunc()

# Output will be "Hello my name is John"
```

### Python Inheritance

Inheritance allows us to define a class that inherits all the methods and properties from another class.

**Parent class** is the class being inherited from, also called base class.

**Child class** is the class that inherits from another class, also called derived class.

#### Use the super() Function

Python also has a `super()` function that will make the child class inherit all the methods and properties from its parent:

```python
class Student(Person):
    def __init__(self, fname, lname):
    super().__init__(fname, lname)
```

在這裡 Person 為 parent class，Student 為 child class，\
此時 Student 透過 `super()` 就會繼承 Person 所有的 method。
