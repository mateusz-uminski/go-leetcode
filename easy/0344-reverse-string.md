# Reverse String

[283. Reverse String](https://leetcode.com/problems/reverse-string/description/)


# Solution

```go
func reverseString(s []byte)  {
    for x, y := 0, len(s)-1; x < len(s)/2; x, y = x+1, y-1 {
        s[x], s[y] = s[y], s[x]
    }
}
```
