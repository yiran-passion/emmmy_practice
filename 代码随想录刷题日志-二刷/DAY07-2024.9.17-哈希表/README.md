## 454. 四数相加 II

### 详情

[代码随想录讲解](https://programmercarl.com/0454.%E5%9B%9B%E6%95%B0%E7%9B%B8%E5%8A%A0II.html)

[题目链接](https://leetcode.cn/problems/4sum-ii/description/)

### 解法

#### Map 数据结构

- 思路：

- 代码：

  ```js
  const fourSumCount = function(nums1, nums2, nums3, nums4, result = 0) {
    const map = new Map()
    for (let i = 0; i < nums1.length; i++) {
      for (let j = 0; j < nums2.length; j++) {
        const sums = nums1[i] + nums2[j]
        map.set(sums, map.get(sums) > 0 ? map.get(sums) + 1 : 1)
      }
    }
    for (let i = 0; i < nums3.length; i++) {
      for (let j = 0; j < nums4.length; j++) {
        const rest = 0 - nums3[i] - nums4[j]
        if (map.get(rest) > 0) {
          result += map.get(rest)
        }
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n^2)
  - 空间复杂度：O(n)


## 383. 赎金信

### 详情

[代码随想录讲解](https://programmercarl.com/0383.%E8%B5%8E%E9%87%91%E4%BF%A1.html)

[题目链接](https://leetcode.cn/problems/ransom-note/description/)

### 解法

#### Map 数据结构

- 代码：

  ```js
  const canConstruct = function(ransomNote, magazine) {
      const map = new Map()
      for (let i = 0; i < ransomNote.length; i++) {
          const item = ransomNote[i]
          map.set(item, map.get(item) > 0 ? map.get(item) + 1 : 1)
      }
      for (let j = 0; j < magazine.length; j++) {
          const item = magazine[j]
          if (map.get(item) > 1) {
              map.set(item, map.get(item) - 1)
          } else if (map.get(item) === 1) {
              map.delete(item)
          }
      }
      return !map.size
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 15. 三数之和

### 详情

[代码随想录讲解](https://programmercarl.com/0015.%E4%B8%89%E6%95%B0%E4%B9%8B%E5%92%8C.html)

[题目链接](https://leetcode.cn/problems/3sum/description/)

### 解法

####

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
