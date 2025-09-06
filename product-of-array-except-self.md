### C O D I N - C O P Y - P E N

## Question 🔥:
Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i]. <br>
The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.<br>
You must write an algorithm that runs in O(n) time and without using the division operation.<br>

Example 1:<br>
Input: nums = [1,2,3,4]<br>
Output: [24,12,8,6]<br>

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/product-of-array-except-self/description/)

## Time Complexity : O(N) 

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        
        int product1 = 1 ; 
        int product2 = 1 ; 
        int cnt = 0 ;
        for( int i=0 ; i<nums.size() ; i++ ){
            product1 *= nums[i] ;
            if( nums[i] == 0 ){ cnt++ ; continue ;  }
            product2 *= nums[i] ;
        }

        for( int i=0 ; i<nums.size() ; i++ ){
            if( cnt > 1 ){ nums[i] = 0 ; continue ; }
            if( cnt == 1 && nums[i]== 0 ){ nums[i] = product2 ; continue ; }
            nums[i] = product1/nums[i] ;
        }
        return nums ; 
    }
};
```
### SOLUTION PYTHON3 🔥:
```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        product1 = 1
        product2 = 1
        cnt = 0

        for x in nums:
            product1 *= x
            if x == 0:
                cnt += 1
            else:
                product2 *= x

        for i in range(len(nums)):
            if cnt > 1:
                nums[i] = 0
            elif cnt == 1 and nums[i] == 0:
                nums[i] = product2
            else:
                nums[i] = product1 // nums[i]

        return nums
```
### SOLUTION JAVA 🔥:
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int product1 = 1;
        int product2 = 1;
        int cnt = 0;

        for (int x : nums) {
            product1 *= x;
            if (x == 0) {
                cnt++;
            } else {
                product2 *= x;
            }
        }

        for (int i = 0; i < nums.length; i++) {
            if (cnt > 1) {
                nums[i] = 0;
            } else if (cnt == 1 && nums[i] == 0) {
                nums[i] = product2;
            } else {
                nums[i] = product1 / nums[i];
            }
        }
        return nums;
    }
}
```
