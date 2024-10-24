## 509. 斐波那契数

### 详情

[代码随想录讲解](https://programmercarl.com/0509.%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91%E6%95%B0.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/fibonacci-number/description/)

### 解法

#### 动态规划

- 代码：

  ```js
  const fib = function(n) {
    let list = new Array(n).fill(null)
    list[0] = 0
    list[1] = 1
    for (let i = 2; i <= n; i++) {
      list[i] = list[i - 1] + list[i - 2]
    }
    return list[n]
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 70. 爬楼梯

### 详情

[代码随想录讲解](https://programmercarl.com/0070.%E7%88%AC%E6%A5%BC%E6%A2%AF.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/climbing-stairs/description/)

### 解法

#### 动态规划

- 代码：

  ```js
  const climbStairs = function(n) {
    let list = new Array(n).fill(null)
    list[0] = 1
    list[1] = 1
    for (let i = 2; i <= n; i++) {
      list[i] = list[i - 1] + list[i - 2]
    }
    return list[n]
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 746. 使用最小花费爬楼梯

### 详情

[代码随想录讲解](https://programmercarl.com/0746.%E4%BD%BF%E7%94%A8%E6%9C%80%E5%B0%8F%E8%8A%B1%E8%B4%B9%E7%88%AC%E6%A5%BC%E6%A2%AF.html)

[题目链接](https://leetcode.cn/problems/min-cost-climbing-stairs/description/)

### 解法

####

- 代码：

  ```js
  const minCostClimbingStairs = function(cost) {
    let dp = [0, 0]
    for (let i = 2; i <= cost.length; i++) {
      dp[i] = Math.min(dp[i - 1] + cost[i - 1], dp[i - 2] + cost[i - 2])
    }
    return dp[cost.length]
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
