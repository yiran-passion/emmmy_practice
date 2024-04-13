## 203.移除链表元素

### 详情

[代码随想录链接](https://programmercarl.com/0203.%E7%A7%BB%E9%99%A4%E9%93%BE%E8%A1%A8%E5%85%83%E7%B4%A0.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[Leetcode 题目链接]()

### 解法

#### 一、常规解法

- 思路：创建一个用于“遍历”链表的辅助链表，操作辅助链表，在辅助链表上进行元素删除。

- 代码：

```js
const removeElements = (head, val) => {
    if (!head) return head
    let result = new ListNode(null, head)
    let sup = result
    while (sup.next) {
        if (sup.next.val === val) {
            sup.next = sup.next.next
        } else {
            sup = sup.next
        }
    }
    return result.next
}
```

## 707.设计链表


## 206.反转链表

### 详情

[代码随想录链接](https://programmercarl.com/0206.%E7%BF%BB%E8%BD%AC%E9%93%BE%E8%A1%A8.html)

[Leetcode 题目链接]()

### 解法

#### 一、常规解法

- 思路：

    1. 定义 result 用于存储结果，定义 current 用于 “遍历” 链表，定义 sup 用于在 while 中存储链表的 next 指针
    2. while 中首先用 sup 存储 next 指针，用于之后的指针移动
    3. 随后对已经遍历的节点进行进行设置
    4. 最后 current = sup 让链表的指针指向 next

- 代码：

```js
const reverseList = (head) => {
    if (!head) return null
    let result = null, current = head, sup = null
    while (current) {
        sup = current.next

        current.next = result

        result = current

        current = sup
    }
    return result
}
```
