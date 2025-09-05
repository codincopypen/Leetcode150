### C O D I N - C O P Y - P E N

## Question 🔥:
Implement the RandomizedSet class:<br>

RandomizedSet() Initializes the RandomizedSet object.<br>
bool insert(int val) Inserts an item val into the set if not present. Returns true if the item was not present, false otherwise.<br>
bool remove(int val) Removes an item val from the set if present. Returns true if the item was present, false otherwise.<br>
int getRandom() Returns a random element from the current set of elements (it's guaranteed that at least one element exists when this method is called).<br>
Each element must have the same probability of being returned.<br>
You must implement the functions of the class such that each function works in average O(1) time complexity.<br>


🔗 [Click to show Question in Leetcode](https://leetcode.com/problems/insert-delete-getrandom-o1/description/)

## Average Time Complexity : O(1) 

### SOLUTION IN C++ 🔥:
```cpp
class RandomizedSet {
    private:
    unordered_map<int,int> mp  ; 
    vector<int> v ; 
    int i = 0 ; 
public:
    RandomizedSet() {
        srand(time(0));
    }
    
    bool insert(int val) {
        if( mp.count(val) == 0 ){
            mp[val] = i ; 
            v.push_back(val) ;
            i++ ;
            return true ; 
        }
        return false ; 
    }
    
    bool remove(int val) {
        if( mp.count(val) > 0 ){
            if( v[i-1]==val ){
                v.pop_back() ;
                i-- ;
                mp.erase(val) ;
                return true ; 
            }
            int idx = mp[val];
            int num = v[i-1] ;
            swap( v[idx] , v[i-1] ) ;
            v.pop_back() ;
            mp.erase(val) ;
            i-- ; 
            mp[num] = idx ; 
            return true ; 
        }
        return false ; 
    }
    
    int getRandom() {
        
        int randomNum = rand() % (i);
        return v[randomNum] ;
    }
};
```

### SOLUTION JAVA 🔥:
```java
import java.util.*;

class RandomizedSet {
    private Map<Integer, Integer> mp;
    private List<Integer> v;
    private Random rand;

    public RandomizedSet() {
        mp = new HashMap<>();
        v = new ArrayList<>();
        rand = new Random();
    }
    
    public boolean insert(int val) {
        if (!mp.containsKey(val)) {
            mp.put(val, v.size());
            v.add(val);
            return true;
        }
        return false;
    }
    
    public boolean remove(int val) {
        if (mp.containsKey(val)) {
            int idx = mp.get(val);
            int last = v.get(v.size() - 1);

            // swap val with last element
            v.set(idx, last);
            mp.put(last, idx);

            // remove last element
            v.remove(v.size() - 1);
            mp.remove(val);

            return true;
        }
        return false;
    }
    
    public int getRandom() {
        int randomIndex = rand.nextInt(v.size());
        return v.get(randomIndex);
    }
}
```


### SOLUTION PYTHON3 🔥:
```python
import random

class RandomizedSet:

    def __init__(self):
        self.mp = {}   # maps val -> index
        self.v = []    # stores values

    def insert(self, val: int) -> bool:
        if val not in self.mp:
            self.mp[val] = len(self.v)
            self.v.append(val)
            return True
        return False

    def remove(self, val: int) -> bool:
        if val in self.mp:
            idx = self.mp[val]
            last = self.v[-1]

            # swap val with last element
            self.v[idx] = last
            self.mp[last] = idx

            # remove last element
            self.v.pop()
            del self.mp[val]

            return True
        return False

    def getRandom(self) -> int:
        return random.choice(self.v)
```
