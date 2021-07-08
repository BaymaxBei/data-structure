# data-structure
 数据结构算法整理

# 已实现
## 字符串
1. KMP
2. AC Trie

## 二叉树
1. 前序遍历、中序遍历、后序遍历
2. Morris遍历
3. 二叉搜索树

## LeetCode题目
1. 两数之和：利用字典
2. 链表反转


# 未实现
## 查找第k小（大）的数：
1. 二分法
2. bfptr
## 利用KMP：
1. 判断是否是翻转字符串
2. 判断一棵树是否是另一棵树的子树：利用先序遍历得到节点数组，利用KMP判断是否为子数组
## 查找同源异构体
利用负债表，窗口滑动查找
## 图
1. 构造经典图表示
2. 其他图表示转换为经典表示
3. 图的广度优先遍历
4. 图的深度优先遍历
5. 图的拓扑排序（有向无环图）
6. 最小生成树   Kruskal算法：利用并查集，Prim算法：先激活点，再激活边，找最小激活边，激活点，依次循环...
## 排序
1. 选择排序
2. 冒泡排序
3. 插入排序
## 二分法
1. 有序数组，是否包含元素m
2. 有序数组，找到<=m的最右位置
3. 有序数组，找到>=m的最左位置
4. 找局部最小值/相邻最小，利用数学单调性
## 异或运算
二进制运算无进位相加
满足交换律和结合律
0^N=N
N^N=0
a^b^c^d^e=a^d^b^c=... 与位置无关
1. 交换两个整数值，不申请额外变量（必须是两个不同的变量，如果是同一个变量，最后会=0）【不实用，纯装X】
    int a=甲, int b=乙
    a = a^b（甲^乙）
    b = a^b（甲^乙^乙=甲）
    a = a^b（甲^乙^甲=乙）
2. 数组中有一个数出现了奇数次，其他数都出现了偶数次
    把所有数异或起来，最后的结果就是这个奇数次出现的数
3. int a=N，求N的二进制最右一位1
    rightOne = N&(~N+1)
    举例：N=0101001000，rightOne=0000001000
4. 数组中有两个数出现了奇数次，其他数都出现了偶数次
    把所有数异或起来，得到
    eor = A^B
    rightOne = eor & (~eor+1)
    利用rightOne将数组分为两部分，一部分求&=0（P1），另一部分求&!=0（P2）
    分别对P1,P2求异或，得到A和B（可以求出一个之后利用eor^求出另一个）
5. 求一个数的二进制出现了多少个1
    先求rightOne, +1
    ^rightOne, 再求rightOne, +1
    继续直到=0

## 链表
技巧：
使用容器
快慢指针（减少空间复杂度）
1. 输入链表头结点，奇数长度返回中点，偶数长度返回上中点

2. 输入链表头结点，奇数长度返回中点，偶数长度返回下中点

3. 输入链表头结点，奇数长度返回中点前一个，偶数长度返回上中点前一个

4. 输入链表头结点，奇数长度返回中点前一个，偶数长度返回下中点前一个

5. 给定一个单链表，判断是否为回文链表
 5.1 利用栈（base)
 5.2 利用快慢指针得到中点/上中点，将中点/上中点之后的部分加入栈，从头比较(base1)
 5.3 利用快慢指针得到中点/上中点，将中点/上中点指向None，后续节点反向，从头部和尾部开始比较，当左边指向None时停止，期间有不同就返回False；判断完之后将后半部分逆序回来(optimize)

6. 将单链表按照某值划分成左边小，中间相等，右边大的形式
6.1 利用数组，将节点放进去，按照值partition，按顺序重组链表（base）
6.2 用三组头尾节点标识符（小于区域头、尾；等于区域头尾；大于区域头尾），遍历链表每个节点，小于值的放入小于区域，等于值的放入等于区域，大于值的放入大于区域，最后，将小于区域的尾连等于区域的头，等于区域的尾连大于区域的头（考虑小于区域等于区域大于区域可能为空的情形，coding注意）
7. 特殊单链表（含rand指针），复制链表，时间复杂度O(N),空间复杂度O(1)
7.1 利用hashmap，存储老新指针映射关系，利用hashmap将新节点的next指针和rand指针指向对应的新节点
7.2 不使用hashmap
copy节点：遍历节点，克隆每一个节点连在自身的后面；
连接rand：每次拿出一对老新节点，将新节点的rand指针指向老节点rand的后一个节点(clone节点)；
拆分：首先记录新节点的head，然后每次拿出一对老新节点，老指向老，新指向新，返回head
8. 
9. 约瑟夫环问题


