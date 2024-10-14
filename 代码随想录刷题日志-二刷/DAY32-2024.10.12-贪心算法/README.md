## 122. 买卖股票的最佳时机 II

### 详情

[代码随想录讲解](https://programmercarl.com/0122.%E4%B9%B0%E5%8D%96%E8%82%A1%E7%A5%A8%E7%9A%84%E6%9C%80%E4%BD%B3%E6%97%B6%E6%9C%BAII.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-ii/description/)

### 解法

#### 贪心

- 代码：

  ```js
  const maxProfit = function(prices, result = 0) {
    const sales = []
    // 使用最频繁的交易，当天买，第二天卖，计算每天的收益
    for (let i = 0; i < prices.length - 1; i++) {
      sales.push(prices[i + 1] - prices[i])
    }
    // 在收益中取所有 >0 的值，加起来就是最大收益了
    for (let j = 0; j < sales.length; j++) {
      if (sales[j] > 0) {
        result += sales[j]
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)


## 55. 跳跃游戏

### 详情

[代码随想录讲解](https://programmercarl.com/0055.%E8%B7%B3%E8%B7%83%E6%B8%B8%E6%88%8F.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/jump-game/description/)

### 解法

####

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
