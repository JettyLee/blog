---
layout: post
title:  "算法面试--数组&链表"
date:  2020-11-26 12:01:39 +0800 
categories: 学习笔记
tag: 算法
---


* content
{:toc}


### 数组&链表笔记
1.	
2.	

### leecode 
1#[206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/){:target="_blank"}  
>Reverse a singly linked list.<br>
<br><b>Example:</b>
<br>Input: 1->2->3->4->5->NULL
<br>Output: 5->4->3->2->1->NULL
<br>Follow up:
<br>A linked list can be reversed either iteratively or recursively. Could you implement both?

```
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func reverseList(head *ListNode) *ListNode {
    var prev ListNode
    cur:=head
	for cur != nil {
		prev.Next, cur.Next, cur = cur, prev.Next, cur.Next
	}
	return prev.Next
}
```

2#[24. Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/){:target="_blank"}

>Given a linked list, swap every two adjacent nodes and return its head.
<br>You may not modify the values in the list's nodes. Only nodes itself may be changed.<br>
<br><b>Example 1:</b>
<br>Input: head = [1,2,3,4]
<br>Output: [2,1,4,3]
<br><b>Example 2:</b>
<br>Input: head = []
<br>Output: []
<br><b>Example 3:</b>
<br>Input: head = [1]
<br>Output: [1]

```

```

3#[141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/){:target="_blank"}


>Given head, the head of a linked list, determine if the linked list has a cycle in it.
<br>There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.
<br>Return true if there is a cycle in the linked list. Otherwise, return false.<br>
<br><b>Example 1:</b>
<br>Input: head = [3,2,0,-4], pos = 1
<br>Output: true
<br>Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).
<br><b>Example 2:</b>
<br>Input: head = [1,2], pos = 0
<br>Output: true
<br>Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.
<br><b>Example 3:</b>
<br>Input: head = [1], pos = -1
<br>Output: false
<br>Explanation: There is no cycle in the linked list.
<br><br><b>Constraints:</b>
<br>The number of the nodes in the list is in the range [0, 104].
<br>-105 <= Node.val <= 105
<br>pos is -1 or a valid index in the linked-list.


```

```

4#[142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/){:target="_blank"}

>Given a linked list, return the node where the cycle begins. If there is no cycle, return null.
<br>There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.
<br>Notice that you should not modify the linked list.
<br><br><b>Example 1:</b>
<br>Input: head = [3,2,0,-4], pos = 1
<br>Output: tail connects to node index 1
<br>Explanation: There is a cycle in the linked list, where tail connects to the second node.
<br><b>Example 2:</b>
<br>Input: head = [1,2], pos = 0
<br>Output: tail connects to node index 0
<br>Explanation: There is a cycle in the linked list, where tail connects to the first node.
<br><b>Example 3:</b>
<br>Input: head = [1], pos = -1
<br>Output: no cycle
<br>Explanation: There is no cycle in the linked list.
<br><br><b>Constraints:</b>
<br>The number of the nodes in the list is in the range [0, 104].
<br>-105 <= Node.val <= 105
<br>pos is -1 or a valid index in the linked-list.

```

```

5#[25. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/){:target="_blank"}

>Given a linked list, reverse the nodes of a linked list k at a time and return its modified list.
<br>k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.
<br>Follow up:
<br>Could you solve the problem in O(1) extra memory space?
You may not alter the values in the list's nodes, only nodes itself may be changed.
<br><br><b>Example 1:</b>
<br>Input: head = [1,2,3,4,5], k = 2
<br>Output: [2,1,4,3,5]
<br><b>Example 2:</b>
<br>Input: head = [1,2,3,4,5], k = 3
<br>Output: [3,2,1,4,5]
<br><b>Example 3:</b>
<br>Input: head = [1,2,3,4,5], k = 1
<br>Output: [1,2,3,4,5]
<br><b>Example 4:</b>
<br>Input: head = [1], k = 1
<br>Output: [1]
<br><br><b>Constraints:</b>
<br>The number of nodes in the list is in the range sz.
<br>1 <= sz <= 5000
<br>0 <= Node.val <= 1000
<br>1 <= k <= sz

```

```

