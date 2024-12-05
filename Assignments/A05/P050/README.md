## **Leetcode 50: Pow(x, n)**

**Problem:**

![image](https://github.com/user-attachments/assets/c786a331-fe05-4679-be2c-0e3acea236e2)




**Test Case(s):**


![image](https://github.com/user-attachments/assets/9a565a4b-d3ea-4387-be72-fea9f142bc84)


![image](https://github.com/user-attachments/assets/990fd40a-0d71-4798-ab99-674771d95ee5)


![image](https://github.com/user-attachments/assets/e1ae37f3-a72e-4ff0-9fa8-b3b266b84586)


**Code Solution:**

```
class Solution {
public:
    double myPow(double x, int n) {
        long long power = n;
        if (power < 0) {
            x = 1 / x;
            power = -power;
        }
        double result = 1.0;
        while (power > 0) {
            if (power % 2 == 1) {
                result *= x;
            }
            x *= x;
            power /= 2;
        }
        return result;
    }
};


```
