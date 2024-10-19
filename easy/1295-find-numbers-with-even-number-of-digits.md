# Find Numbers with Even Number of Digits

[1295. Find Numbers with Even Number of Digits](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/description/)


# Solution

```go
func findNumbers(nums []int) int {
    var max int
    for _, v := range nums {
        if len(strconv.Itoa(v)) % 2 == 0 {
            max++
        }
    }
    return max
}
```
