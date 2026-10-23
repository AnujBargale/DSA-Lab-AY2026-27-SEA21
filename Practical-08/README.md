## Practical 8: Binary Search Tree Operations for Online Directory System

### 1. Practical Title

Binary Search Tree Operations for Online Directory System.

### 2. Problem Statement

Implement a Binary Search Tree (BST) to store directory contact names and phone numbers. Support insertion, searching by name, and recursive inorder, preorder, and postorder traversals.

### 3. Objective

* Understand BST ordering properties.

* Insert and search directory entries.

* Implement recursive tree traversals.

* Observe how tree shape affects search efficiency.

### 4. Algorithm / Approach

1. Initialise the root pointer to `NULL`.

2. **Insert:** allocate a node for the name and phone number. If the tree is empty, make it the root; otherwise compare names case-insensitively and move left for smaller names or right for larger names until an empty child is found.

3. **Inorder traversal:** traverse left subtree, print the node, then traverse right subtree.

4. **Preorder traversal:** print the node, traverse left subtree, then traverse right subtree.

5. **Postorder traversal:** traverse left subtree, traverse right subtree, then print the node.

6. **Search:** compare the key with the current node; report found if equal, otherwise continue into the appropriate subtree. Report not found at a null pointer.

### 5. Data Structure / Concept Used

* Binary Search Tree

* Dynamically allocated nodes with left/right pointers

* Recursion

* Inorder, preorder, and postorder traversals

* Case-insensitive string comparison

### 6. Test Cases

| Test Case | Inserted Names | Operation | Expected Result | 
| ----- | ----- | ----- | ----- | 
| **Empty tree** | None | Traverse/search | Program reports that the tree is not created | 
| **Basic tree** | Mira, Asha, Ravi | Inorder | `Asha Mira Ravi` | 
| **Search success** | Mira, Asha, Ravi | Search `Ravi` | Contact found with phone number | 
| **Search failure** | Same tree | Search `Zoya` | Contact not found | 
| **One node** | Mira | All traversals | Each traversal prints `Mira` | 

### 7. Sample Input and Output

Insert contacts in this order: `Mira`, `Asha`, `Ravi`.

Inorder output:

```
Asha Mira Ravi

```

Preorder output:

```
Mira Asha Ravi

```

Postorder output:

```
Asha Ravi Mira

```

Search:

```
Enter contact name to search: Ravi
Contact found
Name: Ravi
Phone: 9000000003

```

### 8. Time Complexity

Let $h$ be the height of the tree:

* **Insert/search:** $\mathcal{O}(h)$; average $\mathcal{O}(\log n)$ for a reasonably balanced tree, worst-case $\mathcal{O}(n)$.

* **Each full traversal:** $\mathcal{O}(n)$.

### 9. Space Complexity

$\mathcal{O}(n)$ for the nodes. Recursive operations use $\mathcal{O}(h)$ call-stack space.

### 10. Conclusion

A BST organises names according to a comparison rule, enabling searching and sorted output through inorder traversal. Performance depends on the tree's height.
