## Practical 7: Dynamic Text Editor Using Singly Linked List

### 1. Practical Title

Dynamic Text Editor Using Singly Linked List.

### 2. Problem Statement

Create a simple text editor that stores text items dynamically in a singly linked list. Support creating a list, inserting and deleting an item at a specified position, displaying the list, and reversing the list.

### 3. Objective

* Understand singly linked list nodes and pointers.

* Practise dynamic memory allocation using `malloc` and release nodes using `free`.

* Insert and delete nodes at specified positions.

* Reverse links in a singly linked list.

### 4. Algorithm / Approach

1. Initialise $\text{head} = \text{NULL}$.

2. **Create:** allocate a new node, read its data, set its `next` to `NULL`, and append it to the end of the list. Repeat while requested.

3. **Insert:** allocate and populate a node. If the location is 1, link it before the current `head`; otherwise traverse to the preceding node and update links.

4. **Display:** traverse from `head` to `NULL`, printing each node.

5. **Delete:** locate the requested node, unlink it from the list, and free its memory.

6. **Reverse:** initialise $\text{previous} = \text{NULL}, \text{current} = \text{head}$; repeatedly save the next node, reverse the current link, and advance the pointers. Set $\text{head} = \text{previous}$.

7. Repeat until Exit is selected.

### 5. Data Structure / Concept Used

* Singly linked list

* Dynamic memory allocation (`malloc` / `free`)

* Pointers and link manipulation

* Iterative list reversal

### 6. Test Cases

| Test Case | Operations | Expected Result | 
| ----- | ----- | ----- | 
| **Empty list** | Display before creating nodes | Empty list should be reported (the supplied display code prints `NULL`) | 
| **Create** | Add red, green, blue | `red->green->blue->NULL` | 
| **Insert at front** | Insert yellow at position 1 | `yellow->red->green->blue->NULL` | 
| **Delete at position** | Delete position 2 | The second node is removed | 
| **Reverse** | Reverse `red->green->blue` | `blue->green->red->NULL` | 

### 7. Sample Input and Output

Example list before reversal:

```
red->green->blue->NULL

```

After choosing Reverse:

```
blue->green->red->NULL

```

### 8. Time Complexity

* **Create/display:** $\mathcal{O}(n)$.

* **Insert/delete at a position:** $\mathcal{O}(n)$ worst case due to traversal.

* **Reverse:** $\mathcal{O}(n)$.

### 9. Space Complexity

$\mathcal{O}(n)$ for the $n$ dynamically allocated nodes. Reversal uses $\mathcal{O}(1)$ auxiliary pointer space.

### 10. Conclusion

A singly linked list supports dynamic storage and insertion/deletion without shifting array elements. Reversing the list requires updating each node's `next` pointer.
