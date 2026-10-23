## Practical 3: Searching Contact Names Using Sequential Search and Binary Search

### 1. Practical Title

Searching Contact Names Using Sequential Search and Binary Search.

### 2. Problem Statement

Create a contact manager that stores contact names, phone numbers, and addresses. Search for a requested name using sequential search and binary search, and compare the number of comparisons.

### 3. Objective

* Implement sequential (linear) search and binary search.

* Understand that binary search requires sorted data.

* Compare the search methods and their efficiency.

* Apply searching algorithms to contact records.

### 4. Algorithm / Approach

1. Read the number of contacts and input each contact's name, phone number, and address.

2. Display the contact records.

3. **Sequential search:** compare the requested name with each contact name until it is found or the list ends; count comparisons.

4. Sort the contact names alphabetically using bubble sort.

5. **Binary search:** initialise $\text{low} = 0$ and $\text{high} = n - 1$; compare the key with the middle name and discard the half that cannot contain the key.

6. Stop when the name is found or $\text{low} > \text{high}$; display the result and comparison count.

*Implementation note: The supplied code sorts the name fields only; it does not move the corresponding phone and address fields during sorting. Binary-search output therefore reports the name's sorted position, while the original record associations are not preserved in the sorted array.*

### 5. Data Structure / Concept Used

* Array of contact structures

* Sequential search

* Binary search

* Bubble sort

* String comparison (`strcasecmp`)

### 6. Test Cases

| Test Case | Search Key | Expected Result | 
| ----- | ----- | ----- | 
| **First contact** | A name at the beginning of the input | Sequential search finds it | 
| **Existing contact** | A name in the list | Both methods report found | 
| **Missing contact** | Zoya when not entered | Both methods report not found | 
| **Single contact** | One contact in the list | Search checks the sole entry | 

### 7. Sample Input and Output

Example contacts:

```
3
Asha 9000000001 Pune
Meera 9000000002 Mumbai
Ravi 9000000003 Nashik
Search name: Meera

```

Illustrative output:

```
CONTACT FOUND
Name: Meera
Contact: 9000000002
Address: Mumbai
Linear comparisons: 2

Contact found at location 2
Number of binary comparisons: 1

```

Comparison counts depend on the entered order and the exact sorted list.

### 8. Time Complexity

* **Sequential search:** $\mathcal{O}(n)$ worst case.

* **Bubble sort before binary search:** $\mathcal{O}(n^2)$ worst case.

* **Binary search after sorting:** $\mathcal{O}(\log n)$ worst case.

* **Overall program:** $\mathcal{O}(n^2)$ worst case because of bubble sorting.

### 9. Space Complexity

$\mathcal{O}(n)$ for the contact array. The search algorithms themselves use $\mathcal{O}(1)$ auxiliary space.

### 10. Conclusion

Sequential search works with unsorted data, whereas binary search needs sorted names and reduces lookup comparisons. Sorting dominates the overall running time in this implementation.
