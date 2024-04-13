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
          // 因为队列的长度会变，所以提前获取当前层的节点个数
          const length = queue.length
          // 当前层的的节点数组
          const currentLevel = []
          // 遍历当前层
          for (let i = 0; i < length; i++) {
              const node = queue.shift()
              currentLevel.push(node.val)
              node.left && queue.push(node.left)
              node.right && queue.push(node.right)
          }
          result.push(currentLevel)
      }
      return result
  }
  /** n 叉树的层序遍历 */
  const levelOrder = (root, result = []) => {
      if (!root) return result
      const queue = [root]
      while (queue.length) {
          const length = queue.length 
          // 当前层的节点数组
          const currentLevel = []
          // 遍历当前层
          for (let i = 0; i < length; i++) {
              const treeNode = queue..shift()
              if (treeNode.children) {
                  for (let j = 0; j < treeNode.children.length; j++) {
                     queue.push(treeNode.children[i])
                  }
              }
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
