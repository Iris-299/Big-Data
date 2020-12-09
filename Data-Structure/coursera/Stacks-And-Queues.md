# Stack

## Definition
  Abstract data typr with folloing operations:   
  · Push(Key): add key to clooction  
  · Key Top(): returns most recently-addes key   
  · Key Pop(): removes and returns most recently-added key   
  · Boolean Empty(): are there any elements?   

## E.g. 
```C++
IsBalanced(str)
Stack stack
for char in str:
  if char in ['(','[']:
    stack.Push(char)
  else:
    if stack.Empty(): return False
    top <- stack.Pop()
    if (top = '[' and char != ']') or (top = '(' and char != ')')
      return False
return stack.Empty()
```

## Stack Implementation   
* **with Array**  
  · alocate an array of some maximum stack size  
  · all O(1) operations  
 
* **with Linked List**  
  · Push means PushFront   
  · get top element means get head element   
  · top means TopFront   
  · pop means TopFront followed by PopFront    
  · all O(1)operations   
  · no priori limit    
 
# Queues

## Definition  
  Abstract data typr with folloing operations:  
  · Enqueue(Key): adds key to collection  
  · Key Dequeue(): removes and returns least recently-added key   
  · Boolean Empty(): are there any elements?  
 
## Queue Implementation   
* **with Linked List**    
  Enqueue: use List.PushBack   
  Dequeue: use List.TopFront and List.PopFront   
  
* **with Array**    
  maximum size
 
