### 问题描述

> https://leetcode-cn.com/problems/add-two-numbers/

给出两个 **非空** 的链表用来表示两个 **非负的整数**。其中，它们各自的位数是按照 **逆序** 的方式存储的，并且它们的每个节点只能存储 **一位** 数字。

如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。

您可以假设除了数字 0 之外，这两个数都不会以 0 开头。

```
输入：(2 -> 4 -> 3) + (5 -> 6 -> 4)
输出：7 -> 0 -> 8
原因：342 + 465 = 807
```

### 思路

1. 创建一个空节点，用来存储结果链表
2. 链表表头是低位开始的，所以直接从两个链表`l1`, `l2`的表头开始遍历按位计算
3. 计算有进位 `(>= 10)` 使用 `carry` 缓存
4. 分别使用 `p` 和 `q` 控制链表遍历，`x` 和 `y` 分别为当前节点的 `value`
5. 创建节点记录 `x + y` 的结果，注意 `x + y > 10` 的情况，需设置新节点的值为 `(x + y) mod 10` 并将 `carry` 赋值以更新进位
6. 更新当前节点 `p` 和 `q` 的指向直到到链表尾部
7. 返回 `next` 节点

### Key Points

* 进位不是 `0` 就是 `1`，因为每位最大 `9+9` 包括进位 `1` 则为 `19`
* 最高位计算结束之后需要检查 `carry` 是否有进位，若有，则需要增加节点
* 注意链表长度不同时候，链表为空时候的特殊情况处理