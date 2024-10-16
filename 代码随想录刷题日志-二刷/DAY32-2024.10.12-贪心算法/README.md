## 122. 买卖股票的最佳时机 II

### 详情

[代码随想录讲解](https://programmercarl.com/0122.%E4%B9%B0%E5%8D%96%E8%82%A1%E7%A5%A8%E7%9A%84%E6%9C%80%E4%BD%B3%E6%97%B6%E6%9C%BAII.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-ii/description/)

### 解法

#### 贪心算法

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

#### 贪心算法

- 代码：

  ```js
  const canJump = function(nums) {
    let cover = 0
    // 遍历数组，查看每个位置可以跳的最大范围，检查范围是否有覆盖不到的位置
    for (let i = 0; i < nums.length; i++) {
      if (cover < i) {
        return false
      }
      cover = Math.max(cover, i + nums[i])
    }
    return true
  };
  ```

- 复杂度

  - 时间复杂度：O(1)
  - 空间复杂度：O(n)


## 45. 跳跃游戏 II

### 详情

[代码随想录讲解](https://programmercarl.com/0045.%E8%B7%B3%E8%B7%83%E6%B8%B8%E6%88%8FII.html)

[题目链接](https://leetcode.cn/problems/jump-game-ii/description/)

### 解法

#### 贪心算法

- 代码：

  ```js
  const jump = function(nums, result = 0) {
    if (nums.length === 1) return 0
    let currentStart = 0, currentEnd = nums[0], nextEnd = 0
    if (currentEnd >= nums.length - 1) return 1
    for (let i = 1; i < nums.length; i ++) {
      // 下一步结束的位置
      nextEnd = Math.max(nextEnd, i + nums[i])
      if (nextEnd >= nums.length - 1) {
        result += 2
        break
      }
      if (i === currentEnd) {
        result ++
        currentStart = currentEnd
        currentEnd = nextEnd
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)


## 1005. K 次取反后最大化的数组和

### 详情

[代码随想录讲解](https://programmercarl.com/1005.K%E6%AC%A1%E5%8F%96%E5%8F%8D%E5%90%8E%E6%9C%80%E5%A4%A7%E5%8C%96%E7%9A%84%E6%95%B0%E7%BB%84%E5%92%8C.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/maximize-sum-of-array-after-k-negations/description/)

### 解法

#### 贪心算法

- 代码：

  ```js
  const largestSumAfterKNegations = function(nums, k) {
    nums.sort((a, b) => a - b)
    let min = Infinity, count = 0
    // 首先将数组中所有值都转换为正数, 并且求和
    for (let i = 0; i < nums.length; i ++) {
      if (nums[i] < 0 && k > 1) {
        nums[i] = -nums[i]
        k --
      }
      min = Math.min(min, nums[i])
      count += nums[i]
    }
    if (k > 0) {
      // 如果剩余的 k > 0 , 根据 k 可以转换次数处理 ( 奇数次选取最小值取负，并且从之前求和中去掉该值已经加进去的部分； 偶数次表示不需要额外操作 )
      return count + (k % 2 === 0 ? 0 : - 2 * min)
    } else {
      // 如果剩余的 k < 0 , 表示不需要额外操作，直接返回 count
      return count
    }
  };
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
