##  203.移除链表元素  

### 解法

#### 常规解法

- 思路：创建一个用于“遍历”链表的辅助链表，操作辅助链表，在辅助链表上进行元素删除。

- 代码：

```js
const removeElements = (head, val) => {
    if (!head) return head
    let result = new ListNode(null, head)
    let sup = result
    while(sup.next) {
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

### 解法

#### 常规解法

- 思路：

- 代码：

```js
const reverseList = (head) => {
    if (!head) return null
    let result = null, current = head, sup = null
    while(current) {
        sup = current.next

        current.next = result

        result = current

        current = sup
    }
    return result
};
```
