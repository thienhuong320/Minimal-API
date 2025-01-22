# Todo API - Simple Minimal API

Đây là một dự án Todo API đơn giản được tạo ra sử dụng .NET 9 Minimal API và Entity Framework Core. Dự án này minh họa cách xây dựng một API tối giản với cơ sở dữ liệu trong bộ nhớ (in-memory database) để quản lý các Todo item.

## Yêu cầu

- .NET 9.0 hoặc phiên bản mới hơn
- Visual Studio 2022 hoặc phiên bản mới hơn
- Các package NuGet:
  - `Microsoft.EntityFrameworkCore.InMemory`
  - `Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore`

## Các bước tạo dự án

1. **Tạo dự án**:
    - Mở Visual Studio 2022 và tạo một dự án mới.
    - Chọn template **ASP.NET Core Empty** và đặt tên cho dự án là `TodoApi`.
    - Chọn **.NET 9.0** và bỏ chọn "Do not use top-level statements".

2. **Thêm các NuGet Packages**:
    - Thêm các package NuGet sau:
      - `Microsoft.EntityFrameworkCore.InMemory`
      - `Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore`

3. **Tạo Model và Database Context**:
    - Tạo file `Todo.cs` cho model và `TodoDb.cs` cho database context.

4. **Cài đặt mã API**:
    - Thay thế nội dung của file `Program.cs` với mã API để xử lý các thao tác CRUD cho các Todo item.


## Các Endpoints API

| **Method** | **Endpoint**          | **Mô tả**                                          | **Request Body**                                                                                 | **Response Body**                                                     |
|------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| GET        | /todoitems            | Lấy tất cả các Todo items.                       | Không có                                                                                         | Mảng các Todo items.                                                  |
| GET        | /todoitems/complete   | Lấy tất cả các Todo items đã hoàn thành.         | Không có                                                                                         | Mảng các Todo items đã hoàn thành.                                    |
| GET        | /todoitems/{id}       | Lấy một Todo item theo ID.                       | Không có                                                                                         | Todo item yêu cầu hoặc 404 nếu không tìm thấy.                        |
| POST       | /todoitems            | Tạo một Todo item mới.                           | Một Todo item (ví dụ: `{ "name": "Mua sữa", "isComplete": false }`)                              | Todo item vừa tạo với mã trạng thái 201.                              |
| PUT        | /todoitems/{id}       | Cập nhật một Todo item đã tồn tại theo ID.       | Todo item cập nhật (ví dụ: `{ "name": "Mua đồ tạp hóa", "isComplete": true }`)                   | Không có nội dung (mã trạng thái 204) hoặc 404 nếu không tìm thấy.    |
| DELETE     | /todoitems/{id}       | Xóa một Todo item theo ID.                       | Không có                                                                                         | Không có nội dung (mã trạng thái 204) hoặc 404 nếu không tìm thấy.    |


## Kiểm Tra API

- Sử dụng **Endpoints Explorer** trong Visual Studio để kiểm tra các endpoints.
- Có thể tạo và gửi các yêu cầu cho các thao tác `GET`, `POST`, `PUT` và `DELETE` từ cửa sổ **Endpoints Explorer**.

## Kết Luận

Đây là một Todo API tối giản được xây dựng với .NET 9 sử dụng phương pháp Minimal API. Nó minh họa cách tạo một API CRUD đơn giản với lưu trữ trong bộ nhớ sử dụng Entity Framework Core. Cấu trúc này rất phù hợp cho các ứng dụng nhỏ, microservices hoặc mục đích học tập.
