# Minimum Depth of Binary Tree

[111. Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/description/)


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
func minDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }

    queue := []*TreeNode{root}
    depth := 0
    for len(queue) > 0 {
        qSize := len(queue)
        depth++
        for i := 0; i < qSize; i++ {
            if queue[i].Left == nil && queue[i].Right == nil {
                return depth
            }
            if queue[i].Left != nil {
                queue = append(queue, queue[i].Left)
            }
            if queue[i].Right != nil {
                queue = append(queue, queue[i].Right)
            }
        }
        queue = queue[qSize:]
    }

    return depth
}
```
