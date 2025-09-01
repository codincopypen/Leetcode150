## Question Link 🔥:

🔗 [Click to show Problem in Leetcode](https://leetcode.com/problems/rotate-array/?envType=study-plan-v2&envId=top-interview-150)


### SOLUTION C++ 🔥:

==========================================================================================
```cpp 
class Solution {
public:

    void reverse(vector<int>& nums, int left, int right) {
        while (left < right) {
            swap(nums[left], nums[right]);
            left++;
            right--;
        }
    }
    void rotate(vector<int>& nums, int k) {
        k %= nums.size();

        reverse(nums, 0, nums.size() - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.size() - 1);
    }
};
``` 
