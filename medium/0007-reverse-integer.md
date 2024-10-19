# Reverse Integer

[7. Reverse Integer](https://leetcode.com/problems/reverse-integer/description/)


# Solution

```go
func reverse(x int) int {
    solution := 0
    for x != 0 {
        temp := x % 10
        x = x / 10
        if solution > math.MaxInt32/10 || (solution == math.MaxInt32 /10 && temp > 7) {
            return 0
        }
        if solution < math.MinInt32/10 || (solution == math.MinInt32 /10 && temp < -8) {
            return 0
        }
        solution = solution * 10 + temp
    }
    return solution
}
```
