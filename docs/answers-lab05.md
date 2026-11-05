# Lab 05 — Hotfix và bảo trì nhiều phiên bản

## Upstream first và release first

Upstream first sửa master trước rồi chuyển về dòng cũ: phiên bản tương lai
chắc chắn có fix, phù hợp khi master được giữ ổn định bằng CI. Đổi lại master
có thể khác nhiều bản đang chạy, nên backport cần điều chỉnh và kiểm thử.

Release first bắt đầu đúng baseline gặp lỗi: phạm vi nhỏ, có thể kiểm tra và
phát hành bản vá khẩn nhanh. Rủi ro là quên đưa fix về master hoặc dòng release
khác. Cần một checklist lan truyền và kiểm toán hành vi ở từng dòng.

## Nếu quên backport thì cách nào phát hiện?

Chạy cùng một kiểm tra hành vi trên từng nhánh hoặc phiên bản được bảo trì;
dòng nào còn lỗi sẽ cho kết quả sai.

`git tag --contains FIX_SHA` chỉ xét quan hệ tổ tiên của đúng commit gốc.
Cherry-pick tạo SHA mới; vì vậy cần so sánh patch hoặc kiểm tra hành vi thay vì
chỉ tìm SHA. `git cherry` có thể giúp phát hiện patch tương đương giữa hai
nhánh.

## Vì sao tách commit sửa lỗi và tăng version?

Chỉ cherry-pick phần mã/test. Nếu chuyển cả commit 1.0.1 lên master đang 1.1.0,
version sẽ bị hạ hoặc xung đột. CHANGELOG cập nhật riêng theo dòng phát hành.

## Vì sao chưa tag v1.1.0 ngay lúc tạo release/lab05?

Nhánh còn cần nhận hotfix và kiểm thử. Tag chỉ được đặt khi baseline sẵn sàng.
Nếu v1.1.0 đã công bố thì phải phát hành v1.1.1, không di chuyển tag cũ.

## Minh chứng trong repository `202416418`

Repository hiện chưa có Issue, nhánh release, tag hoặc commit backport để truy
vết. Các lệnh và giải thích ở trên là hướng dẫn cho quy trình; không dùng SHA
hay số Issue từ repository khác làm bằng chứng. Trước khi nộp, cần tạo và liên
kết minh chứng thực tế nếu bài yêu cầu.
