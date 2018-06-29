Given a list of contacts which exist in a phone directory and a query string **str**. The task is to implement search query for the phone directory. Run a search query for each prefix **p** of the query string **str** (i.e from  index 1 to str length) that prints all the distinct recommended contacts which have the same prefix as our **query (p) in lexicographical order**. Please refer the explanation part for better understanding.

NOTE: If there is no match between query and contacts , print "0".

**Asked in Microsoft**

## Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains three lines. First line of each test case contains N i.e., number of contacts. Second line contains space separated all the contacts in the form of string. And third line contains query string.

## Output:
For each test case, print each query result in new line. If there is no match between query and contacts, print "0".

## Constraints:
1<=T<=100
1<=N<=50
1<=|contact[i].length|<=50
1<=|query length|<=6

## Example:
### Input:
```
1
3
geeikistest geeksforgeeks geeksfortest
geeips
```
### Output:
```
geeikistest geeksforgeeks geeksfortest 
geeikistest geeksforgeeks geeksfortest
geeikistest geeksforgeeks geeksfortest
geeikistest
0
0
```
### Solution:

+ 3 danh sách là geeikistest geeksforgeeks geeksfortest
+ Chuỗi search: geeips
+ Result 1: Do g nằm trong 3 tên trong danh bạ nên trả về **geeikistest geeksforgeeks geeksfortest**
+ Result 2: Do ge nằm trong 3 tên trong danh bạ nên trả về **geeikistest geeksforgeeks geeksfortest**
+ Result 3: Do gee nằm trong 3 tên trong danh bạ nên trả về **geeikistest geeksforgeeks geeksfortest**
+ Result 4: Do geei nằm trong 1 tên trong danh bạ nên trả về **geeikistest**
+ Result 5: Do geeip không nằm trong trong danh bạ nên trả về **0**
+ Result 6: Do geeips không nằm trong trong danh bạ nên trả về **0**

### Code:

