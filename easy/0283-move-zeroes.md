# Move Zeroes

[283. Move Zeroes](https://leetcode.com/problems/move-zeroes/description/)


# Solution

```go
func moveZeroes(nums []int)  {
    var y int
    for x := 0; x < len(nums); x++ {
        if nums[x] != 0 {
            nums[y], nums[x] = nums[x], nums[y]
            y++
        }
    }
}
```
