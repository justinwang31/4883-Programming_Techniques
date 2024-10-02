Leetcode 125 - Valid Palindrome

Problem:


![image](https://github.com/user-attachments/assets/e2dfb445-d8f0-44b8-8c27-3358d829174f)


Code solution: 



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

