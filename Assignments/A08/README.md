## **Leetcode 733: Flood Fill** ##

**Problem:**


![image](https://github.com/user-attachments/assets/8dd0f7b1-cb65-49cc-adea-d91aafc5ce64)



**Test Case(s):**

![image](https://github.com/user-attachments/assets/f87509be-d178-4b61-a9f0-313b45b529ee)


![image](https://github.com/user-attachments/assets/89c2e946-c6ac-420d-a226-1843458cb3ac)



**Code Solution:**

```
class Solution {
public:
    void dfs(vector<vector<int>>& image, int x, int y, int color,
             int newColor) {

        if (x < 0 || x >= image.size() || y < 0 || y >= image[0].size() ||
            image[x][y] != color || image[x][y] == newColor) {
            return;
        }

        image[x][y] = newColor;

        dfs(image, x + 1, y, color, newColor);
        dfs(image, x - 1, y, color, newColor);
        dfs(image, x, y + 1, color, newColor);
        dfs(image, x, y - 1, color, newColor);
    }

    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc,
                                  int newColor) {
        int color = image[sr][sc];
        if (color != newColor) {
            dfs(image, sr, sc, color, newColor);
        }
        return image;
    }
};
```
