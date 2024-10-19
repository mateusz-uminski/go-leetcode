# Palindrome Linked List

[234. Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/description/)


# Solution

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func isPalindrome(head *ListNode) bool {
    slow := head
    fast := head
    for fast != nil && fast.Next != nil {
        slow = slow.Next
        fast = fast.Next.Next
    }

    reversed := reverseLinkedList(slow)
    p1 := head
    p2 := reversed
    for p1 != nil && p2 != nil {
        if p1.Val != p2.Val {
            return false
        }
        p1 = p1.Next
        p2 = p2.Next
    }
    return true
}

func reverseLinkedList(head *ListNode) *ListNode {
    var previous *ListNode = nil
    for head != nil {
        next := head.Next
        head.Next = previous
        previous = head
        head = next
    }
    return previous
}
```
