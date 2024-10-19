# Remove Linked List Elements

[203. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/description/)


# Solution

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func removeElements(head *ListNode, val int) *ListNode {
    if head == nil {
        return nil
    }


    for head != nil && head.Val == val {
        head = head.Next
    }

    current := head

    for current != nil && current.Next != nil {
        if current.Next.Val == val {
            current.Next = current.Next.Next
        } else {
            current = current.Next
        }
    }
    return head
}
```
