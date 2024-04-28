## 509. 斐波那契数

### 详情

[代码随想录链接](https://programmercarl.com/0509.%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91%E6%95%B0.html)

[Leetcode 题目链接](https://leetcode.cn/problems/fibonacci-number/description/)

### 解法

#### 动态规划

- 思路：

  1. 找规律 f(n) = f(n - 1) + f(n - 2)
  2. 使用数组存储每一个节点的数组，方便计算

- 代码：

  ```js
  const fib = (n) => {
      const list = new Array(n).fill(0)
      // 前两条数据固定 0, 1
      list[0] = 0
      list[1] = 1
      for (let i = 2; i <= n; i++) {
          list[i] = list[i - 1] + list[i - 2]
      }
      return list[n]
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 递归

- 思路：

- 代码：

  ```js
  const fib = (n) => {
      const list = [0, 1]
      if (n < 2) return list[n]
      return fib(n - 1) + fib(n - 2)
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 70. 爬楼梯

### 详情

[代码随想录链接](https://programmercarl.com/0070.%E7%88%AC%E6%A5%BC%E6%A2%AF.html)

[Leetcode 题目链接](https://leetcode.cn/problems/climbing-stairs/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const climbStairs = (n) => {
      let results = [0, 1, 2]
      for (let i = 3; i <= n; i++) {
          results[i] = results[i - 1] + results[i - 2]
      }
      return results[n]
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
