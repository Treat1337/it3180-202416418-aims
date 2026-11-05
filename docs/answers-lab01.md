# Lab 01 — Thiết lập và refactor

## Vì sao dùng `git mv`?

`git mv dvd.py aims/dvd.py` thực hiện di chuyển và đưa thay đổi vào staging
trong một bước, giảm khả năng quên thêm đường dẫn mới hoặc xóa đường dẫn cũ.
Git lưu snapshot, không lưu một thao tác đổi tên riêng. Khi so sánh hai
snapshot, Git suy luận rename từ mức tương đồng; di chuyển thủ công rồi
`git add -A` cũng có thể được nhận diện như vậy.
`git log --follow -- aims/cart.py` giúp lần ngược lịch sử qua lần di chuyển.

## Nhánh release có phải baseline không?

Một nhánh release có thể được dùng làm baseline nếu đó là quy ước của nhóm.
Nhánh có thể tiến lên khi nhận hotfix; annotated tag giữ định danh cố định cho
một bản phát hành. Repository `202416418` hiện chưa có nhánh release hoặc tag.

## Vì sao vẫn dùng PR khi làm một mình?

PR tạo điểm kiểm tra diff, mục đích và kết quả thử nghiệm trước khi tích hợp;
đồng thời lưu dấu vết yêu cầu → thay đổi → baseline. Cấu hình làm cá nhân dùng
0 approval theo đề, nhưng vẫn yêu cầu PR. Không coi tự kiểm tra là review độc lập.
Các commit khởi tạo trước PR đầu tiên là bước bootstrap theo Lab 01.

## Cấu hình global và local khác nhau thế nào?

`--global` thường nằm trong `~/.gitconfig` và áp dụng cho mọi kho của tài khoản
máy tính. `--local` ở `.git/config` chỉ tác động kho hiện tại và được ưu tiên
hơn giá trị global tương ứng. Bài này đặt danh tính ở local để không làm đổi
cấu hình của dự án khác; dùng email noreply của tài khoản GitHub.

## Kiểm tra mã hiện tại

- `python main.py` chạy thành công và in tổng giỏ hàng 63.89 USD.
- `python -m unittest discover -s tests -v` chạy thành công 9 test.
- Các thao tác Git trong bài cần được thực hành trên nhánh riêng; trạng thái
  hiện tại không phải minh chứng cho các thao tác đó.
