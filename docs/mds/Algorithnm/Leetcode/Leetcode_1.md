---
title: Leetcode_1
comment: false
tags:
    - Algorithm
    - Hash
---
# 题目

## [两数之和](https://leetcode.cn/problems/two-sum/description/?envType=study-plan-v2&envId=top-100-liked)

1. 枚举所有可能的两个不同的数字之和，与 target 做比较。
2. 哈希表查询  
```cpp
    // 方法一:
    class Solution {
    public:
        vector<int> twoSum(vector<int>& nums, int target) {
            int n = nums.size();
            for(int i = 0; i < n; ++i){
                for(int j = i + 1; j < n; ++j){
                    if(nums[i] + nums[j] == target){
                        return {i, j};
                    }
                }
            }
            return {};
    
        }
    };
```

```cpp
    // 方法 2: 
    class Solution {
    public:
        vector<int> twoSum(vector<int>& nums, int target) {
            unordered_map<int, int> hashtable;
            // 依次把 (target - nums[i]) : i 键值对放入哈希表中
            // 如果当前查询到哈希表里存在 target - nums[i] 这个 key 
            // 那么就已经存爱一对数字的和为 target 了
            // 返回 {it->second, i} 即可
            for(int i = 0; i < nums.size(); ++i){
                auto it = hashtable.find(target - nums[i]);
                if(it != hashtable.end()){ 
                    return {it->second, i};
                }
                hashtable[nums[i]] = i;
            }
            // 时间复杂度 O(n), 空间复杂度 O(n), 空间换时间
            return {};
        }
    };
```

> 用到了 unordered_map 数据结构做无序哈希表。
    
## [字母异位词分组](https://leetcode.cn/problems/group-anagrams/?envType=study-plan-v2&envId=top-100-liked)

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        // 思考:  关键在于 如何判定两个字符串是字母异位词
        // sort 后为同一字符串 (思路一)
        // 26个字母中每个字母出现的次数都相同 (思路二)

        // 思路 1 : 将每个字符串排序后得到新的字符串 s
        // 把 s : pre_s 看作一个键值对, 用哈希表存起来
        // 创建一个 vector 里面存 vetcor<string>, 一个一个 push 进去就好 

        // 时间复杂度 : O (nklogk (k 为 strs 字符串的最大长度
        // sort 底层是用快速排序实现的时间复杂度为 O (nlogn)[n 为元素的个数, 这里就是字符串的长度]))
        // n 个字符串, sort n 遍, 插入一下哈希表 O(n)
        // 取大头 O(nklogk)

        // 空间复杂度 : O(nk) n 是字符串的数量, k 是 strs 中字符串的最大长度
        unordered_map<string, vector<string>> mp;
        for(auto &s : strs){
            string pre_s = s;
            sort(s.begin(), s.end());
            mp[s].push_back(pre_s);
        }
        vector<vector<string>> ans;
        for(auto &[_ , key] : mp){
            ans.push_back(key);
        }
        return ans;
    }
};
```

# 补充知识

### unordered_map<>容器

[https://deepinout.com/cpp/cpp-tutorials/g_unordered_map-in-cpp-stl.html](https://deepinout.com/cpp/cpp-tutorials/g_unordered_map-in-cpp-stl.html)

