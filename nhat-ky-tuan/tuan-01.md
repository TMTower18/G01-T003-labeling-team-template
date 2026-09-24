# Nhật ký tuần 01 · 15/09 – 21/09/2026

**Lead BBOX:** [@TMTower18](https://github.com/TMTower18)  
**Lead Segmentation:** [@hoanghoang203205](https://github.com/hoanghoang203205)  
**Dữ liệu / task CVAT:** Ảnh giao thông đô thị — [Task 122](https://cvat.note.transformerlabs.ai/tasks/122?page=1&pageSize=10) 
— [Task 176](https://cvat.note.transformerlabs.ai/tasks/176?page=1&pageSize=10 ) 

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Nguyễn Tuấn Minh ([@TMTower18](https://github.com/TMTower18)) | Lead BBOX · Reviewer · Annotator | Lead nhóm BBOX; Gán Job 1554, Review Job 1559; hỗ trợ chốt edge case và review 10% các job BBOX |
| Vũ Huy Hoàng ([@hoanghoang203205](https://github.com/hoanghoang203205)) | Lead Segmentation · Reviewer · Annotator | Lead nhóm Segmentation; Gán Job 1338, Review Job 1340; hỗ trợ chốt edge case và review 10% các job Segmentation |
| Nguyễn Lâm Bách ([@BachNguyen-hub](https://github.com/BachNguyen-hub)) | Reviewer · Annotator | Gán Job 1339 và 1556; Review Job 1341 và 1557 |
| Hoàng Trần Minh Đức ([@minhducht239](https://github.com/minhducht239)) | Reviewer · Annotator | Gán Job 1340 và 1557; Review Job 1339 và 1556 |
| Nguyễn Vũ Quang Minh ([@qungmnh-udev](https://github.com/qungmnh-udev)) | Reviewer · Annotator | Gán Job 1341 và 1559; Review Job 1338 và 1554 |

## Công việc

| # | Nội dung công việc | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | BBOX — Job #1338 — 25 frames, frame 0–24 | [@hoanghoang203205](https://github.com/hoanghoang203205) | [@qungmnh-udev](https://github.com/qungmnh-udev) | ✅ xong | Pass |
| 2 | BBOX — Job #1339 — 25 frames, frame 25–49 | [@BachNguyen-hub](https://github.com/BachNguyen-hub) | [@minhducht239](https://github.com/minhducht239) | ✅ xong | Pass |
| 3 | BBOX — Job #1340 — 25 frames, frame 50–74 | [@minhducht239](https://github.com/minhducht239) | [@hoanghoang203205](https://github.com/hoanghoang203205) | ✅ xong | Pass |
| 4 | BBOX — Job #1341 — 25 frames, frame 75–99 | [@qungmnh-udev](https://github.com/qungmnh-udev) | [@BachNguyen-hub](https://github.com/BachNguyen-hub) | 🟡 8% | Chưa làm xong |
| 5 | Segmentation — Job #1554 — 25 ảnh | [@TMTower18](https://github.com/TMTower18) | [@qungmnh-udev](https://github.com/qungmnh-udev) | ✅ xong | Pass |
| 6 | Segmentation — Job #1557 — 25 ảnh | [@minhducht239](https://github.com/minhducht239) | [@BachNguyen-hub](https://github.com/BachNguyen-hub) | ✅ xong | Pass |
| 7 | Segmentation — Job #1556 — 25 ảnh | [@BachNguyen-hub](https://github.com/BachNguyen-hub) | [@minhducht239](https://github.com/minhducht239) | 🟡 36% | Chưa làm xong |
| 8 | Segmentation — Job #1559 — 25 ảnh | [@qungmnh-udev](https://github.com/qungmnh-udev) | [@TMTower18](https://github.com/TMTower18) | 🟡 56% | Chưa làm xong|
| 9 | Đọc lại Annotation Guideline và gom các ca chưa rõ | [@TMTower18](https://github.com/TMTower18) · [@hoanghoang203205](https://github.com/hoanghoang203205) | — | ✅ xong | Tổng hợp edge case P-001 → P-007 |
| 10 | Đưa ra các quyết định dựa trên guideline và hướng dẫn của mentor cho các edge case | [@TMTower18](https://github.com/TMTower18) · [@hoanghoang203205](https://github.com/hoanghoang203205) | — | ✅ xong | Tổng hợp và ghi nhận QĐ-001 → QĐ-008 trong `decision-log.md` |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đang làm (ghi %) · ⛔ bị chặn (ghi lý do) · ⬜ chưa bắt đầu

## Tổng kết

- BBOX — Job #1338–#1341: **77 / 100 ảnh (77%)**
- Segmentation — Job #1554–#1559: **73 / 100 ảnh (73%)**
- **Tổng cộng: 150 / 200 ảnh (75%)**
- Còn lại: **50 / 200 ảnh (25%)**
- Qua review lần đầu: **43%** (trả lại 85 ảnh) 
- Edge case mới: **P-001 → P-009**

## Vướng mắc

- **P-001:** Chưa rõ cách xử lý pixel của dây điện khi dây điện nằm trên vùng `sky` nhưng không thuộc danh sách class.

- **P-002:** Một số phương tiện ở quá xa hoặc quá mờ khiến annotator không thể xác định chắc chắn `car`, `truck` hay `bus`.

- **P-003:** Chưa có quy tắc cụ thể cho trường hợp `lane/double white` xuất hiện cùng hoặc giao với vạch xương cá.

- **P-004:** Chưa rõ biển chỉ dẫn lối ra có nằm trong phạm vi của class `traffic_sign` hay không.

- **P-005:** Chưa rõ mép của dải/đảo phân cách có được xem và annotate thành `lane/road curb` hay không.

- **P-006:** Chưa có định nghĩa đủ cụ thể để phân biệt ranh giới giữa `area/drivable` và `area/alternative` trong một số tình huống thực tế.

- **P-007:** Với object bị che khuất phần lớn, cần thống nhất việc chỉ annotate phần nhìn thấy hay suy đoán phần boundary bị che.

- **P-008:** Chưa rõ phần đường dẫn từ đường chính đi vào cây xăng, nơi phương tiện vẫn có thể di chuyển bình thường, có được annotate là `area/drivable` hay không.

- **P-009:** Chưa rõ cách phân chia class khi `fence` nằm trực tiếp phía trên `wall`: tách riêng phần `fence` và `wall` hay xem toàn bộ cấu trúc là một class duy nhất.


## Kế hoạch tuần 02

- Tiếp tục gán nhãn phần còn lại của Job Segmentation.
- Hoàn tất review chéo và sửa chữa các Job BBOX và Segmentation.
- Áp dụng thống nhất các quyết định.
- Tiếp tục ghi nhận edge case mới vào `problem-backlog.md`.
- Nếu quyết định hiện tại thay đổi sau khi mentor/BTC phản hồi, tạo quyết định mới thay vì sửa quyết định cũ.