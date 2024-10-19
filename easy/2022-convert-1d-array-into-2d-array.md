# Convert 1D Array Into 2D Array

[2022. Convert 1D Array Into 2D Array](https://leetcode.com/problems/convert-1d-array-into-2d-array/description/)


# Solution

```go
func construct2DArray(original []int, m int, n int) [][]int {
    if m*n != len(original) {
        return [][]int{}
    }

    array2D := make([][]int, m)
    for i, row := range array2D {
        row = original[n*i:n*i+n]
        array2D[i] = row
    }
    return array2D
}
```
