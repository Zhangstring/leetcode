---
title: 选择排序
---

选择排序每次会从未排序区间中找到最小的元素，将其放到已排序区间的末尾。

1. 原地排序算法，空间复杂度O(1)
2. 不稳定的排序算法
3. 平均时间复杂度O(n^2)

```jsx live

function test() {
  const selectionSort = (nums) => {
    for(let i = 0; i < nums.length; i++) {
        let key = i
        for(let j = i + 1; j < nums.length; j++) {
            if(nums[key] > nums[j]) {
                key = j
            }
        }
        let temp = nums[i]
        nums[i] = nums[key]
        nums[key] = temp
    }
    return nums
  }
  return (
    <div>
      <h3>[5,2,3,1]排序后:{selectionSort([5,2,3,1])}</h3>
    </div>
  )
}
```