## 491. 递增子序列

### 详情

[代码随想录链接](https://programmercarl.com/0491.%E9%80%92%E5%A2%9E%E5%AD%90%E5%BA%8F%E5%88%97.html)

[Leetcode 题目链接](https://leetcode.cn/problems/non-decreasing-subsequences/description/)

### 解法

#### 回溯（使用 Set 去重）

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

## 46. 全排列

### 详情

[代码随想录链接](https://programmercarl.com/0046.%E5%85%A8%E6%8E%92%E5%88%97.html)

[Leetcode 题目链接](https://leetcode.cn/problems/permutations/description/)

### 解法

#### 回溯

- 思路：

- 代码：

  ```js
  const permute = (nums, result = []) => {
      const backTracking = (path) => {
          if (path.length === nums.length) {
              result.push(path.concat())
              return
          }
          for (let i = 0; i < nums.length; i++) {
              if (path.includes(nums[i])) continue
              path.push(nums[i])
              backTracking(path)
              path.pop()
          }
      }
      backTracking([])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 47. 全排列 II

### 详情

[代码随想录链接](https://programmercarl.com/0047.%E5%85%A8%E6%8E%92%E5%88%97II.html)

[Leetcode 题目链接](https://leetcode.cn/problems/permutations-ii/description/)

### 解法

#### 回溯（使用 Set 去重）

- 思路：

- 代码：

  ```js
  const permuteUnique = (nums) => {
      const result = new Set()
      const backTracking = (path) => {
          if (path.length === nums.length) {
              const handlePath = path.map(item => nums[item])
              result.add(JSON.stringify(handlePath))
              return
          }
          for (let i = 0; i < nums.length; i++) {
              if (path.includes(i)) continue
              path.push(i)
              backTracking(path)
              path.pop()
          }
      }
      backTracking([])
      return Array.from(result).map(item => JSON.parse(item))
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
