### Interview Question:

There is a building of 100 floors

If an egg drops from the Nth floor or above it will break. If it’s dropped from any floor below, it will not break. You’re given 2 eggs. Find N, while minimizing the number of drops for the worst case.

These are very strong eggs, because they can be dropped multiple times without breaking as long as they are dropped from floors below their “threshold” floor, floor N. But once an egg is dropped from a floor above it’s threshold floor, it will break.

Output the minimum number of drops required to figure out N.

`Answer is a integer. Just put the number without any decimal places if its an integer. If the answer is Infinity, output Infinity. Feel free to get in touch with us if you have any questions`

Một tòa nhà 100 tầng. Nếu qua trứng rơi từ tầng >= Nth thì quả trứng vỡ. Nếu rơi ở bất cứ tầng nào < Nth thì quả trứng không vỡ. Ban đầu bạn có 2 quả trứng. Tìm N số lần rơi tối thiểu trong trường hợp xấu nhất 


### Asked in:
**_Google_**

**_Nvidia_**

### Solution:
+ Nếu quả trứng vỡ ở tầng N thì sẽ vỡ với tất cả các tầng >= N
+ Nếu quả trứng không vỡ ở tầng N thì sẽ không vỡ ở tất cả những tầng phía dưới
+ Quả trứng có thể vỡ ở tầng đầu tiên
+ Quả trứng có thể không vỡ ở tầng cuối cùng

**_Bạn xác định số lần thử tối thiểu để tìm ra một tầng nguy hiểm làm trứng vỡ trong trường hợp xấu nhất với một chiến lược tốt nhất_**

+ **x** tầng là mà quả trứng đầu tiên rơi, nếu quả trứng vỡ thì chúng ta sẽ lùi về **(x - 1)** tầng
+ Nếu **x** tầng quả trứng không vỡ thì thay vì nhảy lên tầng **x** khác thì chúng ta bước lên **(x - 1)** tầng (Vì ta chi có thể rơi 1 lần ít hơn số lần rơi có sẵn nếu chúng ta đi từ tầng này lên tầng khác), sử dụng công thức cộng để tìm ra tầng mà ta thử tiếp theo là **x + (x - 1)** 
+ Tương tự, giả định tầng **x + (x - 1)** sau khi thử không vỡ thì nhảy lên **x + (x - 1) + (x - 2)** tầng, và nếu như thế nữa ta có dãy số **x + (x - 1) + (x - 2) + (x - 3) + ...**
+ Mỗi lần trứng không vỡ thì ta đi lên với số tầng đi lên giảm 1 tầng so với số tầng trước cho đến khi nào lên thêm 1 tầng nữa là tới tầng 100. Áp dụng công thức cộng ta có dãy số và công thức tổng quát:

```
x + (x - 1) + (x - 2) + (x - 3) + (x - 4) + ... + 1 >= 100

<=> x*(x + 1)/2 >= 100

<=> x >= 13.651

Làm tròn x >= 14
```

Bây giờ ta đã có thông tin để tính toán giải pháp tối ưu 2 quả trứng

Drop | Floor
-----|------
1|14
2|27
3|39
4|50
5|60
6|69
7|77
8|84
9|90
10|95
11|99
12|100

Nếu tầng 14 quả trứng không vỡ thì thử ở tầng trên 27, 39, 50,...

Thử quả trứng 1 | Quả trứng 1 vỡ thì quả trứng 2 có thể đi từ tầng này tới những tầng khác | Số lần rơi
----------------|--------------------------------------------------------------------------|-----------
14| 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8 -> 9 -> 10 -> 11 -> 12 -> 13 | 1 + 13  = 14 (13 lần + 1 lần)
27| 15 -> 16 -> 17 -> 18 -> 19 -> 20 -> 21 -> 22 ->23 -> 24 -> 25 -> 26 | 2 + 12 = 14 (12 lần + 1 lần tầng 14 + 1 lần tầng 27)
39| 28 -> 29 -> 30 -> 31 -> 32 -> 33 -> 34 -> 35 -> 36 -> 37 -> 38| 3 + 11 = 14 (11 lần + 1 lần tầng 14 + 1 lần tầng 27 + 1 lần tầng 38)
50| 40 -> 41 -> 42 -> 43 -> 44 -> 45 -> 46 -> 47 -> 48 -> 49| 4 + 10 = 14
60| 51 -> 52 -> 53 -> 54 -> 55 -> 56 -> 57 -> 58 -> 59|5 + 9 = 14
69| 61 -> 62 -> 63 -> 64 -> 65 -> 66 -> 67 -> 68| 6 + 8 = 14
77| 70 -> 71 -> 72 -> 73 -> 74 -> 75 -> 76| 7 + 7 = 14
84| 78 -> 79 -> 80 -> 81 -> 82 -> 83| 8 + 6 = 14
90| 85 -> 86 -> 87 -> 88 -> 89| 9 + 5 = 14
95| 91 -> 92 -> 93 -> 94| 10 + 4 = 14
99| 100 | 11 + 1 = 12*

Với tối đa 14 lần rơi với các phép thử có sự kết hợp của việc cho quả trứng 1 rơi và quả trứng 2 rơi. Mỗi lần rơi ta lại đi lên 1 tầng của tòa nhà và ta sẽ giảm đi các trường hợp xấu nhất trong phép thử quả trứng


### Code:
