
## Question Link 🔥: 
🔗 [Click to show Problem in Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/?envType=study-plan-v2&envId=top-interview-150)

## Time Complexity O(N) 

# SOLUTION IN ALL LANGUAGES 🔥

### SOLUTION C++ 🔥:
```cpp
class Solution {
public:

    int maxProfit(vector<int>& prices) {
        int profit = 0 ; 
        int buy = prices[0] ;

        for( int i=1 ; i<prices.size() ; i++ ){
            profit = max( profit , (prices[i]-buy) ) ;
            if( prices[i] < buy ){
                buy = prices[i] ;
            }
        }
        return profit ; 
    }
};
```

### SOLUTION JAVA 🔥:
```java
class Solution {
    public int maxProfit(int[] prices) {
        int profit = 0;
        int buy = prices[0];

        for (int i = 1; i < prices.length; i++) {
            profit = Math.max(profit, prices[i] - buy);
            if (prices[i] < buy) {
                buy = prices[i];
            }
        }
        return profit;
    }
}
```

### SOLUTION PYTHON 🔥:
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        buy = prices[0]

        for price in prices[1:]:
            profit = max(profit, price - buy)
            if price < buy:
                buy = price
        return profit
```
