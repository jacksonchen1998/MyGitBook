---
description: Notes from W3Schools & Documentation (Python 3.9)
---

# Learn the basics

[W3Schools](https://www.w3schools.com/python/)

[Python Documentation](https://docs.python.org/zh-tw/3.10/tutorial/index.html)

## W3Schools

```python
x = 3 + 4j
// type(x) is complex, j 代表虛部
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
// Output will be ['1', 'Happy', '你好']
```

* Tuple: 是一種序列數據類型，可以包含不同數據類型的元素，但這些元素本質上是不可變的。\
  因為是靜態容器，所以使用上比 list 快。

```python
list = ("1", "Happy", "你好")
print(list)
// Output will be ('1', 'Happy', '你好')
```

![](<../.gitbook/assets/image (1).png>)

