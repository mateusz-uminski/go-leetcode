# Contains Duplicate

[217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)


# Solution

```go
func containsDuplicate(nums []int) bool {
    temp := make(map[int]int)
    for _, v := range nums {
        temp[v]++
        if temp[v] == 2 {
            return true
        }
    }
    return false
}
```
