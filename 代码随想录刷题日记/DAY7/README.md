## 454. 四数之和 Ⅱ

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/4sum-ii/description/)

### 解法

#### 1. 使用 Map 数据结构

- 思路：

- 代码：

  ```js
  const fourSumCount = (nums1, nums2, nums3, nums4, result = 0) => {
      const map = new Map()
      for (let i = 0; i < nums1.length; i++) {
          for (let j = 0; j < nums2.length; j++) {
              const sum = nums1[i] + nums2[j]
              if (map.has(sum)) {
                  map.set(sum, map.get(sum) + 1)
              } else {
                  map.set(sum, 1)
              }
          }
      }
      for (let i = 0; i < nums3.length; i++) {
          for (let j = 0; j < nums4.length; j++) {
              const reset = 0 - nums3[i] - nums4[j]
              if (map.has(reset)) {
                  result += map.get(reset)
              }
          }
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n^2)
  - 空间复杂度：O(n)


## 383. 赎金信

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/4sum-ii/description/)

### 解法

#### 1. 

- 思路：

- 代码：

  ```js
  const canConstruct = (ransomNote, magazine) => {
      const map = new Map()
      for (let i = 0; i < magazine.length; i++) {
          map.set(magazine[i], map.has(magazine[i]) ? map.get(magazine[i]) + 1 : 1)
      }
      for (let j = 0; j < ransomNote.length; j++) {
          if (!map.has(ransomNote[j])) return false
          if (map.get(ransomNote[j]) > 1) {
              map.set(ransomNote[j], map.get(ransomNote[j]) - 1)
          } else {
              map.delete(ransomNote[j])
          }
      }
      return true
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 15. 三数之和

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/3sum/description/)

### 解法

#### 1. 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()


## 18. 四数之和

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/4sum/description/)

### 解法

#### 1. 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
