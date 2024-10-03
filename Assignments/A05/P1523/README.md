## **Leetcode 1523 - Count Odd Numbers in an Interval Range**

**Problem :**


![image](https://github.com/user-attachments/assets/b130b20e-94de-4ec1-a580-281107ac279e)



**Test Case(s):**


![image](https://github.com/user-attachments/assets/2e3b98e5-85e9-4016-b5b4-77ad0f9f5abc)


![image](https://github.com/user-attachments/assets/bd1580de-7fc5-4aca-b827-dadfd919d9ec)




**Code solution: **


```
class Solution {
public:
    int countOdds(int low, int high) { return (high + 1) / 2 - low / 2; }
};
```

