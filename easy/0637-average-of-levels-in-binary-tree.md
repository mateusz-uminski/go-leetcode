# Average of Levels in Binary Tree

[637. Average of Levels in Binary Tree](https://leetcode.com/problems/average-of-levels-in-binary-tree/description/)


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
func averageOfLevels(root *TreeNode) []float64 {
    if root == nil {
        return []float64{}
    }

    queue := []*TreeNode{root}

    results := []float64{}
    for len(queue) > 0 {
        sum := 0
        nodes := len(queue)
        for i := 0; i < nodes; i++ {
            sum += queue[i].Val
            if queue[i].Left != nil {
                queue = append(queue, queue[i].Left)
            }
            if queue[i].Right != nil {
                queue = append(queue, queue[i].Right)
            }
        }
        avg := float64(sum)/float64(nodes)
        queue = queue[nodes:]
        results = append(results, avg)
    }
    return results
}
```
