
# Bypass MDM cho macOS 💻

Script thần thánh giúp anh em bypass cái màn hình Quản lý Thiết bị Di động (MDM)  khi cài mới lại macOS.

## 🚨 Cập nhật: Ngày 3 tháng 2 năm 2026

**Đã có bản V2 cực xịn!** Do nhiều anh em nhắn tin nhờ vả và gặp đủ thứ lỗi vặt với bản cũ, mình đã tút lại và cho ra lò bản mới với vô số cải tiến đáng tiền:

### Bản V2 có gì hot?

* **Tự động quét ổ đĩa:** Không còn ép anh em phải đặt tên phân vùng cứng ngắc như "Macintosh HD" nữa.
* **Bẫy lỗi thông minh:** Báo lỗi cực kỳ chi tiết ở từng bước, kèm theo cơ chế tự kiểm tra.
* **Chặn lỗi nhập liệu:** Tự động check tên đăng nhập với mật khẩu xem có hợp lệ không, đỡ bị gõ nhầm.
* **Tránh đụng độ UID:** Tự động đi lùng các ID người dùng còn trống để không bị trùng lặp.
* **Giao diện trực quan:** Chạy ra màu mè hoa lá cở, có thanh tiến trình và thông báo cực dễ hiểu.

Mặc định các bước bên dưới sẽ dùng **bản v2 (khuyên dùng)**. Nếu lỡ xui xẻo gặp trục trặc, anh em chỉ cần đổi chữ `bypass-mdm-v2.sh` thành `bypass-mdm.sh` là quay lại dùng bản cũ được ngay.

---

## ✨ Tính năng chính

* **🔍 Tự động nhận diện ổ đĩa thông minh:** Tự tìm ra phân vùng hệ thống và dữ liệu dù anh em có đặt tên kiểu gì đi nữa.
* **✅ Kiểm tra dữ liệu đầu vào:** Chặn đứng các lỗi gõ sai tên tài khoản hoặc mật khẩu ngớ ngẩn.
* **🛡️ Xử lý lỗi từ A-Z:** Có hướng dẫn cụ thể nếu không may phát sinh sự cố.
* **🎯 Xử lý xung đột UID:** Tự động bốc một ID sạch sẽ để tránh đụng độ hệ thống.
* **📊 Chạy theo thời gian thực:** Nhìn dòng trạng thái đổi màu là biết máy đang làm gì đến đâu.
* **🔄 Chống trùng lặp:** Quét trước xem có dữ liệu thừa thãi nào không để tránh tạo trùng.

## ⚠️ Lưu ý trước khi chiến

* **Khuyến nghị tuyệt đối nên format (xóa sạch) ổ cứng** trước khi bắt đầu.
* **Nên cài lại macOS thông qua USB cài đặt ngoài** cho mượt.
* **Nên để ngôn ngữ máy lúc cài là tiếng Anh** (bản v2 không bắt buộc nhưng cứ để cho lành).

## 📋 Hướng dẫn cài đặt & Sử dụng chi tiết

Làm theo đúng các bước sau để bẻ khóa MDM trong lúc cài mới lại macOS:

> **Điểm xuất phát:** Máy đang hiện cái màn hình bắt đăng nhập MDM (Remote Management) lúc thiết lập máy.

**1.** **Tắt nguồn ép buộc (Force Shutdown):** Nhấn và giữ liệt nút nguồn cho đến khi máy sập hẳn.

**2.** **Vào chế độ Recovery (Recovery Mode):**

* **Mac dùng chip Apple Silicon (M1/M2/M3...):** Nhấn giữ nút nguồn tới khi hiện dòng chữ "Loading startup options".
* **Mac dùng chip Intel:** Nhấn và giữ đồng thời tổ hợp phím CMD + R lúc vừa bật máy lên.

**3.** **Kết nối Wi-Fi** để máy có mạng kích hoạt.

**4.** **Mở Terminal** trong chế độ Recovery:

* Nhìn lên thanh menu phía trên, bấm vào **Utilities**.
* Chọn **Terminal**.

**5.** **Chạy lệnh thần chú:** Copy đoạn code dưới đây dán thẳng vào Terminal rồi Enter:

```bash
curl -L https://raw.githubusercontent.com/assafdori/bypass-mdm/main/bypass-mdm-v2.sh -o bypass-mdm.sh && chmod +x ./bypass-mdm.sh && ./bypass-mdm.sh

```

