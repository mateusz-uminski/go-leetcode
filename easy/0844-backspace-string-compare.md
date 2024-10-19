# Backspace String Compare

[844. Backspace String Compare](https://leetcode.com/problems/backspace-string-compare/description/)


# Solution

```go
func backspaceCompare(s string, t string) bool {
    if removeCharacters(s) == removeCharacters(t) {
        return true
    }
    return false
}

func removeCharacters(s string) string {
    backspaceCounter := 0
    result := []byte{}
    for i := len(s)-1; i >= 0; i-- {
        if s[i] == '#' {
            backspaceCounter++
        } else {
            if backspaceCounter > 0 {
                backspaceCounter--
                continue
            }
            result = append(result, s[i])
        }
    }
    return string(result)
}
```
