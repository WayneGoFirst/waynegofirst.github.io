# JZ42 和为S的两个数字
## 题目描述
> 输入一个递增排序的数组和一个数字S，在数组中查找两个数，使得他们的和正好是S。  

> 如果有多对数字的和等于S，输出两个数的乘积最小的。

## 解题思路
使用双指针。若指针指向的数字之和大于S，则右指针左移一位；若小于S，则左指针右移一位；若等于S，判断当前指向数字的乘积是否小于前一组数字的乘积，如果是则替换。 

注意：此题若无解需要返回空数组，故最后通过判断乘积是否有改变过来确定是否有解。

## 参考代码（C++）
```C++
class Solution {
public:
    vector<int> FindNumbersWithSum(vector<int> array,int sum) {
        vector<int> ans(2, 0);
        int n = array.size();
        if (n<2) return {};
        int left = 0, right = n-1;
        int product = INT_MAX;
        while(left<right){
            if ((array[left]+array[right]) < sum) ++left;
            else if ((array[left]+array[right]) > sum) --right;
            else {
                if (array[left]*array[right] < product) {
                    ans[0] = array[left];
                    ans[1] = array[right];
                    product = array[left]*array[right];
                }
                ++left;
            }
        }
        if (product == INT_MAX) return {};
        else return ans;
    }
};
```
