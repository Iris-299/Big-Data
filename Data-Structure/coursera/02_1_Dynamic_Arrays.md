## Dynamic Arrays
> Dynamic Array Resizing: store a pointer to a dynamically allocated array, and replace it with a newly-allocated array as needed.

* **Definiton**    
  Abstract data type with the following operations (at a minimum):  
  · Get(i):&emsp;_returns element at location_ **i**&emsp;&emsp;O(1)    
  ```C++
  Get(i)
  if i < 0 or i >= size:
    ERROR: index out of range
  return arr[i]
  ```
  · Set(i,val):&emsp;_Set element i to_ **val**&emsp;&emsp;O(1)   
  ```C++
  Set(i,val)
  if i < 0 or i >= size:
    ERROR: index out of range
  arr[i] = val
  ```
  · PushBack(val):&emsp;_Adds_ **val** _to the end_&emsp;&emsp;O(n)    
  ```C++
  PushBack(val)
  if size = capacity:
    allocate new_arr[2*capacity]
    for i from 0 to size-1:
      new_arr[i] <- arr[i]
    free arr
    arr <- new_arr; capacity <- 2*capacity
  arr[size] <- val
  size <- size+1
  ```
  · Remove(i):&emsp;_Removes element at location_ **i**&emsp;&emsp;O(n)   
  ```C++
  Remove(i)
  if i < 0 or i >= size:
    ERROR: index out of range
  for j from i to size-2
    arr[j] <- arr[j+1]
  size <- size-1
  ```

* **Implementation**    
  Store:    
  · arr:&emsp;_dynamically-allocated array_  
  · capacity:&emsp;_size of the dynamically-allocated array_   
  · size:&emsp;_number of elements currently in the array_   
  
