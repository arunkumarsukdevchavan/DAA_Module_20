# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start with the full set and target sum.
2. Check base conditions: If the sum becomes 0, return True (subset found). If the set becomes empty and the sum is not 0, return False (no subset found).
3. Ignore elements greater than the sum: If the last element is greater than the current sum, exclude it and recursively check the remaining elements.
4. Explore two possibilities for each element: Include the current element and check if the remaining sum can be formed. Exclude the current element and check for the same sum.
5. Return True if any of the above two possibilities return True; otherwise, return False.  

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: ARUN KUMAR SUKDEV CHAVAN
Register Number: 212222230013
*/
```
```
def SubsetSum(a,i,sum,target,n):
    if(i==n):
        return sum==target 
    if(sum>target):
        return False
    if(sum==target):
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)
# Write your code here
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")
```
## Output:
![image](https://github.com/user-attachments/assets/ac9fa034-41f9-456b-89d2-ca9d5a60eefe)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
