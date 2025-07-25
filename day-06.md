# Day 06: Linked List

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list

Given the head of a singly linked list, reverse the list, and return the reversed list.

```ts
// Definition for singly-linked list.
class ListNode {
  val: number;
  next: ListNode | null;
  constructor(val?: number, next?: ListNode | null) {
    this.val = val === undefined ? 0 : val;
    this.next = next === undefined ? null : next;
  }
}

function reverseList(head: ListNode | null): ListNode | null {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

**Approach**: [Approach Name]  
**Pattern**: [Pattern Description]

**Step-by-step explanation**:
[Detailed explanation to be added]

```ts
function reverseList(head: ListNode | null): ListNode | null {
  let prev: ListNode | null = null;
  let curr: ListNode | null = head;

  while (curr !== null) {
    const nextTemp = curr.next; // Save next node
    curr.next = prev; // Reverse pointer
    prev = curr; // Move prev forward
    curr = nextTemp; // Move curr forward
  }

  return prev;
}
```

</details>

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists

You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

```ts
function mergeTwoLists(
  list1: ListNode | null,
  list2: ListNode | null
): ListNode | null {
  // TODO: Implement solution
}
```

<details> <summary>Click to reveal solution</summary>

**Approach**: [Approach Name]  
**Pattern**: [Pattern Description]

**Step-by-step explanation**:
[Detailed explanation to be added]

```ts
// Definition for singly-linked list node
class ListNode {
  val: number; // The value of the node
  next: ListNode | null; // Pointer to the next node

  constructor(val?: number, next?: ListNode | null) {
    this.val = val ?? 0; // Default value is 0 if undefined
    this.next = next ?? null; // Default next is null if undefined
  }
}

/**
 * Merges two sorted linked lists into a single sorted linked list.
 * The original nodes are reused, not copied.
 *
 * @param list1 - Head of the first sorted linked list
 * @param list2 - Head of the second sorted linked list
 * @returns Head of the merged sorted linked list
 */
function mergeTwoLists(
  list1: ListNode | null,
  list2: ListNode | null
): ListNode | null {
  // Create a dummy node to act as the start of the merged list.
  // This simplifies the logic by handling the head the same as any other node.
  const dummy = new ListNode(-1);

  // 'current' is a pointer used to build the new list by attaching nodes to it
  let current = dummy;

  // Traverse both lists until one is exhausted
  while (list1 !== null && list2 !== null) {
    if (list1.val < list2.val) {
      // list1 has the smaller value, so we attach it to the current node
      current.next = list1;
      list1 = list1.next; // Move list1 forward
    } else {
      // list2 has the smaller or equal value, so we attach it instead
      current.next = list2;
      list2 = list2.next; // Move list2 forward
    }

    // Move current forward to the node we just added
    current = current.next;
  }

  // One of the lists is now null. Attach the remaining list (if any) to current.next
  // Since the remaining elements are already sorted, we can just link directly
  current.next = list1 !== null ? list1 : list2;

  // The merged list starts at dummy.next (skip the dummy placeholder)
  return dummy.next;
}
```

</details>
