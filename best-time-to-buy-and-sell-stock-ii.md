###  C O D I N C O P Y P E N

## Question 🔥:
You are given an integer array prices where prices[i] is the price of a given stock on the ith day.
On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.
Find and return the maximum profit you can achieve.

🔗 [Click to show the Question in Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/?envType=study-plan-v2&envId=top-interview-150)

### SOLUTION IN ALL LANGUAGES 🔥

## Time Complexity O(N)

## SOLUTION C++ 🔥:
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        
        int profit = 0 ; 

        for( int i=1 ; i<prices.size() ; i++ ){
            if( prices[i] > prices[i-1] ){
                profit += (  prices[i] - prices[i-1] ) ;
            }
        }
        return profit ; 
    }
};
```
## SOLUTION JAVA 🔥:
```java
class Solution {
    public int maxProfit(int[] prices) {
        int profit = 0;

        for (int i = 1; i < prices.length; i++) {
            if (prices[i] > prices[i-1]) {
                profit += (prices[i] - prices[i-1]);
            }
        }
        return profit;
    }
}
```

## SOLUTION PYTHON 🔥:
```python
class Solution:
    def maxProfit(self, prices: list[int]) -> int:
        profit = 0

        for i in range(1, len(prices)):
            if prices[i] > prices[i-1]:
                profit += (prices[i] - prices[i-1])
        return profit
```
