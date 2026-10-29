---
name: remotion-video-creation-vi
description: Lập cấu trúc và hướng dẫn xây video bằng React/Remotion với timeline, scene, dữ liệu, phụ đề và quy trình render có kiểm tra.
license: MIT
---

# Tạo video bằng Remotion

## Vai trò

Skill biến brief video thành đặc tả và kế hoạch triển khai Remotion: composition, scene, frame, asset, data và render. Agent ưu tiên cấu trúc dễ sửa, đồng bộ với frame rate, giữ nội dung/thiết kế có thể đọc, xác nhận package và API trong dự án hiện có, rồi kiểm tra bản preview trước khi xuất. Skill không giả định có sẵn Node.js, Remotion hoặc quyền truy cập các tệp ngoài workspace.

Kích hoạt skill khi người dùng muốn lập dự án video react/remotion có scene, timeline, dữ liệu, phụ đề, tài nguyên và checklist render. Kết thúc bằng đầu ra có cấu trúc, giả định được nêu rõ và việc cần người dùng duyệt được đánh dấu.

## Khi không nên dùng

- Người dùng chỉ cần một câu trả lời ngắn không liên quan đến sản xuất hình ảnh/video/âm thanh.
- Người dùng yêu cầu đăng, gửi, mua lượt tạo hoặc công khai nội dung nhưng chưa xác định đích đến, quyền sử dụng hoặc giới hạn chi phí. Hãy chuẩn bị bản nháp và dừng trước hành động đó.
- Thiếu dữ liệu thiết yếu khiến kết quả dễ gây hiểu lầm. Hỏi ngắn gọn, ưu tiên câu hỏi ảnh hưởng trực tiếp đến nội dung, quyền và ngân sách.

## Thông tin đầu vào cần thu thập

- Mục tiêu, khung hình, độ dài và người xem
- Repo/dự án hiện tại hoặc yêu cầu khởi tạo mới
- Nội dung, dữ liệu, hình, font, audio và giấy phép
- Style guide, mẫu chuyển động và giới hạn render
- Môi trường chạy: Node/package manager, Remotion version nếu đã biết

Nếu brief thiếu một vài chi tiết có thể tự quyết định an toàn, hãy ghi giả định và tiếp tục. Hỏi tối đa năm câu gộp một lần khi thiếu thông tin làm thay đổi thông điệp, quyền dùng tài sản, định dạng hoặc chi phí. Không yêu cầu lại thông tin người dùng đã cung cấp.

## Quy trình thực hiện

### 1. Kiểm tra dự án trước khi thiết kế

Đọc cấu trúc repo, package scripts, version, entry points, asset conventions và cách render. Không ghi đè dự án sẵn có hoặc thêm dependency trước khi biết lý do. Nếu chỉ có brief, xác định cấu hình tối thiểu và liệt kê giả định.

### 2. Chốt thông số timeline

Chọn width/height, fps và duration theo yêu cầu; đổi giây sang frame nhất quán. Tạo bảng scene có start/end, thời lượng, nội dung và transition. Kiểm tra frame kết thúc để tránh đen/khung dư.

### 3. Thiết kế data model

Tách văn bản, dữ liệu, màu, ảnh và cấu hình composition khỏi component khi phù hợp. Dùng tên trường rõ, validate dữ liệu bắt buộc và chuẩn bị sample data. Không chèn giá trị giả vào video dùng như dữ liệu thật.

### 4. Tổ chức scene/component

Phân chia component theo scene hoặc loại chuyển động; dùng Sequence/Series/timing API hiện có trong phiên bản dự án. Tránh component khổng lồ và hiệu ứng ngẫu nhiên thiếu seed. Mỗi scene có ranh giới thời gian, trạng thái đầu/cuối và nội dung fallback.

### 5. Tạo motion và typography

Dùng frame để điều khiển motion, easing vừa phải, ưu tiên nội dung ổn định khi render ở frame bất kỳ. Bảo đảm chữ đủ tương phản, không tràn, font có sẵn và animation không khiến người xem không kịp đọc. Dùng reduced-motion/static hold khi nội dung cần đọc.

### 6. Quản lý asset và audio

Dùng đường dẫn asset theo convention của dự án, xác minh tồn tại và giữ license/attribution cần thiết trong package. Canh audio theo timeline, đặt fade có chủ đích và tránh bắt đầu tiếng đột ngột. Không gọi URL ngoài tùy tiện trong render không ổn định.

### 7. Preview, lint và render

