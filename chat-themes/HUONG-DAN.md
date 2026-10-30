# Hướng dẫn cài Pixel Chat Themes, từ đầu đến cuối

Tài liệu này dành cho người chưa từng làm những việc như thế này. Mỗi bước chỉ có một việc. Cứ làm lần lượt từ trên xuống.

Ký hiệu phím: `Ctrl + Shift + I` nghĩa là giữ **Ctrl** và **Shift** rồi bấm **I**. Trên Mac, `Ctrl` đổi thành `Cmd` và `Alt` đổi thành `Option`.

---

## Mục lục

1. [Chọn cách phù hợp](#1-chọn-cách-phù-hợp)
2. [Những gì đã được làm sẵn](#2-những-gì-đã-được-làm-sẵn)
3. [App Claude Desktop: hình nền nguyên màn hình](#3-app-claude-desktop-hình-nền-nguyên-màn-hình)
4. [App Claude Desktop: mod `/pixel` trong tab Code](#4-app-claude-desktop-mod-pixel-trong-tab-code)
5. [Trình duyệt trên laptop (claude.ai)](#5-trình-duyệt-trên-laptop-claudeai)
6. [Điện thoại](#6-điện-thoại)
7. [Xử lý sự cố](#7-xử-lý-sự-cố)
8. [Gỡ bỏ](#8-gỡ-bỏ)

---

## 1. Chọn cách phù hợp

| Bạn dùng Claude ở đâu | Cách làm | Kết quả | Phải làm lại không? |
|---|---|---|---|
| **App Claude Desktop** (tab Chat hoặc Code) | [Mục 3](#3-app-claude-desktop-hình-nền-nguyên-màn-hình): chạy script qua Developer Mode | Hình nền **nguyên màn hình** phía sau khung chat | Mỗi lần mở app phải chạy lại: bấm 3 phím |
| **App Claude Desktop**, tab Code | [Mục 4](#4-app-claude-desktop-mod-pixel-trong-tab-code): mod `/pixel` (**đã cài sẵn**) | Dải cảnh động trên ô chat, khung cảnh bên cạnh, tin nhắn có viền màu | Không, tự chạy |
| **claude.ai trên Chrome / Edge / Firefox** | [Mục 5](#5-trình-duyệt-trên-laptop-claudeai): Tampermonkey | Hình nền nguyên màn hình | Không, tự chạy |
| **iPhone (Safari) / Android (Firefox)** | [Mục 6](#6-điện-thoại) | Hình nền nguyên màn hình | Không, tự chạy |

App Claude trên điện thoại (cài từ App Store / CH Play) thì không cài thêm được gì. Trên điện thoại phải mở claude.ai bằng trình duyệt.

---

## 2. Những gì đã được làm sẵn

- Toàn bộ mã nguồn nằm trong repo GitHub [`Aqua2409z/About-Me-`](https://github.com/Aqua2409z/About-Me-), thư mục `chat-themes/`.
- Mod `pixel-themes` đã có trên GitHub, và bạn **đã cài thành công** trong app Desktop (lệnh `/pixel koi` đã chạy).
- File script cho hình nền nguyên màn hình nằm ở link dưới đây. Mục 3 sẽ dùng đến:
  **https://raw.githubusercontent.com/Aqua2409z/About-Me-/main/chat-themes/claude-pixel-themes.user.js**

Phần còn lại phải làm trên máy bạn: app Claude không cho chương trình bên ngoài điều khiển nó, nên các cú bấm trong app bạn phải tự làm.

---

## 3. App Claude Desktop: hình nền nguyên màn hình

Cách này dùng **Developer Mode**, một tính năng gỡ lỗi chính thức có sẵn trong app. Ta mở công cụ dành cho lập trình viên (DevTools) rồi chạy script hình nền trong đó.

> Hình nền chạy tới khi bạn tắt app hoặc tải lại trang. Mở app lần sau thì làm [bước 3.5](#35-mỗi-lần-mở-lại-app) (bấm 3 phím). Theme bạn chọn được nhớ lại.

### 3.1. Bật Developer Mode (chỉ làm 1 lần)

1. Mở app Claude.
2. **Windows:** bấm nút **☰** ở góc trên bên trái cửa sổ.
   **Mac:** dùng thanh menu trên cùng màn hình.
3. Chọn **Help** → **Troubleshooting** → **Enable Developer Mode**.
4. Nếu app hỏi xác nhận thì đồng ý. App có thể tự khởi động lại.
5. Kiểm tra: mở lại menu ☰ (hoặc thanh menu trên Mac). Nếu đã có thêm mục **Developer** là xong.

### 3.2. Mở DevTools

- Bấm `Ctrl + Shift + I` (Mac: `Cmd + Option + I`),
- **hoặc** vào menu **Developer** → chọn mục có chữ **Dev Tools** (ví dụ *Show Dev Tools*). Nếu có nhiều mục, chọn mục nói về cửa sổ chính (*main window*).

Một khung mới hiện ra (dính bên cạnh hoặc là cửa sổ riêng), phía trên có các tab **Elements, Console, Sources…** Đó là DevTools.

### 3.3. Chạy script lần đầu

1. Mở trình duyệt web bất kỳ (Chrome, Edge…) và vào link:
   **https://raw.githubusercontent.com/Aqua2409z/About-Me-/main/chat-themes/claude-pixel-themes.user.js**
2. Trang hiện ra toàn chữ (mã nguồn). Bấm `Ctrl + A` để chọn hết, rồi `Ctrl + C` để chép.
3. Quay lại DevTools trong app Claude, bấm tab **Console**.
4. Bấm chuột vào dòng trống dưới cùng (có dấu `>`), rồi bấm `Ctrl + V` để dán.
5. Nếu DevTools hiện cảnh báo kiểu *"Don't paste code into the DevTools Console…"* và không cho dán:
   gõ đúng chữ `allow pasting`, bấm **Enter**, rồi `Ctrl + V` lại. Việc này chỉ cần làm 1 lần.
6. Bấm **Enter**.
7. Hình nền chuyển động hiện ra phía sau khung chat, và có thêm nút **ô vuông nhiều màu** ở cạnh phải màn hình.
8. Bạn có thể đóng DevTools (nút X của khung DevTools). Hình nền vẫn ở lại.

> Không thấy gì? Xem [Xử lý sự cố](#7-xử-lý-sự-cố), dòng "Chạy script xong không thấy gì".

### 3.4. Lưu script lại để lần sau nhanh hơn (làm 1 lần)

Làm bước này để không phải chép–dán mỗi lần mở app.

1. Mở DevTools (`Ctrl + Shift + I`).
2. Bấm tab **Sources**. Nếu không thấy, bấm `»` ở dãy tab trên cùng rồi chọn **Sources**.
3. Ở cột bên trái của Sources, bấm `»` cạnh chữ **Page**, rồi chọn **Snippets**.
4. Bấm **+ New snippet**. Đặt tên là `pixel` rồi bấm Enter.
5. Bấm vào vùng soạn thảo bên phải, dán script (`Ctrl + V`; nếu đã chép từ bước 3.3 thì vẫn còn trong bộ nhớ, không thì chép lại từ link).
6. Bấm `Ctrl + S` để lưu.

### 3.5. Mỗi lần mở lại app

1. `Ctrl + Shift + I` để mở DevTools.
2. `Ctrl + P`, gõ `!pixel` (có dấu chấm than ở đầu), bấm **Enter**.
3. Đóng DevTools.

Nếu chưa làm bước 3.4 thì làm lại bước 3.3.

### 3.6. Đổi theme và chỉnh cho dễ đọc

Mở bảng chọn theme bằng một trong ba cách:

- bấm **nút ô vuông nhiều màu** ở cạnh phải,
- bấm `Alt + T`,
- gõ `/theme` vào ô chat (ở tab Code, `/theme` có thể bị lẫn với menu lệnh của app, nên dùng hai cách trên chắc ăn hơn).

Trong bảng chọn:

| Thao tác | Kết quả |
|---|---|
| Bấm vào một ảnh | Áp dụng theme đó |
| `←` `→` rồi `Enter` | Xem thử rồi áp dụng |
| `Esc` | Đóng bảng |
| Thanh **Làm dịu nền** | Kéo sang phải nếu chữ khó đọc |
| Thanh **Độ đục khung** | Độ trong của thanh bên, ô chat, bong bóng tin nhắn |
| **Chuyển động** | Bỏ tick để nền đứng yên (đỡ tốn pin) |
| **Nút nổi** | Ẩn/hiện nút ô vuông ở cạnh phải |
| Ô **OFF / Tắt** | Tắt hình nền, trở về giao diện gốc |

Mẹo: theme tối (Koi Pond, Jellyfish, Fireflies, Moonlit, Claude Code) đẹp nhất khi app ở giao diện **Dark**. Theme sáng (Cloud Drift, Honu Lagoon, Paper Boats) hợp giao diện **Light**.

### 3.7. Dùng chung với mod `/pixel`

Nếu dùng cả hình nền nguyên màn hình lẫn mod ở mục 4, sẽ có thêm một dải cảnh trên ô chat. Muốn bỏ dải đó thì gõ `/pixel band` trong tab Code. Gõ lại `/pixel band` để bật lại.

---

## 4. App Claude Desktop: mod `/pixel` trong tab Code

Mod này **đã cài sẵn**. Nó dùng hệ thống plugin chính thức nên tự chạy mỗi lần mở app, nhưng chỉ vẽ được ở 3 chỗ: dải trên ô chat, khung bên cạnh và viền quanh tin nhắn. Muốn nguyên màn hình thì dùng mục 3.

### 4.1. Các lệnh

Gõ vào ô chat của tab Code:

| Lệnh | Kết quả |
|---|---|
| `/pixel` | Mở bảng chọn có ảnh thu nhỏ từng theme |
| `/pixel koi` | Đổi sang Koi Pond (tương tự: `code`, `cloud`, `lagoon`, `jelly`, `boats`, `fireflies`, `moon`) |
| `/pixel trang`, `/pixel sua`, `/pixel may`… | Đổi theme bằng tên tiếng Việt không dấu |
| `/pixel side` | Mở khung cảnh cao bên cạnh khung chat |
| `/pixel band` | Bật/tắt dải cảnh trên ô chat |
| `/pixel tint` | Bật/tắt viền màu quanh tin nhắn |
| `/pixel off` | Tắt hết |

### 4.2. Nếu cần cài lại (máy mới, hoặc lỡ gỡ)

1. Trong tab **Code**, bấm **+** cạnh ô chat → **Plugins** → **Add marketplace**.
2. Ô **URL** chỉ ghi đúng: `Aqua2409z/About-Me-` (không dán link trang web), rồi bấm **Sync**.
3. Chọn **pixel-themes** → **Add plugin** / **Install**.
4. Mở một phiên Code mới và gõ `/pixel`.

---

## 5. Trình duyệt trên laptop (claude.ai)

Dùng cách này nếu bạn chat với Claude bằng trình duyệt. Cài 1 lần là tự chạy mãi.

1. Cài tiện ích **Tampermonkey** từ cửa hàng tiện ích của trình duyệt (Chrome Web Store, Edge Add-ons, Firefox Add-ons).
2. Chỉ với Chrome/Edge: vào `chrome://extensions` (Edge: `edge://extensions`), bấm **Chi tiết / Details** ở Tampermonkey và bật **Allow User Scripts**.
3. Mở link script ở [mục 2](#2-những-gì-đã-được-làm-sẵn). Tampermonkey hiện trang cài đặt, bấm **Install**.
4. Vào claude.ai. Hình nền hiện ra, gõ `/theme` để đổi.

Muốn có cửa sổ riêng như một app: trong Chrome, khi đang ở claude.ai, bấm **⋮ → Truyền, lưu và chia sẻ → Cài đặt trang dưới dạng ứng dụng**.

---

## 6. Điện thoại

### iPhone / iPad (Safari)

1. Cài app miễn phí **Userscripts** từ App Store. Mở app một lần và chọn thư mục lưu script.
2. **Cài đặt → Safari → Phần mở rộng → Userscripts**: bật lên, cho phép trên `claude.ai`. Trên iOS 18: **Cài đặt → Ứng dụng → Safari → Phần mở rộng**.
3. Mở link script bằng **Safari**, chạm biểu tượng **AA** trên thanh địa chỉ → **Userscripts** → **Install**.
4. Vào claude.ai bằng Safari, chạm nút ô vuông nhiều màu ở cạnh phải.

### Android (Firefox)

1. Cài **Firefox**, vào **Menu → Tiện ích (Add-ons)** và cài **Violentmonkey**.
2. Mở link script bằng Firefox và bấm **Install**.
3. Vào claude.ai bằng Firefox.

---

## 7. Xử lý sự cố

| Vấn đề | Cách xử lý |
|---|---|
| Không thấy mục **Help** trên Windows | Bấm nút **☰** ở góc trên bên trái cửa sổ app. |
| Không thấy menu **Developer** | Developer Mode chưa bật, hoặc app chưa khởi động lại. Làm lại [3.1](#31-bật-developer-mode-chỉ-làm-1-lần), rồi thoát hẳn app (Windows: chuột phải biểu tượng Claude ở khay hệ thống góc dưới phải → Quit) và mở lại. |
| `Ctrl + Shift + I` không mở gì | Dùng menu **Developer** → mục **Dev Tools**. |
| Dán vào Console không được | Gõ `allow pasting`, bấm Enter, rồi dán lại. |
| Chạy script xong không thấy gì | Trong tab **Console**, nhìn ô chọn phía trên (thường ghi `top`). Bấm vào đó, chọn mục có chữ **claude**, rồi dán và chạy lại script. Nếu menu Developer có nhiều mục Dev Tools, thử mục còn lại. |
| Console báo lỗi màu đỏ | Chụp màn hình lỗi gửi cho Claude để sửa. |
| Chữ khó đọc | Mở bảng chọn → kéo **Làm dịu nền** sang phải, hoặc chọn theme hợp với giao diện sáng/tối. |
| Có chỗ vẫn nền đặc, chưa trong suốt | Bình thường sau khi app cập nhật giao diện. Chụp màn hình gửi Claude. |
| Mở app lại thì mất hình nền | Bình thường với cách ở mục 3. Làm [3.5](#35-mỗi-lần-mở-lại-app). |
| Gõ `/pixel` không có lệnh | Mở một phiên Code **mới**. Nếu vẫn không có, cập nhật app Claude rồi [cài lại mod](#42-nếu-cần-cài-lại-máy-mới-hoặc-lỡ-gỡ). |
| Add marketplace báo *"isn't a marketplace"* | Ô URL phải ghi `Aqua2409z/About-Me-`, không phải link trang web GitHub. |

---

## 8. Gỡ bỏ

- **Hình nền nguyên màn hình (mục 3):** chọn **Tắt** trong bảng chọn, hoặc chỉ cần tắt và mở lại app. Muốn tắt Developer Mode: vào lại **Help → Troubleshooting** và chọn mục tắt Developer Mode.
- **Mod `/pixel` (mục 4):** tab Code → **+** → **Plugins** → chọn **pixel-themes** → **Remove / Uninstall**.
- **Trình duyệt / điện thoại:** mở Tampermonkey / Userscripts / Violentmonkey, xóa script *Pixel Chat Themes*.

Script chỉ lưu lựa chọn theme của bạn trên máy và không gửi dữ liệu đi đâu.
