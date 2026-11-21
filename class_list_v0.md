# Danh sách lớp v0 — NguyenQuangThuc · G09

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | eye_state | open / closed / unknown | Phát hiện buồn ngủ và nhắm mắt kéo dài | Có, nhưng có thể bị che bởi kính/phản xạ |
| 2 | glasses | none / clear / sun / unknown | Điều chỉnh cảnh báo và đánh giá độ tin cậy vùng mắt | Có thể, không phải lúc nào cũng chắc |
| 3 | gaze_zone | road / mirror / cluster / center / lap / other | Phát hiện nhìn lệch hướng hoặc mất tập trung | Có theo hướng đầu/mắt, nhưng khó hơn |
| 4 | face | bounding box | Xác định vùng mặt để theo dõi tài xế | Có nếu mặt đủ sáng và không bị che |
| 5 | hand_side | left / right | Theo dõi tay nào đang thao tác | Có theo hình dạng/vị trí |
| 6 | phone_state | held / mounted / lap | Phát hiện tài xế đang sử dụng điện thoại | Có theo hình dạng, không dựa màu |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | infant_seat | seat + facing | Nhắc phát hiện ghế/nôi em bé và hỗ trợ an toàn ghế | Có theo hình dạng |
| 2 | child_seat | seat + occupied | Phát hiện ghế trẻ em còn trong xe | Có theo hình dạng |
| 3 | person | seat + seatbelt | Biết ghế nào có người và tình trạng dây an toàn | Có theo hình dạng; dây có thể khó thấy |
| 4 | object | seat + type | Phát hiện đồ vật để cảnh báo đồ bỏ quên | Thường có theo hình dạng, màu bị mất |
| 5 | seat | rear_left / rear_middle / rear_right | Định vị người/vật theo ghế của xe | Có theo vị trí |
| 6 | frame_meta.modality | rgb / ir | Phân biệt nguồn ảnh để diễn giải nhãn đúng | Có từ tên/nguồn ảnh, không phải nội dung thị giác |

## 2 câu hỏi leo thang

1. Câu hỏi: Khi một đồ vật nằm sát ranh giới giữa hai ghế, ưu tiên ghế có tâm vật hay ghế mà vật tiếp xúc nhiều hơn?
   Khung ví dụ: S05_rgb
   Bạn tạm gán thế nào và vì sao: Gán theo ghế mà vật nằm/tiếp xúc chính, nếu không chắc chọn theo ngữ cảnh và ghi chú.
2. Câu hỏi: Khi mắt bị phản xạ che một phần nhưng vẫn đoán được vị trí, nên dùng `occluded` hay `outside`?
   Khung ví dụ: D06
   Bạn tạm gán thế nào và vì sao: Dùng `occluded` nếu xác định được vị trí điểm; dùng `outside` nếu không thể xác định chắc.
