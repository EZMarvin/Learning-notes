## ListNode
### remove dupicate
* keep one duplicate 1-1-2-2-3 -> 1-2-3
* remove duplicate 1-1-2-2-3 -> 3
    * set dummy
    * pre = dummy; cur = head;
    * cur 排重
    * 判断 pre.next = cur 来决定是否中间有重复元素

###

## Stack
### **Largest Rectangle in Histogram** <font color="Red">HARD</font>

## Queue
###

## Heap
###

## Array
### Rotate Array
* rotated array to the left or to the right
    1. use extra space
    2. 整体翻转 + 部分翻转
    3. Math 根据翻转数目 + 整体长度 -> 直接计算位置
### Ties 
* transfer words into tree 将单词拆解为字符树
* store multiple words in one tree
    * start with root
    * keep track of necxt character in list
    * May need another tag to keep track of ending or count number...

## Tree
### Valid BST
* validation of BST tree, input root
    1. divide to left and right
    2. need return isvalid from both left and right and return the min and max value 还需要分支的值范围，左边需要最大，右边需要最小

## String
###

## Matrix
###

## DP
###

## Math
###