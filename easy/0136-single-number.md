# Single Number

[136. Single Number](https://leetcode.com/problems/single-number/description/)


# Solution #1

```go
func singleNumber(nums []int) int {
    result := 0
    for _, v := range nums {
        result ^= v
    }
    return result
}
```


# Solution #2

```go
func singleNumber(nums []int) int {
    set := make(map[int]uint8)
    for _, v := range nums {
        set[v]++
    }
    for k, v := range set {
        if v == 1 {
            return k
        }
    }
    return 0
}
```
