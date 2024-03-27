## 454. 四数之和 Ⅱ

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/4sum-ii/description/)

### 解法

#### 使用 Map 数据结构

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

#### map 数据结构

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

#### 双指针

- 思路：这道题用哈希表很麻烦。使用双指针会简单一点

- 代码：

  ```js
  const threeSum = (nums, result = []) => {
      // 从小到大排序
      nums = nums.sort((a, b) => a - b)

      for (let i = 0; i < nums.length; i++) {
          // 如果第一个数大于 0 ，那么一定不存在三个数的和等于 0
          if (nums[i] > 0) break
          // 去重
          if (nums[i] === nums[i - 1]) continue
          // 定义左/右指针
          let left = i + 1
          let right = nums.length - 1
          while (left < right) {
              const sum = nums[i] + nums[left] + nums[right]
              if (sum < 0) {
                  left++
              } else if (sum > 0) {
                  right--
              } else {
                  const leftNum = nums[left], rightNum = nums[right]
                  result.push([nums[i], leftNum, rightNum])
                  // 这里判断如果重复了，指针再次位移一次进行去重
                  while (nums[left] === leftNum) left++
                  while (nums[right] === rightNum) right--
              }
          }
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n^2)
  - 空间复杂度：O(n)


## 18. 四数之和

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/4sum/description/)

### 解法

#### 双指针

- 思路：思路与三数之和相同，采用双指针，只是外面套一层循环，五数之和就再套一层，以此类推

- 代码：

  ```js
  const fourSum = (nums, target, result = []) => {
      // 数组排序
      nums.sort((a, b) => a - b)
      for (let i = 0; i < nums.length; i++) {
          if (nums[i] === nums[i - 1]) continue
          for (let j = i + 1; j < nums.length; j++) {
              if (j - i > 1 && nums[j] === nums[j - 1]) continue
              let left = j + 1, right = nums.length - 1
              while (left < right) {
                  const sum = nums[i] + nums[j] + nums[left] + nums[right]
                  if (sum < target) {
                      left++
                  } else if (sum > target) {
                      right--
                  } else {
                      const leftNum = nums[left], rightNum = nums[right]
                      result.push([nums[i], nums[j], nums[left], nums[right]])
                      while (nums[left] === leftNum) left++
                      while (nums[right] === rightNum) right--
                  }
              }
          }
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n^3)
  - 空间复杂度：O(n)
