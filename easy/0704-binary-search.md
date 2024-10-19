# Binary Search

[704. Binary Search](https://leetcode.com/problems/binary-search/description/)


# Solution

```go
func search(nums []int, target int) int {
    left := 0
    right := len(nums) - 1

    for left <= right {
        mid := left + (right - left) / 2
        if nums[mid] > target {
            right = mid - 1
        } else if nums[mid] < target {
            left = mid + 1
        } else {
            return mid
        }
    }

    return -1
}
```
