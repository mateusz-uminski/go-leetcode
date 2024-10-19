# Binary Tree Inorder Traversal

[94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/description/)


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
func inorderTraversal(root *TreeNode) []int {
    var solution []int
    if root == nil {
        return []int{}
    }

    solution = append(solution, inorderTraversal(root.Left)...)
    solution = append(solution, root.Val)
    solution = append(solution, inorderTraversal(root.Right)...)
    return solution
}
```
