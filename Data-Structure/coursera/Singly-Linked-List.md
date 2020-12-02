* Node contains:
  * key
  * next pointer<br/>
> Head is a pointer that point to a node.

|List API||no tail|with tail|
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
