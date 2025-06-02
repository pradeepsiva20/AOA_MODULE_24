# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1.Start by defining the number of cities V and input the cost/distance matrix graph[][] representing the distances between each pair of cities.
2. Initialize a list vertex[] to hold all cities except the starting city s.
3. Generate all permutations of the vertex[] list to consider every possible order of visiting the remaining cities.
4. Calculate the cost of each path by summing up the distances between consecutive cities in the permutation and finally adding the return path to the starting 
   city. 
5. Compare and store the minimum cost found across all permutations and return it as the result.
   

## Program:
```
/*
To implement the program for TSP.
Developed by: PRADEEP S
Register Number: 212222100034
*/
```
```
from sys import maxsize
from itertools import permutations
V = 4
def travellingSalesmanProblem(graph, s):
    vertex =[]
    for i in range(V):
        if i !=s:
            vertex.append(i)
    min_path = maxsize
    next_permutation = permutations(vertex)
    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)
        
    return min_path
    

if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:

![image](https://github.com/user-attachments/assets/1976711d-382e-4869-93ef-3fe76b27d15d)


## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
