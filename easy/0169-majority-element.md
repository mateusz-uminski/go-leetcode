# Majority Element

[169. Majority Element](https://leetcode.com/problems/majority-element/description/)


# Solution #1

```go
func majorityElement(nums []int) int {
    temp := make(map[int]int)
    for _, v := range nums {
        temp[v]++
    }

    max := 0
    idx := 0
    for k, v := range temp {
        if v > max {
            max = v
            idx = k
        }
    }
    return idx
}
```


# Solution #2

```go
func majorityElement(nums []int) int {
    sort.Ints(nums)
    return nums[len(nums)/2]
}
```
