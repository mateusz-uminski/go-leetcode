# Max Consecutive Ones

[485. Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/description/)


# Solution

```go
func findMaxConsecutiveOnes(nums []int) int {
    max := 0
    counter := 0
    for _, v := range nums {
        if v == 1 {
            counter++
            if counter > max {
                max = counter
            }
        } else {
            counter = 0
        }
    }
    return max
}
```
