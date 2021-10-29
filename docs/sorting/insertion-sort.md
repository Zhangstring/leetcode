---
title: 插入排序
---

插入排序包含两种操作，一种是元素的比较，一种是元素的移动。当我们需要将一个数据 a 插入到已排序区间时，需要拿 a 与已排序区间的元素依次比较大小，找到合适的插入位置。找到插入点之后，我们还需要将插入点之后的元素顺序往后移动一位，这样才能腾出位置给元素 a 插入。

1. 原地排序算法，空间复杂度O(1)
2. 稳定的排序算法
3. 平均时间复杂度O(n^2)

```jsx live

function test() {
  const insertionSort = (nums) => {
    for(let i = 0; i < nums.length; i++) {
        let value = nums[i]
        let j = i - 1
        for(; j >= 0; j--) {
            if(nums[j] > value) {
                nums[j+1] = nums[j]
            } else {
                break
            }
        }
        nums[j+1] = value
    }
    return nums
  }
  return (
    <div>
      <h3>[5,2,3,1]排序后:{insertionSort([5,2,3,1])}</h3>
    </div>
  )
}
```