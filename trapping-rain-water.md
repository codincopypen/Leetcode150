### C O D I N - C O P Y - P E N
📷[Instagram](https://www.instagram.com/codin_copy_pen?igsh=MW1mMDRvYWF6eDBncw==) &nbsp; &nbsp; 📽[Youtube](https://youtube.com/@codincopypen?si=CQUn3_O_Zu87QK3Q)

## Question 🔥:
Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.<br>
<img width="529" height="223" alt="image" src="https://github.com/user-attachments/assets/d1523444-5090-48b3-985d-88c72578b125" /> <br>

Input: height = [0,1,0,2,1,0,1,3,2,1,2,1] <br>
Output: 6 <br>
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped. <br>

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/trapping-rain-water/description/)

## Time Complexity : O(N) 
## Space Complexity : O(N)

### SOLUTION IN ALL LANGUAGES 👇🏻:

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        
        int n = height.size() ;
        vector<int> right(n) ;
        vector<int> left(n) ;
        int left_max = 0 , right_max = 0 ; 
        int sum = 0 ; 

        for( int i=0 ; i<n ; i++ ){
            left[i] = left_max ;
            right[n-i-1] = right_max ; 
            left_max = max( left_max , height[i] ) ;
            right_max= max( right_max, height[n-i-1] ) ;
        }

        for( int i=0 ; i<n ; i++ ){
            int min_building = min(left[i],right[i]) ;
            if( min_building >= height[i] ){
                sum += min_building-height[i] ;
            }
        }
        return sum ; 
    }
};
```
### SOLUTION IN PYTHON3 🔥:
```python
class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)
        left = [0] * n
        right = [0] * n

        left_max, right_max = 0, 0
        total = 0

        for i in range(n):
            left[i] = left_max
            right[n - i - 1] = right_max
            left_max = max(left_max, height[i])
            right_max = max(right_max, height[n - i - 1])

        for i in range(n):
            min_building = min(left[i], right[i])
            if min_building >= height[i]:
                total += min_building - height[i]

        return total
```
### SOLUTION IN JAVA 🔥:
```java
class Solution {
    public int trap(int[] height) {
        int n = height.length;
        int[] left = new int[n];
        int[] right = new int[n];

        int leftMax = 0, rightMax = 0;
        int total = 0;

        for (int i = 0; i < n; i++) {
            left[i] = leftMax;
            right[n - i - 1] = rightMax;
            leftMax = Math.max(leftMax, height[i]);
            rightMax = Math.max(rightMax, height[n - i - 1]);
        }

        for (int i = 0; i < n; i++) {
            int minBuilding = Math.min(left[i], right[i]);
            if (minBuilding >= height[i]) {
                total += minBuilding - height[i];
            }
        }

        return total;
    }
}
```
