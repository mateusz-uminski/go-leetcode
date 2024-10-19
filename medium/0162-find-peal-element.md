# Find Peak Element

[162. Find Peak Element](https://leetcode.com/problems/find-peak-element/description/)


# Solution

```go
func findPeakElement(nums []int) int {
    max := nums[0]
    pos := 0
    for i, v := range nums {
        if v > max {
            max = v
            pos = i
        }
    }
    return pos
}
```
