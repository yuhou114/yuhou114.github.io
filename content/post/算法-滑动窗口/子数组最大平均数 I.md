---
title: "子数组最大平均数 I"
description: ""
date: 2026-05-21T11:38:06+08:00
lastmod: 2026-05-21T11:38:06+08:00
categories:
    - 
tags:
    - 
draft: false
---

给你一个由 n 个元素组成的整数数组 nums 和一个整数 k 。

请你找出平均数最大且长度为 k 的连续子数组，并输出该最大平均数。

任何误差小于 10^-5 的答案都将被视为正确答案。

 

- 示例 1：

> 输入：nums = [1,12,-5,-6,50,3], k = 4  
> 输出：12.75  
> 解释：最大平均数 (12-5-6+50)/4 = 51/4 = 12.75

- 示例 2：

> 输入：nums = [5], k = 1  
> 输出：5.00000
 

> [!TIP]
> - n == nums.length  
> - 1 <= k <= n <= 10^5  
> - -10^4 <= nums[i] <= 10^4  

## 题解

### 核心思想

我们要计算所有长度恰好为 k 的子串中，找出平均数最大且长度为 k 的连续子数组，
其实就等效于找出最大且长度为 k 的连续子数组。

暴力枚举所有子串？时间复杂度是 O(nk)，太慢了。

这是可以做到的，设一个max值与temp值，对于下图的字符串 abcx，假如我们已经计算出了子串 abc 加起来的temp值，那么从子串 abc 到子串 bcx，只需要减去（离开窗口）的字母 a ，以及添加（进入窗口）的字母 x 即可，因为中间的字母 b 和 c 都在这两个子串中。

![定长滑动窗口](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/%E7%AE%97%E6%B3%95-%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3/%E5%AD%90%E6%95%B0%E7%BB%84%E6%9C%80%E5%A4%A7%E5%B9%B3%E5%9D%87%E6%95%B0%20I/%E5%AE%9A%E9%95%BF%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3.png)

### 举例
示例 1，nums=[-4,7,-2,3,9,-1], k=3。

1. 从左到右遍历 nums。
2. 首先temp加上前 k−1=2的值，temp == 3。
3. num[2] = -2 进入窗口，此时找到了第一个长为 k 的子串，temp == 1，更新答案最大值。然后 s[0] = -4 离开窗口。
4. num[3] = 3 进入窗口，此时找到了第二个长为 k 的子串，temp == 8，更新答案最大值。然后 s[1] = 7 离开窗口。
5. num[4] = 9 进入窗口，此时找到了第三个长为 k 的子串，temp == 10，更新答案最大值。然后 s[2] = -2 离开窗口。
6. num[4] = -1 进入窗口，此时找到了第四个长为 k 的子串，temp == 11，更新答案最大值。遍历结束。

```java
class Solution {
    public double findMaxAverage(int[] nums, int k) {
        int avgg = Integer.MIN_VALUE;
        int temp = 0;
        for(int i = 0; i < nums.length; i++){
            temp += nums[i];

            int left = i - k + 1;
            if(left < 0){
                continue;
            }

            avgg = Math.max(avgg, temp);

            temp -= nums[left];
        }
        double avg = (double)avgg / k;
        return avg;
    }
}
```