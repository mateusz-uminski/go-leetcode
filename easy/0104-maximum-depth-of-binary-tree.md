# Maximum Depth of Binary Tree

[104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)


# Solution #1

```go
/**
 * Definition for a binary tree node.
 * type TreeNode struct {
 *     Val int
 *     Left *TreeNode
 *     Right *TreeNode
 * }
 */
func maxDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }
    left := maxDepth(root.Left)
    right := maxDepth(root.Right)
    if left > right {
        return left + 1
    }
    return right + 1
}
```


# Solution #2

```go
/**
 * Definition for a binary tree node.
 * type TreeNode struct {
 *     Val int
 *     Left *TreeNode
 *     Right *TreeNode
 * }
 */
func maxDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }

    containerRoot := Container{Depth: 0, Node: root}
    depths := []Container{}

    stack := []Container{containerRoot}

    for len(stack) > 0 {
        current := stack[len(stack)-1]
        stack = stack[:len(stack)-1]

        current.Depth += 1

        if current.Node.Right == nil && current.Node.Left == nil {
            depths = append(depths, current)
        }

        if current.Node.Right != nil {
            stack = append(stack, Container{Depth: current.Depth, Node: current.Node.Right})
        }

        if current.Node.Left != nil {
            stack = append(stack, Container{Depth: current.Depth, Node: current.Node.Left})
        }
    }

    max := 0
    for _, v := range depths {
        if v.Depth > max {
            max = v.Depth
        }
    }

    return max
}

type Container struct {
    Depth int
    Node *TreeNode
}
```
