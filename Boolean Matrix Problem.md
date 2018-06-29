Given a boolean matrix mat[M][N] of size M X N, modify it such that if a matrix cell mat[i][j] is 1 (or true) then make all the cells of ith row and jth column as 1.

**Asked in VMWare, Amazon, Ola Cabs, Boomerang Commerce**

**Difficulty: Basic**

## Input:

The first line of input contains an integer T denoting the number of test cases.

The first line of each test case is r and c,r is the number of rows and c is the number of columns.

The second line of each test case contains all the elements of the matrix in a single line separated by a single space.

## Output:

Print the modified array.

## Constraints:

1 ≤ T ≤ 50

1 ≤ r,c ≤ 20

0 ≤ Elements of matrix ≤ 1

## Example:

### Input:
```
3
2 2
1 0 0 0
2 3
0 0 0 0 0 1
3 4
1 0 0 1 0 0 1 0 0 0 0 0
```

### Output:
```
1 1 1 0
0 0 1 1 1 1
1 1 1 1 1 1 1 1 1 0 1 1
```

### Solution:

- Chuyển mảng 1 chiều thành 2 chiều:

```
1 0 0 0
```

sang

```
1   0
0   0
```

- array[0][0] = 1 thì tất cả phần tử chung hàng 0 và cột 0 đổi thành 1

```
1   1
1   0
```

- Đưa mảng 2 chiều thành 1 chiều:
```
1   1   1   0
```

### Code:

```cpp

```
