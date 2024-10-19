# Roman to Integer

[13. Roman to Integer](https://leetcode.com/problems/roman-to-integer/description/)

# Solution

```go
func romanToInt(s string) int {
    symbols := map[byte]int{
        'I': 1,
        'V': 5,
        'X': 10,
        'L': 50,
        'C': 100,
        'D': 500,
        'M': 1000,
    }

    sum := symbols[s[len(s)-1]]
    for i:=len(s)-2; i >= 0; i-- {
        if symbols[s[i+1]] <= symbols[s[i]] {
            sum = sum + symbols[s[i]]
        } else {
            sum = sum - symbols[s[i]]
        }
    }

    return sum
}
```
