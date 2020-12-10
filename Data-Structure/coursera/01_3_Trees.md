# Trees

## Definition 
  A Tree is:  
  · empty, or   
  · a node with:  
    &emsp;&emsp;a key, and  
    &emsp;&emsp;a list of child trees

## Terminology  
* Root: _top node in the tree_
* Child: _a line down directly from a parent_
* Ancestor: _parent, parent od parent, etc._
* Descendant: _child, child of child, tec._
* Sibling: _sharing the same parent_
* Leaf: _node with no children_
* Interior: _node (non-leaf)_
* Level: _1+num edges between root and node_
* Height: _maximum depth of subtree node and farthest leaf_
* Forest: _collection of trees_

Node contains:  
· key   
· children: list of childrennodes   
· (optional) parent   

For binary tree: node contains:   
· key   
· left  
· right   
· (optioanl) parent   

## Tree Traversal

* **Depth-first**: We completely traverse one sub-tree before exploring a sibling sub-tree.
```C++
InOrderTranversal(tree) only defined for a binary tree
if tree = nil:
  return
InOrderTraversal(tree.left)
Print(tree.key)
InOrderTraversal(tree.right)
```
```C++
PreOrderTraversal(tree)
if tree = nil: 
  return
Print(tree.key)
PreOrderTraversal(tree.left)
PreOrderTraversal(tree.right)
```
```C++
PostOrderTraversal(tree)
if tree = nil: 
  return
PostOrderTraversal(tree.left)
PostOrderTraversal(tree.right)
Print(tree.key)
```

* **Breadth-first**: We transverse all nodes at one level before progressing to the next level
```C++
LevelTraversal(tree)
if tree = nil:  return 
Queue q
q.Enqueue(tree)
while not q.Empty():
  node <- q.Dequeue()
  print(node)
  if node.left != nil:
    q.Enqueue(node.left)
  if node.right != nil:
    q.Enqueue(node.right)
    
```














