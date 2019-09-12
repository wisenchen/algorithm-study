### 原题
给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。

<br/>

示例 1:

输入: [1,2,3,1]

输出: true

<br/>

示例 2:

输入: [1,2,3,4]

输出: false

<br/>


示例 3:

输入: [1,1,1,3,3,4,3,2,4,2]

输出: true

<br/>


来源：力扣（LeetCode）

链接：https://leetcode-cn.com/problems/contains-duplicate

#### 方法一 ($)
 **思路**
 
 使用es6 Set 去重后比较长度

**JavaScript代码**
```PowerShell
var containsDuplicate1 = function (nums) {
      return new Set(nums).size !== nums.length;
};
```
#### 方法二($)
**思路**

使用map记录已经出现的元素
**JavaScript代码**
```PowerShell
var containsDuplicate2 = function (nums) {
    let map = {};
    for (let v of nums) {
        if (map[v] === undefined) {
            map[v] = 0;
        } else {
            return true;
        }
    }
    return false;
};
```
### 说明
由于本人是做前端开发的

刷题大多都是以js为主 且题解只是个人或参考他人的解题思路并不代表最优解   

如有问题或更好的方案欢迎提出
