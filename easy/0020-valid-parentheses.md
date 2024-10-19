# Valid Parentheses

[20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)


# Solution

```go
func isValid(s string) bool {
    stack := make([]byte, 0, len(s))
    for _, bracket := range s {
        if bracket == '{' {
            stack = append(stack, '}')
        } else if bracket == '[' {
            stack = append(stack, ']')
        } else if bracket == '(' {
            stack = append(stack, ')')
        } else {
            if len(stack) == 0 || stack[len(stack)-1] != byte(bracket) {
                return false
            }
            stack = stack[:len(stack)-1]
        }
    }
    return len(stack) == 0
}
```
