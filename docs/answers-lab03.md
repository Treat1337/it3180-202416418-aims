# Lab 03 — Bugfix, conflict và hoàn tác

## Merge base là gì?

Merge base là tổ tiên chung tốt nhất của hai commit: không có một tổ tiên
chung khác là hậu duệ của nó. Git dùng baseline này để thực hiện three-way
merge: so sánh từng phía với tổ tiên rồi kết hợp. Lịch sử criss-cross phức tạp
có thể có nhiều merge base, nên 'luôn đúng một commit gần nhất' là chưa đầy đủ.
Xem bằng `git merge-base <nhánh-A> <nhánh-B>`.

## Vì sao master và release cần revert?

Các nhánh này đã được chia sẻ và có baseline/tag phụ thuộc. Reset hoặc rebase
làm đổi lịch sử người khác đang sử dụng. Revert thêm commit đảo ngược nhưng
giữ dấu vết thay đổi và lý do hoàn tác. Revert merge dùng `-m 1` để chọn cha
thứ nhất (master trước merge) làm đường chính; phải kiểm tra các cha trước.

## Minh chứng trong repository `202416418`

Repository hiện chỉ có nhánh `main`; chưa có Issue, PR, hoặc lịch sử nhánh
thể hiện các bước test-fail/fix, xử lý conflict hay revert. Không dùng SHA hoặc
số PR từ repository khác làm minh chứng cho bài này. Bộ test hiện có gồm 9 test
và chạy thành công; xem [đối chiếu bài nộp](submission-checklist.md) để biết
trạng thái đã xác minh.

Reset soft giữ thay đổi ở staging; mixed đưa về working tree; hard loại bỏ
thay đổi trong các tệp được theo dõi. Reflog là nhật ký local, có thời hạn lưu,
không phải bản sao lưu và không được push lên GitHub.
