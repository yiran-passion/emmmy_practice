## 216. 组合总和 III

### 详情

[代码随想录链接](https://programmercarl.com/0216.%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8CIII.html)

[Leetcode 题目链接](https://leetcode.cn/problems/combination-sum-iii/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const combinationSum3 = (k, n, result = []) => {
      const backTracking = (start, sum, path) => {
          if (path.length === k) {
              if (sum === 0) {
                  result.push(JSON.parse(JSON.stringify(path)))
              }
              return
          }
          for (let i = start; i <= 9; i++) {
              // 剪枝：如果 i 大于 sum，后面的值一定大于 sum，所以排除
              if (i > sum) break
              path.push(i)
              backTracking(i + 1, sum - i, path)
              path.pop()
          }
      }
      backTracking(1, n, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n * 2^n)
  - 空间复杂度：O(n)

## 17. 电话号码的字母组合

### 详情

[代码随想录链接](https://programmercarl.com/0017.%E7%94%B5%E8%AF%9D%E5%8F%B7%E7%A0%81%E7%9A%84%E5%AD%97%E6%AF%8D%E7%BB%84%E5%90%88.html)

[Leetcode 题目链接](https://leetcode.cn/problems/letter-combinations-of-a-phone-number/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const letterCombinations = (digits, result = []) => {
      if (!digits.length) return result
      // 因为按键固定，所以设置一个按键 map
      const map = {
          '2': ['a', 'b', 'c'],
          '3': ['d', 'e', 'f'],
          '4': ['g', 'h', 'i'],
          '5': ['j', 'k', 'l'],
          '6': ['m', 'n', 'o'],
          '7': ['p', 'q', 'r', 's'],
          '8': ['t', 'u', 'v'],
          '9': ['w', 'x', 'y', 'z'],
      }
      const backTracking = (start, path) => {
          if (path.length === digits.length) {
              result.push(path.join(''))
              return
          }

          const digitsMap = map[digits[start]]

          for (let i = 0; i < digitsMap.length; i++) {
              path.push(digitsMap[i])
              backTracking(start + 1, path)
              path.pop()
          }
      }
      backTracking(0, [])
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n * 2^n)
  - 空间复杂度：O(n)
