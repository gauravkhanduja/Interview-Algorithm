Link: [https://leetcode.com/problems/rectangle-area-ii/description/](https://leetcode.com/problems/rectangle-area-ii/description/)

Cho một mảng danh sách các hình chữ nhật **rectangles**. Mỗi **rectangle[i] = [x1, y1, x2, y2]** với **(x1, y1)** là tọa độ góc bên trái-phía dưới, và **(x2, y2)** là tọa độ góc bên phải-phía tạo thành hình chữ nhật **rectangle[i]**

Tìm tất cả các vùng được bao bởi tất cả các hình chữ nhật. Nếu kết quả câu trả lời quá lớn thì trả về module **10^9 + 7**

#####  Sơ lược về module **10^9 + 7 (1 000 000 007)**:

Trong hầu hết các cuộc thi lập trình, có một vài vấn đề được yêu cầu kết quả trả về module **10^9 + 7**. Nguyên nhân đằng sau vấn đề này là đối với các số nguyên quá lớn nên chỉ có các thuât toán hiệu quả mới có thể giải quyết chúng trong giới hạn thời gian cho phép. 

Phép toán module là gì? Là phần dư còn lại sau khi chia 2 toán hạng. Toán tử được dùng cho phép toán module là **%**. VD: a % b = c tức là a chia b dư c

Tại sao phải dùng phép toán modulo:

+ Ngăn ngừa bị overflow của input đầu vào là 1 big number. Kiểu số nguyên có miền giá trị lớn nhất trong C/C++ là **"unsigned long long int"** thuộc 64 bit nằm từ **0 đến 2^64 - 1**
  + Nếu có 1 biến A 64bit có value là 2^62
  + Nếu có 1 biến B 64bit có value là 2^63
  + Nhân A và B thì ta sẽ bị overflow
 + Có nhiều vấn đề khi xuất output nằm ngoài vùng giá trị của **""unsigned long long""**
 
 Ví dụ:
 
 + a = 145785635595363569532135132
 + b = 3151635135413512165131321321
 + c = 999874455222222200651351351
 + mod = 1000000007 (1e9 + 7)
 + print = (a * b * c) % mod
 
   + Nếu làm như thế này **(a * b * c) % mod** chắc chắn sẽ không làm được
   + Giải quyết:
     + Khai triển expression: **(a * b * c) % mod** = **((a % mod) * (b % mod) * (c % mod)) % mod**
   ```
   i = 1
   i = (i * a) % m
   i = (i * b) % m
   i = (i * c) % m
   ```

### Example 1:
![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/06/06/rectangle_area_ii_pic.png)
```
Input: [[0,0,2,2],[1,0,2,3],[1,0,3,1]]
Output: 6
Explanation: As illustrated in the picture.
```
### Example 2:
```
Input: [[0,0,1000000000,1000000000]]
Output: 49
Explanation: 
  The answer is 10^18 modulo (10^9 + 7) = 49. 
  Because 10^9 = -7 (mod 10^9 + 7) so 10^18 = (10^9)^2 = (-7)^2 = 49 (mod 10^9 + 7) 
  
```
