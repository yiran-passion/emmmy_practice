## 77. 组合

### 详情

[代码随想录链接](https://programmercarl.com/0077.%E7%BB%84%E5%90%88.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[Leetcode 题目链接](https://leetcode.cn/problems/combinations/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const combine = (n, k, result = []) => {
      const backTracking = (start, path) => {
          if (path.length === k) {
              result.push(JSON.parse(JSON.stringify(path)))
              return
          }
          for (let i = start; i <= n; i++) {
              path.push(i)
              backTracking(i + 1, path)
              path.pop()
          }
      }
      backTracking(1, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n * 2^n)
  - 空间复杂度：O(n)
