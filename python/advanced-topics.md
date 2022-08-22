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

### Inheritance

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

### Iterators

Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable _containers_ which you can get an iterator from.

All these objects have a `iter()` method which is used to get an iterator:

```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit))
print(next(myit))
print(next(myit))

#Output will be 
#apple
#banana
#cherry
```

The `__iter__()` method acts similar, you can do operations (initializing etc.), but must always return the iterator object itself.

The `__next__()` method also allows you to do operations, and must return the next item in the sequence.

To prevent the iteration to go on forever, we can use the `StopIteration` statement.

```python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    if self.a <= 20:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

for x in myiter:
  print(x)
  
# Output will be 1 ~ 20
```

### Scope

* Local Scope: 區域
* Globsl Scope: 全域\
  我們可以使用 `global` 使得區域變數轉成全域變數

### Modules

可以透過 python 檔案 `.py` 來當成一個 module

```python
# mymodule.py

person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}
```

```python
# main.py

import mymodule

a = mymodule.person1["age"]
print(a)

# Output will be "36"
```

