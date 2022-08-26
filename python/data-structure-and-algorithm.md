# Data Structure and Algorithm

This notes based on [GreeksforGreeks](https://www.geeksforgeeks.org/python-data-structures-and-algorithms/?ref=lbp)

## Data Structures

### Frozen Sets

While elements of a set can be modified at any time, elements of the frozen set remain the same after creation.

If no parameters are passed, it returns an empty frozenset.

```python
# creating a dictionary
Student = {"name": "Ankit", "age": 21, "sex": "Male",
           "college": "MNNIT Allahabad", "address": "Allahabad"}
 
# making keys of dictionary as frozenset
key = frozenset(Student)
 
# printing dict keys as frozenset
print('The frozen set is:', key)

# Output may be "The frozen set is: frozenset({'college', 'sex', 'age', 'name', 'address'})"
# It won't change while the execution stage
```

