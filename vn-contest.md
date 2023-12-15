# Spring Boot test project

## Khái quát

* Đây là bài kiểm tra tạo dự án REST API dựa trên kiến thức nền tảng
* Sẽ chấm điểm dựa vào gradle test. ref)https://www.jetbrains.com/help/idea/work-with-gradle-tasks.html
* Khuyến khích thí sinh thực hiện bài thi trên IntelliJ IDEA. https://www.jetbrains.com/idea/download/?section=windows

## Project test
1. Download file nén project mẫu tại https://codepresso-global.s3.ap-northeast-2.amazonaws.com/common/simplesns-monolithic.zip

2. Chọn Open để mở project mẫu giống với hình dưới đây:

![welcome-screen](https://gist.github.com/assets/138753646/52fa4497-32c9-45d6-a242-eb7fe104726a)

3. Giải nén project mẫu và chỉ định đường dẫn

![open-dialog](https://gist.github.com/assets/138753646/850500cb-a772-4f5e-bc21-dbbc38a4f26e)

4. Thực hiện Run để kiểm tra project có chạy bình thường không.
   * Khi chạy bình thường sẽ xuất hiện nhiều dòng tin nhắn (message). `Started SimpleSNSApplication in 4.489 seconds (JVM running for 5.708)`

![run-project](https://gist.github.com/assets/138753646/036d1c2f-e668-4c55-8436-8c4c76af9e27)

## Đề thi

1. Tạo REST API `POST /posts` để triển khai tính năng thêm `Post`
- sample request body

| Field name | Data type |
|------------|-----------|
| title      | String    |
| content    | String    |

- sample response body
```json 
{
  "id": 3,
  "title": "title1",
  "content": "content",
  "createdAt": "2023-12-12T11:10:47.7894438",
  "updatedAt": "2023-12-12T11:10:47.7894438"
}
```

2. Tạo REST API `GET /posts` để triển khai tính năng tìm kiếm toàn bộ `Posts`

- sample response body
```json 
[
  {
    "id": 3,
    "title": "title3",
    "content": "content",
    "createdAt": "2023-12-12T11:10:47.7894438",
    "updatedAt": "2023-12-12T11:10:47.7894438"
  },
  {
    "id": 2,
    "title": "title2",
    "content": "content",
    "createdAt": "2023-12-12T11:10:46.3687086",
    "updatedAt": "2023-12-12T11:10:46.3687086"
  },
  {
    "id": 1,
    "title": "title1",
    "content": "content",
    "createdAt": "2023-12-12T11:10:41.6027313",
    "updatedAt": "2023-12-12T11:10:41.6027313"
  }
]
```


3. Tạo REST API `GET /posts/{postId}` để triển khai tính năng tìm kiếm `Post` cụ thể.

- sample response body
```json 
{
  "id": 3,
  "title": "title1",
  "content": "content",
  "createdAt": "2023-12-12T11:10:47.7894438",
  "updatedAt": "2023-12-12T11:10:47.7894438"
}
```

4. Tạo REST API `GET /posts/{postId}` để chỉnh sửa trả về status 404 HTTP trong trường hợp không có bài `Post` cụ thể

```http request
HTTP/1.1 404 Not Found
Content-Length: 0
```


5. Tạo REST API `DELETE /post/{postId}`  để triển khai tính năng xóa bài `Post` cụ thể

```http request
HTTP/1.1 202 Accepted
Content-Length: 0
```

6. `PostRepositoryImpl` là class quản lý dữ liệu thừa kế từ `PostRepositoryCustom`. Chúng tôi muốn triển khai business logic quản lý dữ liệu bằng cách đưa `PostRepositoryCustom` vào `PostService`. Khi tạo `ArrayList` trong `PostRepositoryImpl` hãy tiêm và đăng ký Spring `@Bean` với tên là `postRepositoryCustom`. 

*Phải tạo Bean với tên là `postRepositoryCustom`.Trương hợp sử dụng cách khác hoặc tên khác có thể sẽ bị tinh là sai* 

7. Hãy sử dụng `postRepositoryCustom` để triển khai lưu `PostService.addPost(title, content)`
- Dựa trên dữ liệu được lưu trữ trong `PostRepositoryImpl`
- Hãy triển khai để id tăng lên 1 so với `posts` vốn có khi lưu các đối tượng(Object) trong `PostRepositoryImpl` 
ex) Nếu lưu 2 bài `Post` thì id của `Post` được thêm mới phải là 2 (id bắt đầu từ 0, id của post vốn có là 0 và 1)

8. Triển khai `PostService.getPostList()` để tìm kiếm toàn bộ bài `Post`
- Tuy nhiên, hãy sắp xếp theo thứ tự `id` giảm dần(Descending)
- Dựa trên dữ liệu lưu trong `PostRepositoryImpl`

9. Triển khai `PostService.getPost(id)` để tìm kiếm `Post` thông qua id
- Dựa trên dữ liệu được lưu trong `PostRepositoryImpl`

10. `PostService.delete(id)` là tính năng xóa `Post` dựa vào `id` field. Hãy triển khai tính năng này.
- Dựa vào dữ liệu được lưu trong PostRepositoryImpl`

11. Hãy viết lệnh SQL sau đây vào `value` trong @Query của phương thức `getComment` của `CommentRepository`
-  Truy vấn SQL tìm kiếm tất cả các column trong comment dựa vào id
ex) getComment(1) => Truy xuất comment có id là 1 

12. Viết `value` SQL của `@Query` của phương thức `findComments` của `CommentRepository`.
- Truy vấn SQL để tìm kiếm tất cả các column của comment bao gồm content của comment, nhưng phải sắp xếp theo thứ tự id ngược lại
ex) findComments("abc") => 
- id : 3, content : "abcd"
- id : 2, content : "abc"
- id : 1, content : "abcf" 

## Cách thức nộp bài
1. Thực hiện nhiệm vụ clean của gradle task (Không bắt buộc)
  ref) gradle clean là task xóa tất cả kết quả đầu ra output như gradle cache và gradle directory v.v, bao gồm tất cả build artifact được tạo ra thông qua gradle build; nhiệm vụ này đóng vai trò đưa dự án trở lại trạng thái trạng thái như khi chúng ta mới build dự án lần đầu tiên. 
Tức là khi bắt đầu một build mới bằng cách khởi động môi trường build thông qua gradle clean, nó có thể được rút ngắn thời gian xây dựng do không bị ảnh hưởng bởi cache và build directory cũ, và cải thiện tính ổn định của build do không còn vấn đề hoặc lỗi phát sinh trong build trước đó.

2. Nén folder project
3. Đổi tên file nén thành email đã dùng để đăng kí tài khoản trên  https://codepresso.io ex) `student@gmail.com`
4. Upload file nén lên Goole form https://forms.gle/ENZWRwdLqBPgTMZ47
- Khi nộp ghi email đã đăng kí tài khoản trên https://codepresso.io

## Chú ý`
- Kiểm tra xem file có được biên dịch trước khi nộp
- Không chỉnh sửa code dưới đây `/src/test`, trường hợp chỉnh sửa sẽ ảnh hưởng đến việc chấm điểm
- Có thể tra mạng, không được sử dụng GPT
