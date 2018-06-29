In a country where everyone wants a boy, each family continues having babies till they have a boy. After some time, what is the proportion of boys to girls in the country? (Assuming probability of having a boy or a girl is the same)

Trong một quốc gia mà mọi người đều muốn mình có con trai, mỗi gia đình sẽ tiếp tục sinh con cho đến được bé trai. Nếu họ có bé gái thì họ sẽ tiếp tục sinh. Khoảng thời gian sau đó tỉ lệ giữa boy và girl là bao nhiêu? Giả sử xác xuất có được một boy và một girl là như nhau.

`
 Round off your answer to 2 decimal places and output the answer as I.xx where I is the integer part of your answer, and xx are the first 2 decimal places of the rounded off answer. 
`

`
Làm tròn output thành 2 số thập phân dạng I.xx với I là phần nguyên và xx là phần thập phân.
`

**Asked in Google**

### Solution:

#### Solution 1:

- Đề cho xác xuất sinh trai và gái là như nhau. Giả sử tỷ lệ sinh trai và gái: 1/2:1/2
- Bao gồm kịch bản hơi cực đoan thì nếu chỉ có 1 gia đình và tỷ lệ sinh trai và sinh gái là 1/2 thì tỷ lệ sinh gái là 0 (Chỉ có một cậu con trai duy nhất trong gia đình)
- Nếu có 2 gia đình với tỷ lệ sinh trai sinh gái là 1/4 thì tỷ lệ sinh gái là 1/2 (Girl Boy) là xác xuất có thể xảy ra
- Nếu có 3 gia đình với tỷ lệ sinh trai sinh gái là 1/8 thì tỷ lệ sinh gái là 2/3 (Girl Girl Boy) là xác xuất có thể xảy ra
- Nếu có 4 gia đình với tỷ lệ sinh trai sinh gái là 1/16 thì tỷ lệ sinh gái là 3/4 (Girl Girl Girl Boy) là xác xuất có thể xảy ra
- Nếu có 5 gia đình với tỷ lệ sinh trai sinh gái là 1/32 thì tỷ lệ sinh gái là 4/5 (Girl Girl Girl Girl Boy) là xác xuất có thể xảy ra

Xác xuất sinh gái có thể xảy ra là: 0 * 1/2 + 1/4 * 1/2 + 1/8 * 2/3 + 1/16 * 3/4 + 1/32 * 4/5 + .... = 1 - ln2 = 0.301

Tham khảo [ở đây](https://mathoverflow.net/questions/17960/google-question-in-a-country-in-which-people-only-want-boys/17963#17963)

#### Solution 2:
 Xác xuất có được bé trai và bé gái là như nhau. Xác xuất em bé kế tiếp là trai thì không phụ thuộc vào history. Vậy sẽ tìm số lượng dự kiến các bé gái trước khi 1 bé trai sinh ra.
 
 + Gọi x là xác xuất dự kiến về các bé gái trước khi 1 bé trai được sinh ra
 
 + Gọi y là xác xuất 1 đứa trẻ sinh ra là gái và (1 - y) là xác xuất 1 đứa trẻ sinh ra là gái
 
 **_Tại sao có biểu thức trên?_** 
 
 _Mô hình hóa như "các vòng" sinh con. Tất cả các gia đình đều có con đầu lòng như round 1 với tỉ lệ trai-gái là 1/2:1/2, tiếp tục round 2, round 3,..._
 
  **Với 10 gia đình thì:** 
 
  Round 1 (Xác xuất sinh trai sinh gái là 50%)| B | G | G | B | B | B | G | B | G | G |
  -------|---|---|---|---|---|---|---|---|---|---|  
  Round 2 (Xác xuất sinh trai sinh gái là 25%)|   | B | G |   |   |   | B |   | G |   |
  Round 3 (Xác xuất sinh trai sinh gái là 12.5%)|   |   | G |   |   |   |   |   | B |   |

Vì vậy gọi y là xác xuất sinh bé gái và (1 - y) cũng là xác xuất sinh bé gái

+ x có thể viết thành một dãy vô hạn như: **0*y + 1*y*(1 - y) + 2*y*y*(1 - y) + 3*y*y*y*(1 - y) + 4*y*y*y*y*(1 - y) + ...**
  + Nếu chỉ có 1 gia đình thì tỉ lệ sinh gái cho là 0
  + Nếu chỉ có 2 gia đình thì tỉ lệ sinh gái cho là 1/2
  + Nếu chỉ có 3 gia đình thì tỉ lệ sinh gái cho là 2/3
  + Nếu chỉ có 4 gia đình thì tỉ lệ sinh gái cho là 3/4
  + Nếu chỉ có 5 gia đình thì tỉ lệ sinh gái cho là 4/5
+ Thay y = 1/2 và (1 - y) = 1/2 vào biểu thức trên thành:
  + y    = 0*(1/2) + 1*(1/2)^2 + 2*(1/2)^3 + 3*(1/2)^4  +  4*(1/2)^5 + ...
  + y/2  = 0*(1/2)^2 + 1*(1/2)^3 + 2*(1/2)^4 + 3*(1/2)^5  +  4*(1/2)^6 + ...
  + y - y/2 =  (0*(1/2) + 1*(1/2)^2 + 2*(1/2)^3 + 3*(1/2)^4  +  4*(1/2)^5) - (0*(1/2)^2 + 1*(1/2)^3 + 2*(1/2)^4 + 3*(1/2)^5  +  4*(1/2)^6)
  + y - y/2 = 1*(1/2)^2 + 1*(1/2)^3 + 1*(1/2)^4 + 1*(1/2)^5  +  1*(1/2)^6 + ...
  + y/2 = (1/4)/(1 - 1/2) = 1/2
  + y = 1
 
 Số lượng con gái mong muốn là 1. Và kể từ lúc số lượng con gái mong muốn là 1 cộng với việc luôn muốn có 1 đứa con trai thì tỉ lệ mong đợi sinh con trai - con gái là 50:50  
  
### Code:
