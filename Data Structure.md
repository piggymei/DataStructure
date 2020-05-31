
#### linear data structure: array, stack, queue and linked list
hierarchical data structure: tree

##### array: an ordered sequence of items, indexed by numbers 0 to N-1, where N is the size of the array. contiguous area of memory consisting of equal-size elements indexed by contigous integers. constant-time access according to the index, O(N) to add or remove elements.

#### singly Linked list: node contains value and  a pointer.
access is O(n), for remove or add, situation if we have the pointers point to the right position
add before is O(N) add after is O(1)

#### doubly linked List: constant time to insert between nodes or remove a node with the pointers in the right position,list elements do not need to be contiguous

#### Stack: abstract data type can push and top and pop the top the element easily. eg blanced brackets.
stack can be implemented with array and linked list, the difference is the array is allocated fix amount of space, the linked list has additional head pointer. stack is last in first out.

#### Queue: Enqueue/Dequeue, FIFO, can be implemented with linked list with head and tail poiters. and implemented with array with read index, and write index. enqueue: change write index, dequeue: change the read index, and the buffer is 1 in the array.

#### Heap data structure is a complete binary tree satisfy the heap property. Max heap, value of each node is always greater than its child node, the value of the root is the largest.
Basic operation: GetMax, O(1), insert, O(logn), extractMax, O(logn), remove(i), O(logn).
to keep the binary tree shallow

Completed binary tree: all the levels are filled except the last one  which is filled from left to the right. with n nodes and the height at most O(logn). Can be stored as Array, parent(i), leftchild 2i-1, rightchild 2i.

#### priority queue is an abstract data type supporting the following operations: insert(p) and extractMax() with max priority, additional operations as Remove(it), GetMax(), ChangePriority().
Algorithsm that use Dijsktra's algorithm, Prim's algorithm, Huffman's algorithm, Heap sort.
Naive implementation: array or linked list. sorted or unsorted, it will be extractMax o(1), insert O(n) or extractMax o(n), insert O(1).
 

Heapify:  turn to the binary tree to heap.
```
def min_heapify(array, i):
    left = 2 * i + 1
    right = 2 * i + 2
    length = len(array) - 1
    smallest = i    if left <= length and array[i] > array[left]:
        smallest = left
    if right <= length and array[smallest] > array[right]:
        smallest = right
    if smallest != i:
        array[i], array[smallest] = array[smallest], array[i]
        min_heapify(array, smallest)
 ```
Time complexity O(log(n))
```
def build_min_heap(array):
for i in reversed(range(len(array)//2)):
min_heapify(array, i)
```
Time complexity O(nlog(n))

Heapsort:
```def heapsort(array):
    array = array.copy()
    build_min_heap(array)    sorted_array = []
    for _ in range(len(array)):
        array[0], array[-1] = array[-1], array[0]
        sorted_array.append(array.pop())
        min_heapify(array, 0)    return sorted_array
 ```
Time complexity O(nlog(n))
#### Tree height，depth
node contains tree and children.

The ```depth``` of a node is the number of edges from the node to the tree's root node.
A root node will have a depth of 0.
```level```: depth + 1
The ```height``` of a node is the number of edges on the longest path from the node to a leaf.
A leaf node will have a height 0, can be calculated recursively
sibling, leaf, interior node
```size``` of the tree: total nodes of the tree, can be calculated recursively

traversal tree: 
Depth-first: completely traverse one subtree before exploring a sibling sub-tree
inorder traversal(typically for binary tree), preorder traversal, postorder traversal
recursively traversal is saving implicity where we are on the stack
Breadth-first: traverse all nodes at one level before progressing to the next level
use the queue: enqueue, dequeue while the queue is not empty and enqueue the child.
#### Forest: collection of trees

#### Binary Search Tree
contains key, left and right
Has the most of two children for each node, every node's val is greater or equal than the left child, and less than the right child's val. tree either is empty or has a key and a list of child tree.

#### Dynamic Arrays (resizable array)
Store a pointer to a dynamically allocated array, and replace it with a newly allocated array as needed.Implemented get(i), set(i, val), remove(i), pushback(val),size(), capacity.

#### Amortized Analysis:
Aggregate method use example of dynamic array
Banker's method 
Physicist's Method: s = ct + phi(ht)-phi(ht-1), sum of the amortized costs is phi(hn) - phi(h0) + sum of ci >= sum of of ci, phi(hn) = 2xsize - capacity, s =3.

#### Hash table
