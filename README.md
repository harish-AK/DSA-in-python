# DSA-in-python 

## DSA in Leetcode problems (a complete roadmap) is [here](https://github.com/harish-AK/DSA-roadmap/blob/main/AlGORITHM%20MAP.ipynb)  


## Array operations and algorithms - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Array%20operations)
Array operations are - insertion ,deletion, update, searching (linear, binary), sorting (bubble, selection, insertion, merge, quick, heap, counting, radix, bucket ), two pointer algorithm, sliding window 
### Algorithms:
  1. Two pointer
  2. Siding window


## Hashmap - an dictionary{}


## Linked list - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Linked%20list)
Linked is a collection of data (node) where each node contains an value and a reference to next node. Last node is pointed to null.
Allocate memory one by one.
contiguous data structure - single section of memory block will be allocated.
### Types:
  1. Singular linked list
  2. Doubly linked list
  3. Circular linked list
### Algorithms:
  1. Slow fast


## Stack - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Stack)
It is an linear data structure which uses LIFO and FIFO
### functions
**empty()** - returns True if stack is empty else False - O(1)
**size()** - returns size of stack - O(1)
**top()** - top most value in the stack (last value in the array) - O(1)
**push(a)** - insert an element at last (top) - O(1)
**pop()** - deleted the top most element in the stack - O(1)
**peek()** - get the top most element without deleting it.

### Types
  ### Monotonic increasing stack
  
  initialize empty stack
  iterate to elements of array.
  while stack is not empty and stack.peek() < curr:
  	  pop the element and insert the current.
  at end monotonic increasing stack will be formed.
  
  ### Monotonic decreasing stack
  
  initialize empty stack.
  iterate elements of the array.
  while stack is not empty and stack.peek() > curr:
  	  pop the element and insert the current element.
  at end monotonic decreasing stack will be formed.

## Queue - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Queue)
Queue follows FIFO manner. add and remove elements at the same time.

