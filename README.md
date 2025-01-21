# Book Store API Project

## Mô tả Dự án

Dự án này là một API quản lý cửa hàng sách sử dụng ASP.NET Core và MongoDB. Dự án cung cấp các endpoint để thực hiện các thao tác CRUD (Create, Read, Update, Delete) đối với các sách trong cơ sở dữ liệu MongoDB. Các tính năng chính của API bao gồm:

- **Get**: Lấy tất cả các sách hoặc lấy một cuốn sách theo ID.
- **Post**: Thêm một cuốn sách mới vào cơ sở dữ liệu.
- **Put**: Cập nhật thông tin của một cuốn sách theo ID.
- **Delete**: Xóa một cuốn sách theo ID.

## Các Thành Phần Chính

### 1. **Model** (`Book` và `BookStoreDatabaseSettings`)

- `Book`: Mô hình đại diện cho một cuốn sách với các thuộc tính bao gồm:
  - `Id`: ID duy nhất của cuốn sách (kiểu ObjectId của MongoDB).
  - `BookName`: Tên cuốn sách.
  - `Price`: Giá của cuốn sách.
  - `Category`: Thể loại của cuốn sách.
  - `Author`: Tác giả của cuốn sách.
  
- `BookStoreDatabaseSettings`: Cấu hình kết nối MongoDB với các trường bao gồm:
  - `ConnectionString`: Chuỗi kết nối đến MongoDB.
  - `DatabaseName`: Tên cơ sở dữ liệu.
  - `BooksCollectionName`: Tên bộ sưu tập sách trong cơ sở dữ liệu.

### 2. **Controller** (`BooksController`)

- **Get**: 
  - Lấy tất cả các sách từ cơ sở dữ liệu.
  - Lấy một cuốn sách theo ID.
  
- **Post**:
  - Thêm một cuốn sách mới vào cơ sở dữ liệu.

- **Put**:
  - Cập nhật một cuốn sách đã tồn tại theo ID.

- **Delete**:
  - Xóa một cuốn sách theo ID.

### 3. **Service** (`BooksService`)

- `BooksService`: Cung cấp các phương thức để thao tác với cơ sở dữ liệu MongoDB, bao gồm các chức năng:
  - `GetAsync`: Lấy danh sách tất cả các sách hoặc một cuốn sách theo ID.
  - `CreateAsync`: Tạo một cuốn sách mới.
  - `UpdateAsync`: Cập nhật thông tin cuốn sách.
  - `RemoveAsync`: Xóa một cuốn sách.

### 4. **Cấu hình MongoDB** trong `appsettings.json`

- Cấu hình kết nối MongoDB và tên cơ sở dữ liệu được lưu trữ trong `appsettings.json`:
  ```json
  "BookStoreDatabase": {
    "ConnectionString": "mongodb://localhost:27017",
    "DatabaseName": "BookStore",
    "BooksCollectionName": "Books"
  }
## Kết quả 
- **API Hoạt Động**: Tất cả các endpoint API đều hoạt động như mong đợi, cho phép quản lý sách từ cơ sở dữ liệu MongoDB thông qua các phương thức GET, POST, PUT, DELETE.
  ![Screenshot](images/Screenshot%202025-01-21%20113154.png)

- **Tương tác cơ sở dữ liệu **: Kết nối thành công với MongoDB để thực hiện các thao tác.
- **Swagger**:  Cho phép thử nghiệm các API trực tiếp trên trình duyệt, giúp việc kiểm tra và phát triển thuận tiện hơn với người dùng.
