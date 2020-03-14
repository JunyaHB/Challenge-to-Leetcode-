## Question
Given a matrix of m x n elements (m rows, n columns), return all elements of the matrix in spiral order.

Example 1:
```
Input:
[
 [ 1, 2, 3 ],
 [ 4, 5, 6 ],
 [ 7, 8, 9 ]
]
Output: [1,2,3,6,9,8,7,4,5]
```

Example 2:
```
Input:
[
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9,10,11,12]
]
Output: [1,2,3,4,8,12,11,10,9,5,6,7]
```

## MyAnswer
```
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        if not matrix:
            return []
        start_row = 0
        end_row = len(matrix)
        start_column = 0
        end_column = len(matrix[0])
        
        result = []
        
        while (start_row < end_row and start_column < end_column):
            
            for i in range(start_column, end_column):
                result.append(matrix[start_row][i])
            start_row += 1
            
            if start_row < end_row:
                for i in range(start_row, end_row):
                    result.append(matrix[i][end_column - 1])
                end_column -= 1
            else:
                return result
            
            if start_column < end_column:
                for i in range(end_column - 1, start_column - 1, -1):
                    result.append(matrix[end_row - 1][i])
                end_row -= 1
            else:
                return result                    
                
            if start_row < end_row:
                for i in range(end_row - 1, start_row - 1, -1):
                    result.append(matrix[i][start_column])
                start_column += 1
                
        return result            
```
