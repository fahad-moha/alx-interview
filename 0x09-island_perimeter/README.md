# The problem statement is as follows:

Given a grid of 0s and 1s, where 0 represents water and 1 represents land, find the perimeter of the island(s).

The perimeter is the total number of edges in the grid that are adjacent to water.

Here's the step-by-step solution:

1. Iterate through the grid and find all the land cells (cells with value 1).
2. For each land cell, check its four neighboring cells (up, down, left, right). If a neighboring cell is water (0), increment the perimeter count by 1.
3. Return the total perimeter count.

Here's the Python code to solve this problem:

```python
def islandPerimeter(grid):
    perimeter = 0
    for i in range(len(grid)):
        for j in range(len(grid[0])):
            if grid[i][j] == 1:
                # Check the four neighboring cells
                if i == 0 or grid[i-1][j] == 0:
                    perimeter += 1
                if i == len(grid)-1 or grid[i+1][j] == 0:
                    perimeter += 1
                if j == 0 or grid[i][j-1] == 0:
                    perimeter += 1
                if j == len(grid[0])-1 or grid[i][j+1] == 0:
                    perimeter += 1
    return perimeter
```

Here's an example usage:

```python
grid = [[0,1,0,0],
        [1,1,1,0],
        [0,1,0,0],
        [1,1,0,0]]

print(islandPerimeter(grid))  # Output: 16
```

In this example, the island has a perimeter of 16 because there are 16 edges that are adjacent to water.

