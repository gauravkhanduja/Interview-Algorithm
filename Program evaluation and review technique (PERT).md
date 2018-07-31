Pert phát triển trong những năm 1950 trong dự án tên lửa Polaris của Mỹ. Quan ngại về kho vũ khí hạt nhân đang phát triển của Liên Xô, chính phủ Mỹ muốn hoàn thành dự án Polaris càng nhanh càng tốt. Hải quân Mỹ đã sử dụng PERT để điều phối 3000 nhà thầu liên quan tới dự án giúp rút ngắn thời gian từ 5 năm xuống còn 3 năm. Tại Việt Nam, PERT được ứng dụng trong công trình xây lăng chủ tịch Hồ Chí Minh.

Ví dụ đơn giản nhất của sơ đồ mạng lưới PERT là áp dụng tính toán về các đơn vị thời gian mà chưa có các yếu tố xác xuất khác như tâm lý, môi trường, rủi ro,..

![](https://github.com/flightstar/Interview-Algorithm/blob/master/images/Pert_Network_Simple_Excersise.PNG)

Hình ảnh trên cho thấy các đỉnh và tính các chỉ tiêu thời gian cho sơ đồ mạng lưới với 19 công việc. Mỗi cung có 2 số như công việc thứ 16 mất 5 đơn vị thời gian hoàn thành

## VD: Dự án thi công khu nhà A

STT | Tên công việc | Công việc cần làm trước | Thời gian hoàn thành (tháng)
----|---------------|-------------------------|----------------------
1|Khảo sát xây dựng phục vụ cho việc tìm kiếm địa điểm xây dựng và thi tuyển kiến trúc|0|
2|Lựa chọn nhà thầu lập báo cáo đầu tư xây dựng|1|
3|Lập báo cáo đầu tư xây dựng|1|
4|Trình báo cáo đầu tư xây dựng để xin phép đầu tư xây dựng|1|
5|Tổ chức thi tuyển kiến trúc: chọn phương án để triển khai thiết kế cơ sở|1|
6|Lựa chọn nhà thầu lập dự án đầu tư xây dựng|2|
7|Lập dự án đầu tư xây dựng (trong đó đã có thiết kế cơ sở và tổng mức đầu tư)|6|
8|Trình, thẩm định, phê duyệt dự án đầu tư xây dựng|7|
9|Thành lập ban QLDA hoặc thuê tư vấn QLDA|8|
10|Xin giấy phép xây dựng|7, 8|
11|Lựa chọn nhà thầu khảo sát xây dựng, nhà thầu thiết kế, nhà thầu thấm tra thiết kế|8, 9|
12|Lập thiết kế các bước tiếp theo (thiết kế kỹ thuật và thiết kế bản vẽ thi công)|11|
13|Tổ chức thấm định và phê duyệt thiết kế kỹ thuật, thiết kế bản vẽ thi công và tổng dự toán|7, 11, 12|
14|Lựa chọn nhà thầu thi công xây dựng|13|
15|Lựa chọn tư vấn giám sát, tư vấn chứng nhận chất lượng công trình xây dựng|13|
16|Thi công xây dựng|15|
17|Nghiệm thu công trình hoàn thành đưa vào sử dụng|16|
18|Thanh toán và quyết toán với nhà thầu thi công xây dựng|17|
19|Quyết toán vốn đầu tư xây dựng|18|
20|Bàn giao công trình|17, 18, 19|
21|Theo dõi, đôn đốc nhà thầu thi công xây dựng bảo hành công trình|20|
22|Thực hiện bảo trì công trình xây dựng|21|

### _Viết chương trình cho biết thời gian hoàn thành dự án sớm nhất và thời gian hoàn thành dự án muộn nhất mà không ảnh hưởng đến thời gian hoàn thành của toàn bộ dự án_

+ Sơ đồ PERT cho dự án:
+ Code:

## Tham khảo:
Nghị định 59/2015/NĐ-CP về quản lý dự án đầu tư xây dựng, https://luatvietnam.vn/dau-tu/nghi-dinh-59-2015-nd-cp-chinh-phu-95563-d1.html
