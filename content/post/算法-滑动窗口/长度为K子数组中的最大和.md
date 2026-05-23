---
title: "长度为K子数组中的最大和"
description: ""
date: 2026-05-23T22:14:10+08:00
lastmod: 2026-05-23T22:14:10+08:00
categories:
    - 算法-滑动窗口
tags:
    - 算法
draft: false
---

本题目为[2461.长度为 K 子数组中的最大和](https://leetcode.cn/problems/maximum-sum-of-distinct-subarrays-with-length-k/description/)

给你一个整数数组 nums 和一个整数 k 。请你从 nums 中满足下述条件的全部子数组中找出最大子数组和： 

- 子数组的长度是 k，且  
- 子数组中的所有元素**各不相同** 。  
 
返回满足题面要求的最大子数组和。如果不存在子数组满足这些条件，返回 0 。 

**子数组**是数组中一段连续非空的元素序列。

***

- 示例 1：

> 输入：nums = [1,5,4,2,9,9,9], k = 3  
> 输出：15  
> 解释：nums 中长度为 3 的子数组是：  
> \- [1,5,4] 满足全部条件，和为 10 。  
> \- [5,4,2] 满足全部条件，和为 11 。  
> \- [4,2,9] 满足全部条件，和为 15 。  
> \- [2,9,9] 不满足全部条件，因为元素 9 出现重复。  
> \- [9,9,9] 不满足全部条件，因为元素 9 出现重复。  
> 因为 15 是满足全部条件的所有子数组中的最大子数组和，所以返回 15 。  

- 示例 2：

> 输入：nums = [4,4,4], k = 3  
> 输出：0  
> 解释：nums 中长度为 3 的子数组是：  
> \- [4,4,4] 不满足全部条件，因为元素 4 出现重复。  
> 因为不存在满足全部条件的子数组，所以返回 0 。  
 

> [!tip]  
> - 1 <= k <= nums.length <= 10^5  
> - 1 <= nums[i] <= 10^5  

***

## 题解

### 核心思想

通用思路见[定长子串中元音的最大数目]({{< relref "post/算法-滑动窗口/定长子串中元音的最大数目" >}})

本题思路见[几乎唯一子数组的最大和]({{< relref "post/算法-滑动窗口/几乎唯一子数组的最大和" >}})

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public long maximumSubarraySum(int[] nums, int k) {
        long maxx = 0;
        long temp = 0;
        Map<Integer,Integer> count = new HashMap<>();

        for(int i = 0; i < nums.length; i++){
            // 1. 进入窗口
            temp += nums[i];
            count.merge(nums[i], 1, Integer::sum);

            int left = i - k + 1;
            if(left < 0){
                continue;
            }

            // 2. 更新答案
            if(count.size() == k){
                maxx = Math.max(maxx, temp);
            }

            // 3. 离开窗口
            int out = nums[left];
            temp -= out;
            int outC = count.get(out);
            if(outC > 1){
                count.put(out, outC - 1);
            }else{
                count.remove(out);
            }
        }
        return maxx;
    }
}
```