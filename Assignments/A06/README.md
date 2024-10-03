## **Leetcode 692: Top K Frequent Words**

**Problem:**


![image](https://github.com/user-attachments/assets/5f5faa8e-f066-4dfb-be5b-bd9a337cb8ca)


**Test Case(s):**


![image](https://github.com/user-attachments/assets/ac4ecb54-78c7-4fac-a850-e8056ddf148f)

![image](https://github.com/user-attachments/assets/c1571bfe-d2d6-4074-8b9b-a1abeb1b6290)



**Code Solution:**

```
#include <algorithm>
#include <string>
#include <unordered_map>
#include <vector>

class Solution {
public:
    vector<string> topKFrequent(vector<string>& words, int k) {
        unordered_map<string, int> count;
        for (const string& word : words) {
            count[word]++;
        }

        vector<string> sortedWords;
        for (const auto& entry : count) {
            sortedWords.push_back(entry.first);
        }

        sort(sortedWords.begin(), sortedWords.end(),
             [&](const string& a, const string& b) {
                 if (count[a] == count[b]) {
                     return a < b;
                 }
                 return count[a] > count[b];
             });

        return vector<string>(sortedWords.begin(), sortedWords.begin() + k);
    }
};

```