### Operations
**enqueue()** - add an element to queue if queue is full returns queue overflow condition - O(1)
**dequeue()** - removes first element from the queue - O(1)
**front()** - returns the front element of the queue (first element) - O(1)
**rear()** - returns the rear element of the queue (last element) - O(1)

  `from collections import deque
  `q = [ 1, 2, 3, 4 ]
  `q.popleft() # will pop 1
  
  `from queue import Queue
  `q = Queue(maxsize = 3)
  `q.put(1) - insert an element
  `q.get() - pop the first element
  `q.isempty() - returns True if queue is empty else False
  `q.full()  - returns True if queue is full else Fasle
  
### Monotonic increasing and decreasing queue

index  v                  Increasing queue                              Decreasing queue  
1         5                         [5] [5]  
2         3                        [3] 3 kick out 5                                [5, 3] #3->5  
3         1                        [1] 1 kick out 3                                [5, 3, 1] #1->3  
4         2                        [1, 2] #2->1                                 [5, 3, 2] 2 kick out 1 #2->3  
5         4                         1, 2, 4] #4->2                             [5,4] 4 kick out 2, 3 #4->2


## Priority queue
2i+1 - gives left child in a tree
2i+2 - gives right child of a tree
where i is the index starting from 0.

Min heap and Max heap
Min heap - parent is smaller than its child
to pop an element we do heapify  - heappop() whose time complexity is O(logn). cause after popped the tree need to be adjusted.
Max heap - root will be bigger than its parent.
heapq module only supports min heap to make it as an max heap we need an -heap

## Searching techniques - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Searching)
  1. Linear search
  2. Binary search
### Linear search
  Is known for sequential search

  if an arr = [1,2,3,4,5]
  for i in arr:
  	if i == 1:
  		print(i)
  Sequentially search the target starting from 1st index to last index.

### Binary search
  This works for a sorted array only. 
  First, mid = (high-low)/2 will be calculated. 
  if the mid is greater than the target search will be on left part. if mid is smaller than target search will be on right half.
  This process will continue till the target element is found.
  
  high = len(arr) - 1
  low = 0
  while high >= low:
  	mid = low+(high-low)//2
  	if arr[mid] > tar:
  		high = mid-1
  	elif arr[mid] < tar:
  		low = mid + 1


## Sorting techniques - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Sorting)
Bubble sort

Lets take an array like arr = [3 , 2, 6, 9, -2, 1, 0, -9]
this will start from index 1 then checks whether the previous element is smaller then the current one or not if not swap those to elements. arr[i] < arr[i-1] results arr[i], arr[i-1] = arr[i-1], arr[i].
This process will continue until no swaps needed. 

**Time complexity - O(n^2)**
**Space complexity - O(1)**

## Insertion sort

arr = [3 , 2, 6, 9, -2, 1, 0, -9] take an array in that use two indexes i and j which points index 1 at the start and j used to check previous number if its not sorted means swap it if  its sorted means assign i and j to next element, then j will be decreased all the way to 0th index to check the i is lesser than the j or not.

**Time complexity - O(n^2)**
**Space complexity - O(1)**

## Selection sort

In this sorting technique i, j will be initialized to 0th index j will used to iterate the array if j less than i swap j and i and increment i and j by 1 (1st index).  

**Time complexity - O(n^2)**
**Space complexity - O(1)**

## Merge sort

Is an recursive sorting algorithm uses divide and conquer method.
### Divide :
first middle element will found then array will be divided int two parts this process will continue until no splitting required. then l and r two pointers taken which points -5 and 3 if both not sorted swap l and r accordingly then merge the array.

For array [-5,3] and [1,2] pointers will be like l for array [5,3], r for array [1,2] within that another l1and r1 pointers will be used. in a new array of size 4 (array [5,3] and [1,2]) . first l1 check with r1 in this case l1 is lesser than r1 so l1 will be added to list [-5, #, #, #] then l1 will increased by 1 
l1 checks with r1 (3 and 1), r1 is greater than l1 so and r1 to list then list becomes [-5,1,#,#] then r1 will be increased by 1 which is 2 again l1 is greater than r1 so add r1 then l1 finally list becomes [-5,1,2,3]. 

### if l gets added increment l id r gets added increment r.

**Time complexity - O(n log n)**
**Space complexity - O(n)**

## Quick sort

Its also an recursive algorithm.
1. Take an pivot (last element in the array).
2. divide the array into 3 parts
3. 1st part is left, elements which are lesser than  or equal to the pivot, middle element is pivot itself, on right elements greater than pivot will be stored. 

**Time complexity - O(n log n) - on good pivot for bad pivot it could become O(n^2)** 
**Space complexity - O(n log n)**


## Counting sort

Initialize a array of zero's in the size of max+1 positions. 
if arr = [5,3,2,1, 3, 3,7,2,2], new array = [0,0,0,0,0,0,0,0] - max is 7 , 7+1, totally eight positions.

### Step 1
Basically iterate through the array with i.
the new array will be used to count the each element.

array = [0, 0, 0, 0, 0, 0, 0, 0]
   pos = 0, 1, 2, 3, 4, 5, 6, 7
 
first element is 5 so increment 5th index by 1, array =[0,0,0,0,0,1,0,0]
next element is 3 so increment 3rd index by 1, array =[0,0,0,1,0,1,0,0] and so on.
finally new array looks like, array = [0,1,3,3,0,1,0,1] for elements 0,1,2,3,4,5,6,7.

Decrement the value of c in new array and replace the element in original array.

now iterate through new array with c we can see 0 times 0 so no need to modify. 
Then 1 times 1 so replace 5 with 1 in the original array, then 3 times 2 add 3 times 2 in the original array 3,2,1 in the original array will be replaced by 2,2,2 now original array looks like 
[1,2,2,2,   3,3,7,2,2].

**Time complexity is O(n + k) where k is the max element in the array 
Space complexity - O(k)**

arr.sort() - O(n log n)
sorted(arr) - O(n)


## Tree - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/Tree)
Binary tree
Each parent node will have  at most 2 children, 
perfect tree - all nodes will have exact 2 children.
leaf node - node without children.

#### "In simple words BFS works in vertical and DFS works in horizontal"
### DFS - depth first search uses stack or recursion
Bottom to top


In DFS there are three types of traversal which are preorder, in order, post order traversal

### Pre order traversal
root note -> left node -> right node
preorder traversal for above binary tree is [1,2,4,5,3,10]

### In order traversal
left node -> root node -> right node
in order traversal for above binary tree is [4,2,5,1,10,3]

### post order traversal
left node -> right node -> root node
post order traversal for above binary tree is [4,5,2,10,3,1]

## BFS - Breath first search uses queue
Top to bottom

### Check whether an element is present or not
## DFS - stack
**Time complexity** - O(n)
**Space complexity** - O(n)

## BFS - queue
**Time complexity** - O(n)
**Space complexity** - O(n)

# Binary search tree
All nodes on left of root node are small than the root node and all node on right of root node are bigger than root node, its easy to solve in order traversal for binary search tree.

### Find a node
**Time complexity** - O(log2​(N))

## Depth of binary tree

left = root.left
right = root.right
start from 6.

## Difference between DFS and BFS

DFS  - uses stack also follows LIFO - last in first out
BFS - uses queue also follows FIFO - first in first out

DFS will be suitable for solutions that are away from source.
BFS will be suitable for solutions that are closer to source. 



### DFS in-order traversal using stack

`root = [1, null, 2, 3]
`out = []
`st = []
`curr = root # which is 1
`while curr or st:
	`while curr:
		`st.append(curr) 
		`curr = curr.left
		`# now the stack becomes [1]
	`#curr = None because null in left if node 1
`	 curr = st.pop() # stack will become empty 
`	 out.append(curr.val) # poped value will be added to out list out = [1]
`     curr = curr.right  # then curr will move to right which is 2

