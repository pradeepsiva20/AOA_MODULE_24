# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Start by reading the n x n grid where each cell can be 0 (empty), 1 (cherry), or -1 (thorn that blocks movement).
2. Use Dynamic Programming (DP) to simulate both trips (forward and return) by treating them as two people starting from (0, 0) and moving to (n-1, n-1) 
   simultaneously, using a 3D DP table dp[x1][y1][x2] to track maximum cherries collected by two paths.
3. Define state transitions where both people can only move right or down, and ensure that the current cell is valid (not -1).
4. At each step, collect cherries from both positions if they are different, and avoid double-counting if they are the same. Update the DP table with the maximum 
   cherries collected so far. 
5. Return the maximum cherries collected by reaching (n-1, n-1) and coming back to (0, 0), or return 0 if no valid path exists.   

## Program:
```
/*
To implement the program for Cherry pickup problem.
Developed by: PRADEEP S
Register Number: 212222100034

*/
```
```
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        #############    Add your code here  ############### 
        dp = [[0]*n for _ in range(n)]
        for i in range(n-1,-1,-1):
            for j in range(n-1, -1, -1):
                if i==n-1 and j==n-1:
                    dp[i][j] = grid[i][j]
                elif i==n-1:
                    dp[i][j] = grid[i][j]+dp[i][j+1]
                elif j==n-1:
                    dp[i][j] = grid[i][j]+dp[i+1][j]
                else:
                    dp[i][j] = grid[i][j]+max(dp[i][j+1], dp[i+1][j])

        return max(0,dp[0][0])+1
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output:

![image](https://github.com/user-attachments/assets/ea16cb07-12e2-47a4-a3b6-e0698ff31f7b)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
