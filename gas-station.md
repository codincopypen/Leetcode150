### C O D I N - C O P Y - P E N
📷[Instagram](https://www.instagram.com/codin_copy_pen?igsh=MW1mMDRvYWF6eDBncw==) &nbsp; &nbsp; 📽[Youtube](https://youtube.com/@codincopypen?si=CQUn3_O_Zu87QK3Q)

## Question 🔥:
There are n gas stations along a circular route, where the amount of gas at the ith station is gas[i].<br>
You have a car with an unlimited gas tank and it costs cost[i] of gas to travel from the ith station to its next (i + 1)th station. <br>
You begin the journey with an empty tank at one of the gas stations.<br>
Given two integer arrays gas and cost, return the starting gas station's index if you can travel around the circuit once in the clockwise direction, otherwise return -1. <br>
If there exists a solution, it is guaranteed to be unique.<br>

Example:<br>
Input: gas = [1,2,3,4,5], cost = [3,4,5,1,2] <br>
Output: 3 <br>
Explanation: <br>
Start at station 3 (index 3) and fill up with 4 unit of gas. Your tank = 0 + 4 = 4 <br>
Travel to station 4. Your tank = 4 - 1 + 5 = 8<br>
Travel to station 0. Your tank = 8 - 2 + 1 = 7<br>
Travel to station 1. Your tank = 7 - 3 + 2 = 6<br>
Travel to station 2. Your tank = 6 - 4 + 3 = 5<br>
Travel to station 3. The cost is 5. Your gas is just enough to travel back to station 3.<br>
Therefore, return 3 as the starting index.<br>

🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/gas-station/description/)

## Time Complexity : O(N) 

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int canCompleteCircuit(vector<int>& gas, vector<int>& cost) {
        
        int fuelrem = 0 ; 
        int start = 0 ; 
        int n = gas.size() ;

        int totalgas = 0 ; 
        int totalcost = 0 ; 
        for( int i=0 ; i<n ; i++ ){
            totalgas += gas[i] ;
            totalcost += cost[i] ;
        }

        if( totalgas < totalcost ){
            return -1 ; 
        }

        for( int i=0 ; i<n ; i++ ){
            fuelrem += gas[i]-cost[i]; 
            if( fuelrem < 0 ){
                start = i+1 ; 
                fuelrem = 0 ;
            }
        }
        return start ; 
    }
};
```
### SOLUTION PYTHON3 🔥:
```python
class Solution:
    def canCompleteCircuit(self, gas: List[int], cost: List[int]) -> int:
        n = len(gas)
        total_gas = sum(gas)
        total_cost = sum(cost)

        if total_gas < total_cost:
            return -1

        fuel_rem = 0
        start = 0
        for i in range(n):
            fuel_rem += gas[i] - cost[i]
            if fuel_rem < 0:
                start = i + 1
                fuel_rem = 0

        return start
```

### SOLUTION JAVA 🔥:
```java
class Solution {
    public int canCompleteCircuit(int[] gas, int[] cost) {
        int n = gas.length;
        int totalGas = 0, totalCost = 0;

        for (int i = 0; i < n; i++) {
            totalGas += gas[i];
            totalCost += cost[i];
        }

        if (totalGas < totalCost) {
            return -1;
        }

        int fuelRem = 0;
        int start = 0;

        for (int i = 0; i < n; i++) {
            fuelRem += gas[i] - cost[i];
            if (fuelRem < 0) {
                start = i + 1;
                fuelRem = 0;
            }
        }

        return start;
    }
}
```
