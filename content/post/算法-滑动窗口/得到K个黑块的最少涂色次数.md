---
title: "得到K个黑块的最少涂色次数"
description: "本题目为 2379.得到 K 个黑块的最少涂色次数"
date: 2026-05-23T11:27:47+08:00
lastmod: 2026-05-23T11:27:47+08:00
categories:
    - 
tags:
    - 
draft: false
---

本题目为[2379.得到 K 个黑块的最少涂色次数](https://leetcode.cn/problems/minimum-recolors-to-get-k-consecutive-black-blocks/description/)

给你一个长度为 n 下标从 0 开始的字符串 blocks ，blocks[i] 要么是 'W' 要么是 'B' ，表示第 i 块的颜色。字符 'W' 和 'B' 分别表示白色和黑色。

给你一个整数 k ，表示想要 连续 黑色块的数目。

每一次操作中，你可以选择一个白色块将它 涂成 黑色块。

请你返回至少出现 一次 连续 k 个黑色块的 最少 操作次数。

***

- 示例 1：

> 输入：blocks = "WBBWWBBWBW", k = 7  
> 输出：3  
> 解释：  
> 一种得到 7 个连续黑色块的方法是把第 0 ，3 和 4 个块涂成黑色。  
> 得到 blocks = "BBBBBBBWBW" 。  
> 可以证明无法用少于 3 次操作得到 7 个连续的黑块。  
> 所以我们返回 3 。  
 
- 示例 2：

> 输入：blocks = "WBWBBBW", k = 2  
> 输出：0  
> 解释：  
> 不需要任何操作，因为已经有 2 个连续的黑块。  
> 所以我们返回 0 。  
 


> [!tip]
> - n == blocks.length
> - 1 <= n <= 100
> - blocks[i] 要么是 'W' ，要么是 'B' 。
> - 1 <= k <= n

***

## 题解

### 核心思想

通用思路见[定长子串中元音的最大数目]({{< relref "post/算法-滑动窗口/定长子串中元音的最大数目" >}})

```java
class Solution {
    public int minimumRecolors(String blocks, int k) {
        int minn = Integer.MAX_VALUE;
        int temp = 0;
        char[] bb = blocks.toCharArray();
        for(int i = 0; i < bb.length; i++){
            if(bb[i] == 'W'){ //统计需要修改的白块
                temp++;
            }

            int left = i - k + 1; //在k下当前最左边的块
            if(left < 0){
                continue;
            }
            
            minn = Math.min(minn, temp); //更新最小值

            if(bb[left] == 'W'){ //移除前面的块
                temp--;
            }

        }
        return minn;
    }
}
```