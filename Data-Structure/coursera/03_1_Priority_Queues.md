# Priority Queues
> A priority queue is an generlization of a queue where each element is assigned a priority and elements come out in order by priority.  

## Definition
* A **queue** is an abstract data type supporting the folloing main operations:   
  · PushBack(e) &emsp; _adds an element **e** to the back of the queue_   
  · PopFront() &emsp; _extracts an element from the front of the queue_  

* **Priority queue** is an abstract data type supporting the following main operations:   
  · Insert(p) &emsp; _adds a new element with priority **p**_    
  · ExtractMax() &emsp; _extracts an element with maximum priority_   

## Additonal Operations
* **Remove(it)** &emsp; _removes an element pointed by an iterator **it**_
* **GetMax()** &emsp; _returns an element with maximum priority (without changing the set of elements)_
* **ChangePriority(it,p)** &emsp; _change the priority of an element pointed by **it** to **p**_

## Use  
* **Typical Use Case** —— Scheduling jobs   
  Want to process jobs one by one in order of decreasing priority. While the current job is processed, new jobs may arrive.   
  To add a job to the set of scheduled jobs, call Insert(job).    
  To process a job with the highest priority, get it by calling ExtractMax().   
  
* **Algorithms that Use Priority Queues**   
  · **Dijsktra's alorithm**: _finding a shortest parth in a graph_    
  · **Prim's alorithm**: _constructing a minimum spanning tree of a graph_    
  · **Huffman's alorithm**: _ constructing an optimum prefix_free encoding of a string_   
  · **Heap sort**: _sorting a given sequence_   
  
## Naive Implementations
| |Insert|ExtractMax|
|:-|:-:|:-:
|Unsorted array/list|O(1)|O(n)|
|Sorted array/list|O(n)|O(1)|
