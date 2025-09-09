### C O D I N - C O P Y - P E N
📷[Instagram](https://www.instagram.com/codin_copy_pen?igsh=MW1mMDRvYWF6eDBncw==) &nbsp; &nbsp; 📽[Youtube](https://youtube.com/@codincopypen?si=CQUn3_O_Zu87QK3Q)

## Question 🔥:
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M. <br>

Symbol       Value  <br>
I             1  <br>
V             5 <br>
X             10 <br>
L             50<br>
C             100<br>
D             500<br>
M             1000<br>
For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.<br>

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. <br>
Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:<br>

I can be placed before V (5) and X (10) to make 4 and 9. <br>
X can be placed before L (50) and C (100) to make 40 and 90. <br>
C can be placed before D (500) and M (1000) to make 400 and 900.<br>
Given a roman numeral, convert it to an integer.<br>

Example 2:<br>

Input: s = "LVIII"<br>
Output: 58<br>
Explanation: L = 50, V= 5, III = 3.<br>


🔗 [Click to show Question in Leetocode](https://leetcode.com/problems/roman-to-integer/description/)

## Time Complexity : O(N)
## Space Complexity : O(N)

### SOLUTION IN ALL LANGUAGES 👇🏻:

### SOLUTION IN C++ 🔥:
```cpp
class Solution {
public:
    int romanToInt(string s) {
        unordered_map<char,int> mp ; 
        mp['I'] = 1 ;
        mp['V'] = 5 ;
        mp['X']= 10;
        mp['L'] = 50; 
        mp['C'] = 100 ; 
        mp['D'] = 500 ; 
        mp['M'] = 1000;

        int i = 0 ; 
        int n = s.size() ;
        int sum = 0 ; 
        while( i < n ){
            if( i < n-1 && mp[s[i]] < mp[s[i+1]] ){
                sum += mp[s[i+1]]- mp[s[i]] ;
                i += 2 ; 
                continue ; 
            }
            sum += mp[s[i]] ;
            i++ ;
        }
        return sum ; 
    }
};
```

### SOLUTION IN PYTHON3 🔥:
```python
class Solution:
    def romanToInt(self, s: str) -> int:
        mp = {
            'I': 1,
            'V': 5,
            'X': 10,
            'L': 50,
            'C': 100,
            'D': 500,
            'M': 1000
        }

        i, n, total = 0, len(s), 0

        while i < n:
            if i < n - 1 and mp[s[i]] < mp[s[i + 1]]:
                total += mp[s[i + 1]] - mp[s[i]]
                i += 2
            else:
                total += mp[s[i]]
                i += 1

        return total
```

### SOLUTION IN JAVA 🔥:
```java
import java.util.*;

class Solution {
    public int romanToInt(String s) {
        Map<Character, Integer> mp = new HashMap<>();
        mp.put('I', 1);
        mp.put('V', 5);
        mp.put('X', 10);
        mp.put('L', 50);
        mp.put('C', 100);
        mp.put('D', 500);
        mp.put('M', 1000);

        int n = s.length();
        int i = 0, total = 0;

        while (i < n) {
            if (i < n - 1 && mp.get(s.charAt(i)) < mp.get(s.charAt(i + 1))) {
                total += mp.get(s.charAt(i + 1)) - mp.get(s.charAt(i));
                i += 2;
            } else {
                total += mp.get(s.charAt(i));
                i++;
            }
        }

        return total;
    }
}
```

