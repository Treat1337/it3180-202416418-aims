# Chạy lại bài thực hành

## 1. Lấy repository và chạy chương trình

```console
git clone https://github.com/Treat1337/it3180-202416418-aims.git
cd it3180-202416418-aims
python main.py
python -m unittest discover -s tests -v
```

Demo in tổng giỏ hàng 63.89 USD; bộ test hiện có gồm 9 test.

## 2. Kiểm tra trạng thái Git hiện tại

```console
git branch -a
git tag -n
git log --oneline --graph --all
```

Repository hiện dùng nhánh `main`. Chưa có nhánh release, tag phát hành hoặc
lịch sử PR trong repository này; vì vậy các quy trình nhiều nhánh và release
trong câu trả lời Lab là nội dung giải thích, không phải lịch sử có thể checkout
tại đây.

## 3. Tự giải thích trước khi nộp

- Vì sao nên dùng `git mv` và `git log --follow` khi di chuyển tệp?
- Khi nào nên dùng merge, squash hoặc rebase and merge cho PR?
- Vì sao không nên viết lại lịch sử của nhánh đã chia sẻ?
- Merge base giúp Git giải quyết conflict như thế nào?
- Khi nào nên dùng revert thay vì reset?
- Tag khác nhánh release ở điểm nào?
- Vì sao cần kiểm tra và ghi nhận backport trên từng dòng phiên bản?

Trạng thái review và nộp bài cần được xác nhận riêng trên GitHub và LMS; xem
[đối chiếu bài nộp](submission-checklist.md).
