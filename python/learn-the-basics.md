---
description: Notes from W3Schools & Documentation (Python 3.9)
---

# Learn the basics

[W3Schools](https://www.w3schools.com/python/)

[Python Documentation](https://docs.python.org/zh-tw/3.10/tutorial/index.html)

## W3Schools

```python
x = 3 + 4j
# type(x) is complex, j 代表虛部
```

### Escape Characters

| No. |     | Meanings |
| --- | --- | -------- |
| 1   | \\' | 單引號      |
| 2   | \n  | 換行       |
| 3   | \t  | 空格       |
| 4   | \b  | 退格       |
| 5   | \o  | 8進制      |
| 6   | \x  | 16進制     |

### Difference Between List and Tuple

* List: 類似陣列，且內容類別不須相同，是用於保留數據序列並進一步反覆運算數據的有用工具。

```python
list = ["1", "Happy", "你好"]
print(list)
# Output will be ['1', 'Happy', '你好']
```

* Tuple: 是一種序列數據類型，可以包含不同數據類型的元素，但這些元素本質上是不可變的。\
  因為是靜態容器，所以使用上比 list 快。

```python
list = ("1", "Happy", "你好")
print(list)
#Output will be ('1', 'Happy', '你好')
```

![](<../.gitbook/assets/image (4) (2).png>)

#### Set

A set is a collection which is _unordered_, _unchangeable\*_, and _unindexed_.

```python
thisset = {"apple", "banana", "cherry", "apple"}
```

#### Dictionary

Duplicate values will overwrite existing values.

```python
thisdict = { 
"brand": "Ford", 
"model": "Mustang", 
"year": 1964, 
"year": 2020 
}
print(thisdict)
# Output will be {'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
```

[Dictionary method](https://www.w3schools.com/python/python\_ref\_dictionary.asp)

#### Multiple statement in the same line

```python
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
```

### Arbitrary Arguments, \*args

If you do not know how many arguments that will be passed into your function, add a `*` before the parameter name in the function definition.

This way the function will receive a _**tuple**_ of arguments, and can access the items accordingly:

```python
def my_function(*kids): 
    print("The youngest child is " + kids[2])
    
my_function("Emil", "Tobias", "Linus")

# Output will be "The youngest child is Linus"
```

### Arbitrary Keyword Arguments, \*\*kwargs

If you do not know how many keyword arguments that will be passed into your function, add two asterisk: `**` before the parameter name in the function definition.\
\
This way the function will receive a _**dictionary**_** ** of arguments, and can access the items accordingly:

```python
def my_function(**kid):
  print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")

# Output will be "His last name is Refsnes"
```

### [Lambda](https://www.learncodewithmike.com/2019/12/python-lambda-functions.html)

`lambda`` `_`arguments`_` ``:`` `_`expression`_

* lambda(關鍵字)
* parameter\_list(參數清單)
* expression(運算式)

```python
def myfunc(n):
    return lambda a : a * n

mydoubler = myfunc(2)

print(mydoubler(11))

# Output will be "22"
```

