# Tạo video bằng Remotion

Lập dự án video React/Remotion có scene, timeline, dữ liệu, phụ đề, tài nguyên và checklist render.

## Skill này giúp gì?

Skill biến brief video thành đặc tả và kế hoạch triển khai Remotion: composition, scene, frame, asset, data và render. Agent ưu tiên cấu trúc dễ sửa, đồng bộ với frame rate, giữ nội dung/thiết kế có thể đọc, xác nhận package và API trong dự án hiện có, rồi kiểm tra bản preview trước khi xuất. Skill không giả định có sẵn Node.js, Remotion hoặc quyền truy cập các tệp ngoài workspace.

## Nội dung gói

- `SKILL.md`: quy trình chi tiết, đầu vào, đầu ra và tiêu chí tự kiểm tra.
- `README.md`: hướng dẫn cài và prompt bắt đầu.
- `LICENSE`: giấy phép MIT.

## Cách cài và dùng

1. Tải ZIP rồi giải nén; giữ nguyên thư mục có `SKILL.md`.
2. Mở phần Skills/Agent Skills của ứng dụng AI đang dùng và thêm thư mục hoặc tải gói theo hướng dẫn trong ứng dụng. Nếu ứng dụng chưa hỗ trợ nạp skill, dán nội dung `SKILL.md` vào chỉ dẫn của một cuộc trò chuyện/dự án và dùng prompt mẫu bên dưới.
3. Bắt đầu cuộc trò chuyện bằng mục tiêu, người xem, nền tảng, giới hạn và tệp tham chiếu bạn có quyền sử dụng. Không gửi mật khẩu, mã xác minh, token hoặc dữ liệu khách hàng không cần thiết.
4. Đọc phần **Giả định** và **Cần người dùng duyệt**. Kiểm tra kỹ quyền dùng tài nguyên, dữ liệu, giá và quy định hiện hành trước khi tạo tệp tốn phí hoặc đăng công khai.
5. Lặp lại bằng cách nêu một thay đổi cụ thể; yêu cầu Agent giữ nguyên những phần đã duyệt.

Cách nạp skill khác nhau giữa ứng dụng và tài khoản. Hãy làm theo giao diện hiện hành của ChatGPT, Claude hoặc Agent khác; đừng giả định một nút cài đặt giống nhau có ở mọi gói.

## Prompt bắt đầu

> Trong dự án hiện tại, hãy kiểm tra package/version trước rồi tạo video 20 giây, 1080x1920, 30fps: 4 scene giới thiệu khóa học, tiêu đề lớn, 3 điểm lợi ích và CTA. Lập timeline bằng frame, dùng dữ liệu dễ sửa, không tải asset ngoài, preview các điểm đầu/cuối scene và chỉ báo đã render khi file đầu ra thực sự tồn tại.

## Tác giả và watermark

Biên soạn: [cachdungai.blog](https://cachdungai.blog/)

Gói được phân phối miễn phí theo điều khoản trong `LICENSE`. Kết quả tạo media có thể cần công cụ, tài khoản hoặc chi phí riêng; hãy duyệt đầu ra trước khi dùng công khai.
