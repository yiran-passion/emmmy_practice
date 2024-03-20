## 704 二分查找

### 二分法

- 思路：二分法，顾名思义，在两种情况中做选择。二分查找的前提是 **有序数组** ，取数组中间的数，大于中间数则取中间数右侧的数。小于中间数则取中间数左侧的数，指导只剩下一个值就是目标值。

- 代码

```js
// while 遍历
const search = (nums, target) => {
    let left = 0, right = nums.length - 1, mid
    while(left <= right) {
        mid = Math.floor((left + right) / 2)
        if (nums[mid] > target) {
            right = mid - 1
        }
        if (nums[mid] < target) {
            left = mid + 1
        }
        if (nums[mid] === target) {
            return mid
        }
    }
    return -1
}
// 递归 ？
```

## 27 移除元素

### 双指针

- 思路：使用快、慢指针，快指针遍历数组，慢指针用于检查数组的值是/否等于目标值。如果快指针指向的值等于目标值，指针直接右移。如果快指针指向的值不等于目标值，更新数组的值。这样慢指针走过的位置就是符合条件的数组值。

- 代码

```js
const removeElement = (nums, val) => {
  if (!nums.length) return 0 
  let slowIndex = 0
  for (let fastIndex = 0, len = nums.length; fastIndex < len; fastIndex ++) {
      if (nums[fastIndex] === val) {
        continue
      }
      nums[slowIndex] = nums[fastIndex]
      slowIndex ++
  }
  return slowIndex
}
```
