## 344. 反转字符串

### 详情

[代码随想录讲解](https://programmercarl.com/0344.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.html)

[题目链接](https://leetcode.cn/problems/reverse-string/description/)

### 解法

#### 双指针法

- 代码：

  ```js
  const reverseString = function(s) {
    let left = 0, right = s.length - 1
    while (left < right) {
      let sup = s[left]
      s[left] = s[right]
      s[right] = sup
      left ++
      right --
    } 
    return s
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)


## 541. 反转字符串 II

### 详情

[代码随想录讲解](https://programmercarl.com/0541.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2II.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/reverse-string-ii/description/)

### 解法

#### 双指针法

- 代码：

  ```js
  const reverseStr = function(s, k, result = '') {
    let array = s.split('')
    for (let i = 0; i < array.length; i += 2 * k) {
      let left = i, right = i + k - 1
      while (left < right) {
        [array[left], array[right]] = [array[right], array[left]]
        left ++
        right --
      }
    }
    return array.join('')
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