` #now condition is curr is not none so it will enter into 1st while same condition for inner while loop then 2 will add in the stack so st = [2], 

` #curr will move to left 3 which will add to stack so st becomes [2,3], then 3's left is none so pop 3 (st = [2]) and add 3 in out, out becomes [1,3], now curr.right which means 3's right is also none so pop 2 nd add it in out, out = [1,3,2] and st = []/

## Recursion - [here](https://github.com/harish-AK/DSA-in-python/tree/main/DSA%20in%20PYTHON/recursion)

Order of execution - first f(n-1) will complete then it will go for f(n-2). 

**Time complexity is O(2^n)**
**Space complexity is O(n).**

recursion - a function that call itself.


## Recursive backtracking

## Steps
1. Make decisions
2. Recursion
3. Base case
4. Undo decisions.

Function will keep on divide the elements when it hits null (returns a value ) the called function will be popped.

Lets take a problem like print all the subsets in a array = [1,2,3].

This is how recursive backtracking works. 
Uses DFS (left, root, right).

Lets take two lists res = [], sol = []
in res add [] values if the iteration reaches null, first process will be from top to left when its null add empty [] to res list so res becomes res = [ [], ] now left is completed now iterate to root of last node then right while moving right there is an value (3). which will temporarily added to list sol, sol=[3], again looks for values below 3, there is no value its null so add 3 to res list then res becomes res = [[]., 3 ] so backtrack to root of while backtracking pop the element from sol.

- **Include the Current Element**:
    
    - Add the element to `sol`.
    - Recursively process the next element.
- **Exclude the Current Element**:
    
    - Do not add the element to `sol`.
    - Recursively process the next element.
- **Base Case**:
    
    - Add a copy of `sol` to `res` when all elements have been processed.
- **Backtracking**:
    
    - Remove the current element from `sol` after exploring the possibility of including it.


