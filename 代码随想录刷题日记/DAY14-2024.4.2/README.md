## 144. 二叉树的前序遍历

### 详情

[Leetcode 题目链接](https://leetcode.cn/problems/binary-tree-preorder-traversal/description/)

### 解法

#### 递归

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root, result = []) => {
      if (!root) return result
      result.push(root.val)
      root.left && preorderTraversal(root.left, result)
      root.right && preorderTraversal(root.right, result)
      return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 迭代

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root) => {
      let stack = [root], result = []
      if (!root) return result
      while (stack.length) {
          const treeNode = stack.pop()
          result.push(treeNode.val)
          treeNode.right && stack.push(treeNode.right)
          treeNode.left && stack.push(treeNode.left)
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 统一递归法

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 145. 二叉树的后序遍历

### 详情

[Leetcode 题目链接]()

### 解法

#### 递归

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root, result = []) => {
      if (!root) return result
      root.left && preorderTraversal(root.left, result)
      root.right && preorderTraversal(root.right, result)
      result.push(root.val)
      return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 迭代

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

#### 统一递归法

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 94. 二叉树的中序遍历

### 详情

[Leetcode 题目链接]()

### 解法

#### 递归

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root, result = []) => {
      if (!root) return result
      root.left && preorderTraversal(root.left, result)
      result.push(root.val)
      root.right && preorderTraversal(root.right, result)
      return result
  };
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

#### 迭代

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

#### 统一递归法

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root) => {
      let stack = [root], result = []
      if (!root) return result
      while (stack.length) {
          const treeNode = stack.pop()
          result.push(treeNode.val)
          treeNode.right && stack.push(treeNode.right)
          treeNode.left && stack.push(treeNode.left)
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
