---
title: 冒泡排序
---

冒泡排序只会操作相邻的两个数据。每次冒泡操作都会对相邻的两个元素进行比较，看是否满足大小关系要求。如果不满足就让它俩互换。一次冒泡会让至少一个元素移动到它应该在的位置，重复 n 次，就完成了 n 个数据的排序工作。

1. 原地排序算法，空间复杂度O(1)
2. 稳定的排序算法
3. 平均时间复杂度O(n^2)

```jsx live

function test() {
  const bubbleSort = (nums) => {
    if(nums.length <= 1) return nums
    for(let i = 0; i < nums.length; i++) {
        let completed = true
        for(let j = 0; j < nums.length - i; j++) {
            if(nums[j] > nums[j+1]) {
                completed = false
                let a = nums[j+1]
                nums[j+1] = nums[j]
                nums[j] = a
            }
        }
        if (completed) {
            return nums
        }
    }
    return nums
  }
  return (
    <div>
      <h3>[5,2,3,1]排序后:{bubbleSort([5,2,3,1])}</h3>
    </div>
  )
}
```