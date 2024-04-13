## 242. 有效的字母异位词

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/valid-anagram/description/)

### 解法

#### 一、使用 Map 数据结构

- 思路：

  1. 判断 xxx 中是否包含 xxx ，这种问题可以考虑使用哈希表。

- 代码：

  ```js
  const isAnagram = (s, t) => {
    if (s.length !== t.length) return false
    // 定义一个 map 用于存储
    const map = new Map()
    // 将字符串 s 中的每一个字符存储为 map 中的 key，字符的出现次数存储为 value
    for (let i = 0; i < s.length; i++) {
        map.set(s[i], map.has(s[i]) ? map.get(s[i]) + 1 : 1 )
    }
    // 遍历字符串 t 
    for (let j = 0; j < t.length; j++) {
        // 如果 t 中存在 map 没有的字符，一定不相同
        if (!map.has(t[j])) return false
        if (map.get(t[j]) > 1) {
            // 如果 t 中的字符在 map 中，并且 map 中对应的 value(出现次数) 大于 1，次数减 1
            map.set(t[j], map.get(t[j]) - 1)
        } else {
            // 次数等于 1，直接在 map 中删除对应的键值对
            map.delete(t[j])
        }
    }
    // 最后判断，如果 map 没有剩余的键值对，则代表 s 与 t 互为异位词；否则不是互为异位词
    return !map.size
  }
  ```

## 349. 两个数组的交集

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/intersection-of-two-arrays/)

### 解法

#### 一、使用 Set 数据结构

- 代码：

  ```js
  const intersection = (nums1, nums2) => {
      const set = new Set(nums1)
      const result = new Set()
      for (let i = 0; i < nums2.length; i++) {
          if (set.has(nums2[i])) {
            result.add(nums2[i])
          }
      }
      return Array.from(result)
  }
  ```

## 202. 快乐数

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/happy-number/description/)

### 解法

#### 一、使用 Set 数据结构

- 代码：

  ```js
  const isHappy = (n) => {
    const sums = (number) => {
        let result = 0
        while (number) {
            result += (number % 10) * (number % 10)
            number = Math.floor(number / 10)
        }
        return result
    }
    const set = new Set()
    while (true) {
        n = sums(n)
        if (n === 1) return true 
        if (set.has(n)) return false
        set.add(n)
    }
  }
  ```

## 1. 两数之和

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/two-sum/description/)

### 解法

#### 一、使用 Set 数据结构

- 代码：

  ```js
  const intersection = (nums1, nums2) => {
      const set = new Set(nums1)
      const result = new Set()
      for (let i = 0; i < nums2.length; i++) {
          if (set.has(nums2[i])) {
              result.add(nums2[i])
          }
      }
      return Array.from(result)
  }
  ```
