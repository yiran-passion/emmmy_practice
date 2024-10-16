## 151. 反转字符串中的单词

### 详情

[代码随想录讲解](https://programmercarl.com/0151.%E7%BF%BB%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2%E9%87%8C%E7%9A%84%E5%8D%95%E8%AF%8D.html)

[题目链接](https://leetcode.cn/problems/reverse-words-in-a-string/description/)

### 解法

####

- 代码：

  ```js
  const reverseWords = function(s) {
    let array = [], word = ''
    // 将字符串中的单词提取到数组中
    for (let i = 0; i < s.length; i++) {
      if (s[i] !== ' ') {
        word += s[i]
      }
      if ((s[i] === ' ' || i === s.length - 1) && word !== '') {
        array.unshift(word)
        word = ''
      }
    }
    return array.join(' ')
  };
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
