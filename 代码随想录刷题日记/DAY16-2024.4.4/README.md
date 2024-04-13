## 104. 二叉树的最大深度

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/maximum-depth-of-binary-tree/description/)

### 解法

#### 层序遍历

- 思路：

  1. 使用层序遍历遍历每一个节点，每遍历一层层数 +1， 直到没有子节点

- 代码：

  ```js
  const maxDepth = (root, result = 0) => {
      if (!root) return result
      const queue = [root]
      while (queue.length) {
          const length = queue.length
          for (let i = 0; i < length; i++) {
              const treeNode = queue.shift()
              treeNode.left && queue.push(treeNode.left)
              treeNode.right && queue.push(treeNode.right)
          }
          result += 1
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 递归

- 思路：

- 代码：

  ```js
  const maxDepth = (root, result = 0) => {
      if (!root) return result
      return Math.max(maxDepth(root.left, result + 1), maxDepth(root.right, result + 1))
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 111. 二叉树的最小深度

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/minimum-depth-of-binary-tree/description/)

### 解法

#### 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 222. 完全二叉树的节点个数

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/count-complete-tree-nodes/description/)

### 解法

#### 

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
