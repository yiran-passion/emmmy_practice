## 24. 两两交换链表中的节点

### 详情

[代码随想录链接]()

[题目链接](https://programmercarl.com/0024.%E4%B8%A4%E4%B8%A4%E4%BA%A4%E6%8D%A2%E9%93%BE%E8%A1%A8%E4%B8%AD%E7%9A%84%E8%8A%82%E7%82%B9.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

### 解法

#### 常规解法

- 思路：

- 代码：

```js
var swapPairs = (head) => {
    if (!head) return head
    let result = new ListNode(null, head), sup  = result
    while (sup.next && sup.next.next) {
        const prev = sup.next.next, current = sup.next
        current.next = prev.next
        prev.next = current
        sup.next = prev
        sup = current
    }
    return result.next
}
```