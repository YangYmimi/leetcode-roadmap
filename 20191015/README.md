### 问题描述

> https://leetcode-cn.com/problems/length-of-last-word/

给定一个仅包含大小写字母和空格 ' ' 的字符串，返回其最后一个单词的长度。如果不存在最后一个单词，请返回 0 。

说明：一个单词是指由字母组成，但不包含任何空格的字符串。

示例:

```
输入: "Hello World"
输出: 5
```

### 思路

* 解法一：

  JS 的话可以先转为数组，取最后一个元素，得出 length

```
var lengthOfLastWord = function(s) {
  var sArr = s.trim().split(" ");
  return sArr[sArr.length - 1].length;
}
```

* 解法二：

  尾指针找到第一个空格，从后往前很快可以找到

### Key Points

