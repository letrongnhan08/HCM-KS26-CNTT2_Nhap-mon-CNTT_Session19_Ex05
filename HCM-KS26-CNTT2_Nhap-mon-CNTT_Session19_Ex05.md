**Bài 5 : Xây dựng cơ chế xác thực an toàn cho Crypto Wallet** 

***Thiết kế kiến trúc***

- **Vẽ sơ đồ ,giải thích:**

Lớp 1: Tri thức (Something you know) - (mật khẩu,mã pin) 
    Bắt nhập mật khẩu

        ↓
        
 (Hacker có mật khẩu \-\> Vượt qua)  
 
        ↓

 Lớp 2: Sở hữu vật lý (Something you have)  - (thiết bị vật lý có authenticators)
     Nhập mã TOTP 
  (Hacker không có thiết bị của người dùng vì mã Secret Key nằm trong thiết bị người dùng,mã thay đổi liên tục sau 30 giây, nhập sai mã và bị chặn) 
  
        ↓

 (Xác thực mã không khớp và bị chặn)  
 
         ↓ 

 Lớp 3:Xác thực sinh trắc học (Something you are)       
 \- FaceID / Vân tay   
(Không khớp và bị chặn)

***Xử lý bẫy (Edge Case)***

- **Nếu người dùng đang ở trên máy bay (không có internet/sóng điện thoại), làm sao họ vẫn có thể lấy mã OTP để thực hiện giao dịch?**  
- Dùng app Authenticator vì có thuật toán TOTP: vì không cần mạng bởi vì Secret Key đã được lưu trữ mã hóa cục bộ trên thiết bị của người dùng từ lúc cài đặt ban đầu, và cơ chế đồng bộ thiết bị theo thời gian thực vơi app và thiết bị.
        
