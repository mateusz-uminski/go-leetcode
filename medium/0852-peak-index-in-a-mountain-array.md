# Peak Index in a Mountain Array

[852. Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/description/)


# Solution

```go
func peakIndexInMountainArray(arr []int) int {
    left := 0
    right := len(arr) - 1

    for left <= right {
        mid := left + (right - left) / 2

        if arr[mid - 1] < arr[mid] && arr[mid] > arr[mid + 1] {
            return mid
        }

        if arr[mid - 1] < arr[mid] && arr[mid] < arr[mid + 1] {
            left = mid
        } else {
            right = mid
        }
    }

    return 0
}
```
