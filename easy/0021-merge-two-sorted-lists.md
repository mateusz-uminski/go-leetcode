# Merge Two Sorted Lists

[21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)


# Solution

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func mergeTwoLists(list1 *ListNode, list2 *ListNode) *ListNode {
    if list1 == nil {
        return list2
    }

    if list2 == nil {
        return list1
    }


    pointer1 := list1
    pointer2 := list2
    newList := &ListNode{Val: -1, Next: nil}
    head := newList

    for pointer1 != nil && pointer2 != nil {
        if pointer1.Val <= pointer2.Val {
          //  fmt.Println(pointer1.Val, pointer2.Val)
            newList.Next = pointer1
            pointer1 = pointer1.Next
            newList = newList.Next
        } else {
            newList.Next = pointer2
            pointer2 = pointer2.Next
            newList = newList.Next
        }
    }

    if pointer1 != nil {
        newList.Next = pointer1
    }

    if pointer2 != nil {
        newList.Next = pointer2
    }

    return head.Next
}
```
