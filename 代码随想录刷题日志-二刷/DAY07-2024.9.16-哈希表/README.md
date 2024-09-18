## 242. 有效的字母异位词

### 详情

[代码随想录讲解](https://programmercarl.com/0242.%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.html)

[题目链接](https://leetcode.cn/problems/valid-anagram/description/)

### 解法

#### Map 数据结构

- 代码：

  ```js
  var isAnagram = function(s, t) {
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

####

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
