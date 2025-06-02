# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Start by reading the number of items (n), their respective values (val[]), weights (wt[]), and the maximum weight capacity of the knapsack (W).
2. Define a recursive function knapSack(W, wt, val, n) that returns the maximum value that can be obtained with n items and a remaining capacity W.
3. Base Condition: If n == 0 (no items left) or W == 0 (no capacity left), return 0.
4. Check if the weight of the current item is more than the remaining capacity W. If yes, skip the item. If not, consider two cases — include the item or exclude       it — and take the maximum value of both choices. 
5. Return the result of the recursive function, which gives the maximum total value possible within the given capacity.   

## Program:

```
/*
To implement the program for 0/1 knapsack problem.
Developed by: PRADEEP S
Register Number: 212222100034
*/
```

```python
def knapSack(W, wt, val, n):
    if n == 0 or W == 0 :
        return 0
    if (wt[n-1] > W):
        return knapSack(W, wt, val, n-1)
    else:
        return max(val[n-1] + knapSack(W-wt[n-1], wt, val, n-1), knapSack(W, wt, val, n-1))

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:

![image](https://github.com/user-attachments/assets/b682abc8-8f1c-4a18-9a3d-2b0bc582c99a)



## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
