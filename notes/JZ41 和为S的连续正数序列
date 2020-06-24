# JZ41 和为S的连续正数序列
## 题目描述
> 小明很喜欢数学,有一天他在做数学作业时,要求计算出9~16的和,他马上就写出了正确答案是100。  
> 但是他并不满足于此,他在想究竟有多少种连续的正数序列的和为100(至少包括两个数)。没多久,他就得到另一组连续正数和为100的序列:18,19,20,21,22。  
> 现在把问题交给你,你能不能也很快的找出所有和为S的连续正数序列? Good Luck!

## 解题思路
思路1：使用一个队列作为滑动窗口，每次循环使一个大数入队，当队列的和大于S时，将小数依次出队，并判断此时和是否为S。  

思路2：使用双指针作为滑动窗口。

## 参考代码（C++）
```C++
class Solution {
public:
    vector<vector<int>> FindContinuousSequence(int sum) {
        vector<vector<int>> ans;
        if (sum<=2) return ans;
        vector<int> seq;
        int cur = 0;
        int i = 1;
        while (i<=(sum+1)/2){
            cur += i;
            seq.push_back(i);
            while (cur > sum){
                cur -= seq.front();
                seq.erase(seq.begin());
            }
            if (cur == sum){
                ans.push_back(seq);
            }
            ++i;
        }
        return ans;
    }
};
```
