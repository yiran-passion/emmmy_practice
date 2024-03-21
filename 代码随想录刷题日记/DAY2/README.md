## 977.有序数组的平方

### 解法

#### 1. 双指针

- 思路：给定一个 **非递减顺序** 排序的整数数组，数组中可能存在正数或者负数。思路是两侧的值的平方分别为正/负数的最大值，使用双指针，从两侧向中间位移。比较两侧值的大小，大的值插入数组。由于结果也需要 非递减顺序 的数组，所以使用 unshift 在数组前面插入值，这样能避免翻转数组。

- 代码

```js
const sortedSquares = (nums, result = []) => {
    if (!nums.length) return result
    let left = 0, right = nums.length - 1
    while (left <= right) {
        if (nums[left] * nums[left] < nums[right] * nums[right]) {
            result.unshift(nums[right] * nums[right])
            right --
        } else {
            result.unshift(nums[left] * nums[left])
            left ++
        }
    }
    return result
}
```

## 209.长度最小的子数组

### 解法

#### 滑动窗口

- 代码

```js
const minSubArrayLen = (target, nums, result = 0) => {
    let left = 0, right = 0, count = 0, length = nums.length
    while (right <= length - 1) {
        count += nums[right]
        while (count >= target) {
            result = result ? Math.min(result, right - left + 1) : right - left + 1
            count -= nums[left]
            left ++
        }
        right ++
    }
    return result
}
```

## 59.螺旋矩阵II

### 解法

#### 常规

- 代码

```js
const generateMatrix = (n) => {
    let result = new Array(n).fill(null).map(item => new Array(n).fill(null))
    let startX = 0, startY = 0, loop = Math.floor(n / 2)
    let count = 0
    while (loop > 0) {
        for (let i = startX, j = startY; i < n - 1 - startX; i++) {
        count++
        result[j][i] = count
        }
        for (let i = n - 1 - startX, j = startY; j < n - 1 - startY; j++) {
        count++
        result[j][i] = count
        }
        for (let i = n - 1 - startX, j = n - 1 - startY; i > startX; i--) {
        count++
        result[j][i] = count
        }
        for (let i = startX, j = n - 1 - startY; j > startX; j--) {
        count++
        result[j][i] = count
        }
        startX++
        startY++
        loop--
    }
    // 如果 n 为奇数，中间的层只有一个数，直接赋值
    if (n % 2 === 1) {
        const mid = (n - 1) / 2
        result[mid][mid] = n * n
    }
    return result
}
```
