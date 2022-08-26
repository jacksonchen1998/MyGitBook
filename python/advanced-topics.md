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

{% code title="mymodule.py" %}
```python
person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}
```
{% endcode %}

{% code title="main.py" %}
```python
import mymodule

a = mymodule.person1["age"]
print(a)

# Output will be "36"
```
{% endcode %}

#### [import platform](https://docs.python.org/zh-tw/3/library/platform.html)

<pre class="language-python"><code class="lang-python">import platform as p

print(p.machine())
print(p.platform())
print(p.system())

# Output will be
# AMD64
<strong># Windows-10-10.0.19043-SP0
</strong># Windows</code></pre>

### [JSON (<mark style="color:red;">J</mark>ava<mark style="color:red;">S</mark>cript <mark style="color:red;">o</mark>bject <mark style="color:red;">n</mark>otation)](https://www.w3schools.com/python/python\_json.asp)

```python
import json

# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y["age"])

# Output will be "30"
```

我們可以用 `json.dumps()` 來將 Python 資料儲存成 JSON 格式

```python
import json

# a Python object (dict):
x = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string:
print(y)

# Output will be {"name": "John", "age": 30, "city": "New York"}
```

### [RegEx](https://www.fooish.com/regex-regular-expression/)

正規表示法 (Regex) 是用來**處理字串的方法**，Regex 用自己一套特殊的符號表示法，讓我們可以很方便的搜尋字串、取代字串、刪除字串或測試字串是否符合樣式規則。

Regex 它**不是一個程式語言**，他只是一種「字串樣式規則」的「表示法」，用來表達字元符號在字串中出現的規則，**大部分的程式語言都有支援 Regex 的用法**，而**任何工具只要支援這種表示法**，你就可以在這工具上用 Regex 來處理字串。

### try...expect...

The `try` block lets you test a block of code for errors.

The `except` block lets you handle the **error.**

The `else` block lets you execute code when there is **no error.**

The `finally` block lets you execute code, regardless of the result of the try- and except blocks.

### File Handling

`"r"` - Read - Default value. Opens a file for reading, error if the file does not exist

`"a"` - Append - Opens a file for appending, creates the file if it does not exist

`"w"` - Write - Opens a file for writing, creates the file if it does not exist

`"x"` - Create - Creates the specified file, returns an error if the file exists

`"t"` - Text - Default value. Text mode

`"b"` - Binary - Binary mode (e.g. images)
