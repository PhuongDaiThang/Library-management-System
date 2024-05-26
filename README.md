Các thông tin sẽ được lưu trữ trong file .txt tương ứng (Coi mỗi file .txt là 1 database trong thực tế).

1. Mô tả các thuộc tính của các class:
     Class Book:
id: int
title: string
author: string
quantity: int
     Class EBook kế thừa class Book và có thêm các thuộc tính:
fileFormat: string
fileSize: int
     Class Person:
id: int
name: string
email: string
sex: string
birthdate: string
address: string
phoneNumber: string
role: string
    Class BorrowInfo:
id: int
personId: int
bookId: int
eBookId: int
    Class User:
id: int
email: string
password: string
2. Mô tả các methods của các class (Các tham số các bạn tự chọn):
   Class Book:
Book(): Hàm khởi tạo 1 cuốn sách với các thông tin tương ứng. Các thông tin cần được validate. Id sẽ tự động nhận là id bé nhất chưa xuất hiện trong file books.txt và không truyền id vào constructor.
addBook(): Thêm thông tin 1 cuốn sách vào file books.txt. Chỉ người
getBooks(): Lấy tất các các thông tin các cuốn sách có trong file books.txt và trả về 1 vector Book.
updateBook(): Cập nhật thông tin của 1 cuốn sách trong file books.txt theo id. Các thông tin cũng cần được validate.
deleteBook(): Xóa thông tin 1 cuốn sách trong file books.txt theo id. Cần được validate xem id có tồn tại không trước khi xóa.
   Class EBook có thể override lại các methods trong class Book (Nếu cần).
   Class Person:
Person(): Hàm khởi tạo 1 người với các thông tin tương ứng. Các thông tin cần được validate. Id sẽ tự động nhận là id bé nhất chưa xuất hiện trong file people.txt và không truyền id vào constructor.
   Class User:
User(): Hàm khởi tạo thông tin 1 user với các thông tin tương ứng. Các thông tin cần được validate. Id sẽ tự động nhận là id bé nhất chưa xuất hiện trong file users.txt và không truyền id vào constructor.
register(): Thêm thông tin đăng nhập 1 user vào file users.txt. Chú ý validate dữ liệu (email không được trùng, password cần có thêm rule gì đó các bạn tự quy định).
login(): Kiểm tra thông tin đăng nhập và trả về Person với email tương ứng.
logout(): Đăng xuất.
    Class BorrowInfo():
BorrowInfo(): Hàm khởi tạo 1 thông tin mượn sách mới với các thông tin tương ứng. Các thông tin cần được validate. Id sẽ tự động nhận là id bé nhất chưa xuất hiện trong file borrowInfos.txt và không truyền id vào constructor.
addInfo(): Thêm thông tin mượn sách vào file borrowInfos.txt, validate dữ liệu đầu vào.
updateInfo(): Cập nhật thông tin mượn sách vào file borrowInfos.txt, validate dữ liệu đầu vào.
Các methods trên có thể chưa đủ, các bạn có thể thêm các methods khác nếu cần thiết.

3. Kịch bản thao tác:
    Khi chạy chương trình, sẽ hiển thị ra 1 menu lựa chọn:
 Đăng nhập: Nếu người dùng chọn chức năng này sẽ cho phép nhập vào thông tin đăng nhập và xác thực thông tin, nếu đăng nhập thành công sẽ in ra dòng chữ "Welcome <tên>!". Các chức năng từ chức năng thứ 3 trở đi sẽ phải yêu cầu người dùng đăng nhập mới có thể thao tác.
 Đăng ký: Cho phép người dùng đăng ký tài khoản, role mặc định sẽ là user.
 Thêm sách: Chỉ thực hiện được nếu người dùng có role admin. Sẽ cho phép người dùng thêm thông tin 1 cuốn sách mới.
 Sửa thông tin sách: Chỉ thực hiện được nếu người dùng có role admin. Sẽ cho phép người dùng nhập vào id cuốn sách và cho phép sửa thông tin cuốn sách đó.
 Xóa sách: Chỉ thực hiện được nếu người dùng có role admin. Cho phép người dùng nhập vào id cuốn sách, và có xác nhận trước khi xóa.
 Mượn sách: Chỉ thực hiện được nếu người dùng có role user. Cho phép người dùng nhập vào id cuốn sách muốn mượn.
 Trả sách: Chỉ thực hiện được nếu người dùng có role user. Cho phép người dùng nhập vào id cuốn sách muốn trả.
 Lấy thông tin các quyển sách: Hiển thị toàn bộ danh sách các cuốn sách hiện có trong file books.txt. Các thông tin hiển thị theo thứ tự id tăng dần.
 Lấy thông tin 1 quyển sách: Cho phép người dùng nhập vào id 1 quyển sách và hiển thị thông tin quyển sách đó.
 Lấy thông tin tất cả các eBook hiện có.
 Lấy thông tin 1 eBook có id nằm trong file eBooks.txt.
 Hiển thị tất cả các quyển sách đã mượn của bản thân (Đối với role user).
 Hiển thị tất cả các quyển sách của 1 người dùng đã mượn với id người dùng: Cho phép người dùng có role admin nhập vào id của 1 người dùng và hiển thị thông tin các quyển sách mà người dùng đó đã mượn.
 Chỉnh sửa thông tin cá nhân: Cho phép người dùng chỉnh sửa thông tin cá nhân, trừ role và id.
 Chỉnh sửa thông tin cá nhân của người khác: Chỉ thực hiện được nếu người dùng có role admin. Cho phép người dùng nhập nhập vào id của 1 user và chỉnh sửa thông tin của user đó, có thể cập nhật role cho user đó lên admin, nhưng không được chỉnh sửa id.
 Đăng xuất.
 Thoát chương trình.
