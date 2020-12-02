# Arrays
## Definition
  > Array: Contiguous area of memory consisting of equal-size elements indexed by contiguous integers.

* Constant-time access to any element
<br> `array_addr+elem_size*(i-first_index)`

* Multi-Dimensional Arrays
<br>`array_addr+ elem_size*((i-1)*6+(j-1))`
<br> Row-major column index changes most rapidly
<br> Column-major row index changes most rapidly

## Time for Common Operations
| |Add|Remove|
|:-:|:-:|:-:|
|Beginning|O(n)|O(n)|
|End|O(1)|O(1)|
|Middle|O(n)|O(n)|
* Constant time to add/remove at the end
* Linear time to add/remove at ana arbitrary location

# Lists
> Head is a pointer that point to a node.
## Singly-Linked Lists
* Node contains:
  * key
  * next pointer<br/>

|List API|Singly-Linked List|no tail|with tail|
|:-|:-|:-:|:-:|
|PushFront(Key)|add to front|O(1)||
|Key TopFront()|returen front item|O(1)||
|PopFront()|remove front item|O(1)||
|PushBack(Key)|add to back|O(n)|O(1)|
|Key TopBack()|return back item|O(n)|O(1)|
|PopBack()|remove back item|O(n)||
|Boolean Find(Key)|is key in list?|O(n)||
|Erase(Key)|remove key from list|O(n)||
|Boolean Empty|empty list?|O(1)||
|AddBefore(Node,Key)|adds key before node|O(n)||
|AddAfter(Node,Key)|adds key after node|O(1)||

## Doubly-Linked Lists
* Node contains:
  * key
  * next pointer
  * prev pointer<br/>
  
  PopBack() ~~O(n)~~ O(1)<br/>
  AddBefore(Node,Key) ~~O(n)~~ O(1)<br/>
  
+ Constant time to insert at or remove from the front.
+ With tail and doubly-linked, constant time to insert at or remove from the back.
+ O(n) time to find arbitrary element.
+ List elements need not be contiguous.
+ With doubly-linked list, constant time to insertt between nodes or remove a node.
