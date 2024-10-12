## 242. 有效的字母异位词

### 详情

[代码随想录讲解](https://programmercarl.com/0242.%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.html)

[题目链接](https://leetcode.cn/problems/valid-anagram/description/)

### 解法

#### Map 数据结构

- 代码：

  ```js
  const isAnagram = function(s, t) {
    // 如果两个字符串长度不同，一定不是有效的字母异位词
    if (s.length !== t.length) return false
    // 定义一个 map 用于存储字母及其出现次数
    const map = new Map()
    // 遍历一次字符串 s 用于存储字符串 s 的字母及其出现次数
    for (let i = 0, len = s.length; i < len; i++) {
      map.set(s[i], map.get(s[i]) ? map.get(s[i]) + 1 : 1)
    }
    for (let j = 0, len = t.length; j < len; j++) {
      // 如果获取到当前字母在 map 中不存在或者 key 对应的值为 0 ,表示不符合
      if (!map.get(t[j])) return false
      // 如果 map 中字母的剩余个数不为 0 , 则在 map 中将次数 -1
      map.set(t[j], map.get(t[j]) - 1)
    }
    return true
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 349. 两个数组的交集

### 详情

[代码随想录讲解](https://programmercarl.com/0349.%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86.html)

[题目链接](https://leetcode.cn/problems/intersection-of-two-arrays/)

### 解法

#### Set 数据结构

- 代码：

  ```js
  const intersection = function(nums1, nums2) {
    const set = new Set(nums1), result = new Set()
    for (let i = 0, len = nums2.length; i < len; i++) {
      if (set.has(nums2[i])) {
        result.add(nums2[i])
      }
    }
    return Array.from(result)
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 202. 快乐数

### 详情

[代码随想录讲解](https://programmercarl.com/0202.%E5%BF%AB%E4%B9%90%E6%95%B0.html#%E6%80%9D%E8%B7%AF)

[题目链接](https://leetcode.cn/problems/happy-number/description/)

### 解法

#### Set 数据结构

- 代码：

  ```js
  // 用于计算数每个位置上的数字的平方和
  const sum = (n) => {
    if (n < 10) return Math.pow(n, 2)
    return sum(Math.floor(n / 10)) + sum(n % 10)
  };

  const isHappy = (n) => {
    const set = new Set()
    while (true) {
      if (set.has(sum(n))) return false
      if (sum(n) === 1) return true
      set.add(sum(n))
      n = sum(n)
    }
    return true
  };
  ```

- 复杂度

  - 时间复杂度：O(logn)
  - 空间复杂度：O(logn)


## 1. 两数之和

### 详情

[代码随想录讲解](https://programmercarl.com/0001.%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/two-sum/description/)

### 解法

#### Map 数据结构

- 代码：

  ```js
  const twoSum = (nums, target) => {
    const map = new Map()
    for (let i = 0, len = nums.length; i < len; i++) {
      if (map.get(target - nums[i]) >= 0) {
        return [i, map.get(target - nums[i])]
      }
      map.set(nums[i], i)
    }
    return []
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
