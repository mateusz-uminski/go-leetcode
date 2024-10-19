# Plus One

[66. Plus One](https://leetcode.com/problems/plus-one/description/)


# Solution

```go
func plusOne(digits []int) []int {
    for x := len(digits) - 1; x >= 0; x-- {
        if digits[x] < 9 {
            digits[x]++
            return digits
        }
        digits[x] = 0
    }
    digits = append([]int{1}, digits...)
    return digits
}
```
