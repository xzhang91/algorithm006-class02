# 学习笔记

## 位运算

### 指定位置的位运算

- 将 x 最右边的 n 位清零：x & (~0 << n)
- 获取 x 的第 n 位值（0 或者 1）： (x >> n) & 1
- 获取 x 的第 n 位的幂值：x & (1 << (n -1))
- 仅将第 n 位置为 1：x | (1 << n)
- 仅将第 n 位置为 0：x & (~ (1 << n))
- 将 x 最高位至第 n 位（含）清零：x & ((1 << n) - 1)
- 将第 n 位至第 0 位（含）清零：x & (~ ((1 << (n + 1)) - 1))

###  位运算要点

- 判断奇偶
 -  x % 2 == 1 —> (x & 1) == 1
 -  x % 2 == 0 —> (x & 1) == 0

- x >> 1 —> x / 2
> 即： x = x / 2; —> x = x >> 1;
> mid = (left + right) / 2; —> mid = (left + right) >> 1;

- X = X & (X-1) 清零最低位的 1
- X & -X => 得到最低位的 1
- X & ~X => 0

## 布隆过滤器

一个很长的二进制向量和一系列随机映射函数。布隆过滤器可以用于检索一个元素是否在一个集合中。

- 优点是空间效率和查询时间都远远超过一般的算法
- 缺点是有一定的误识别率和删除困难

## LRU Cache

- 两个要素： 大小 、替换策略
- Hash Table + Double LinkedList
- O(1) 查询  O(1) 修改、更新

## 排序算法

- 比较类排序
   - 通过比较来决定元素间的相对次序，由于其时间复杂度不能突破
O(nlogn)，因此也称为非线性时间比较类排序
   
- 非比较类排序
  -  不通过比较来决定元素间的相对次序，它可以突破基于比较排序的时
间下界，以线性时间运行，因此也称为线性时间非比较类排序
  
- 初级排序 - O(n^2)

   - 选择排序（Selection Sort）
      每次找最小值，然后放到待排序数组的起始位置
   - 插入排序（Insertion Sort）
      从前到后逐步构建有序序列；对于未排序数据，在已排序序列中从后
      向前扫描，找到相应位置并插入。
   - 冒泡排序（Bubble Sort）
      嵌套循环，每次查看相邻的元素如果逆序，则交换。

- 高级排序 - O(N*LogN)

   - 快速排序（Quick Sort）

      数组取标杆 pivot，将小元素放 pivot左边，大元素放右侧，然后依次
      对右边和右边的子数组继续快排；以达到整个序列有序。

   - 归并排序（Merge Sort）— 分治

      - 把长度为n的输入序列分成两个长度为n/2的子序列；
      - 对这两个子序列分别采用归并排序；
      - 将两个排序好的子序列合并成一个最终的排序序列。

   - 比较

      - 归并 和 快排 具有相似性，但步骤顺序相反
      - 归并：先排序左右子数组，然后合并两个有序子数组
      - 快排：先调配出左右子数组，然后对于左右子数组进行排序

   - 堆排序（Heap Sort） — 堆插入 O(logN)，取最大/小值 O(1)

      - 数组元素依次建立小顶堆
      - 依次取堆顶元素，并删除

- 特殊排序

   - 计数排序（Counting Sort）
   - 桶排序（Bucket Sort）
   - 基数排序（Radix Sort）
