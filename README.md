# Merge Two Sorted Linked Lists

## Problem Statement

Given two sorted linked lists, merge them into a single sorted linked list without changing the order of elements.

### Input

**List 1:**
```text
10 → 30 → 50 → 70
```

**List 2:**
```text
20 → 25 → 40 → 80
```

### Expected Output

```text
10 → 20 → 25 → 30 → 40 → 50 → 70 → 80
```

## Algorithm

1. Start with the first node of both linked lists.
2. Compare the data of the current nodes of both lists.
3. Select the node with the smaller value.
4. Add the selected node to the merged list.
5. Move the pointer of the selected list to its next node.
6. Repeat the comparison until one list becomes empty.
7. Add all remaining nodes of the other list to the merged list.
8. Return the merged sorted list.

## Example

```text
L1:     10 → 30 → 50 → 70
         ↓
L2:     20 → 25 → 40 → 80

Compare:
10 < 20  → 10
30 > 20  → 20
30 > 25  → 25
30 < 40  → 30
50 > 40  → 40
50 < 80  → 50
70 < 80  → 70
L1 finished → 80
```

### Final Result

```text
10 → 20 → 25 → 30 → 40 → 50 → 70 → 80
```

## Pseudocode

```text
MergeSortedLists(L1, L2)

P = L1
Q = L2
Create empty MERGED list

while P != NULL and Q != NULL:
    if P.data < Q.data:
        add P to MERGED
        P = P.next
    else:
        add Q to MERGED
        Q = Q.next

while P != NULL:
    add P to MERGED
    P = P.next

while Q != NULL:
    add Q to MERGED
    Q = Q.next

return MERGED
```

## Complexity

- **Time Complexity:** `O(n + m)`
- **Space Complexity:** `O(1)` when existing nodes are reused.

## Key Concept

The main idea is to **compare the current nodes of both sorted lists and always select the smaller value**. Since both lists are already sorted, there is no need to sort them again.
