---
title: 快速排序
---

快速排序的最坏运行情况是 O(n²)，比如说顺序数列的快排。但它的平摊期望时间是 O(nlogn)，且 O(nlogn) 记号中隐含的常数因子很小，比复杂度稳定等于 O(nlogn) 的归并排序要小很多。所以，对绝大多数顺序性较弱的随机数列而言，快速排序总是优于归并排序。


1. 空间复杂度O(logn)
2. 不稳定的排序算法
3. 平均时间复杂度O(nlogn)

```jsx live

function test() {
  const swap = (arr, i, j) => {
    let temp = arr[i]
    arr[i] = arr[j]
    arr[j] = temp
  }
  const partition = (arr, left, right) => {
    let pivot = left;
    let index = pivot + 1
    for(let i = index; i <= right; i++) {
      if(arr[i] < arr[pivot]) {
        swap(arr, i, index)
        index++
      }
    }
    swap(arr, pivot, index - 1)
    return index - 1
  }
  const quickSort = (arr, left ,right) => {
    let len = arr.length;
    let partitionIndex;
    left = typeof left !== 'number' ? 0 : left;
    right = typeof right !== 'number' ? len - 1 : right;
    if(left < right) {
      partitionIndex = partition(arr, left ,right)
      quickSort(arr, left, partitionIndex - 1)
      quickSort(arr, partitionIndex + 1, right)
    }
    return arr
  }
  return (
    <div>
      <h3>[5,2,3,1]排序后:{quickSort([5,2,3,1])}</h3>
    </div>
  )
}
```