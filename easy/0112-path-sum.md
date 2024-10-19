# Path Sum

[112. Path Sum](https://leetcode.com/problems/path-sum/description/)


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
func hasPathSum(root *TreeNode, targetSum int) bool {
    if root == nil {
        return false
    }

    rootContainer := Container{PathSum: 0, Node: root}

    stack := []Container{rootContainer}

    for len(stack) > 0 {
        current := stack[len(stack)-1]
        stack = stack[:len(stack)-1]

        current.PathSum += current.Node.Val

        if current.PathSum == targetSum && isLeaf(current) {
            return true
        }

        if current.Node.Right != nil {
            stack = append(stack, Container{PathSum: current.PathSum, Node: current.Node.Right})
        }

        if current.Node.Left != nil {
            stack = append(stack, Container{PathSum: current.PathSum, Node: current.Node.Left})
        }
    }

    return false
}

func isLeaf(c Container) bool {
    if c.Node.Left == nil && c.Node.Right == nil {
        return true
    }
    return false
}

type Container struct {
    PathSum int
    Node *TreeNode
}
```
