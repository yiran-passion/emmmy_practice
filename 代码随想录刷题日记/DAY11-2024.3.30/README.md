## 20. 有效的括号

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/valid-parentheses/description/)

### 解法

#### 使用栈

- 思路：

- 代码：

  ```js
  const isValid = (s) => {
      let stack = new Array()
      const map = {
          '{': '}',
          '[': ']',
          '(': ')'
      }
      for (let i = 0; i < s.length; i++) {
          if (['{', '[', '('].includes(s[i])) {
              stack.push(s[i])
              continue
          }
          if (map[stack[stack.length - 1]] === s[i]) {
              stack.pop()
          } else {
              return false
          }
      }
      return !stack.length
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


#### 使用 js 的 api 神奇思路（看到 leetcode 学习到的）

- 思路：

- 代码：

  ```js
  const isValid = (s) => {
      let length = 0
      while (length !== s.length) {
          length = s.length
          s = s.replace('()', '').replace('[]', '').replace('{}', '')
      }
      return !s.length
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)

## 1047. 删除字符串中的所有相邻重复项

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/remove-all-adjacent-duplicates-in-string/description/)

### 解法

#### 使用栈

- 思路：

- 代码：

  ```js
  const removeDuplicates = (s) => {
      let stack = []
      for (let i = 0; i < s.length; i++) {
          const top = stack[stack.length - 1]
          if (s[i] !== top) {
              stack.push(s[i])
          } else {
              stack.pop()
          }
      }
      return stack.join('')
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 150. 逆波兰表达式求值

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/evaluate-reverse-polish-notation/description/)

### 解法

#### 使用栈

- 思路：

- 代码：

  ```js
  const evalRPN = (tokens) => {
      const stack = []
      const sup = ['+', '-', '*', '/']
      for (let i = 0; i < tokens.length; i++) {
          if (!sup.includes(tokens[i])) {
              stack.push(Number(tokens[i]))
              continue
          }
          console.log(stack)
          const n1 = stack.pop()
          const n2 = stack.pop()
          switch(tokens[i]) {
              case '+':
                  stack.push(n2 + n1)
                  break;
              case '-':
                  stack.push(n2 - n1)
                  break;
              case '*':
                  stack.push(n2 * n1)
                  break;
              case '/':
                  stack.push((n2 / n1 > 0) ? Math.floor(n2 / n1) : Math.ceil(n2 / n1))
                  break;
          }
      }
      return stack[0]
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
