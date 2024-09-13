## 209. 长度最小的子数组

### 详情

[代码随想录讲解](https://programmercarl.com/0209.%E9%95%BF%E5%BA%A6%E6%9C%80%E5%B0%8F%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84.html)

[题目链接](https://leetcode.cn/problems/minimum-size-subarray-sum/description/)

### 解法

####

- 代码：

  ```js
  var minSubArrayLen = function(target, nums, result = 0) {
    let sum = 0, slowIndex = 0
    for (let fastIndex = 0, len = nums.length; fastIndex < len; fastIndex++) {
      sum += nums[fastIndex]
      while (sum >= target) {
        result = result === 0 ? fastIndex - slowIndex + 1 : Math.min(result, fastIndex - slowIndex + 1)
        sum -= nums[slowIndex]
        slowIndex ++
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)


## 59. 螺旋矩阵II

### 详情

[代码随想录讲解](https://programmercarl.com/0059.%E8%9E%BA%E6%97%8B%E7%9F%A9%E9%98%B5II.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/spiral-matrix-ii/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  var generateMatrix = function(n) {
    const result = new Array(n).fill(null).map(item => new Array(n).fill(null))
    let startX = 0, startY = 0, loop = Math.floor(n / 2), sum = 0
    while (loop--) {
      for (let i = startX, j = startY; j < n - 1 - startY; j ++) {
        sum ++
        result[i][j] = sum
      }
      for (let i = startX, j = n - startY -1; i < n - 1 - startX; i ++) {
        sum ++
        result[i][j] = sum
      }
      for (let i = n - startX - 1, j = n - startY - 1; j > startY; j --) {
        sum ++
        result[i][j] = sum
      }
      for (let i = n - startX - 1, j = startY; i > startX; i --) {
        sum ++
        result[i][j] = sum
      }
      startX ++
      startY ++
    }
    if (n % 2 === 1) {
      result[Math.floor(n / 2)][Math.floor(n / 2)] = n * n
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n^2)
