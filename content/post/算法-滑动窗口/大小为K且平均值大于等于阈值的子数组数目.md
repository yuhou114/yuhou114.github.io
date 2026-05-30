---
title: "大小为K且平均值大于等于阈值的子数组数目"
description: "本题目为 1343. 大小为 K 且平均值大于等于阈值的子数组数目"
date: 2026-05-22T23:08:52+08:00
lastmod: 2026-05-22T23:08:52+08:00
categories:
    - 算法-滑动窗口
tags:
    - 算法
draft: false
---

本题目为[1343. 大小为 K 且平均值大于等于阈值的子数组数目](https://leetcode.cn/problems/number-of-sub-arrays-of-size-k-and-average-greater-than-or-equal-to-threshold/description/)

给你一个整数数组 arr 和两个整数 k 和 threshold 。

请你返回长度为 k 且平均值大于等于 threshold 的子数组数目。

***

- 示例 1：

> 输入：arr = [2,2,2,2,5,5,5,8], k = 3, threshold = 4  
> 输出：3  
> 解释：子数组 [2,5,5],[5,5,5] 和 [5,5,8] 的平均值分别为 4，5 和 6 。其他长度为 3 的子数组的平均值都小于 4 （threshold 的值)。

- 示例 2：

> 输入：arr = [11,13,17,23,29,31,7,5,2,3], k = 3, threshold = 5  
> 输出：6  
> 解释：前 6 个长度为 3 的子数组平均值都大于 5 。注意平均值不是整数。  
 

> [!TIP]
> - 1 <= arr.length <= 10^5  
> - 1 <= arr[i] <= 10^4  
> - 1 <= k <= arr.length  
> - 0 <= threshold <= 10^4  

***

## 题解

### 核心思想

通用思路见[定长子串中元音的最大数目]({{< relref "post/算法-滑动窗口/定长子串中元音的最大数目" >}})

```java
class Solution {
    public int numOfSubarrays(int[] arr, int k, int threshold) {
        double avg = Double.MIN_VALUE;
        int total = 0;
        double sum = 0;

        for(int i = 0; i < arr.length; i++){
            sum+=arr[i];

            int left = i - k + 1;
            if(left < 0){
                continue;
            }

            avg = sum / k;

            if(avg >= threshold){
                total++;
            }

            sum-=arr[left];

        }

        return total;
    }
}
```