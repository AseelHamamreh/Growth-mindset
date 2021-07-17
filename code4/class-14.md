# Read: Trees

Some important concepts in trees: 

- Node - A Tree node is a component which may contain it’s own values, and references to other nodes
- Root - The root is the node at the beginning of the tree
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree
- Right - A reference to the other child node, in a binary tree
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not have any children
- Height - The height of a tree is the number of edges from the root to the furthest leaf

***

Types of Traversals:
- Depth First
- Breadth First

#### Depth first

Depth first traversal is where we prioritize going through the depth (height) of the tree first.
methods for depth first traversal:

Pre-order: ```root >> left >> right```

```
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
```

In-order: ```left >> root >> right```

```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

Post-order: ```left >> right >> root```

```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```


#### Breadth First

Breadth first traversal iterates through the tree by going through each level of the tree node-by-node.
breadth first traversal uses a **queue** (instead of the call stack via recursion) to traverse the width/breadth of the tree.

Pseudocode:

```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```

***


## Binary Tree Vs K-ary Trees

| Binary Tree | K-ary Trees |
| ----------- | ----------- |
| restrict the number of children to two (left and right) | can have any number of children per node |
| no specific sorting order for a binary tree | we use K to refer to the maximum number of children that each Node is able to have |