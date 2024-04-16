## 93. 复原IP地址

### 详情

[代码随想录链接](https://programmercarl.com/0093.%E5%A4%8D%E5%8E%9FIP%E5%9C%B0%E5%9D%80.html)

[Leetcode 题目链接](https://leetcode.cn/problems/restore-ip-addresses/description/)

### 解法

#### 回溯

- 思路：

- 代码：

  ```js
  const restoreIpAddresses = (s, result = []) => {
      const backTracking = (string, path) => {
          if (!string.length) {
              if (path.length === 4) {
                  result.push(path.join('.'))
              }
              return
          }
          for (let i = 1; i <= string.length; i++) {
              const handleString = string.slice(0, i)
              if (handleString.length > 1 && handleString.startsWith('0')) continue
              if (Number(handleString) > 255) continue
              if (path.length > 4) break
              path.push(handleString)
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

## 78. 子集

### 详情

[代码随想录链接](https://programmercarl.com/0078.%E5%AD%90%E9%9B%86.html)

[Leetcode 题目链接](https://leetcode.cn/problems/subsets/description/)

### 解法

#### 回溯

- 思路：

- 代码：

  ```js
  const subsets = (nums, result = []) => {
      const backTracking = (start, path) => {
          result.push(path.concat())
          for (let i = start; i < nums.length; i++) {
              path.push(nums[i])
              backTracking(i + 1, path)
              path.pop()
          }
      }
      backTracking(0, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
 
## 90. 子集II

### 详情

[代码随想录链接](https://programmercarl.com/0090.%E5%AD%90%E9%9B%86II.html)

[Leetcode 题目链接](https://leetcode.cn/problems/subsets-ii/description/)

### 解法

#### 回溯

- 思路：

- 代码：

  ```js
  const subsetsWithDup = (nums, result = []) => {
      nums.sort((a, b) => a - b)
      const backTracking = (start, path) => {
          result.push(path.concat())
          for (let i = start; i < nums.length; i++) {
              if (nums[i] === nums[i - 1] && i > start) continue
              path.push(nums[i])
              backTracking(i + 1, path)
              path.pop()
          }
      }
      backTracking(0, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

### 解法

#### 回溯（使用 set 去重）

- 思路：

- 代码：

  ```js
  const subsetsWithDup = (nums) => {
      nums.sort((a, b) => a - b)
      let result = new Set()
      const backTracking = (start, path) => {
          result.add(JSON.stringify(path))
          for (let i = start; i < nums.length; i++) {
              path.push(nums[i])
              backTracking(i + 1, path)
              path.pop()
          }
      }
      backTracking(0, [])
      return Array.from(result).map(item => JSON.parse(item))
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()


