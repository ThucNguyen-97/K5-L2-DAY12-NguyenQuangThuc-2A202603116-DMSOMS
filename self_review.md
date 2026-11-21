# Tự đánh giá — NguyenQuangThuc · G09

## 1. Tự rà soát 4 cảnh

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| D06 | frame_meta | missing | Ban đầu thiếu tag cho ảnh | có |
| D06 | eye_left / face13 | flag | Mắt không rõ cần đối chiếu unknown với cờ occluded/outside | có |
| S05_rgb | object | wrong_class | Ban đầu để seat=driver trong ảnh chỉ nhìn hàng ghế sau | có |
| S10_ir | frame_meta | missing | Bản extra ban đầu thiếu tag | có |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: quên kiểm tra đủ một `frame_meta` trên từng ảnh.

Vì sao mình mắc: tập trung vào box và thuộc tính đối tượng nên bỏ sót tag của ảnh.

Lần sau tránh bằng cách: tạo `frame_meta` đầu tiên trên mỗi ảnh, sau đó mới gán box; cuối cùng chạy `cabin_check`.

## 3. Ghi chú về disagreement_log

Đã review chéo với Nguyen Cao Ngoc Duc - 2A202603178. Đã xử lý 8 dòng trong disagreement_log.csv; ca S07_ir còn ambiguous để hai bạn xác nhận.

Sau review, đã xoá 6 box `object` khỏi các frame DMS D02–D06 theo GUIDE.md; các box `object` còn lại chỉ thuộc các frame S (OMS). Đã export lại `export_final_v2.zip` và chạy lại kiểm tra: 22 ảnh, 0 lỗi, 0 cảnh báo.
