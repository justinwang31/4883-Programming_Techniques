## **Leetcode 69: Sqrt(x)**

**Problem:**


![image](https://github.com/user-attachments/assets/beefca06-a9f3-4e59-9302-df2ed70496c3)



**Test Case(s):**


![image](https://github.com/user-attachments/assets/25f7a694-4967-4e66-9f22-030bc9af3a17)




**Code Solution:**

```
class Solution {
public:
    int subtractProductAndSum(int n) {
        int sumDigits = 0, productDigits = 1;

        while (n > 0) {
            int digit = n % 10;
            sumDigits += digit;
            productDigits *= digit;
            n /= 10;
        }

        return productDigits - sumDigits;
    }
};



```
