# Lab 04 — Release flow và phiên bản

## Vì sao không merge release vào master?

Theo quy ước của học phần, release là dòng bảo trì một baseline đã nộp.
Merge toàn bộ có thể đưa cả metadata hoặc version dành riêng cho dòng cũ
vào master. Chỉ chuyển phần sửa lỗi cần thiết bằng cherry-pick có nguồn gốc.
Đây là chính sách của flow đang học, không phải giới hạn kỹ thuật của Git;
các quy trình khác có thể cho phép merge-back với quy tắc khác.

## So với GitFlow

Release Flow ở bài dùng master cho tích hợp liên tục, rẽ release/labXX làm
bản nộp, nhánh feature/bugfix/refactor sống ngắn. GitFlow truyền thống có thêm
develop cho tích hợp, main/master đại diện các bản production, với nhánh
release và hotfix được đưa về những nhánh dài hạn phù hợp. GitFlow có nhiều
bước phối hợp hơn, hữu ích khi nhịp phát hành và môi trường cần tách biệt.

## Vì sao 1.0.0 thay vì 0.4.0?

1.0.0 là quyết định công bố hợp đồng sử dụng ổn định đầu tiên cho phạm vi
đã chọn; không phải cứ hoàn thành Lab 04 là SemVer bắt buộc dùng 1.0.0.
Nếu hợp đồng còn thay đổi mạnh, 0.4.0 vẫn phù hợp. Trong bài, 1.0.0 đóng mốc
phát hành để các lab sau thực hành minor 1.1.0 và patch 1.0.1.

## Vì sao nên chuẩn bị release trên nhánh tích hợp?

Tích hợp version, tài liệu và test trước khi tạo nhánh release giúp nhánh phát
hành bắt đầu từ trạng thái đã kiểm tra. Cách này cũng giảm nguy cơ bản sửa chỉ
tồn tại trên release và bị bỏ quên ở dòng phát triển.

## Tag và nhánh release

Annotated tag định danh một baseline cố định; nhánh release có thể tiến lên
khi nhận hotfix. Nếu phát hành bản vá, giữ tag cũ và tạo tag mới thay vì di
chuyển tag đã công bố. Repository `202416418` hiện chưa có tag hoặc nhánh
release.

## Ghi nhận và tái tạo

`git log A..B` liệt kê commit chỉ có ở B; `git diff A B` so snapshot.
`git describe --tags` cho tag tổ tiên gần nhất kèm khoảng cách commit.
Dùng detached HEAD/worktree để chạy lại bản cũ và `git archive` đóng gói.
Repository `202416418` hiện chưa có workflow CI hoặc lịch sử phát hành; các
lệnh này mô tả cách thực hiện khi có tag và nhánh tương ứng.
