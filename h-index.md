### C O D I N - C O P Y - P E N

## Question 🔥:
Given an array of integers citations where citations[i] is the number of citations a researcher received for their ith paper, return the researcher's h-index.
According to the definition of h-index on Wikipedia: The h-index is defined as the maximum value of h such that the given researcher has published at least h papers that have each been cited at least h times.<br>
Example 1:

Input: citations = [3,0,6,1,5] <br>
Output: 3 <br>
Explanation: [3,0,6,1,5] means the researcher has 5 papers in total and each of them had received 3, 0, 6, 1, 5 citations respectively.
Since the researcher has 3 papers with at least 3 citations each and the remaining two with no more than 3 citations each, their h-index is 3.
<br>

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/h-index/description/)

## Time Complexity : O(N) 
## Extra Space Complexity : O(N) 

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int hIndex(vector<int>& citations) {
        
        int n = citations.size() ;

        vector<int> frequency( n+1 , 0 ) ;

        for( auto x : citations ){
            frequency[ min( x , n ) ]++;
        }

        int sum = 0 ; 
        for( int i=n ; i>=0 ; i-- ){
            sum  += frequency[i] ;
            if( sum >= i ){
                return i ; 
            }
        }
        return 0 ; 
    }
};
```

### SOLUTION JAVA 🔥:
```java
class Solution {
    public int hIndex(int[] citations) {
        int n = citations.length;
        int[] frequency = new int[n + 1];
        
        for (int x : citations) {
            frequency[Math.min(x, n)]++;
        }
        
        int total = 0;
        for (int i = n; i >= 0; i--) {
            total += frequency[i];
            if (total >= i) {
                return i;
            }
        }
        return 0;
    }
}

```

### SOLUTION PYTHON3 🔥:
````python
class Solution:
    def hIndex(self, citations: List[int]) -> int:
        n = len(citations)
        frequency = [0] * (n + 1)
        
        for x in citations:
            frequency[min(x, n)] += 1
        
        total = 0
        for i in range(n, -1, -1):
            total += frequency[i]
            if total >= i:
                return i
        return 0
```
