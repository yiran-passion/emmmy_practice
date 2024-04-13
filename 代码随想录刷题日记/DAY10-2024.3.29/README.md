## 232. 用栈实现队列

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/implement-queue-using-stacks/description/)

### 解法

#### 一、两个栈实现

- 思路：

  1. 栈是**后进先出**，队列是**先进先出**
  2. 用两个栈去模拟队列，入栈 inStack，出栈 outStack

- 代码：

  ```js
  var MyQueue = function() {
      this.inStack = []
      this.outStack = []
  };

  /** 
  * @param {number} x
  * @return {void}
  */
  MyQueue.prototype.push = function(x) {
      this.inStack.push(x)
  };

  /**
  * @return {number}
  */
  MyQueue.prototype.pop = function() {
      if (!this.outStack.length) {
          while (this.inStack.length) {
              this.outStack.push(this.inStack.pop())
          }
      }
      return this.outStack.pop()
  };

  /**
  * @return {number}
  */
  MyQueue.prototype.peek = function() {
      if (!this.outStack.length) {
          while (this.inStack.length) {
              this.outStack.push(this.inStack.pop())
          }
      }
      return this.outStack[this.outStack.length - 1]
  };

  /**
  * @return {boolean}
  */
  MyQueue.prototype.empty = function() {
      return !this.inStack.length && !this.outStack.length
  };
  ```

## 225. 用队列实现栈

### 详情

[代码随想录链接]()

[Leetcode 题目链接](https://leetcode.cn/problems/implement-stack-using-queues/)

### 解法

#### 一、一个队列实现

- 思路：

- 代码：

  ```js
  var MyStack = function() {
      this.queue = []
  };

  /** 
  * @param {number} x
  * @return {void}
  */
  MyStack.prototype.push = function(x) {
      this.queue.push(x)
  };

  /**
  * @return {number}
  */
  MyStack.prototype.pop = function() {
      for (let i = 0; i < this.queue.length - 1; i++) {
          this.queue.push(this.queue.shift())
      }
      return this.queue.shift()
  };

  /**
  * @return {number}
  */
  MyStack.prototype.top = function() {
      for (let i = 0; i < this.queue.length - 1; i++) {
          this.queue.push(this.queue.shift())
      }
      const top = this.queue.shift()
      this.queue.push(top)
      return top
  };

  /**
  * @return {boolean}
  */
  MyStack.prototype.empty = function() {
      return !this.queue.length
  };
  ```
