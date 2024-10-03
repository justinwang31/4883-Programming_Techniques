**Leetcode 69: Sqrt(x)**

**Problem:**


![image](https://github.com/user-attachments/assets/d2ab6774-de0c-4aa5-9569-b36f170f62cb)



**Test Case(s):**


![image](https://github.com/user-attachments/assets/c1f5d5a0-4615-4ae4-915f-6f9776dcae55)

![image](https://github.com/user-attachments/assets/ffdf92d7-d44b-485d-8988-37659854b080)



**Code Solution:**

```
class Solution {
public:
    int mySqrt(int x) {
        if (x < 2)
            return x;

        int left = 2, right = x / 2;

        while (left <= right) {
            int mid = left + (right - left) / 2;
            long long midSquared = static_cast<long long>(mid) * mid;
            if (midSquared == x) {
                return mid;
            } else if (midSquared < x) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return right;
    }
};
```
