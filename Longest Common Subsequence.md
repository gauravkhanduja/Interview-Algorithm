Given two sequences, find the length of longest subsequence present in both of them. Both the strings are of uppercase.

**Asked in VMWare, MakeMyTrip, Amazon**

## Input:
First line of the input contains no of test cases  **T**,the **T** test cases follow.

Each test case consist of 2 space separated integers **A** and **B** denoting the size of string **str1** and **str2** respectively

The next two lines contains the 2 string **str1** and **str2**.


## Output:
For each test case print the length of longest  common subsequence of the two strings .

## Constraints:
1 <= T <= 200
1 <= size(str1),size(str2) <= 100

## Example:
### Input:
```
2
6 6
ABCDGH
AEDFHR
3 2
ABC
AC
```
### Output:
```
3
2
```

### Solution:

LCS for input Sequences **A** BC **D** G **H** and **A** E **D** F **H** R is **ADH** of length 3.

LCS of **A** B **C** and **AC** is **AC** of length 2

Dùng quy hoạch động để giải bài toán này. Chia nhỏ bài toán thành các bài toán con tối ưu nối tiếp nhau và kế thừa kết quả từ chương trình con trước. 

Các kết quả của bài toán con trước được sử dụng làm kết quả cho bài toán toàn cục.

```
ABCDGH              AEDFHR
[A]BCDGH            [A]EDFHR (Same)
[A]BCDGH            [A]EDFHR (Difference)
   ^                   ^
[A]BCDGH            [A]EDFHR (Difference)
   ^                    ^
[A]BCDGH            [A]EDFHR (Difference)
   ^                     ^
[A]BCDGH            [A]EDFHR (Difference)
   ^                      ^
[A]BCDGH            [A]EDFHR (Difference)
   ^                       ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                  ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                   ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                    ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                     ^
[A]BCDGH            [A]EDFHR (Difference)
    ^                      ^
[A]BCDGH            [A]EDFHR (Difference)
     ^              ^
[A]BCDGH            [A]EDFHR (Difference)
     ^                 ^
[A]BCDGH            [A]EDFHR (Same)
     ^                  ^
[A]BCDGH            [A]EDFHR (Difference)
     ^                   ^
[A]BCDGH            [A]EDFHR (Difference)
     ^                    ^
[A]BCDGH            [A]EDFHR (Difference)
     ^                     ^
[A]BCDGH            [A]EDFHR (Difference)
      ^              ^
[A]BCDGH            [A]EDFHR (Difference)
      ^                ^
[A]BCDGH            [A]EDFHR (Difference)
      ^                 ^
[A]BCDGH            [A]EDFHR (Difference)
      ^                  ^
[A]BCDGH            [A]EDFHR (Difference)
      ^                   ^
[A]BCDGH            [A]EDFHR (Difference)
      ^                    ^
[A]BCDGH            [A]EDFHR (Difference)
       ^             ^
[A]BCDGH            [A]EDFHR (Difference)
       ^               ^
[A]BCDGH            [A]EDFHR (Difference)
       ^                ^
[A]BCDGH            [A]EDFHR (Difference)
       ^                 ^
[A]BCDGH            [A]EDFHR (Same)
       ^                  ^
[A]BCDGH            [A]EDFHR (Difference)
       ^                   ^
```

Giải quyết bằng quy hoạch động

### X 

0 | 1 | 2 | 3 | 4 | 5
--|---|---|---|---|---
A | B | C | D | G | H

XLen = 6

### Y

0 | 1 | 2 | 3 | 4 | 5
--|---|---|---|---|---
A | E | D | F | H | R

YLen = 6

Tạo một mảng subSequenceString 2 chiều với:

+ row = XLen + 1 = 5 + 1 = 6
+ column = YLen + 1 = 5 + 1 = 6

subSequenceString | 0 | 1 | 2 | 3 | 4 | 5 | 6
------------------|---|---|---|---|---|---|---
0|||||||
1|||||||
2|||||||
3|||||||
4|||||||
5|||||||
6|||||||

Điền 0 vào subSequenceString[0][i] và subSequenceString[i][0]:

subSequenceString | 0 | 1 | 2 | 3 | 4 | 5 | 6
------------------|---|---|---|---|---|---|---
0|0|0|0|0|0|0
1|0||||||
2|0||||||
3|0||||||
4|0||||||
5|0||||||
6|0||||||

Find match the characters in 2 string:

Sau khi tìm được các kí tự giống nhau thì bảng sẽ như dưới đây:

subSequenceString | 0 | 1 | 2 | 3 | 4 | 5 | 6
------------------|---|---|---|---|---|---|---
0|0|0|0|0|0|0|0
1|0|1|1|1|1|1|1
2|0|1|1|1|1|1|1
3|0|1|1|1|1|1|1
4|0|1|1|2|2|2|2
5|0|1|1|2|2|2|2
6|0|1|1|2|2|3|3

Trả về độ dài lớn nhất của dãy con chung của 2 mảng

```cpp
void findLCS(char *X, char *Y, int XLen, int YLen) {
   int **subSequenceString = new int*[XLen + 1];
      int row, column, i;
      for (row = 0; row <= XLen; ++row) {
         subSequenceString[row] = new int[YLen];
         for (column = 0; column <= YLen; ++column) {
            if (row == 0 || column == 0) {
               subSequenceString[row][column] = 0;
            }
            else if (X[row - 1] == Y[column - 1]) {
               subSequenceString[row][column] = subSequenceString[row - 1][column - 1] + 1;
            }
            else {
               subSequenceString[row][column] = max(subSequenceString[row - 1][column], subSequenceString[row][column - 1]);
            }
         }
      }
   cout << subSequenceString[row][column] << endl;
   for (row = 0; row <= XLen; ++row) {
		subSequenceString[row] = NULL;
		delete[] subSequenceString[row];
   }
   delete[] subSequenceString;
   subSequenceString = NULL;
}
```


