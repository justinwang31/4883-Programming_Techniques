## **Leetcode 1281: Subtract the Product and Sum of Digits of an Integer** ##

**Problem:**


![image](https://github.com/user-attachments/assets/beefca06-a9f3-4e59-9302-df2ed70496c3)



**Test Case(s):**


![image](https://github.com/user-attachments/assets/125b80c8-11e6-4ef2-b461-820bf5d81c94)


![image](https://github.com/user-attachments/assets/c9de4120-2460-4f59-912c-ce80d2460c23)


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
