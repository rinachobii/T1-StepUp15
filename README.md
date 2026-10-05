# Step Up 15+ Tracker

Web song ngữ EN/VI theo dõi chương trình Step Up 15+ (05/10/2026 – 31/12/2026). Mặc định hiển thị tiếng Anh.
Bilingual tracker for the Step Up 15+ program. English by default.

```
index.html        ← web của team (4 tab: My log · Leaderboard · Viral · Scoring)
huong-dan.html    ← trang hướng dẫn vận hành, KHÔNG có link trong menu của team
apps-script.gs    ← code backend Google Sheets
fonts/            ← Metropolis WOFF2 × 6 weight — bắt buộc upload kèm
```

Toàn bộ hướng dẫn chi tiết (lưu trữ dữ liệu, nối Google Sheets 9 bước, publish, xuất/nhập file)
nằm trong `huong-dan.html` — mở bằng trình duyệt hoặc truy cập
`https://<tài-khoản>.github.io/<repo>/huong-dan.html`.

---

## Tóm tắt

**Dữ liệu lưu ở đâu**
- Mặc định: `localStorage` của từng trình duyệt — không chia sẻ được.
- Sau khi điền `const API_URL = "..."` trong `index.html`: ghi thẳng vào Google Sheet của team
  (3 tab tự sinh: `Log`, `Posts`, `Config`).

**Cách tính điểm** — điểm chỉ cộng khi hoàn thành trọn một Level.

| Đi bộ / Chạy (≥1 km/buổi) | | Cầu lông · Bóng đá · Pickleball (≥30 phút/buổi) | |
|---|---|---|---|
| 100 km | 100đ | 13 buổi | 130đ |
| 200 km | 200đ | 26 buổi | 260đ |
| 300 km | 300đ | 52 buổi | 520đ |
| 400 km | 400đ | 65 buổi | 650đ |
| 500 km | 500đ | 78 buổi | 780đ |

Mục tiêu cá nhân: **300 điểm**.

**Minh chứng & xác minh** — khi ghi nhận buổi tập, mỗi người chọn 1 trong 3:
`Chưa nộp` · `📁 Đã up lên Drive` · `💬 Đã gửi group Zalo`. Chọn Drive hoặc Zalo thì bản ghi
tự chuyển sang ✅ Đã xác minh. Mỗi người tự đổi trạng thái bản ghi của mình, không có bước duyệt
trung gian, và mọi bản ghi đều được tính điểm.

**Chiến lược giải Viral** (tab Viral)
1. Tất cả thành viên: up ảnh/video lên Drive hoặc gửi group Zalo, rồi chọn đúng mục đó khi ghi nhận buổi tập.
2. Mai Phương · Phương Thảo · Ánh Đào: lấy source từ kho chung, chia nhau đăng MXH kèm
   `#StepUp15+ #Handong15thAnniversary`.
3. Sau khi đăng: ghi nhận link bài vào tab Viral — chỉ số giải Viral tự cập nhật
   (tổng bài đăng + số thành viên khác nhau đóng góp ảnh).

**Buổi tập chung** (tab Scoring) — ghi nhận từng buổi cả team cùng tập theo format
`ngày · loại hoạt động · số thành viên tham gia`. App tự tính TB thành viên/buổi và số buổi ≥ 5 người,
đổ thẳng vào chỉ số giải Best Team Engagement. Không còn ô nhập tay tổng hợp.

**Sửa bản ghi** — mỗi dòng trong Lịch sử luyện tập có nút ✏️ để sửa ngày, môn, số liệu và cách nộp
minh chứng; nút ✕ để xóa.

**Font** — Metropolis 6 weight (400–900), WOFF2, ~120 KB, nhúng trong `fonts/`. Không phụ thuộc Google Fonts.
