# Same Tree

[100. Same Tree](https://leetcode.com/problems/same-tree/description/)


# Solution

```go
/**
 * Definition for a binary tree node.
 * type TreeNode struct {
 *     Val int
 *     Left *TreeNode
 *     Right *TreeNode
 * }
 */
func isSameTree(p *TreeNode, q *TreeNode) bool {
    stack1 := []*TreeNode{p}
    stack2 := []*TreeNode{q}

    for len(stack1) > 0 && len(stack2) > 0 {
        current1 := stack1[len(stack1) - 1]
        stack1 = stack1[:len(stack1) - 1]

        current2 := stack2[len(stack2) - 1]
        stack2 = stack2[:len(stack2)-1]

        if current1 == nil && current2 == nil {
            continue
        }

        if current1 == nil && current2 != nil {
            return false
        }

        if current1 != nil && current2 == nil {
            return false
        }

        if current1.Val != current2.Val {
            return false
        }

        stack1 = append(stack1, current1.Right, current1.Left)
        stack2 = append(stack2, current2.Right, current2.Left)
    }

    return len(stack1) == len(stack2)
}
```
