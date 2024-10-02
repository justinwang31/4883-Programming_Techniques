Leetcode 125 - Valid Palindrome

Problem + Test Case(s):


![image](https://github.com/user-attachments/assets/e2dfb445-d8f0-44b8-8c27-3358d829174f)

![image](https://github.com/user-attachments/assets/d06618a6-07e4-4041-99ab-470eeeec9dd6)

![image](https://github.com/user-attachments/assets/30939f3b-d353-4a02-8c0b-2f2ec026cf54)

![image](https://github.com/user-attachments/assets/756266cb-ae44-47cb-aff8-47e7c07a1ec5)



Code solution: 


```
#include <iostream>
#include <string>
#include <cctype>

class Solution {
public:
    bool isPalindrome(std::string s)
    {
        std::string filtered;
        for (char c : s)
        {
            if (std::isalnum(c))
            {
                filtered += std::tolower(c);
            }
        }
        int left = 0;
        int right = filtered.size() - 1;
        while (left < right)
        {
            if (filtered[left] != filtered[right])
            {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
};
```

