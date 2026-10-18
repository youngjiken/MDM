**Lệnh thần chú:**

```bash
curl -L https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/bypass-mdm-v2.sh -o bypass-mdm.sh && chmod +x ./bypass-mdm.sh && ./bypass-mdm.sh

```
*Video hướng dẫn: https://vt.tiktok.com/ZSg6jav66/
# Bypass MDM cho macOS 💻
![mdm-screen](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/mdm-screen.png)
Script thần thánh giúp anh em bypass cái màn hình Quản lý Thiết bị Di động (MDM)  khi cài mới lại macOS.

## 🚨 Cập nhật: Ngày 16 tháng 10 năm 2026

**Đã có bản mới cực xịn!** Có thể bypass MDM Phiên bản macOS mới nhất hiện nay là macOS 27 Golden Gate !

---

## ⚠️ Lưu ý trước khi bypass

* **Khuyến nghị tuyệt đối nên format (xóa sạch) ổ cứng** trước khi bắt đầu.
* **Nên cài lại macOS thông qua USB cài đặt ngoài** cho mượt.
* **Nên để tiếng anh cho dễ làm và đỡ lỗi**

## 📋 Hướng dẫn cài đặt & Sử dụng chi tiết

Làm theo đúng các bước sau để bẻ khóa MDM trong lúc cài mới lại macOS:

> **Chuẩn Bị:** Máy đang hiện cái màn hình bắt đăng nhập MDM (Remote Management) lúc thiết lập máy. Hoặc khi anh em muốn bán máy thì phải Restore lại mới bán đúng không, thì sau khi active xong nó sẽ hiện màn hình Hello chào mừng. Vô bước 1

**1.** **Tắt nguồn ép buộc (Force Shutdown):** Nhấn và giữ liệt nút nguồn ( Touch Id) cho đến khi máy sập hẳn.

**2.** **Vào chế độ Recovery (Recovery Mode):**

* **Mac dùng chip Apple Silicon (M1/M2/M3...):** Nhấn giữ nút nguồn( Touch Id) tới khi hiện dòng chữ "Loading startup options".
* **Mac dùng chip Intel:** Nhấn và giữ đồng thời tổ hợp phím CMD + R lúc vừa bật máy lên.

**3.** **Chọn Option** Để vào Recovery, Sau khi vào recovery nhớ kết nối wifi.

![option](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/option.jpg)
___
**4.** **Chọn Safari** trong chế độ Recovery:

![safari](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/safari.jpg)
___
* **Gõ địa chỉ web**:  Github.com/youngjiken/MDM  **Enter**.

![link](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/link.png)

* Ngay phần đầu hướng dẫn có cái code ae bấm coppy cái code đó lại.

![code](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/code.png)

* Sau đó nhìn lên góc trên cùng tay trái,Bấm **Safari**, rồi chọn **Quit Safari**

* Tiếp tục nhìn lên thanh menu phía trên, bấm vào **Utilities**.
* Chọn **Terminal**.
  
![ter](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/ter.jpg)

---
**5.** **Chạy lệnh thần chú:** Paste đoạn code nãy coppy dán thẳng vào Terminal rồi Enter:

**6.** **Đợi máy tự quét ổ đĩa:** Script sẽ tự động tìm ra:

* Phân vùng hệ thống (ví dụ: `Macintosh HD`, `MacOS` hoặc tên tự đặt).
* Phân vùng dữ liệu (ví dụ: `Data`, `Macintosh HD - Data`...).

**7.** **Chọn số 1** - Bấm `1` rồi Enter để chọn mục "Bypass MDM from Recovery".

**8.** **Tạo tài khoản tạm:** Thiết lập tài khoản admin giả lập (cứ bấm **Enter** liên tục để lấy mặc định cho nhanh, 3 lần ENTER):

