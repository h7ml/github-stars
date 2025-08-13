---
project: algorithm-practice
stars: 6
description: 算法题解析系列文章配套源码
url: https://github.com/likaia/algorithm-practice
---

algorithm-practice
==================

算法题解析系列文章配套源码

运行说明
----

本项目代码使用`ts-node`运行，项目依赖安装完毕后，通过`ts-node xxx.ts`就可以执行（windows系统下可能需要使用`npx ts-node xxx.ts`）。

> 如果你想更进一步的了解ts-node的话，请移步我的另一篇文章：搭建一套支持TS的Node运行环境

目录说明
----

-   src
    -   lib
    -   utils
    -   ArrayRepeatedNumber.ts 数组相关操作的算法
        -   寻找数组中的重复数字
        -   二维数组中的查找
    -   StringOperate.ts 字符串相关操作的算法
        -   替换字符串中的空格
    -   LinkedListOperation.ts 链表相关操作的算法
        -   从尾到头打印链表
    -   TreeOperate.ts 树相关操作的算法
        -   重建二叉树
        -   寻找二叉树的下一个节点
        -   按层遍历二叉树-广度优先搜索的应用
        -   按层遍历树结构-广度优先搜索的应用
        -   分行从上到下打印二叉树
        -   之字形打印二叉树
        -   校验二叉树的后续遍历序列
        -   二叉树中和为某一值的路径
        -   拍平多个深层级子树
    -   StacksAndQueues.ts 栈与队列相关操作的算法
        -   用队列实现栈&用栈实现队列
    -   Fibonacci.ts 斐波那契数列的多种实现算法
        -   自下而上实现
        -   递归实现
    -   FindWhirlingArrayMinVal.ts 寻找旋转数组中的最小数字
    -   Backtracking.ts 回溯法的应用
        -   矩阵中的路径
        -   机器人的运动范围
-   DynamicProgramming 动态规划的应用
    -   剪绳子
-   BinaryOperation 二进制运算
-   IntegerPower 数值的整数次方
-   PrintMaxNumber 打印从1到最大的n位数
-   DeleteLinkedListNode 删除链表节点
    -   用O(1)的时间复杂度删除链表节点
    -   删除链表中的重复节点
-   RegExprMatch 正则表达式匹配
-   NumericalCheck 数值校验算法
-   AdjustArrayOrder 调整数组顺序算法
-   GetLinkedListNode 获取链表节点
    -   获取倒数第K个节点
    -   寻找环的入口节点
-   ReverseLinkedList 反转链表
-   MergeLinkedList 合并两个排序的链表
-   TreeSubstructure 树的子结构
-   MirrorImageOfTree 树的镜像
-   SymmetricBinaryTree 对称的二叉树
-   PrintMatrix 顺时针打印矩阵
-   StackContainingMinFunction 包含min函数的栈
-   StackPushAndPopSequence 栈的压入/弹出序列
-   DataConversion 字符串数组转树结构
-   CopyComplexLinkedList 复杂链表的复制
-   BinaryTreeToDoublyLinkedList 二叉树转双向链表
-   SerializedBinaryTree 序列化二叉树
-   ArrayOfStrings 字符串的排列
    -   字符串的所有排列
    -   字符串的所有组合
    -   正方体的构成
    -   八皇后问题
