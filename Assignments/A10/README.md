## **Leetcode 335: Self Crossing**

**Problem:**


![image](https://github.com/user-attachments/assets/ecb23d0c-3f86-4bae-8238-dc742f9f6642)




**Test Case(s):**

![image](https://github.com/user-attachments/assets/abbd5dd1-963c-4d61-8879-0bf0fa23c56f)

![image](https://github.com/user-attachments/assets/47567956-b56f-43ee-a5b0-aa15d77cfa52)

![image](https://github.com/user-attachments/assets/0c0faea3-66e5-4e76-a119-44bfa07b0ab3)

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
