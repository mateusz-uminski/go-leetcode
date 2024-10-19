# Fizz Buzz

[412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/description/)


# Solution

```go
func fizzBuzz(n int) []string {
    solution := make([]string, n, n)
    for i := 1; i <= n; i++ {
        if i % 3 == 0 && i % 5 == 0 {
            solution[i-1] = "FizzBuzz"
        } else if i % 3 == 0 {
            solution[i-1] = "Fizz"
        } else if i % 5 == 0 {
            solution[i-1] = "Buzz"
        } else {
            solution[i-1] = strconv.Itoa(i)
        }
    }
    return solution
}
```
