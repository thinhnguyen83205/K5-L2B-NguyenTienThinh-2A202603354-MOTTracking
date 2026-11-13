# Báo cáo cá nhân — Nguyễn Tiến Thịnh

Đoạn video: MOT17-09, 150 frame (frame CVAT 0–149; frame MOT 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên: Nguyễn Tiến Thịnh
- MSSV: 2A202603354
- Mã đề (A/B/C): A
- Email: 26ai.thinhnt@vinuni.edu.vn
- Link repository: https://github.com/thinhnguyen83205/K5-L2B-NguyenTienThinh-2A202603354-MOTTracking
- Giờ bắt đầu: 16:00
- Giờ kết thúc: 19:30

## 1. Xem trước đoạn video (CP0)

Các frame xuất hiện/kết thúc và khoảng `outside` dưới đây lấy từ file xuất, dùng chỉ số CVAT bắt đầu từ 0; chúng không thay thế ghi chú CP0 trước khi vẽ. Kết quả kiểm tra không cho biết frame rẽ/đổi tốc độ hoặc các frame `occluded` một phần.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---:|---:|---|---|---|
| P1 | 0 | 149 | Chưa có dữ liệu | — | — |
| P2 | 0 | 109 | Chưa có dữ liệu | — | — |
| P3 | 0 | 146 | Chưa có dữ liệu | `outside`: 111–134 | — |
| P4 | 0 | 139 | Chưa có dữ liệu | `outside`: 120–129 | — |
| P5 | 0 | 149 | Chưa có dữ liệu | `outside`: 40–47 | — |

## 2. Keyframe và thời gian (CP1, CP4)

P1–P5 lần lượt tương ứng với track ID 1–5 trong `gt.txt` và track 0–4 trong CVAT. Frame keyframe dưới đây dùng chỉ số CVAT, bắt đầu từ 0. Số keyframe, frame có mặt và tỷ lệ lấy từ `src/check_submission.py`; thời gian và chỗ khó cần điền theo thực tế.

| Mã | Số keyframe | Keyframe ở frame (CVAT) | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---:|---|---:|---:|---|---|
| P1 | 17 | 0, 10, 20, 30, 39, 49, 59, 69, 79, 89, 99, 109, 119, 129, 130, 139, 149 | 150 | 11.3 | | |
| P2 | 8 | 0, 10, 20, 40, 50, 60, 70, 100 | 110 | 7.3 | | |
| P3 | 12 | 0, 10, 20, 30, 40, 50, 106, 110, 135, 140, 142, 143 | 123 | 9.8 | | |
| P4 | 14 | 0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 98, 100, 110, 130 | 130 | 10.8 | | |
| P5 | 23 | 0, 10, 11, 20, 22, 30, 48, 50, 54, 55, 56, 58, 60, 70, 80, 90, 98, 100, 110, 120, 130, 140, 149 | 142 | 16.2 | | |
| **Tổng** | **74** | — | **655** | **11.3** | | |

Keyframe / 100 frame của cả bài = 74 ÷ 655 × 100 = **11.3 keyframe / 100 frame**.

P5 có nhiều keyframe nhất (23 keyframe; 16.2 keyframe / 100 frame). Cần bổ sung lý do quan sát thực tế, chẳng hạn người đó rẽ, đổi tốc độ, lại gần camera hay bị che.

## 3. Đoạn bị che (CP2)

CP2 dùng P4 (CVAT track 3, track ID 4 trong `gt.txt`). Kết quả xuất cho biết P4 vắng ở frame 120–129 (chỉ số CVAT) và có tổng cộng 62 frame bật `occluded`, nhưng không cho biết chính xác các mốc bật/tắt `occluded`.

Người bị che: `P4`

| Mốc | Frame CVAT |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | Chưa xác định từ kết quả tổng hợp |
| Mất hẳn (bật `outside`) | 120 |
| Hiện lại (tắt `outside`) | 130 |
| Thấy rõ trở lại (tắt `occluded`) | Chưa xác định từ kết quả tổng hợp |

- Thời gian khuất hẳn: 10 frame = khoảng 0.33 giây (nếu video 30 FPS).
- Quyết định: giữ cùng ID, như ảnh minh họa sau khi hiện lại.
- Lý do (3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):

  Khoảng `outside` kéo dài 10 frame, ngắn hơn mốc 60 frame. Tôi giữ cùng ID như ảnh minh họa sau khi người đó hiện lại. Cần đối chiếu trực tiếp trên CVAT để xác nhận ngoại hình, hướng và tốc độ tại frame 130 trước khi chốt phần nhận xét này.

Ảnh chụp màn hình:

![Trước khi che](images/che_1_truoc.png)
![Giữa đoạn che, thấy cờ trên panel object](images/che_2_giua.png)
![Sau khi hiện lại, cùng ID](images/che_3_sau.png)

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Đã kiểm tra cả hai lượt và không phát hiện lỗi ID.

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| — | — | — | Đã kiểm hai lượt, không lỗi. | Lượt 1 và lượt 2 | Không áp dụng |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Không có lỗi nào chỉ lượt 2 mới phát hiện vì cả hai lượt đều không phát hiện lỗi. Lượt 2 giúp xem các track trong bối cảnh toàn cảnh, đặc biệt hữu ích để kiểm tra nhầm ID giữa những người ở gần nhau.

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 | `NguyenTienThinh_mot.zip` |
| Tên file CVAT for video 1.1 | `NguyenTienThinh_cvat_video.zip` |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | 5 — đạt |
| Frame `outside` không có dòng trong `gt.txt` | Đạt theo kết quả kiểm tra: 0 lỗi, 0 cảnh báo |
| Job đã completed trên CVAT máy cá nhân | Chưa xác minh bằng kết quả `check_submission.py`; kiểm tra trên CVAT |

Tóm tắt in ra từ `src/check_submission.py`:

```text
Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: NguyenTienThinh_mot.zip ===
  Số track ID: 5   |   Tổng số box: 655
  [OK]        Đúng 5 track ID.

  Track | Frame có mặt | Số frame | Đoạn vắng (outside)
      1 |   0–149      |      150 | -
      2 |   0–109      |      110 | -
      3 |   0–146      |      123 | 111–134
      4 |   0–139      |      130 | 120–129
      5 |   0–149      |      142 | 40–47


=== File CVAT for video 1.1: NguyenTienThinh_cvat_video.zip ===

  Track | Nhãn   | Frame thấy | Keyframe | KF/100 frame | Frame occluded | Lần bật outside
      0 | person |        150 |       17 |         11.3 |              9 |               0
              Track 0: keyframe ở frame [0, 10, 20, 30, 39, 49, 59, 69, 79, 89, 99, 109, 119, 129, 130, 139, 149]
      1 | person |        110 |        8 |          7.3 |             10 |               1
              Track 1: keyframe ở frame [0, 10, 20, 40, 50, 60, 70, 100]
      2 | person |        123 |       12 |          9.8 |             15 |               2
              Track 2: keyframe ở frame [0, 10, 20, 30, 40, 50, 106, 110, 135, 140, 142, 143]
      3 | person |        130 |       14 |         10.8 |             62 |               2
              Track 3: keyframe ở frame [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 98, 100, 110, 130]
      4 | person |        142 |       23 |         16.2 |             66 |               1
              Track 4: keyframe ở frame [0, 10, 11, 20, 22, 30, 48, 50, 54, 55, 56, 58, 60, 70, 80, 90, 98, 100, 110, 120, 130, 140, 149]

  Tổng: 74 keyframe / 655 frame có mặt = 11.3 keyframe / 100 frame
  [OK]        Đọc được 5 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 0
  Đạt. Dán phần tóm tắt này vào báo cáo mục 5.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   Tôi sẽ kiểm tra và cân nhắc thêm keyframe ở các khoảng cách xa giữa hai keyframe, nhất là P2 khoảng frame 20–40 và P3 khoảng frame 50–106, nếu người đó vẫn hiện diện và chuyển động thay đổi. Keyframe bổ sung ở giữa các khoảng này giúp hạn chế box bị trôi khi nội suy. Với P5, tôi sẽ chỉ thêm keyframe nếu lúc review thấy box không bám sát người, vì track này đã có 23 keyframe.

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   Tôi chưa chắc chắn ở đoạn người xuất hiện lại sau khi bị che khuất. Tôi giữ cùng ID khi nhận diện đó là cùng người và ghi nhận các cờ `occluded`/`outside` trong track; các ảnh minh họa CP2 cũng thể hiện người đó xuất hiện lại với cùng ID. Khi gặp trường hợp tương tự, cần đối chiếu thêm ngoại hình, hướng di chuyển và tốc độ trước khi quyết định.

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   Nếu một người bị gán ID mới sau khi khuất rồi xuất hiện lại, hệ thống có thể xem đó là hai người khác nhau, làm đứt quãng lịch sử vị trí và dự đoán sai hướng hoặc tốc độ di chuyển. Lỗi đổi ID thường ảnh hưởng IDF1 rõ hơn vì IDF1 đánh giá tính nhất quán của danh tính qua các frame; MOTA cũng bị ảnh hưởng do có tính đến lỗi ID switch.

## Bonus (nếu làm)

### B1 — Hai người đi sát

Ở frame 35, Person ID 1 và Person ID 7 đi gần nhau; Person ID 7 che khuất một phần Person ID 1. Tôi giữ nguyên ID của cả hai, đánh dấu Person ID 1 là `occluded` và tiếp tục gán nhãn bình thường cho Person ID 7. Không tạo Track ID mới cho người bị che, nhằm duy trì ID riêng và tính liên tục của track.

### B2 — So cách đặt keyframe

| Cách đặt | Số keyframe | Frame trôi nhất | Ghi chú |
|---|---:|---:|---|
| Đều mỗi 30 frame | — | — | Chưa thực hiện so sánh |
| Theo chỗ đổi hướng | — | — | Chưa thực hiện so sánh |

### B3 — So với tracker có sẵn

| Frame | Mã người | Tracker làm gì | Nhãn của bạn | Giải thích (đoán rồi sửa / ghép IoU / box score thấp / ngoại hình) |
|---:|---|---|---|---|
| 35 | Person ID 1 | Chưa chạy tracker tự động | `person`, giữ ID 1, `occluded=true` | Đây là gán nhãn thủ công; chưa có kết quả tracker để so sánh. |

Tôi chưa chạy Tracker tự động. Việc giữ ID 1 và đánh dấu `occluded` là quyết định gán nhãn thủ công trên CVAT, không phải kết quả của Tracker.

## 7. Tài liệu tham khảo và công cụ AI đã dùng

- MOTChallenge, bộ dữ liệu MOT17-09 (giấy phép CC BY-NC-SA 3.0).
- CVAT, dùng để gán nhãn video và xuất dữ liệu.
- `src/check_submission.py`, dùng để kiểm tra hai file xuất.
