# Invert Binary Tree

[226. Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/description/)


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
func invertTree(root *TreeNode) *TreeNode {
    if root == nil {
        return nil
    }

    stack := []*TreeNode{root}

    for len(stack) > 0 {
        current := stack[len(stack)-1]
        stack = stack[:len(stack)-1]

        if current.Right != nil {
            stack = append(stack, current.Right)
        }

        if current.Left != nil {
            stack = append(stack, current.Left)
        }

        current.Left, current.Right = current.Right, current.Left
    }

    return root
}
```
