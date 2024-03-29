## 344. 反转字符串

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/reverse-string/description/)

### 解法

#### 双指针

- 思路：

- 代码：

  ```js
  const reverseString = (s) => {
      let left = 0, right = s.length - 1
      while (left < right) {
          let sup = s[left]
          s[left] = s[right]
          s[right] = sup
          left ++
          right --
      }
      return s
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)

## 541. 反转字符串 Ⅱ

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/reverse-string-ii/description/)

### 解法

#### 双指针

- 思路：

- 代码：

  ```js
  const reverseStr = (s, k) => {
      let array = s.split('')
      for (let i = 0; i < array.length; i += 2 * k) {
          let left = i, right = i + k - 1
          while (left < right) {
              [array[left], array[right]] = [array[right], array[left]]
              left++
              right--
          }
      }
      return array.join('')
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 151.翻转字符串里的单词

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/reverse-string-ii/description/)

### 解法

#### 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 卡码网：54. 替换数字

### 详情

[卡码网 题目链接]()

### 解法

#### 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 卡码网：55. 右旋转字符串

### 详情

[卡码网 题目链接]()

### 解法

#### 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
