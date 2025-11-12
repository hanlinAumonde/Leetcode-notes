# 题目 - 训练计划 III

## 题目描述

给定一个头节点为 head 的单链表用于记录一系列核心肌群训练编号，请将该系列训练编号 倒序 记录于链表并返回。


### 示例 1：

* `输入`：head = `[1,2,3,4,5]`
* `输出`：`[5,4,3,2,1]`


### 示例 2：

* `输入`：head = `[1,2]`
* `输出`：`[2,1]`


### 示例 3：

* `输入`：head = `[]`
* `输出`：`[]`


### 提示：

* 链表中节点的数目范围是 `[0, 5000]`
* -5000 <= `Node.val` <= 5000

## 题解

这是一个标准的链表反转问题，流程如下：

* 设置`pred`指针和`tmp`临时指针为空
* 每次循环中，临时记录下当前`head.next`，再设置`head.next`为`pred`，然后将`pred`推进至当前`head`，最后将`head`推进至前面临时记录的`head.next`

```java
class Solution {
    public ListNode trainningPlan(ListNode head) {
        ListNode pred = null , tmp = null;
        while(head != null){
            tmp = head.next;
            head.next = pred;
            pred = head;
            head = tmp;
        }
        return pred;
    }
}
```