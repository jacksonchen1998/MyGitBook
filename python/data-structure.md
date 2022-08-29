# Data Structure

This notes based on [GreeksforGreeks](https://www.geeksforgeeks.org/python-data-structures-and-algorithms/?ref=lbp)

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

### Heap

heapify 順序是由後往前選取 list 內元素建 min heap，

而 list 輸出元素順序，由 heap index 由 root 往下輸出。

#### Method&#x20;

`heapq.heappush`(_heap_, _item_)

`heapq.heappop`(_heap_)

`heapq.heappushpop`(_heap_, _item_)

`heapq.heapify`(_x_)

```python
# importing "heapq" to implement heap queue
import heapq
  
# initializing list
li = [5, 7, 9, 1, 3]
  
# using heapify to convert list into heap
heapq.heapify(li)
  
# printing created heap
print ("The created heap is : ",end="")
print (list(li))

# using heappush() to push elements into heap
# pushes 4
heapq.heappush(li,4)
  
# printing modified heap
print ("The modified heap after push is : ",end="")
print (list(li))
  
# using heappop() to pop smallest element
print ("The popped and smallest element is : ",end="")
print (heapq.heappop(li))

# Output will be
#The created heap is : [1, 3, 9, 7, 5]
#The modified heap after push is : [1, 3, 4, 7, 5, 9]
#The popped and smallest element is : 1
```

### Tree

```python
# Python program to for tree traversals
  
# A class that represents an individual node in a
# Binary Tree
class Node:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.val = key
  
# A function to do inorder tree traversal
def printInorder(root):
  
    if root:
        printInorder(root.left)
        print(root.val, end = " "),
        printInorder(root.right)
  
# A function to do postorder tree traversal
def printPostorder(root):
  
    if root:
        printPostorder(root.left)
        printPostorder(root.right)
        print(root.val, end = " "),
  
# A function to do preorder tree traversal
def printPreorder(root):
  
    if root:
        print(root.val, end = " "),
        printPreorder(root.left)
        printPreorder(root.right)
        
def printLevelorder(root):
  
    # Base Case
    if root is None:
        return
      
    # Create an empty queue
    # for level order traversal
    queue = []
  
    # Enqueue Root and initialize height
    queue.append(root)
  
    while(len(queue) > 0):
      
        # Print front of queue and
        # remove it from queue
        print (queue[0].val, end = " ")
        node = queue.pop(0)
  
        # Enqueue left child
        if node.left is not None:
            queue.append(node.left)
  
        # Enqueue right child
        if node.right is not None:
            queue.append(node.right)
  
# Driver code
root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)

'''
    1
   / \
  2   3
 / \
4   5  
'''

print("Preorder traversal of binary tree is")
printPreorder(root)
  
print("\nInorder traversal of binary tree is")
printInorder(root)
  
print("\nPostorder traversal of binary tree is")
printPostorder(root)

print("\nLevelorder traversal of binary tree is")
printLevelorder(root)

'''
Output will be

Preorder traversal of binary tree is
1 2 4 5 3 
Inorder traversal of binary tree is
4 2 5 1 3
Postorder traversal of binary tree is
4 5 2 3 1
Levelorder traversal of binary tree is
1 2 3 4 5
'''
```

### Binary Search Tree

```python
# Python program to demonstrate
# insert operation in binary search tree
  
# A utility class that represents
# an individual node in a BST
class Node:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.val = key
  
# A utility function to insert
# a new node with the given key
def insert(root, key):
    if root is None:
        return Node(key)
    else:
        if root.val == key:
            return root
        elif root.val < key:
            root.right = insert(root.right, key)
        else:
            root.left = insert(root.left, key)
    return root
  
# A utility function to do inorder tree traversal
def inorder(root):
    if root:
        inorder(root.left)
        print(root.val, end = " ")
        inorder(root.right)
  
# Driver program to test the above functions
# Let us create the following BST
#     50
#    /   \
#   30    70
#  / \    / \
# 20 40  60 80
  
r = Node(50)
r = insert(r, 30)
r = insert(r, 20)
r = insert(r, 40)
r = insert(r, 70)
r = insert(r, 60)
r = insert(r, 80)
  
# Print inorder traversal of the BST
inorder(r) # 20 30 40 50 60 70 80 
```

### Graph (non-directed)

* Adjacency matrix
* Adjencecy list

Change to directed graph, just comment out this code section on line 20

```python
self.adjMatrix[to][frm] = cost
```

{% code lineNumbers="true" %}
```python
# A simple representation of graph using Adjacency Matrix
class Graph:
    def __init__(self,numvertex):
        self.adjMatrix = [[-1]*numvertex for x in range(numvertex)]
        self.numvertex = numvertex
        self.vertices = {}
        self.verticeslist = [0]*numvertex
  
    def set_vertex(self,vtx,id):
        if 0<=vtx<=self.numvertex:
            self.vertices[id] = vtx
            self.verticeslist[vtx] = id
  
    def set_edge(self,frm,to,cost=0):
        frm = self.vertices[frm]
        to = self.vertices[to]
        self.adjMatrix[frm][to] = cost
          
        # for directed graph do not add this
        self.adjMatrix[to][frm] = cost
  
    def get_vertex(self):
        return self.verticeslist
  
    def get_edges(self):
        edges=[]
        for i in range (self.numvertex):
            for j in range (self.numvertex):
                if (self.adjMatrix[i][j]!=-1):
                    edges.append((self.verticeslist[i],self.verticeslist[j],self.adjMatrix[i][j]))
        return edges
          
    def get_matrix(self):
        return self.adjMatrix
  
G = Graph(6)
G.set_vertex(0,'a')
G.set_vertex(1,'b')
G.set_vertex(2,'c')
G.set_vertex(3,'d')
G.set_vertex(4,'e')
G.set_vertex(5,'f')
G.set_edge('a','e',10)
G.set_edge('a','c',20)
G.set_edge('c','b',30)
G.set_edge('b','e',40)
G.set_edge('e','d',50)
G.set_edge('f','e',60)

'''
      f
  10  |60  50
a  -  e   -  d
|20   |40
c  -  b
  30
'''

print("Vertices of Graph")
print(G.get_vertex()) # ['a', 'b', 'c', 'd', 'e', 'f']
  
print("Edges of Graph")
print(G.get_edges())

'''
[('a', 'c', 20), ('a', 'e', 10), ('b', 'c', 30), 
('b', 'e', 40), ('c', 'a', 20), ('c', 'b', 30), 
('d', 'e', 50), ('e', 'a', 10), ('e', 'b', 40), 
('e', 'd', 50), ('e', 'f', 60), ('f', 'e', 60)]
'''
  
print("Adjacency Matrix of Graph")
print(G.get_matrix())

'''
[[-1, -1, 20, -1, 10, -1], 
[-1, -1, 30, -1, 40, -1], 
[20, 30, -1, -1, -1, -1], 
[-1, -1, -1, -1, 50, -1], 
[10, 40, -1, 50, -1, 60], 
[-1, -1, -1, -1, 60, -1]]
'''
```
{% endcode %}

```python
# A class to represent the adjacency list of the node
class AdjNode:
    def __init__(self, data):
        self.vertex = data
        self.next = None
  
# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [None] * self.V
  
    # Function to add an edge in an undirected graph
    def add_edge(self, src, dest):
      
        # Adding the node to the source node
        node = AdjNode(dest)
        node.next = self.graph[src]
        self.graph[src] = node
  
        # Adding the source node to the destination as
        # it is the undirected graph
        node = AdjNode(src)
        node.next = self.graph[dest]
        self.graph[dest] = node
  
    # Function to print the graph
    def print_graph(self):
        for i in range(self.V):
            print("Adjacency list of vertex {}\n head".format(i), end="")
            temp = self.graph[i]
            while temp:
                print(" -> {}".format(temp.vertex), end="")
                temp = temp.next
            print(" \n")
  
  
# Driver program to the above graph class
if __name__ == "__main__":
    V = 5
    graph = Graph(V)
    graph.add_edge(0, 1)
    graph.add_edge(0, 4)
    graph.add_edge(1, 2)
    graph.add_edge(1, 3)
    graph.add_edge(1, 4)
    graph.add_edge(2, 3)
    graph.add_edge(3, 4)
    
    '''
        4
      / | \
    0 - 1 - 3
        | /
        2
    '''
  
    graph.print_graph()
    
'''
Output will be

Adjacency list of vertex 0
head -> 4 -> 1 

Adjacency list of vertex 1
head -> 4 -> 3 -> 2 -> 0

Adjacency list of vertex 2
head -> 3 -> 1

Adjacency list of vertex 3
head -> 4 -> 2 -> 1

Adjacency list of vertex 4
head -> 3 -> 1 -> 0

'''
```
