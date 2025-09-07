### C O D I N - C O P Y - P E N
📷[Instagram](https://www.instagram.com/codin_copy_pen?igsh=MW1mMDRvYWF6eDBncw==) &nbsp; &nbsp; 📽[Youtube](https://youtube.com/@codincopypen?si=CQUn3_O_Zu87QK3Q)

## Question 🔥:
There are n children standing in a line. Each child is assigned a rating value given in the integer array ratings.<br>
You are giving candies to these children subjected to the following requirements:<br>
Each child must have at least one candy.<br>
Children with a higher rating get more candies than their neighbors.<br>
Return the minimum number of candies you need to have to distribute the candies to the children.<br>

Example 1:<br>
Input: ratings = [1,0,2]<br>
Output: 5<br>
Explanation: You can allocate to the first, second and third child with 2, 1, 2 candies respectively.<br>

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/candy/description/)

## Time Complexity : O(N) 
## Space Complexity : O(1) 

### SOLUTION IN ALL LANGUAGES 👇🏻:

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int candy(vector<int>& ratings) {
        
        int peak = 0 , down = 0 , i = 1 , n = ratings.size() ;
        int sum = 1 ; 
        while( i < n ){

            while( i<n && ratings[i] == ratings[i-1] ){
                sum += 1 ; 
                i++ ;
            }
            peak = 1 ; 
            while( i<n && ratings[i] > ratings[i-1] ){
                peak++ ; 
                sum += peak ;
                i++ ;
            }
            down = 1 ; 
            while( i<n && ratings[i] < ratings[i-1] ){
                sum += down ; 
                down++;
                i++ ; 
            }
            if( down > peak ){
                sum += (down-peak) ;
            }
        }
        return sum ; 
    }
};
```
### SOLUTION IN PYTHON3 🔥:
```python
class Solution:
    def candy(self, ratings: List[int]) -> int:
        n = len(ratings)
        i = 1
        total = 1

        while i < n:
            # handle equal ratings
            while i < n and ratings[i] == ratings[i - 1]:
                total += 1
                i += 1

            # handle increasing slope
            peak = 1
            while i < n and ratings[i] > ratings[i - 1]:
                peak += 1
                total += peak
                i += 1

            # handle decreasing slope
            down = 1
            while i < n and ratings[i] < ratings[i - 1]:
                total += down
                down += 1
                i += 1

            if down > peak:
                total += (down - peak)

        return total
```
### SOLUTION IN JAVA 🔥:
```java
class Solution {
    public int candy(int[] ratings) {
        int n = ratings.length;
        int i = 1;
        int total = 1;

        while (i < n) {
            // handle equal ratings
            while (i < n && ratings[i] == ratings[i - 1]) {
                total += 1;
                i++;
            }

            // handle increasing slope
            int peak = 1;
            while (i < n && ratings[i] > ratings[i - 1]) {
                peak++;
                total += peak;
                i++;
            }

            // handle decreasing slope
            int down = 1;
            while (i < n && ratings[i] < ratings[i - 1]) {
                total += down;
                down++;
                i++;
            }

            if (down > peak) {
                total += (down - peak);
            }
        }

        return total;
    }
}
```
