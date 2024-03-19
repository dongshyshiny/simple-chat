# I. Hướng dẫn tích hợp vào ứng dụng CRM của doanh nghiệp

**1. Chức năng của webphone**
- Là một webphone sử dụng công nghệ sử dụng WebRTC chạy trực tiếp trên trình duyệt (Chrome/Firefox/Edge/CocCoc/Safari)
- Không cần cài đặt thêm softphone ngoài.
- Thực hiện gọi ra Click-to-call trên webphone
- Tiếp nhận cuộc gọi vào trên webphone
- Hỗ trợ popup thông tin khách hàng khi có cuộc gọi đến

**2. Khởi tạo thông tin tài khoản**

Bộ tham số Alohub cung cấp gồm có:
| STT | Tên tham số         | Mô tả                                                                    | Chú thích |
|-----|---------------------|--------------------------------------------------------------------------|------|
| 1   | txtDomain           | Địa chỉ API endpoint, ví dụ: **https://domain.com/api/**                 |Chỉ dùng khi tích hợp API, nếu nhúng jsphone thì không cần)
| 2   | txtApiKey           | Key tích hợp, ví dụ **kjlkjkdshlfjdslkj@#!23**                           |Chỉ dùng khi tích hợp API, nếu nhúng jsphone thì không cần
| 3   | txtWebsocketServerUrl | Địa chỉ socket server, ví dụ **wss://alohub.vn:7443**                  |Bắt buộc
| 4   | txtPassword         | Mật khẩu                                                                 |Bắt buộc
| 5   | txtDisplayName      | Tên hiển thị của máy lẻ, ví dụ **Sale 1000**                             |Tùy chọn
| 6   | txtPublicIdentity   | Địa chỉ của máy lẻ, ví dụ **sip:1000@alohub.vn:5060**                    |Bắt buộc

**3. Tải mã nguồn và demo**
- Sử dụng package mã nguồn: demo-js-new
- Có thể chạy thử demo trên local hoặc demo online tại: https://app.alohub.vn/jsphonev10.0/index.html

**4. Cấu hình jsphone**
| STT | Name         | Mô tả                                                                                                 |
|-----|--------------|-------------------------------------------------------------------------------------------------------|
| 1   | usingCallJs | Hệ thống có 2 option gọi ra cho khách hàng: dùng JSPhone(tham số = 1), dùng API makeCall(tham số = 0).|
| 2   | isAutoAnswer  | Nếu muốn hệ thống tự bắt máy thì 1 và ngược lại (mặc định 1) |

**5. Hướng dẫn lập trình tích hợp**

**Phương pháp 1: Nhúng trực tiếp giao diện jsphone vào CRM**
- Đây là phương án đơn giản, nhanh và ko đòi hỏi lập trình phức tạp.
- Chỉ cần dùng bộ tham số ở trên đưa vào file index.html và nhúng html vào CRM của doanh nghiệp
- Lưu ý với phương pháp này thì một số tham số txtDomain, txtApiKey là không cần thiết.

**Phương pháp 2: Chỉ sử dụng thư viện javascript của webRTC phone**
- Import các lib javascript vào ứng dụng CRM của doanh nghiệp, các lib này được đóng gói trong mã nguồn cung cấp (trong
  đó sipjs.js là file js chứa các hàm Alohub định nghĩa sẵn để hỗ trợ thông báo, xử lý giao diện, tương tác tuỳ theo nhu
  cầu của từng CRM)

       <script src="jssip-3.10.0.min.js" type="text/javascript"></script>
        <script src="sipjs.js" type="text/javascript"></script>

- Copy dòng sau giữa thẻ body:

        <div id="alohub_shipjs_container">
        <audio id="audio_remote" autoplay="autoplay"></audio>
        <audio id="ringtone" loop="" src="sounds/ringtone.wav"></audio>
        <audio id="ringbacktone" loop="" src="sounds/ringbacktone.wav"></audio>
        <audio id="dtmfTone" src="sounds/dtmf.wav"></audio>
        </div>
