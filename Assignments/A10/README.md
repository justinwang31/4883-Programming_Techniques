## **Leetcode 335: Self Crossing**

**Problem:**


![image](https://github.com/user-attachments/assets/ecb23d0c-3f86-4bae-8238-dc742f9f6642)




**Test Case(s):**

![image](https://github.com/user-attachments/assets/994c71f2-4811-48da-82c8-17193e4e698e)


![image](https://github.com/user-attachments/assets/e8b4963a-9003-4bd2-9111-e2bbcc780897)



**Code Solution:**

```
class Solution {
public:
    bool isSelfCrossing(vector<int>& distance) {
        int n = distance.size();
        for (int i = 3; i < n; ++i) {
            if (distance[i] >= distance[i - 2] &&
                distance[i - 1] <= distance[i - 3]) {
                return true;
            }
            if (i >= 4 && distance[i - 1] == distance[i - 3] &&
                distance[i] + distance[i - 4] >= distance[i - 2]) {
                return true;
            }
            if (i >= 5 && distance[i - 2] >= distance[i - 4] &&
                distance[i] + distance[i - 4] >= distance[i - 2] &&
                distance[i - 1] <= distance[i - 3] &&
                distance[i - 1] + distance[i - 5] >= distance[i - 3]) {
                return true;
            }
        }
        return false;
    }
};
```
