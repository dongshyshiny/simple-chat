# I. Hướng dẫn tích hợp chat vào trang web của doanh nghiệp

**1. Chức năng của chat**
- Dùng để khách hàng có thể dễ dàng tra cứu các thông tin cần thiết trên trang của bạn

**2. Khởi tạo thông tin tài khoản**

Bộ tham số được cung cấp có:

| STT | Tên tham số         | Mô tả                      | Chú thích |
|-----|---------------------|----------------------------|-----------|
| 1   | crm_token           | Token dùng để kết nối chat |Bắt buộc   |

**3. Tải mã nguồn và demo**
- Sử dụng file js và css

**4. Hướng dẫn lập trình tích hợp**

**Phương pháp kết nối: Chỉ sử dụng thư viện javascript và css**
- Import file main.min.js vào trang web của bạn

       <script src="main.min.js" type="text/javascript"></script>
- Import file style.min.css vào trang web của bạn

       <link rel="stylesheet" href="style.min.css">

- Copy dòng sau giữa thẻ body:

        <div class="chat-simple-crm" id="crm_chat_simple">
          <div class="settings hidden">
            <label for="crm_token"></label>
            <input type="text" class="hidden" id="crm_token" value="crm_token">
          </div>
        </div>
