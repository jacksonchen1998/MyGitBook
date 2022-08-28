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

### [Matrix](https://www.geeksforgeeks.org/python-numpy/)

```python
numpy.append(arr, values, axis=None)
```

The axis along which _values_ are appended. If _axis_ is not given, both _arr_ and _values_ are flattened before use.

<pre class="language-python"><code class="lang-python"><strong>import numpy as np
</strong>  
a = np.array([[1,2,3,4],[4,55,1,2],
              [8,3,20,19],[11,2,22,21]])
m = np.reshape(a,(4, 4))

# Adding Element
m = np.append(m,[[1, 15,13,11]],0)
print("\nAdding Element")
print(m)

# Adding Element
# [[ 1  2  3  4]
# [ 4 55  1  2]
# [ 8  3 20 19]
# [11  2 22 21]
# [ 1 15 13 11]]</code></pre>

### Bytearray

```python
# Creating bytearray
a = bytearray((12, 8, 25, 2))
print("Creating Bytearray:")
print(a)

# Creating Bytearray:
# bytearray(b'\x0c\x08\x19\x02')
```

### Linked List

```python
# A simple Python program to introduce a linked list
  
# Node class
class Node:
  
    # Function to initialise the node object
    def __init__(self, data):
        self.data = data # Assign data
        self.next = None # Initialize next as null
  
  
# Linked List class contains a Node object
class LinkedList:
  
    # Function to initialize head
    def __init__(self):
        self.head = None
    
    # This function prints contents of linked list
    # starting from head
    def printList(self):
        temp = self.head
        while (temp):
            print (temp.data)
            temp = temp.next
  
  
# Code execution starts here
if __name__=='__main__':
  
    # Start with the empty list
    llist = LinkedList()
  
    llist.head = Node(1)
    second = Node(2)
    third = Node(3)
  
    llist.head.next = second; # Link first node with second
  
    second.next = third; # Link second node with the third node
    
    llist.printList()

# Output will be
#1
#2
#3
```

#### Insertion Linked List

```python
# A complete working Python program to demonstrate all
# insertion methods of linked list

class Node:
    def __init__(self, data):
        self.data = data  # Assign data
        self.next = None  # Initialize next as null
 
class LinkedList:
    def __init__(self):
        self.head = None
 
    # Function to insert a new node at the beginning
    def push(self, new_data):
 
        new_node = Node(new_data)
 
        new_node.next = self.head
 
        self.head = new_node
 
 
    # This function is in LinkedList class. Inserts a
    # new node after the given prev_node. This method is
    # defined inside LinkedList class shown above */
    def insertAfter(self, prev_node, new_data):
 
        if prev_node is None:
            print("The given previous node must inLinkedList.")
            return
            
        new_node = Node(new_data)
 
        new_node.next = prev_node.next
 
        prev_node.next = new_node
 
    # This function is defined in Linked List class
    # Appends a new node at the end.  This method is
    # defined inside LinkedList class shown above */
    def append(self, new_data):

        new_node = Node(new_data)
 
        if self.head is None:
            self.head = new_node
            return
 
        last = self.head
        while (last.next):
            last = last.next
 
        last.next =  new_node
 
    # Utility function to print the linked list
    def printList(self):
        temp = self.head
        while (temp):
            print(temp.data,end=" ")
            temp = temp.next
 
# Code execution starts here
if __name__=='__main__':
 
    llist = LinkedList()

    llist.append(6) # 6
 
    llist.push(7); # 7 6
 
    llist.push(1); # 1 7 6

    llist.append(4) # 1 7 6 4
 
    llist.insertAfter(llist.head.next, 8) # 1 7 8 6 4
 
    print('Created linked list is: ')
    llist.printList()
 
# This code is contributed by Manikantan Narasimhan
```

