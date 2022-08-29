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

#### Deletion / Reverse Linked List

```python
# A complete working Python3 program to
# demonstrate deletion in singly
# linked list with class
 
# Node class
 
class Node:
 
    # Constructor to initialize the node object
    def __init__(self, data):
        self.data = data
        self.next = None
 
 
class LinkedList:
 
    # Function to initialize head
    def __init__(self):
        self.head = None
 
    # Function to insert a new node at the beginning
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        self.head = new_node
 
    # Given a reference to the head of a list and a key,
    # delete the first occurrence of key in linked list
    def deleteNode(self, key):
 
        # Store head node
        temp = self.head
 
        # If head node itself holds the key to be deleted
        if (temp is not None):
            if (temp.data == key):
                self.head = temp.next
                temp = None
                return
 
        # Search for the key to be deleted, keep track of the
        # previous node as we need to change 'prev.next'
        while(temp is not None):
            if temp.data == key:
                break
            prev = temp
            temp = temp.next
 
        # if key was not present in linked list
        if(temp == None):
            return
 
        # Unlink the node from linked list
        prev.next = temp.next
 
        temp = None
 
    # Utility function to print the linked LinkedList
 
    def printList(self):
        temp = self.head
        while(temp):
            print(" %d" % (temp.data)),
            temp = temp.next
            
    def get_length(self):
        temp = self.head
        count = 0
        while(temp):
            count += 1
            temp = temp.next
            
        return count
    def reverse(self):
        current = self.head
        prev = None
        while(current is not None):
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        self.head = prev
 
# Driver program
llist = LinkedList()
llist.push(7)
llist.push(1)
llist.push(3)
llist.push(2)
 
print("Created Linked List: ")
llist.printList() # 2 3 1 7
llist.deleteNode(1) # 2 3 7
print("\nLinked List after Deletion of 1:")
llist.printList()
print("Count length: {}".format(llist.get_length()))
llist.reverse()
llist.printList() # 7 3 2
 
# This code is contributed by Nikhil Kumar Singh (nickzuck_007)
```

### Stack

append: insert into the last

```python
stack = []

stack.append('a')
stack.append('b')
stack.append('c')

print(stack) # a b c

print(stack.pop()) # c
print(stack.pop()) # b
print(stack.pop()) # a

print(stack)
```

### Queue

```python
queue = []

queue.append('A')
queue.append('B')
queue.append('C')

print(queue)

print(queue.pop(0)) # A
print(queue.pop(0)) # B
print(queue.pop(0)) # C

print(queue)
```

### Priority Queue

```python
# A simple implementation of Priority Queue
# using Queue.
class PriorityQueue(object):
    def __init__(self):
        self.queue = []
 
    def __str__(self):
        return ' '.join([str(i) for i in self.queue])
 
    # for checking if the queue is empty
    def isEmpty(self):
        return len(self.queue) == 0
 
    # for inserting an element in the queue
    def insert(self, data):
        self.queue.append(data)
 
    # for popping an element based on Priority
    def delete(self):
        try:
            max_val = 0
            for i in range(len(self.queue)):
                if self.queue[i] > self.queue[max_val]:
                    max_val = i
            item = self.queue[max_val]
            del self.queue[max_val]
            return item
        except IndexError:
            print()
            exit()
 
if __name__ == '__main__':
    myQueue = PriorityQueue()
    myQueue.insert(12)
    myQueue.insert(1)
    myQueue.insert(14)
    myQueue.insert(7)
    print(myQueue) # 12 1 14 7     
    while not myQueue.isEmpty():
        print(myQueue.delete()) # 14 12 7 1
```

