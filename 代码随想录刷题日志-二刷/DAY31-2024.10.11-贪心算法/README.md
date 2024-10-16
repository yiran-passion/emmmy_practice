## 455. 分发饼干

### 详情

[代码随想录讲解](https://programmercarl.com/0455.%E5%88%86%E5%8F%91%E9%A5%BC%E5%B9%B2.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/assign-cookies/description/)

### 解法

#### 贪心算法

- 代码：

  ```js
  const findContentChildren = function(g, s, result = 0) {
      g = g.sort((a, b) => b - a)
      s = s.sort((a, b) => b - a)
      let j = 0
      for (let i = 0; i < g.length; i++) {
          if (s[j] >= g[i]) {
              result ++
              j ++
          }
      }
      return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n^2)
  - 空间复杂度：O(1)


## 376. 摆动序列

### 详情

[代码随想录讲解](https://programmercarl.com/0376.%E6%91%86%E5%8A%A8%E5%BA%8F%E5%88%97.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/wiggle-subsequence/description/)

### 解法

#### 贪心算法

- 代码：

  ```js
  const wiggleMaxLength = function(nums, result = 1) {
    if (nums.length <= 1) return nums.length
    let preDiff = 0
    for (let i = 0; i < nums.length; i ++) {
      let currentDiff = nums[i + 1] - nums[i]
      if ((currentDiff > 0 && preDiff <= 0) || (currentDiff < 0 && preDiff >= 0)) {
        result ++
        preDiff = currentDiff
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)


## 53. 最大子数组和

### 详情

[代码随想录讲解](https://programmercarl.com/0053.%E6%9C%80%E5%A4%A7%E5%AD%90%E5%BA%8F%E5%92%8C.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/maximum-subarray/description/)

### 解法

#### 贪心算法

- 代码：

  ```js
  const maxSubArray = function(nums, result = -Infinity) {
    let count = 0
    for (let i = 0; i < nums.length; i++) {
      count += nums[i]
      if (count > result) {
        result = count
      }
      if (count < 0) {
        count = 0
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)
