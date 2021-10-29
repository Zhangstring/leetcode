---
title: 归并排序
---

归并排序使用的就是分治思想。如果要排序一个数组，我们先把数组从中间分成前后两部分，然后对前后两部分分别排序，再将排好序的两部分合并在一起，这样整个数组就都有序了。

1. 空间复杂度O(n)
2. 稳定的排序算法
3. 平均时间复杂度O(nlogn)

```jsx live

function test() {
  const merge = (left, right) => {
    const result = []
    while(left.length && right.length) {
        if(left[0] < right[0]) {
            result.push(left.shift())
        } else {
            result.push(right.shift())
        }
    }
    while(left.length) {
        result.push(left.shift())
    }
    while(right.length) {
        result.push(right.shift())
    }
    return result
  }
  const mergeSort = (nums) => {
    const len = nums.length
    if(len < 2) {
        return nums
    }
    const mid = Math.floor(len / 2)
    const left = nums.slice(0, mid)
    const right = nums.slice(mid)
    return merge(mergeSort(left), mergeSort(right))
  }
  return (
    <div>
      <h3>[5,2,3,1]排序后:{mergeSort([5,2,3,1])}</h3>
    </div>
  )
}
```