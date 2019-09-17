### 原题
给你一个字符串 text，你需要使用 text 中的字母来拼凑尽可能多的单词 "balloon"（气球）。

字符串 text 中的每个字母最多只能被使用一次。请你返回最多可以拼凑出多少个单词 "balloon"。

<br/>
示例 1：

输入：text = "nlaebolko"

输出：1

<br/>
示例 2：

输入：text = "loonbalxballpoon"

输出：2

<br/>
示例 3：

输入：text = "leetcode"
输出：0
 

提示：

1 <= text.length <= 10^4

text 全部由小写英文字母组成

来源：力扣（LeetCode）

链接：https://leetcode-cn.com/problems/maximum-number-of-balloons

#### 方法一 ($)
**思路**
1. 创建一个flagMap记录关键词的每个字母出现次数
2. 创建textMap记录text中各字母出现次数
3. 遍历flagMap 得到在text中出现flag对应字母的倍数之后返回最少出现的次数;

**JavaScript代码**
```PowerShell
var maxNumberOfBalloons1 = function (text) {
    const flag = "balloon";
    let textMap = {};
    let flagMap = {};
    let minN = Infinity;
    for (let j of flag) {
        if (!flagMap[j]) {
            flagMap[j] = 0;
        }
        flagMap[j]++;
    }
    for (let i of text) {
        if (!textMap[i]) {
            textMap[i] = 0;
        }
        textMap[i]++;
    }
    for (let key in flagMap) {
        minN = Math.min(Math.floor((textMap[key] || 0) / flagMap[key]), minN);
    }
    return minN;
};
```
#### 方法二
**思路**

直接遍历记录text中各字母出现的次数后取最小数

该方法不太灵活 如需改动指定单词比较麻烦

**JavaScript代码**
```PowerShell
var maxNumberOfBalloons2 = function (text) {
    const map = {};
    for (let i of text) {
        if (!map[i]) {
            map[i] = 0;
        }
        map[i]++;
    }
    return Math.min(map['b'], map['a'], Math.floor(map['l'] / 2), Math.floor(map['o'] / 2), map['n']) || 0;
};
```
### 说明
由于本人是做前端开发的

刷题大多都是以js为主 且题解只是个人或参考他人的解题思路并不代表最优解   

如有问题或更好的方案欢迎提出

[github地址](https://github.com/wisenchen/ac/blob/master/leetcode/leetcode%20217.%20%E5%AD%98%E5%9C%A8%E9%87%8D%E5%A4%8D%E5%85%83%E7%B4%A0.md)