# Spring Boot test project
## Khái quát
* Đây là bài kiểm tra tạo dự án REST API dựa trên kiến thức nền tảng
* Sẽ chấm điểm dựa vào gradle test. ref)https://www.jetbrains.com/help/idea/work-with-gradle-tasks.html
* Khuyến khích thí sinh thực hiện bài thi trên IntelliJ IDEA. https://www.jetbrains.com/idea/download/?section=windows

## Project test
1. Download file nén project mẫu tại https://codepresso-global.s3.ap-northeast-2.amazonaws.com/common/simplesns-monolithic.zip
2. Chọn Open để mở project mẫu giống với hình dưới đây:
   (사진)
3. Giải nén project mẫu và chỉ định đường dẫn
   (사진)
4. Thực hiện Run để kiểm tra project có chạy bình thường không.
   * Khi nó chạy bình thường sẽ xuất hiện nhiều tin nhắn. `Started SimpleSNSApplication in 4.489 seconds (JVM running for 5.708)`

## Đề thi
 1. Tạo REST API `POST /posts` để triển khai tính năng thêm `Post`
 2. `POST /posts` Tạo REST API  để triển khai tính năng thêm `Post`
 * sample request body
      (표)
 * sample response body
   `Code`
 2. Tạo REST API `GET /posts` để triển khai tính năng tìm kiếm toàn bộ `Posts`
 * sample request body
   `Code`
 3. Tạo REST API `GET /posts/{postId}` để triển khai tìm kiếm bài `Post` cụ thể.
 * sample response body
 4. Tạo REST API `GET /posts/{postId}`, chỉnh sửa để trả về status 404 HTTP trong trường hợp không có bài `Post`
   `Code`
 5. `DELETE /post/{postId}` Tạo REST API để triển khai tính năng xóa bài `Post` cụ thể
    `Code`
 6. `PostRepositoryImpl` là class quản lý dữ liệu thừa kế `PostResositoryCustom`. Chúng tôi muốn đưa `PostRepositoryCustom` vào `PostService` và hình

## Cách thức nộp bài
1. Thực hiện clean của gradle task ???
2. Nén folder project
3. ĐỔi tên file nén thành email đã dùng để đăng kí tài khoản trên  https://codepresso.io ex) `student@gmail.com`
4. Upload file nén lên Goole form https://forms.gle/ENZWRwdLqBPgTMZ47
* Khi nộp ghi email đã đăng kí tài khoản trên https://codepresso.io

## Chú ý
* Kiểm tra xem file có được biên dịch trước khi nộp
* Không chỉnh sửa code dưới đây `/src/test`, trường hợp chỉnh sửa sẽ ảnh hưởng đến việc chấm điểm
* Có thể tra mạng, không được sử dụng GPT

   
