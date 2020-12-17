# Disjoint Sets

## Definition    
A disjoint-set data structure supports the following operations:    
· MakeSet(x) &emsp;_creates a singleton set {x}_    
· Find(x) &emsp;_return ID of the set containing x: if x and y lie in the same set, then Find(X) = Find(y), otherwise, Find(x) ≠ Find(y)_    
· Union(x,y) &emsp;merges two sets containing x and y   

```
Preprocess(maze)
for each cell c in maze:
  MakeSet(c)
for each cell c in maze:
  for each neighbor n of c:
    Union(c,n)
```  
    
```
IsReachable(A,B)
return Find(A) = Find(B)
```


## Naive Implementations
```
MakeSet(i)
smallest[i] <- i
```
Running time: **O(1)**
```
Find(i)
return samllest[i]
```
Running time: **O(1)**
```
Union(i,j)
i_id <- Find(i)
j_id <- Find(j)
if i_id = j_id:
  return
m <- min(i_id, j_id)
for k from 1 to n:
  if smallest[k] in {i_id,j_id}:
    smallest[k] <- m
```
Running time: **O(n)**

## Efficient Implementations

### Trees for Disjoint Sets
> Union by rank heuristic: hang a shorter tree under the root of a taller one

* Represent each set as a rootedm tree
* ID of a set is the root of the tree
* Use array Parent[1...n]: parent[i] is the parent of i, or i if it is the root
  
  ```
  MakeSet(i)
  parent[i] <- i
  rank[i] <- 0
  ```
  Running time: **O(1)**
  ```
  Find(i)
  while i ≠ parent[i]:
    i <- parent[i]
  return i
  ```
  Running time: **O(tree height)**
  ```
  Union(i,j)
  i_id <- Find(i)
  j_id <- Find(j)
  if i_id = j_id:
    return
  if rank[i_id] > rank[j_id]:
    parent[j_id] <- i_id
  else:
    parent[i_id] <- j_id
    if rank[i_id] = rank[j_id]:
    rank[j_id] <- rank[j_id]+1
  ```
**important property**: for any node i, rank[i] is equal to the height of the tree rooted at i    

**Lemma**   
The height od any tree inthe forest is at most log<sub>2</sub> n.   

**Lemma**   
Any tree of height k in the forest has at least 2<sup>k</sup> nodes.    

### Path Compression
> when finding the root of a tree for a particular node, reattach each node from the traversed path to the root.

```
Find(i)
if i ≠ parent[i]:
  parent[i] <- Find(parent[i])
return parent[i]
```
**Definiton**   
The iterated logarithm of n, log*n, is the number of times the logarithm function needs to be applied to n before the result is less or equal than 1.

**Lemma**   
Assume that initially the data struction is empty. We make a sequence od m operations including n calls to MakeSet. Then the total running time is O(mlog* n).

**In other words**    
The amortized time of a single operation is O(log* n).    
__For practical values of n, log* n ≤ 5.__




