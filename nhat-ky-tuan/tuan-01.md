# Nhật ký tuần 01 · 15/09 – 21/09/2026

**Lead tuần này:** [@TMTower18](https://github.com/TMTower18)
**Dữ liệu / task CVAT:** Ảnh giao thông đô thị — [task 122](https://cvat.note.transformerlabs.ai/tasks/122?page=1&pageSize=10)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Nguyễn Tuấn Minh ([@TMTower18](https://github.com/TMTower18)) | Lead | Chia job, chốt edge case, review xác suất 10% mọi job |
| Nguyễn Lâm Bách [@BachNguyen-hub](https://github.com/BachNguyen-hub) | Reviewer · Annotator | Gán job 1339, Review job 1341 |
| Vũ Huy Hoàng (@thanh-vien-b) | Reviewer · Annotator | Gán job 1338, Review job 1340 |
| Hoàng Trần Minh Đức (@thanh-vien-b) | Reviewer · Annotator | Gán job 1340, Review job 1339 |
| Nguyễn Vũ Quang Minh (@thanh-vien-b) | Reviewer · Annotator | Gán job 1341, Review job 1338|


## Công việc

| # | Nội dung công việc | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | Job #1338 — 25 frames, frame 0–24 | @Vũ Huy Hoàng | @Nguyễn Vũ Quang Minh | ⬜ 0% | Chưa bắt đầu |
| 2 | Job #1339 — 25 frames, frame 25–49 | [@BachNguyen-hub](https://github.com/BachNguyen-hub) | @Hoàng Trần Minh Đức | ⬜ 0% | Chưa bắt đầu |
| 3 | Job #1340 — 25 frames, frame 50–74 | @Hoàng Trần Minh Đức | @Vũ Huy Hoàng | ⬜ 0% | Chưa bắt đầu |
| 4 | Job #1341 — 25 frames, frame 75–99 | @Nguyễn Vũ Quang Minh | ([@qungmnh-udev](https://github.com/qungmnh-udev)) | ⬜ 7% | Đang làm |
| 5 | Đọc lại Annotation Guideline và gom các ca chưa rõ | [@TMTower18](https://github.com/TMTower18) | ----- | ⬜ 0% | Chưa bắt đầu |


Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đang làm (ghi %) · ⛔ bị chặn (ghi lý do) · ⬜ chưa bắt đầu

## Tổng kết

- Đã gán: 0 / 100 ảnh (34%)
- Qua review lần đầu: 0% (trả lại 0 ảnh)
- Edge case mới: P-001, P-002, P-003 — đã chốt P-001 thành [QĐ-001](../so-quyet-dinh.md#qđ-001)

## Vướng mắc

- P-002 (xe bị che khuất) chưa chốt nên job 103 phải dừng. Lead đã gửi câu hỏi lên BTC.
- P-003: vẽ lại box y hệt qua các frame liên tiếp mất ~40% thời gian job 105.
  Đang cân nhắc làm tool trong [`source-tool/`](../source-tool/).

## Kế hoạch tuần 02

- Chốt P-002, mở lại job 103.
- Xong job 102, 104, 105.
- Quyết định có làm tool cho P-003 hay dùng chế độ Track sẵn có của CVAT.