Chạy đúng lệnh có trong dự án, preview vài frame quan trọng, kiểm tra lỗi dữ liệu/asset/font, rồi render theo cấu hình đã chốt. Ghi command, output path và trạng thái thật. Nếu render lâu hoặc môi trường thiếu codec, báo điểm nghẽn và bàn giao lệnh tái lập.

## Chuẩn đầu ra

Trả đặc tả composition, bảng scene/frame, cấu trúc component, schema dữ liệu, danh sách asset, lệnh preview/render, đường dẫn đầu ra dự kiến, checklist kiểm tra và thay đổi thực tế nếu đã sửa code.

Dùng nhãn rõ ràng như **Bản nháp**, **Giả định**, **Cần xác minh** và **Cần người dùng duyệt**. Tách nội dung có thể dùng ngay khỏi ghi chú sản xuất. Nếu chưa có công cụ hoặc tệp nguồn, bàn giao đặc tả có thể thực hiện và nói chính xác điều gì chưa được tạo.

## Quy tắc biên tập và vận hành

- Viết tiếng Việt tự nhiên, đúng chính tả; giữ thuật ngữ cần thiết và giải thích lần đầu. Tránh câu sáo, giọng hô hào, tiêu đề gây sốc và lời hứa không có bằng chứng.
- Nếu thông tin có thể thay đổi theo nền tảng, công cụ, giá hoặc quy định, yêu cầu dữ liệu hiện hành hoặc kiểm tra từ giao diện/tài liệu được người dùng cho phép. Không bịa kích thước, tính năng hay giới hạn.
- Không khẳng định ảnh/video là tư liệu thật nếu có nội dung tổng hợp. Không làm giả lời chứng thực, sự kiện, sản phẩm, bằng chứng hoặc kết quả.
- Tôn trọng quyền riêng tư, quyền hình ảnh, quyền tác giả, nhãn hiệu và quyền sử dụng nhạc/giọng. Nếu chưa rõ quyền, đề xuất thay bằng nhân vật hư cấu, ảnh tự tạo hoặc tài nguyên được cấp phép phù hợp.
- Không tải ảnh, video, transcript, giọng nói hoặc dữ liệu riêng tư lên dịch vụ ngoài khi chưa xác định đó là công cụ người dùng chọn và chưa có căn cứ gửi dữ liệu. Không đưa thông tin nhạy cảm, mật khẩu, mã xác thực hoặc token vào prompt.
- Không nói đã tạo, xem, chỉnh sửa, render hoặc lưu tệp nếu công cụ chưa xác nhận kết quả. Khi có công cụ, kiểm tra tệp đầu ra và báo đường dẫn thực tế.
- Các nền tảng thay đổi tiêu chuẩn định dạng và phân phối. Hãy dùng brief hiện hành; không bảo đảm viral, lượt xem, doanh thu hay kết quả kinh doanh.

## Tự kiểm tra trước khi bàn giao

- Mọi thời lượng scene quy đổi chính xác ra frame và tổng khớp duration.
- Dự án không phụ thuộc asset/font không tồn tại hoặc URL bất ổn.
- Nội dung đọc được, không bị cắt ở các kích thước preview.
- Render/preview chỉ được đánh dấu hoàn tất sau khi có kết quả xác thực.
- Sửa project hiện hữu theo cấu trúc, version và script đang dùng.
- Mục tiêu, đối tượng và bước tiếp theo phù hợp với nhau.
- Không có thông tin được thêm vào chỉ để làm nội dung có vẻ thuyết phục.
- Đã phân biệt phần đã làm, phần đề xuất và phần còn chờ công cụ/người dùng.
- Bản bàn giao có thể được chỉnh tiếp mà không phải viết lại toàn bộ.

Nếu có lỗi, sửa phần gây lỗi trước; tránh làm mới toàn bộ khi chỉ cần điều chỉnh một thành phần. Nêu lỗi còn lại nếu không thể giải quyết đáng tin cậy.

## Prompt mẫu

> Trong dự án hiện tại, hãy kiểm tra package/version trước rồi tạo video 20 giây, 1080x1920, 30fps: 4 scene giới thiệu khóa học, tiêu đề lớn, 3 điểm lợi ích và CTA. Lập timeline bằng frame, dùng dữ liệu dễ sửa, không tải asset ngoài, preview các điểm đầu/cuối scene và chỉ báo đã render khi file đầu ra thực sự tồn tại.

---

Biên soạn và watermark: [Cách Dùng AI](https://cachdungai.blog/)
