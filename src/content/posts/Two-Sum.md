---
title: 'Two Sum'
description: ''
categories: ['算法']
pubDate: 2017-02-27 16:51:49
---

> 开始整理下自己之前在 LeetCode 上的一些题解，每天再做一些。

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,

return [0, 1].

解法：

```java
public class Solution {
    public int[] twoSum(int[] nums, int target) {
        		int[] result = new int[2];
		Map<Integer, Integer> map = new HashMap<>();
		for (int i = 0; i < nums.length; i++) {
			if (map.containsKey(target - nums[i])) {
				result[1] = i;
				result[0] = map.get(target - nums[i]);
			}
			map.put(nums[i], i);
		}
		return result;
    }
}
```
