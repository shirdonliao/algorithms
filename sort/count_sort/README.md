# 计数排序

计数排序和基数排序都是非比较类排序，过程比较简单，但是计数是比较巧妙的，借助第三个数组 `countsArr` 存元素出现的频率往后累加，对应减一即可得出该元素在排序数组中的位置。看代码更好理解。

## 排序过程

```shell
count_sort $ go run main.go
[UNSORTED]:      [1 4 2 4 6 9 8 2]
[DEBUG countsArr]:  [0 1 3 3 5 5 6 6 7 8]
[SORTED]:        [1 2 2 4 4 6 8 9]
```

## 排序效果

 <img src="http://p7f8yck57.bkt.clouddn.com/2018-06-14-100212.gif" width=400/>



## 复杂度

### 时间复杂度

对于元素个数为 n 的数组，最大值为 max，则其时间复杂度为 **O(N + max + 1)**

### 空间复杂度

借助第两个中间数组，一个长度为 n，一个长度为 max + 1，空间复杂度也为 **O(N + max + 1)**

### 稳定性

在填充排序好的数组时，每个统计的数字都会减一，保证其稳定性。可能你看到上边的 GIF 并不区分重复的两个 4，但在计数数组中是区分的（见注释）

## 使用场景

计数排序的复杂度比任何基于比较的排序都要低，不过空间开销不容忽视。