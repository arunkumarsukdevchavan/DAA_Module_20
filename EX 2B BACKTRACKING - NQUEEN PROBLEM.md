# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start with an empty chessboard of size N×N, where initially no queens are placed.
2. Place a queen in the current row: For each column in the current row: Check if placing the queen at that (row, column) position is safe (no other queen in the same column, upper left diagonal, or upper right diagonal).
3. If the placement is safe: Place the queen at that position. Recursively attempt to place the next queen in the next row.
4. If placing a queen in any column of the current row is not possible: Backtrack by removing the previously placed queen and trying a new position.
5. Continue this process until either: All queens are placed successfully (solution found), Or all possibilities are exhausted (no solution exists).  

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: ARUN KUMAR SUKDEV CHAVAN
Register Number: 212222230013
*/
```
```
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if(col>=N):
        return True
    for i in range(N):
        if isSafe(board, i, col):
            board[i][col]=1
            if solveNQUtil(board, col+1)==True:
                return True
            board[i][col]=0
    return False
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```
## Output:
![image](https://github.com/user-attachments/assets/d0545e4e-190d-4c3e-9091-7f5c9d5402e0)

## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
