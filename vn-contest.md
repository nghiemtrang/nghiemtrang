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
 1. `POST /posts` tạo REST API thực hiện tính năng thêm `Post`
    * sample request body
      (표)
    * sample response body
      `{
        "id": 3,
        "title": "title1",
        "content": "content",
        "createdAt": "2023-12-12T11:10:47.7894438",
        "updatedAt": "2023-12-12T11:10:47.7894438"
       }`
