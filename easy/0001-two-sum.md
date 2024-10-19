# Two Sum

[1. Two Sum](https://leetcode.com/problems/two-sum/description/)


# Solution

```go
func twoSum(nums []int, target int) []int {
    temp := make(map[int]int)
    for i, v := range nums {
        if result, ok := temp[target-v]; ok {
            return []int{result, i}
        }
        temp[v] = i
    }
    return []int{}
}
```
