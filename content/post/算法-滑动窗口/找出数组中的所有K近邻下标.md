---
title: "找出数组中的所有K近邻下标"
description: ""
date: 2026-05-25T15:18:27+08:00
lastmod: 2026-05-25T15:18:27+08:00
categories:
    - 算法-滑动窗口
tags:
    - 算法
draft: false
---

本题目为[2200.找出数组中的所有 K 近邻下标](https://leetcode.cn/problems/find-all-k-distant-indices-in-an-array/description/)

给你一个下标从 0 开始的整数数组 nums 和两个整数 key 和 k 。**K 近邻下标** 是 nums 中的一个下标 i ，并满足至少存在一个下标 j 使得 |i - j| <= k 且 nums[j] == key 。

以列表形式返回按 **递增顺序** 排序的所有 K 近邻下标。

***

- 示例 1：

> 输入：nums = [3,4,9,1,3,9,5], key = 9, k = 1  
> 输出：[1,2,3,4,5,6]  
> 解释：因此，nums[2] == key 且 nums[5] == key。  
> \- 对下标 0 ，|0 - 2| > k 且 |0 - 5| > k，所以不存在 j 使得 |0 - j| <= k 且 nums[j] == key。所以 0 不是一个 K 近邻下标。  
> \- 对下标 1 ，|1 - 2| <= k 且 nums[2] == key，所以 1 是一个 K 近邻下标。  
> \- 对下标 2 ，|2 - 2| <= k 且 nums[2] == key，所以 2 是一个 K 近邻下标。  
> \- 对下标 3 ，|3 - 2| <= k 且 nums[2] == key，所以 3 是一个 K 近邻下标。  
> \- 对下标 4 ，|4 - 5| <= k 且 nums[5] == key，所以 4 是一个 K 近邻下标。  
> \- 对下标 5 ，|5 - 5| <= k 且 nums[5] == key，所以 5 是一个 K 近邻下标。  
> \- 对下标 6 ，|6 - 5| <= k 且 nums[5] == key，所以 6 是一个 K 近邻下标。  
> 因此，按递增顺序返回 [1,2,3,4,5,6] 。   

- 示例 2：

> 输入：nums = [2,2,2,2,2], key = 2, k = 2  
> 输出：[0,1,2,3,4]  
> 解释：对 nums 的所有下标 i ，总存在某个下标 j 使得 |i - j| <= k 且 nums[j] == key，所以每个下标都是一个 K 近邻下标。   
> 因此，返回 [0,1,2,3,4] 。  
 

> [!tip]
> 1 <= nums.length <= 1000
> 1 <= nums[i] <= 1000
> key 是数组 nums 中的一个整数
> 1 <= k <= nums.length

***

## 题解

### 核心思想

通用思路见[定长子串中元音的最大数目]({{< relref "post/算法-滑动窗口/定长子串中元音的最大数目" >}})

本题思路主要在于能否意识到 k 与 |i - j| <= k 其实等效于 2k+1的滑窗问题，用last接收最后一次出现key的位置即可。

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<Integer> findKDistantIndices(int[] nums, int key, int k) {
        int last = - k - 1; //确保key一开始不存在
        for(int i = k - 1; i >= 0; i--){
            if(nums[i] == key){
                last = i;
                break;
            }
        }

        List<Integer> ans = new ArrayList<>();
        for(int j = 0; j < nums.length; j++){
            if(j + k < nums.length && nums[j + k] == key){
                last = j + k;
            }

            if(last >= j - k){
                ans.add(j);
            }
        }

        return ans;
    }
}
```



























































