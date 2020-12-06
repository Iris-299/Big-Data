# Trees
> A Tree is 
> * empty, or 
> * a node with: 
>   * a key, and
>   * a list of child trees

* Root: top node in the tree
* Child: a line down directly from a parent
* Ancestor: parent, parent od parent, etc.
* Descendant: child, child of child, tec.
* Sibling: sharing the same parent
* Leaf: node with no children
* Interior node (non-leaf)
* Level: 1+num edges between root and node
* Height: maximum depth of subtree node and farthest leaf
* Forest: collection of trees

## Node contains:
* key
* children: list of childrennodes
* (optional) parent

### For binary tree: node contains:
* key
* left
* right
* (optioanl) parent

## Tree Traversal
* Depth-first: We completely traverse one sub-tree before exploring a sibling sub-tree.
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
* Breadth-first: We transverse all nodes at one level before progressing to the next level
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














