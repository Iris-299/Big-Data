# Definition
  > Array: Contiguous area of memory consisting of equal-size elements indexed by contiguous integers.

* Constant-time access to any element
<br> `array_addr+elem_size*(i-first_index)`

* Multi-Dimensional Arrays
<br>`array_addr+ elem_size*((i-1)*6+(j-1))`
<br> Row-major column index changes most rapidly
<br> Column-major row index changes most rapidly

# Time for Common Operations
| |Add|Remove|
|:-:|:-:|:-:|
|Beginning|O(n)|O(n)|
|End|O(1)|O(1)|
|Middle|O(n)|O(n)|
* Constant time to add/remove at the end
* Linear time to add/remove at ana arbitrary location
