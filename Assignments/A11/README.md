## **Leetcode 886: Possible Bipartition**

**Problem:**


![image](https://github.com/user-attachments/assets/e60cf75f-3add-40d4-b1c8-138179a20018)




**Test Case(s):**


![image](https://github.com/user-attachments/assets/4034a8d7-9800-4dca-ab30-cac4de44d86d)



**Code Solution:**

```
class Solution {
public:
    bool possibleBipartition(int n, vector<vector<int>>& dislikes) {
        vector<vector<int>> graph(n + 1); 
        for (const auto& edge : dislikes) {
            graph[edge[0]].push_back(edge[1]);
            graph[edge[1]].push_back(edge[0]);
        }

        vector<int> color(n + 1, 0); 
        for (int i = 1; i <= n; ++i) {
            if (color[i] == 0) { 
                queue<int> q;
                q.push(i);
                color[i] = 1;

                while (!q.empty()) {
                    int current = q.front();
                    q.pop();

                    for (int neighbor : graph[current]) {
                        if (color[neighbor] == 0) {
                            color[neighbor] = -color[current];
                            q.push(neighbor);
                        } else if (color[neighbor] == color[current]) {
                            return false;
                        }
                    }
                }
            }
        }
        return true;
    }
};



```
