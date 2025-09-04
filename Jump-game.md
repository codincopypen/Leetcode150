### C O D I N - C O P Y - P E N 

## Question 🔥:
You are given an integer array nums. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.
Return true if you can reach the last index, or false otherwise.

Example 1:
Input: nums = [2,3,1,1,4]
Output: true

🔗 [Click here to show question in Leetcode](https://leetcode.com/problems/jump-game/description/)

### Time Complexity O(N)

## SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        
        int power = 0 ;
        int n = nums.size() ;
        for( int i=0 ; i<nums.size() ; i++ ){
            if( power >= i ){
                int newPower = nums[i] + i ;
                power = max( newPower, power ) ;
            }
            else{
                return false ;
            }
        }
        return true ; 
    }
};
```

## SOLUTION IN JAVA 🔥:
```java
class Solution {
    public boolean canJump(int[] nums) {
        int power = 0;
        int n = nums.length;

        for (int i = 0; i < n; i++) {
            if (power >= i) {
                int newPower = nums[i] + i;
                power = Math.max(newPower, power);
            } else {
                return false;
            }
        }

        return true;
    }
}
```
## SOLUTION IN PYTHON 🔥:
```python
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        power = 0
        n = len(nums)

        for i in range(n):
            if power >= i:
                newPower = nums[i] + i
                power = max(newPower, power)
            else:
                return False

        return True
```
