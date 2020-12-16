# Heaps

## Definition
**Binary max-heap** is a binary tree (each node has zero, one, or two children) where the value of each node is at least the values of its children.
For each edge of the tree, the value of the parent is at least the value of the child.

## Basic Operation    
 
**invariant**: heap property is violated on at most one edge 

* **ShiftUP**   
  for this, we swap the problematic node with its parent until the property is satisfied.   
  running time: O(tree height)    
  
* **ShiftDown**   
  for this, we swap the problematic node with larger child until the heap property is satisfied.    
  running time: O(tree height)    

* **ChangePriority**
  change the priority and let the changed element sift up or down depending on wether its priority decreased or increased.    
  running time: O(tree height)

* **Remove**
  change the priority of the element to ∞, let it shift up and then extract maximum.  
  running time: O(tree height)

## Complete Binary Tree

* **Definition**     
A binary tree is **complete** if all its levels are filled except possibly the last one which is filled left to right.    

* **Lemma**   
A complete binary tree with _n_ nodes has height at most O(log _n_)    

* **Keeping the Tree Complete**   
· to **insert** ana element, insert it as a leaf in the leftmost vacant position in the last level and shift it up.   
· to **extract** the maximum value, replace the root by the last leaf and let it shift down.    

## Pseudocode

* General Setting   
**maxSize** is the maximum number of element in the leap.   
**size** is the size of the heap.   
**H[1...maxSize]** is an array of length maxSize where the heap occupies the first _size_elements.    

```Pseudocode
Parent(i)
return  ⎣i/2⎦
```

```
LeftChild(i)
return 2i
```

```
RightChild(i)
return 2i+1
```

```
ShiftUp(i)
while i > 1 and H[Parent(i)] < H[i]
  swap H[Parent(i)] and H[i]
  i <- Parent(i)
```

```
ShiftDown(i)
maxIndex <- i
l <- LetftChild(i)
if l ≤ size and H[l] > H[maxIndex]
  maxIndex <- l
r <- RightChild(i)
if r ≤ size and H[r] > H[maxIndex]
  maxIndex <- r
if i ≠ maxIndex:
  swap H[i] and H[maxIndex]
  ShiftDown(maxIndex)
```

```
Insert(p)
if size = maxSize;
  return ERROR
size <- size + 1
H[size] <- p
ShiftUp(size)
```

```C++
ExtractMax()
result <- H[1]
H[1] <- size-1
ShiftDown(1)
return result
```

```
Remove(i)
H[i] <- ∞
ShiftUp(i)
ExtractMax()
```

## Heap Sort

* Sort Using Priority Queue   
· The resulting alagorithm is comparison-based and has running time O(nlong n) (hence, asymptotically optimal!)   
· Natural generalization of selection sort: instead of simply scanning the rest of the array to find the maximum value, use a smart data structure.   
· Not in-place: use additional space to store the priority queue.  

```
HeapSort(A[1...n])
create an empty priority queque
for i from 1 to n:
  Insert(A[i])
for i from n downto 1:
  A[i] <- ExtractMax()
```

* Turn Array into a Heap    
· We repair the heap property going from bottom to top.   
· Initially, the heap property is satisfied in all leaves (subtrees of depth 0).    
· We then start repairing the heap property in all subtrees of depth 1.   
· When we reach the root, the heap property is satisfied in the whole tree.
· Running time: O(nlog n)

```
BuildHeap(A[1...n])
size <- n
for i from ⎣n/2⎦ downto 1:
  ShiftDown(i)
```

* In-place Heap Sort

```
HeapSort(A[1...n])
BuildHeap(A)
repaeat (n-1) times:
  swap A[1] and A[size]
  size <- size - 1
  ShiftDown(1)

 






