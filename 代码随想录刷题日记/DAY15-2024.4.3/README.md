## 102. 二叉树的层序遍历

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/binary-tree-level-order-traversal/description/)

### 解法

#### 一、迭代法（使用队列）

- 思路：

  1. 使用队列存储每层的阶段，通过队列的 push && shift 操作获取节点 val

- 代码：

  ```js
  const levelOrder = (root, result = []) => {
      if (!root) return result
      const queue = [root]
      while (queue.length) {
          // 当前层的节点个数
          const length = queue.length
          // 用于存储当前层的节点
          const currentLevel = []
          // 遍历当前层
          for (let i = 0; i < length; i++) {
              const treeNode = queue.shift()
              currentLevel.push(treeNode.val)
              treeNode.left && queue.push(treeNode.left)
              treeNode.right && queue.push(treeNode.right)
          }
          result.push(currentLevel)
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 429. N 叉树的层序遍历

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/n-ary-tree-level-order-traversal/description/)

### 解法

#### 使用队列

- 思路：

- 代码：

  ```js
  const levelOrder = (root, result = []) => {
      if (!root) return result
      const queue = [root]
      while (queue.length) {
          // 当前层的节点个数
          const length = queue.length
          // 用于存储当前层的节点
          const currentLevel = []
          // 遍历当前层
          for (let i = 0; i < length; i++) {
              const treeNode = queue.shift()
              currentLevel.push(treeNode.val)
              treeNode.left && queue.push(treeNode.left)
              treeNode.right && queue.push(treeNode.right)
          }
          result.push(currentLevel)
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 226. 翻转二叉树

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/invert-binary-tree/description/)

### 解法

#### 一、前序遍历（递归法）

- 思路：
  
  1. 使用前序遍历，遍历所有节点
  2. 翻转每一个节点的 left && right

- 代码：

  ```js
  const invertTree = (root) => {
      if (!root) return root
      const treeLeft = root.left, treeRight = root.right
      root.left = invertTree(treeRight)
      root.right = invertTree(treeLeft)
      return root
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 层序遍历

- 思路：

- 代码：

  ```js
  const invertTree = (root) => {
      if (!root) return root
      const queue = [root]
      while (queue.length) {
          const length = queue.length
          for (let i = 0; i < length; i++) {
              let treeNode = queue.shift()
              // 翻转
              const treeNodeLeft = treeNode.left
              treeNode.left = treeNode.right
              treeNode.right = treeNodeLeft
              // 子节点
              treeNode.left && queue.push(treeNode.left)
              treeNode.right && queue.push(treeNode.right)
          }
      }
      return root
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

## 101. 对称二叉树

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/symmetric-tree/description/)

### 解法

#### 一、递归法

- 思路：

- 代码：

  ```js
  const isSymmetric = (root) => {
      if (!root) return true
      const compare = (left, right) => {
          if (left && !right) return false
          if (!left && right) return false
          if (!left && !right) return true
          if (left.val !== right.val) return false
          if (left.val === right.val) return compare(left.left, right.right) && compare(left.right, right.left)
      }
      return compare(root.left, root.right)
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)
