# Missing Number

[268. Missing Number](https://leetcode.com/problems/missing-number/description/)


# Solution

```go
func missingNumber(nums []int) int {
    currentSum := 0
    for i := 0; i < len(nums); i++ {
        currentSum += nums[i]
    }

    expectedSum := 0
    for i := 0; i <= len(nums); i++ {
        expectedSum += i
    }

    return expectedSum-currentSum
}
```
