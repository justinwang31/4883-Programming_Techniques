## **Leetcode 367: Valid Perfect Square**

**Problem:**


![image](https://github.com/user-attachments/assets/4cf1abf1-4617-4dec-99a9-6cf08cc1a94a)




**Test Case(s):**


![image](https://github.com/user-attachments/assets/c837080a-c864-4360-a90b-bcc1fa970f3f)


![image](https://github.com/user-attachments/assets/65c77225-ba10-41df-9c76-0f1820f77441)




**Code Solution:**

```
class Solution {
public:
    bool isPerfectSquare(int num) {
        int root = sqrt(num);

        if (root * root == num) {
            return true;
        } else {
            return false;
        }
    }
};
```

