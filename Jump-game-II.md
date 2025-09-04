### C O D I N - C O P Y - P E N

## Question 🔥:
You are given a 0-indexed array of integers nums of length n. You are initially positioned at index 0.
Each element nums[i] represents the maximum length of a forward jump from index i. In other words, if you are at index i, you can jump to any index (i + j) where:

----  0 <= j <= nums[i] and
----  i + j < n
Return the minimum number of jumps to reach index n - 1. The test cases are generated such that you can reach index n - 1.

Example :
Input: nums = [2,3,1,1,4]
Output: 2
Explanation: The minimum number of jumps to reach the last index is 2. 
Jump 1 step from index 0 to 1, then 3 steps to the last index.

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/jump-game-ii/description/)
🔗 [Solution Video Link]()

## Time Complexity : O(N) 

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int jump(vector<int>& nums) {
        
        int ci = 0 , mx = 0 , cb=0 ; 
        int steps = 0 ; 

        while( mx < nums.size()-1 ){

            while( ci <= cb ){
                mx = max( mx , (ci+nums[ci]) );
                ci++;
            }

            steps++;
            cb = mx ; 
        }

        return steps ; 
    }
};
```
### SOLUTION IN JAVA 🔥:
```java
class Solution {
    public int jump(int[] nums) {
        int ci = 0, mx = 0, cb = 0;
        int steps = 0;

        while (mx < nums.length - 1) {
            while (ci <= cb) {
                mx = Math.max(mx, ci + nums[ci]);
                ci++;
            }
            steps++;
            cb = mx;
        }

        return steps;
    }
}
```
### SOLUTION PYTHON3 🔥:
```python
from typing import List

class Solution:
    def jump(self, nums: List[int]) -> int:
        ci, mx, cb = 0, 0, 0
        steps = 0

        while mx < len(nums) - 1:
            while ci <= cb:
                mx = max(mx, ci + nums[ci])
                ci += 1
            steps += 1
            cb = mx

        return steps
```
