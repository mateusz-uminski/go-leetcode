# Find All Numbers Disappeared in an Array

[448. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/)


# Solution

```go
func findDisappearedNumbers(nums []int) []int {
    for i := 0; i < len(nums); i++ {
        idx := abs(nums[i])-1
        if nums[idx] > 0 {
            nums[idx] = -nums[idx]
        }
    }

    result := []int{}
    for i, v := range nums {
        if v > 0 {
            result = append(result, i+1)
        }
    }
    return result
}

func abs(x int) int {
    if x > 0 {
        return x
    }
    return -x
}
```
