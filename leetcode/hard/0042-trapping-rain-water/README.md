# Trapping Rain Water

![Difficulty](https://img.shields.io/badge/Difficulty-Hard-red)

## Problem

Given `n` non-negative integers representing an elevation map where the width of each bar is `1`, compute how much water it can trap after raining.

 

 **Example 1:** 

```
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.

```

 **Example 2:** 

```
Input: height = [4,2,0,3,2,5]
Output: 9

```

 

 **Constraints:** 

- n == height.length
- 1 <= n <= 2 * 104
- 0 <= height[i] <= 105

## Solution

**Language:** Python  
**Runtime:** 7 ms (beats 72.05%)  
**Memory:** 21.4 MB (beats 9.89%)  
**Submitted:** 2026-11-12T16:10:22.710Z  

```py
class Solution:
    def trap(self, height: list[int]) -> int:
        lmax = 0
        rmax = 0
        total = 0
        l = 0
        r = len(height) - 1
        
        while l <= r:
            if height[l] <= height[r]:
                if height[l] > lmax:
                    lmax = height[l]
                else: 
                    total += lmax - height[l]
                l = l + 1
            else :
                if rmax > height[r]:
                    total += rmax - height[r]
                else :
                    rmax = height[r]
                r = r - 1
        return total






        
         
        
```

---

[View on LeetCode](https://leetcode.com/problems/trapping-rain-water/)