* **Tên đầy đủ (Fullname):** `Apple` (mặc định)
* **Tên đăng nhập (Username):** `Apple` (mặc định)
* **Mật khẩu (Password):** `1234` (mặc định)

> 💡 **Mẹo nhỏ:** Script tự test dữ liệu anh em gõ, nếu sai cú pháp nó bắt gõ lại ngay.

**9.** **Ngồi đợi chạy xong:** Màn hình sẽ hiện lần lượt các dòng báo xanh lét:

* ✓ Đang check đường dẫn hệ thống
* ✓ Đang tạo tài khoản
* ✓ Đang chặn mấy con domain MDM của Apple
* ✓ Đang thiết lập cấu hình né MDM

**10.** **Khởi động lại máy:** Khi thấy hiện dòng chữ **"MDM Bypass Completed Successfully"**, hãy tắt Terminal đi và reboot lại máy.

---

### 🔄 Các việc cần làm tiếp theo khi máy lên nguồn

**11.** **Đăng nhập** bằng cái tài khoản tạm vừa tạo:

* Username: `Apple` (hoặc tên anh em vừa đổi)
* Password: `1234` (hoặc mật khẩu anh em vừa đặt)

**12.** **Bơ hết mấy cái thiết lập đi** - Cứ bấm Skip qua hết (Apple ID, Siri, Touch ID, Định vị... tính sau).

**13.** **Tạo tài khoản chính chủ của anh em:**

* Vào **System Settings > Users and Groups**.
* Tạo tài khoản Admin thật sự với tên và mật khẩu của chính anh em.

**14.** **Chuyển nhà:** Đăng xuất tài khoản tạm ra rồi vào lại bằng tài khoản xịn mới tạo.

**15.** **Cài đặt lại từ đầu:** Lúc này tha hồ add Apple ID, bật Siri, Touch ID các kiểu con đà điểu.

**16.** **Dọn rác:** Xóa sổ cái tài khoản tạm `Apple` hồi nãy đi cho nhẹ máy:

* Vào lại **System Settings > Users and Groups**.
* Chọn profile tài khoản `Apple` rồi bấm nút trừ (`−`) để xóa.

**17.** **🎉 Xong phim!** Máy đã hoàn toàn tự do, sạch bóng MDM.

---

### ❤️ Gửi lời cảm ơn / Donate (Tùy tâm)

Nhiều anh em nhắn tin cảm ơn vì script cứu cánh cho cái máy cưng nên muốn gửi chút đỉnh. **Cái này hoàn toàn tự nguyện, không ép buộc gì đâu nhé!** Anh em nào có lòng muốn ủng hộ tiền cà phê thì mình rất cảm kích.

thích thì cứ donate:

**VCB (Nguyen Thanh Hoang):**

```
9887999999

```
![vcb](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/vcb.jpg)

**TCB (Nguyen Thanh Hoang):**

```
719719

```
![tcb](https://raw.githubusercontent.com/youngjiken/bypass-mdm-vn/main/tcb.jpeg)
## ⚖️ Tuyên bố miễn trách nhiệm

> **Cảnh cáo nhẹ:** Mặc dù gần như không đời nào công ty phát hiện ra anh em đã gỡ MDM (vì nó được xử lý cục bộ tận gốc), nhưng hãy nhớ là **số serial máy** của anh em vẫn còn nằm trong hệ thống quản lý của công ty cũ. Script này chỉ đơn giản là bẻ khóa để máy không bị quản lý từ xa nữa thôi.
> **Tự làm tự chịu nhé!** Công cụ này sinh ra để cứu cánh cho thiết bị cá nhân, đừng đem ra để mưu đồ chuộc lợi hay lách luật trái phép ở các cơ quan, tổ chức không được phép.

---

## 📄 Giấy phép sử dụng

Hàng chia sẻ miễn phí theo hiện trạng (as-is) phục vụ mục đích học tập và cứu hộ. Dùng sao cho khôn ngoan nhé anh em!
