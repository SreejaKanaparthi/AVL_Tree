# AVL_Tree
# Binary Search Tree (BST) and Its Time Complexity for Important Operations

A Binary Search Tree (BST) is a node-based binary tree data structure which has the following properties:
- The left subtree of a node contains only nodes with keys less than the node's key.
- The right subtree of a node contains only nodes with keys greater than the node's key.
- Both the left and right subtrees must also be binary search trees.

### Time Complexity
- **Search**: Average case O(log n), Worst case O(n)
- **Insertion**: Average case O(log n), Worst case O(n)
- **Deletion**: Average case O(log n), Worst case O(n)

# Need for Self-Balancing Trees

Self-balancing trees, such as AVL trees and Red-Black trees, are necessary because in a basic BST, the tree can become unbalanced and degenerate into a linked list, leading to poor performance with time complexity O(n) for operations like search, insert, and delete. Self-balancing trees ensure the height of the tree remains logarithmic with respect to the number of nodes, maintaining efficient operation time.

# AVL Trees: Introduction and Detection of Imbalance

An AVL (Adelson-Velsky and Landis) tree is a self-balancing binary search tree. In an AVL tree, the difference in heights between the left and right subtrees (called the balance factor) of any node is at most one. An imbalance is detected if the balance factor of any node is greater than 1 or less than -1.

# Sub-cases of Imbalance in AVL Trees

There are four types of imbalances:
- **LL (Left-Left)**: The left subtree of the left child is unbalanced.
- **LR (Left-Right)**: The right subtree of the left child is unbalanced.
- **RL (Right-Left)**: The left subtree of the right child is unbalanced.
- **RR (Right-Right)**: The right subtree of the right child is unbalanced.

# How to Balance Each of These Cases

### LL Case
Perform a right rotation around the unbalanced node.

### LR Case
Perform a left rotation on the left child followed by a right rotation on the unbalanced node.

### RL Case
Perform a right rotation on the right child followed by a left rotation on the unbalanced node.

### RR Case
Perform a left rotation around the unbalanced node.

# AVL Trees vs. Red-Black Trees: When to Use Which One?

### AVL Trees
They provide faster lookups because they are more strictly balanced. They are suitable when read-heavy operations are common.

### Red-Black Trees
They provide faster insertion and deletion operations because they are less strictly balanced. They are suitable when write-heavy operations are common.

### UML Diagram 

- +---------------------+
- |      AVLTree        |
- +---------------------+
- | - root: Node        |
- +---------------------+
- | + insert(value): void|
- | + delete(value): void|
- | + balance(node): Node|
- +---------------------+
           |</br>
           |</br>
          has</br>
           |</br>
           v</br>
- +---------------------+
- |        Node         |
- +---------------------+
- |  value: int        |
- |  left: Node        |
- |  right: Node       |
- |  height: int       |
- +---------------------+
- | + getBalance(): int |
- | + updateHeight(): void|
- +---------------------+