**6.** **Đợi máy tự quét ổ đĩa:** Script sẽ tự động lùng ra:

* Phân vùng hệ thống (ví dụ: `Macintosh HD`, `MacOS` hoặc tên tự đặt).
* Phân vùng dữ liệu (ví dụ: `Data`, `Macintosh HD - Data`...).

**7.** **Chọn số 1** - Bấm `1` rồi Enter để chọn mục "Bypass MDM from Recovery".

**8.** **Tạo tài khoản tạm:** Thiết lập tài khoản admin giả lập (cứ bấm Enter liên tục để lấy mặc định cho nhanh):

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

## 🔧 Xử lý sự cố khi gặp lỗi (Troubleshooting)

### Lỗi không tìm thấy ổ đĩa

* **Nguyên nhân/Cách sửa:** Chắc chắn là anh em đang đứng ở màn hình Recovery Mode chứ không phải đang dùng máy bình thường nhé. Kiểm tra xem trong *Disk Utility* ổ đĩa có hiện không. Nếu lỗi quá thì quất bản gốc legacy xem sao:

```bash
curl -L https://raw.githubusercontent.com/assafdori/bypass-mdm/main/bypass-mdm.sh -o bypass-mdm.sh && chmod +x ./bypass-mdm.sh && ./bypass-mdm.sh

```

### Lỗi từ chối quyền (Permission denied)

* **Cách sửa:** Xem lại đã mở Terminal chuẩn trong Recovery Mode chưa (mode này quyền root là trùm cuối rồi). Gõ thêm lệnh cấp quyền rồi chạy lại: `chmod +x bypass-mdm.sh`.

### Lỗi script không thèm chạy

* **Cách sửa:** Gõ lại hai lệnh này cho chuẩn:

```bash
chmod +x bypass-mdm.sh
./bypass-mdm.sh

```

### Lỗi chê tên đăng nhập hoặc mật khẩu

* **Quy tắc đặt tên:**
* Username chỉ được xài chữ cái, số, dấu gạch dưới `_` hoặc gạch ngang `-`, và bắt buộc phải mở đầu bằng chữ cái hoặc dấu gạch dưới.
* Password bèo nhất cũng phải từ 4 ký tự trở lên. Lười quá thì cứ ấn Enter để lấy mặc định `1234`.



---

## 📦 Bảng thông số phiên bản

| Phiên bản | Mô tả | Trạng thái |
| --- | --- | --- |
| `bypass-mdm-v2.sh` | Bản nâng cấp xịn sò, tự quét ổ đĩa và check lỗi ngon nghẻ | ✅ **Khuyên dùng** |
| `bypass-mdm.sh` | Bản gốc cổ điển, để tên ổ cứng cố định | ⚠️ Bản cũ (Legacy) |

### ❤️ Gửi lời cảm ơn / Donate (Tùy tâm)

Nhiều anh em nhắn tin cảm ơn vì script cứu cánh cho cái máy cưng nên muốn gửi chút đỉnh. **Cái này hoàn toàn tự nguyện, không ép buộc gì đâu nhé!** Anh em nào có lòng muốn ủng hộ tiền cà phê bằng crypto thì tôi rất cảm kích.

Cũng có mấy thánh đem nguyên repo này về fork rồi đem đi bán thu phí, nói thật là tôi đéo quan tâm lắm. Miễn anh em dùng thấy vui là được, còn thích thì cứ donate:

**VCB (Nguyen Thanh Hoang):**

```
9887999999

```

**TCB (Nguyen Thanh Hoang):**

```
719719

```

## ⚖️ Tuyên bố miễn trách nhiệm

> **Cảnh cáo nhẹ:** Mặc dù gần như không đời nào công ty phát hiện ra anh em đã gỡ MDM (vì nó được xử lý cục bộ tận gốc), nhưng hãy nhớ là **số serial máy** của anh em vẫn còn nằm trong hệ thống quản lý của công ty cũ. Script này chỉ đơn giản là bẻ khóa để máy không bị quản lý từ xa nữa thôi.
> **Tự làm tự chịu nhé!** Công cụ này sinh ra để cứu cánh cho thiết bị cá nhân, đừng đem ra để mưu đồ chuộc lợi hay lách luật trái phép ở các cơ quan, tổ chức không được phép.

---

## 📄 Giấy phép sử dụng

Hàng chia sẻ miễn phí theo hiện trạng (as-is) phục vụ mục đích học tập và cứu hộ. Dùng sao cho khôn ngoan nhé anh em!