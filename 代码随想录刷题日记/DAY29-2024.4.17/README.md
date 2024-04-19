## 491. 递增子序列

### 详情

[代码随想录链接](https://programmercarl.com/0491.%E9%80%92%E5%A2%9E%E5%AD%90%E5%BA%8F%E5%88%97.html)

[Leetcode 题目链接](https://leetcode.cn/problems/non-decreasing-subsequences/description/)

### 解法

#### 回溯（使用 set 去重）

- 思路：

- 代码：

  ```js
  const findSubsequences = (nums, result = []) => {
      const set = new Set()
      const backTracking = (start, path) => {
          if (path.length >= 2) {
              set.add(JSON.stringify(path))
          }
          for (let i = start; i < nums.length; i++) {
              if (nums[i] < path[path.length - 1]) continue
              path.push(nums[i])
              backTracking(i + 1, path)
              path.pop()
          }
      }
      backTracking(0, [])
      return Array.from(set).map(item => JSON.parse(item))
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
