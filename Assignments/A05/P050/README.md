## **Leetcode 50: Pow(x, n)**

**Problem:**

![image](https://github.com/user-attachments/assets/c786a331-fe05-4679-be2c-0e3acea236e2)




**Test Case(s):**



![image](https://github.com/user-attachments/assets/b40f61c3-e899-47ec-949c-58a7fdd9b746)



**Code Solution:**

```
class Solution {
public:
    double myPow(double x, int n) {
        if (n < 0) {
            x = 1 / x;
            n = -n;
        }

        double result = 1;
        while (n > 0) {
            if (n % 2 == 1) {
                result *= x;
            }
            x *= x;
            n /= 2;
        }

        return result;
    }
};

```
