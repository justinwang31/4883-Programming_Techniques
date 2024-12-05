## **Leetcode 794: Valid Tic-Tac-Toe State**

**Problem:**


![image](https://github.com/user-attachments/assets/1957984b-d456-420b-9837-27d83247e31d)




**Test Case(s):**

![image](https://github.com/user-attachments/assets/29beaa01-1a1b-4caf-9ed4-13683027c9f3)


![image](https://github.com/user-attachments/assets/2d67afdf-0fd5-4233-b601-54a32481b094)


![image](https://github.com/user-attachments/assets/addf39ed-50dd-4378-b28e-43a6fbd8d319)


**Code Solution:**

```
class Solution {
public:
    bool validTicTacToe(vector<string>& board) {
        int countX = 0, countO = 0;
        for (const string& row : board) {
            for (char c : row) {
                if (c == 'X')
                    countX++;
                else if (c == 'O')
                    countO++;
            }
        }

        if (!(countX == countO || countX == countO + 1)) {
            return false;
        }
        bool xWin = checkWin(board, 'X');
        bool oWin = checkWin(board, 'O');

        if (xWin && oWin)
            return false;

        if (xWin && countX != countO + 1)
            return false;

        if (oWin && countX != countO)
            return false;

        return true;
    }

private:
    bool checkWin(vector<string>& board, char player) {

        for (int i = 0; i < 3; i++) {
            if ((board[i][0] == player && board[i][1] == player &&
                 board[i][2] == player) ||
                (board[0][i] == player && board[1][i] == player &&
                 board[2][i] == player)) {
                return true;
            }
        }

        if ((board[0][0] == player && board[1][1] == player &&
             board[2][2] == player) ||
            (board[0][2] == player && board[1][1] == player &&
             board[2][0] == player)) {
            return true;
        }
        return false;
    }
};

```
