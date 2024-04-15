## 39. 组合总和

### 详情

[代码随想录链接](https://programmercarl.com/0039.%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C.html)

[Leetcode 题目链接](https://leetcode.cn/problems/combination-sum/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const combinationSum = (candidates, target, result = []) => {
      const backTracking = (start, sum, path) => {
          if (sum <= 0) {
              if (sum === 0) {
                  result.push(JSON.parse(JSON.stringify(path)))
              }
              return
          }
          for (let i = start; i < candidates.length; i++) {
              path.push(candidates[i])
              backTracking(i, sum - candidates[i], path)
              path.pop()
          }
      }
      backTracking(0, target, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 40.组合总和 II

### 详情

[代码随想录链接](https://programmercarl.com/0040.%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8CII.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[Leetcode 题目链接](https://leetcode.cn/problems/combination-sum-ii/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const combinationSum2 = (candidates, target, result = []) => {
      const handleCandidates = candidates.sort((a, b) => a - b)
      console.log(handleCandidates)
      const backTracking = (start, sum, path) => {
          if (sum <= 0) {
              if (sum === 0) {
                  result.push(JSON.parse(JSON.stringify(path)))
              }
              return
          }
  
          for (let i = start; i < handleCandidates.length; i++) {
              if (i - start > 0 && handleCandidates[i] === handleCandidates[i - 1]) continue
              path.push(handleCandidates[i])
              backTracking(i + 1, sum - handleCandidates[i], path)
              path.pop()
          }
      }
      backTracking(0, target, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 131. 分割回文串

### 详情

[代码随想录链接](https://programmercarl.com/0131.%E5%88%86%E5%89%B2%E5%9B%9E%E6%96%87%E4%B8%B2.html)

[Leetcode 题目链接](https://leetcode.cn/problems/palindrome-partitioning/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const sup = (string) => {
      let left = 0, right = string.length - 1
      while (left < right) {
          if (string[left] === string[right]) {
              left++
              right--
          } else {
              return false
          }
      }
      return true
  }
  
  const partition = (s, result = []) => {
      const backTracking = (string, path) => {
          if (!string.length) {
              result.push(JSON.parse(JSON.stringify(path)))
              return
          }
          for (let i = 1; i <= string.length; i++) {
              if (!sup(string.slice(0, i))) continue
              path.push(string.slice(0, i))
              backTracking(string.slice(i), path)
              path.pop()
          }
      }
      backTracking(s, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
