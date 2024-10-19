# Squares of a Sorted Array

[977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/description/)


# Solution

```go
func sortedSquares(nums []int) []int {
    leftPointer := 0
    rightPointer := len(nums)-1

    result := make([]int, len(nums))
    i := len(result)-1
    for i >= 0 {
        leftSquare := nums[leftPointer] * nums[leftPointer]
        rightSquare := nums[rightPointer] * nums[rightPointer]
        if leftSquare > rightSquare {
            result[i] = leftSquare
            leftPointer++
        } else {
            result[i] = rightSquare
            rightPointer--
        }
        i--
    }
    return result
}
```
