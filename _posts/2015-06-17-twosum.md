---
layout: post
category: LeetCode,Algorithms
title: Two Sum 
---

## 题目

原文：
Given an array of integers, find two numbers such that they add up to a specific target number.

The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2. Please note that your returned answers (both index1 and index2) are not zero-based.

You may assume that each input would have exactly one solution.

Input: numbers={2, 7, 11, 15}, target=9
Output: index1=1, index2=2

译文：
输入两个整数，输出一对整数使得它们的和为给定值。

##解答

{% highlight cpp %}
class Solution {
public:
    vector<int> twoSum(vector<int> &numbers, int target) {
        map<int, int> numindex;
        vector<int> ret;
        for(int i=0; i<numbers.size(); i++){
            int diff = target - numbers[i];
            if(numindex.count(diff) != 0){
                ret.push_back(numindex[diff]);
                ret.push_back(i+1);
                return ret;
            }
            numindex[numbers[i]] = i+1;
        }
    }
};
{% endhighlight %}
