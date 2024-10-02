**Leetcode 9: Palindrome Number**

**Problem:**


![image](https://github.com/user-attachments/assets/f9f4bd08-ad7b-4006-9bd4-f8b2ccd04b72)


**Test Case(s):**


![image](https://github.com/user-attachments/assets/9c898be5-f498-4d70-aa18-845b15afadea)

![image](https://github.com/user-attachments/assets/7e7b20d9-ad2e-4a55-b655-f6d5dbedca3f)

![image](https://github.com/user-attachments/assets/91352474-39af-4ebc-9286-612e0d6f33c6)


**Code Solution:**

```
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int reversedNumber = 0;
        while (x > reversedNumber) {
            reversedNumber = reversedNumber * 10 + x % 10;
            x /= 10;
        }
        return x == reversedNumber || x == reversedNumber / 10;
    }
};
```










