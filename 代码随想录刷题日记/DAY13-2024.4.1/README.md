## 239. 滑动窗口最大值

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/sliding-window-maximum/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const maxSlidingWindow = (nums, k) => {
      const n = nums.length;
      const q = [];
      for (let i = 0; i < k; i++) {
          while (q.length && nums[i] >= nums[q[q.length - 1]]) {
              q.pop();
          }
          q.push(i);
      }

      const ans = [nums[q[0]]];
      for (let i = k; i < n; i++) {
          while (q.length && nums[i] >= nums[q[q.length - 1]]) {
              q.pop();
          }
          q.push(i);
          while (q[0] <= i - k) {
              q.shift();
          }
          ans.push(nums[q[0]]);
      }
      return ans;
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 347.前 K 个高频元素

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/top-k-frequent-elements/description/)

### 解法

####

- 思路：

- 代码：

  ```js
  const topKFrequent = (nums, k) => {
      const map = new Map();
      nums.forEach(n => {
          map.set(n, map.has(n) ? map.get(n) + 1 : 1);
      });
      // 先将 map 转化为 Array
      const list = Array.from(map).sort((a, b) => b[1] - a[1]);
      // 只取元素值
      return list.slice(0, k).map(n => n[0]);
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
