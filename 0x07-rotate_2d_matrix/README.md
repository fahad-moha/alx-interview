```python
def rotate_matrix(matrix):
    """
    Rotates a 2D matrix 90 degrees clockwise.
    
    Args:
        matrix (list[list[int]]): The input matrix to be rotated.
    
    Returns:
        list[list[int]]: The rotated matrix.
    """
    # Get the dimensions of the matrix
    rows, cols = len(matrix), len(matrix[0])
    
    # Create a new matrix to store the rotated result
    rotated_matrix = [[0 for _ in range(rows)] for _ in range(cols)]
    
    # Perform the rotation
    for i in range(rows):
        for j in range(cols):
            rotated_matrix[j][rows - 1 - i] = matrix[i][j]
    
    return rotated_matrix
```

Here's how the `rotate_matrix()` function works:

1. We first get the dimensions of the input matrix, which are the number of rows (`rows`) and the number of columns (`cols`).
2. We create a new matrix `rotated_matrix` with the dimensions swapped (i.e., the new number of rows is the previous number of columns, and the new number of columns is the previous number of rows).
3. We iterate through the original matrix and populate the `rotated_matrix` with the values from the original matrix, but in a rotated fashion. Specifically, the new row index is the previous column index, and the new column index is the previous row index subtracted from the maximum row index (to achieve the 90-degree clockwise rotation).
4. Finally, we return the `rotated_matrix`.

Here's an example usage:

```python
original_matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

rotated_matrix = rotate_matrix(original_matrix)
print(rotated_matrix)
```

This will output the following rotated matrix:

```
[[7, 4, 1],
 [8, 5, 2],
 [9, 6, 3]]
```

The key points to understand are:

- The new row index is the previous column index (`j`).
- The new column index is the previous row index subtracted from the maximum row index (`rows - 1 - i`).
- We create a new matrix with the dimensions swapped to store the rotated result.

This solution has a time complexity of O(n^2), where n is the number of rows (or columns) in the input matrix, as we need to iterate through all the elements in the matrix.