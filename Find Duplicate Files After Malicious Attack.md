You left your computer unlocked and your friend decided to troll you by copying a lot of your files to random spots all over your file system.

_Bạn rời khỏi máy tính của bạn mà chưa khóa và bạn của bạn troll bạn bằng cách copy rất nhiều file đến các vị trí ngẫu nhiên trong tất cả hệ thống tập tin của máy bạn_

Even worse, she saved the duplicate files with random, embarrassing names ("this_is_like_a_digital_wedgie.txt" was clever, I'll give her that).

_Thậm chí còn tồi tệ hơn, cô ấy lưu các bản sao của file đã copy với các tên ngẫu nhiên, tên xấu hổ_

Write a function that returns a list of all the duplicate files. We'll check them by hand before actually deleting them, since programmatically deleting files is really scary. To help us confirm that two files are actually duplicates, return a list of tuples ↴ where:

+ The first item is the duplicate file
+ The second item is the original file

Viết 1 hàm trả về danh sách tất cả các bản sao file. Và kiểm tra thủ công trước khi xóa chúng. Để  xác nhận rằng hai tệp thực sự là bản sao, hãy trả về danh sách các bộ dữ liệu như **tuple** trong đó:
+ Item 1 là file bản sao 
+ Item 2 là file gốc

Ví dụ:
```
  [('/tmp/parker_is_dumb.mpg', '/home/parker/secret_puppy_dance.mpg'),
   ('/home/trololol.mov', '/etc/apache2/httpd.conf')]
 ```
 
 **Asked in Google**
