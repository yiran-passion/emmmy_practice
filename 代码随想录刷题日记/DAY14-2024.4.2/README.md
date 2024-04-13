## 144. 二叉树的前序遍历

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/binary-tree-preorder-traversal/description/)

### 解法

#### 一、递归

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

#### 二、迭代

- 思路：

- 代码：

  ```js
  const preorderTraversal = (root, result = []) => {
      if (!root) return result
      // 使用栈因为要先遍历 left 的所有节点，然后再遍历 right 所有节点
      let stack = [root]
      while (stack.length) {
          const treeNode = stack.pop()
          result.push(treeNode.val)
          // 先 push 当前节点的 right 节点，因为栈是“先进后出”，下一次循环的时候优先 pop right 节点。
          treeNode.right && stack.push(treeNode.right)
          treeNode.left && stack.push(treeNode.left)
      }
      return result
  }
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 三、统一迭代法

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 145. 二叉树的后序遍历

### 详情

[代码随想录链接]()

[Leetcode 题目链接]()

### 解法

#### 一、递归

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

#### 二、迭代

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

#### 三、统一迭代法

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

## 94. 二叉树的中序遍历

### 详情

[代码随想录链接]()

[Leetcode 题目链接]()

### 解法

#### 一、递归

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

  - 时间复杂度：O(n)
  - 空间复杂度：O(n)

#### 二、迭代

- 思路：

- 代码：

  ```js

  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()

#### 三、统一迭代法

- 思路：

- 代码：

  ```js
  ```

- 复杂度

  - 时间复杂度：O()
  - 空间复杂度：O()
