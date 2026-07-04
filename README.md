# 📈 Hệ Thống Tiêu Chí Giao Dịch Scalping Forex (M1/M3/M5/M15) — RSI & MACD

Bộ tài liệu tổng hợp tiêu chí giao dịch cho phong cách **scalping đa khung thời gian M1/M3/M5/M15**, dựa trên nguyên tắc RSI–MACD (phân kỳ/hội tụ, đồng thuận đa khung, quản lý lệnh) và nguyên tắc xây dựng hệ thống giao dịch cá nhân. Có kèm minh họa biểu đồ và file nhật ký giao dịch dùng cho tài khoản **Exness**.

## 📂 Cấu trúc repo

```
forex-scalping-system/
├── README.md                                    ← file này
├── docs/
│   ├── 01-he-thong-tieu-chi-giao-dich.md        ← Tài liệu chính: đầy đủ nguyên tắc + tiêu chí + hình minh họa
│   └── 02-checklist-nhanh.md                     ← Checklist rút gọn để in/dán màn hình
├── images/
│   ├── 01-phan-ky-giam-rsi.svg                   ← Minh họa phân kỳ giảm RSI
│   ├── 02-hoi-tu-tang-rsi.svg                     ← Minh họa hội tụ tăng RSI
│   ├── 03-macd-histogram-phan-ky.svg              ← Minh họa phân kỳ MACD Histogram
│   ├── 04-da-khung-thoi-gian.svg                  ← Minh họa quy trình đa khung M15→M5→M3→M1
│   └── 05-vi-du-setup-vao-lenh.svg                ← Ví dụ setup vào lệnh đầy đủ tiêu chí
└── templates/
    └── trade_journal_exness.xlsx                  ← File Excel nhật ký/tổng hợp lệnh giao dịch Exness
```

## 🚀 Bắt đầu từ đâu

1. Đọc [`docs/01-he-thong-tieu-chi-giao-dich.md`](docs/01-he-thong-tieu-chi-giao-dich.md) để hiểu toàn bộ logic hệ thống.
2. In hoặc mở song song [`docs/02-checklist-nhanh.md`](docs/02-checklist-nhanh.md) khi giao dịch thực tế.
3. Dùng [`templates/trade_journal_exness.xlsx`](templates/trade_journal_exness.xlsx) để ghi lại **mọi** lệnh — mục tiêu tối thiểu ~100 lệnh có ghi chép trước khi kết luận hệ thống có phù hợp với bạn hay không.
4. Sau mỗi 20–30 lệnh, xem lại sheet "Dashboard" trong file Excel để đánh giá Win Rate, R:R trung bình và điều chỉnh lại tiêu chí nếu cần.

## ⚠️ Tuyên bố miễn trừ trách nhiệm

Tài liệu này mang tính chất **tổng hợp kiến thức & giáo dục cá nhân**, không phải lời khuyên đầu tư/tài chính. Giao dịch Forex có sử dụng đòn bẩy tiềm ẩn rủi ro mất vốn cao. Bạn cần tự backtest, forward-test trên tài khoản demo, và chịu trách nhiệm hoàn toàn với quyết định giao dịch của mình.

## 📤 Hướng dẫn đưa repo này lên GitHub

Xem hướng dẫn chi tiết ở cuối phản hồi của trợ lý, hoặc chạy nhanh:

```bash
cd forex-scalping-system
git init
git add .
git commit -m "Initial commit: he thong tieu chi giao dich scalping forex M1-M15"
git branch -M main
git remote add origin https://github.com/<username>/<ten-repo>.git
git push -u origin main
```
