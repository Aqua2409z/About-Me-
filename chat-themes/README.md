# Pixel Chat Themes

Hình nền **pixel / ASCII chuyển động** phía sau khung chat của [claude.ai](https://claude.ai), giống các video "Claude chat theme" đang lan truyền. Gõ `/theme` ngay trong ô chat để mở bảng chọn.

![Bảng chọn /theme với theme Cloud Drift](preview.png)

> **Mới làm lần đầu?** Đọc [HUONG-DAN.md](HUONG-DAN.md): hướng dẫn từng bước cho app Claude Desktop, trình duyệt và điện thoại, kèm phần xử lý sự cố.

| Theme | Gõ nhanh | Cảnh |
|---|---|---|
| Claude Code | `/theme code` | Nền terminal tối, tia sáng cam nhấp nháy, dòng code trôi |
| Cloud Drift | `/theme may` | Trời xanh, mây ghép từ ký tự trôi ngang |
| Honu Lagoon | `/theme rua` | Đầm nước xanh, rùa biển, đàn cá, san hô, rong |
| Koi Pond | `/theme koi` | Hồ cá koi, lá sen, gợn sóng |
| Jellyfish | `/theme sua` | Biển sâu, sứa phát sáng bơi lên |
| Paper Boats | `/theme thuyen` | Thuyền giấy dập dềnh trên sóng |
| Fireflies | `/theme dom dom` | Rừng đêm, đom đóm lập lòe |
| Moonlit | `/theme trang` | Trăng, sao lấp lánh, sao băng, mặt biển |

## Xem thử (không cần cài)

Mở trang demo: **https://aqua2409z.github.io/About-Me-/chat-themes/** (chạy được trên laptop và điện thoại).

> Trang demo cần bật GitHub Pages một lần: repo **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**. Chạy trên máy: mở `chat-themes/index.html` bằng trình duyệt.

## Cài cho claude.ai

File cần cài: [`claude-pixel-themes.user.js`](https://raw.githubusercontent.com/Aqua2409z/About-Me-/main/chat-themes/claude-pixel-themes.user.js)

> Script chạy trên **claude.ai mở bằng trình duyệt**. App Claude trên điện thoại không cho cài thêm gì. **App Claude Desktop** có cách riêng, xem mục [Trong app Claude Desktop](#trong-app-claude-desktop).

### 💻 Laptop: Chrome, Edge, Brave, Firefox

1. Cài tiện ích **Tampermonkey** (hoặc Violentmonkey) từ cửa hàng tiện ích của trình duyệt.
2. Chrome/Edge: vào `chrome://extensions` (Edge: `edge://extensions`), bấm **Chi tiết** ở Tampermonkey và bật **Allow User Scripts**. Bản trình duyệt cũ thì bật **Developer mode** ở góc phải.
3. Mở link file `.user.js` ở trên và bấm **Install**.
4. Vào claude.ai và gõ `/theme`.

Safari trên Mac: dùng app **Userscripts** (Mac App Store), cách cài giống iPhone.

### 📱 iPhone / iPad: Safari

1. Cài app miễn phí **Userscripts** từ App Store, mở app một lần và chọn thư mục lưu script.
2. **Cài đặt → Safari → Tiện ích mở rộng → Userscripts**: bật lên, cho phép trên `claude.ai` (hoặc Tất cả trang web).
3. Trong Safari, mở link file `.user.js`, chạm biểu tượng tiện ích trên thanh địa chỉ (**AA** hoặc 🧩) → **Userscripts** → **Install**.
4. Mở claude.ai **trong Safari**, rồi chạm nút ô vuông nhiều màu ở cạnh phải hoặc gõ `/theme`.

### 🤖 Android: Firefox

1. Cài **Firefox**, vào **Menu → Tiện ích (Add-ons)** và cài **Violentmonkey** hoặc **Tampermonkey**.
2. Mở link file `.user.js` và bấm **Install**.
3. Mở claude.ai trong Firefox.

## Trong app Claude Desktop

App Desktop không cài được tiện ích trình duyệt, nhưng có 2 cách chính chủ để thêm hình nền:

| | Cả cửa sổ (tab Chat và Code) | Chỉ tab **Code** |
|---|---|---|
| Cách làm | Chạy userscript dưới dạng *snippet* trong DevTools (Developer Mode) | Cài mod [`pixel-themes`](pixel-themes/) |
| Hình nền | Phủ kín phía sau khung chat, giống trên web | Dải cảnh trên ô chat, khung cảnh bên cạnh, tô màu tin nhắn |
| Mở lại app | Phải chạy lại snippet (2 phím tắt) | Tự chạy, cài 1 lần |
| Lệnh | `/theme` | `/pixel` |

### Hình nền nguyên màn hình: chạy script trong DevTools

Hướng dẫn chi tiết từng cú bấm ở [HUONG-DAN.md, mục 3](HUONG-DAN.md#3-app-claude-desktop-hình-nền-nguyên-màn-hình). Tóm tắt:

1. Bật Developer Mode (chỉ làm 1 lần): **Help → Troubleshooting → Enable Developer Mode**. App khởi động lại và có thêm menu **Developer**. Trên Windows, menu Help nằm trong nút ☰ ở góc trên bên trái.
2. Bấm vào cửa sổ app Claude, mở DevTools: `Ctrl + Alt + I` (Windows; nếu không được thử `Ctrl + Shift + Alt + I`) / `Cmd + Option + I` (Mac). Nếu hiện 2 cửa sổ DevTools, dùng cửa sổ mà lệnh `location.href` trong Console trả về địa chỉ có `claude.ai`.
3. Trong DevTools, mở tab **Sources** → bấm `»` cạnh *Page* → **Snippets** → **+ New snippet**, đặt tên `pixel`.
4. Mở file [`claude-pixel-themes.user.js`](https://raw.githubusercontent.com/Aqua2409z/About-Me-/main/chat-themes/claude-pixel-themes.user.js), chép **toàn bộ** nội dung, dán vào snippet rồi lưu (`Ctrl/Cmd + S`).
5. Chạy: `Ctrl + Enter` (Mac: `Cmd + Enter`). Hình nền hiện ra, gõ `/theme` để đổi.

**Những lần mở app sau:** mở DevTools, bấm `Ctrl/Cmd + P`, gõ `!pixel` rồi Enter. Snippet đã lưu sẵn, theme bạn chọn cũng được nhớ.

**Không thấy gì sau khi chạy?** Mở tab **Console** của DevTools. Ở ô chọn ngữ cảnh phía trên (thường ghi `top`), chọn mục mang tên claude.ai. Sau đó dán toàn bộ nội dung file vào Console và nhấn Enter.

> Developer Mode là tính năng gỡ lỗi chính thức của app. Chỉ dán vào DevTools mã bạn tin tưởng (ở đây là mã trong repo của bạn). Khi app cập nhật giao diện, script vẫn tự dò nền theo màu nên thường vẫn chạy; nếu có lỗi, chọn **Tắt** trong bảng `/theme` hoặc khởi động lại app.

### Tab Code: cài mod `pixel-themes`

1. Trong tab **Code**, bấm **+** cạnh ô chat → **Plugins** → **Add marketplace**, nhập `Aqua2409z/About-Me-`.
2. Chọn **pixel-themes** → **Add plugin**.
3. Gõ `/pixel` để mở bảng chọn theme. `/pixel koi` đổi thẳng; `/pixel side` mở khung cảnh bên cạnh; `/pixel tint` bật/tắt tô màu tin nhắn.

Mod dùng hệ thống plugin chính thức của Claude Code. Hệ thống này chỉ cho vẽ ở dải trên ô chat, khung bên cạnh và quanh tin nhắn, nên mod không phủ kín phía sau khung chat như trên web. Chi tiết: [pixel-themes/README.md](pixel-themes/README.md).

## Cách dùng

| Thao tác | Kết quả |
|---|---|
| Gõ `/theme` trong ô chat | Mở bảng chọn ngay trên ô chat |
| `←` `→` | Xem thử theme |
| `Enter` | Áp dụng (tin nhắn `/theme` **không** bị gửi cho Claude) |
| `Esc` | Đóng, giữ theme cũ |
| `/theme koi`, `/theme trang`, `/theme off` | Đổi thẳng theo tên hoặc tên tiếng Việt không dấu |
| `Alt + T` | Mở/đóng bảng chọn |
| Nút ô vuông nhiều màu ở cạnh phải | Mở bảng chọn (tiện trên điện thoại) |

Bộ gõ Telex hay biến `/theme` thành `/thêm`. Script hiểu cả `/thêm` và `/nen`, nên không cần tắt bộ gõ.

Trong bảng chọn còn có:

- **Làm dịu nền**: phủ thêm một lớp mờ để chữ dễ đọc hơn.
- **Độ đục khung**: độ trong của thanh bên, ô chat và bong bóng tin nhắn.
- **Chuyển động**: tắt để nền đứng yên (đỡ tốn pin).
- **Nút nổi**: ẩn/hiện nút ở cạnh phải.

Theme tối (Koi Pond, Jellyfish, Fireflies, Moonlit, Claude Code) đẹp nhất khi claude.ai ở giao diện **Dark**, theme sáng thì hợp giao diện **Light**. Nếu không khớp, script tự phủ thêm lớp mờ để chữ vẫn đọc được.

## Cách hoạt động

1. Một `<canvas>` toàn màn hình nằm **sau** trang (z-index −1) và vẽ cảnh bằng lưới ô vuông nhỏ. Mỗi ô chứa một ký tự ASCII, nên nhìn giống pixel.
2. Script đọc **màu nền thật** của từng khung (không dựa vào tên class) rồi xử lý:
   - Khung lớn (nền chính) → trong suốt.
   - Khung nhỏ hơn (thanh bên, ô chat, bong bóng tin nhắn, menu) → kính mờ.
   - Nút màu nổi bật như nút gửi → giữ nguyên.

   Nhờ vậy khi claude.ai đổi giao diện, script vẫn chạy được trong đa số trường hợp.
3. Không dùng `innerHTML` hay `<style>` inline, nên chạy được cả trên trang có Content-Security-Policy / Trusted Types chặt.
4. Chạy 10–12 khung hình/giây (đúng chất pixel), tự dừng khi chuyển tab, và đứng yên nếu máy bật chế độ giảm chuyển động.
5. Script **không gửi dữ liệu đi đâu**. Nó chỉ lưu cài đặt (`pixel-themes:v1`) trong localStorage của claude.ai.

## Tự tạo theme

Mỗi theme là một object trong mảng `THEMES` của file script:

```js
THEMES.push({
  id: 'sakura', name: 'Sakura', dark: false, alias: ['hoa'],
  glyphs: '*.:',                       // ký tự in trong các ô
  bg(ctx, w, h) { /* vẽ gradient nền một lần */ },
  init(world) {                        // tạo trạng thái ban đầu
    world.s.petals = Array.from({ length: 30 }, () => ({ x: Math.random() * world.cols, y: Math.random() * world.rows }));
  },
  frame(world, dt) {                   // gọi mỗi khung hình
    for (const p of world.s.petals) {
      p.y += dt; if (p.y > world.rows) p.y = 0;
      world.tile(p.x, p.y, '#ffc4d6', '#e88aa8', '*');   // ô: (cột, hàng, màu ô, màu chữ, ký tự)
    }
  },
});
```

Các hàm vẽ có sẵn: `world.tile`, `world.sprite` (vẽ hình từ ASCII art), `world.glyph`, `world.dot`, `world.glow`.

## Cấu trúc

```
chat-themes/
├── claude-pixel-themes.user.js   # userscript, cũng là thư viện cho trang demo
├── index.html                    # trang demo kiểu ứng dụng chat
├── pixel-themes/                 # mod cho tab Code của app Claude Desktop
└── README.md
.claude-plugin/marketplace.json   # (gốc repo) để app Desktop cài mod từ repo này
```

## Giới hạn

- App Claude trên điện thoại không cài thêm được gì. App Desktop dùng một trong 2 cách ở mục [Trong app Claude Desktop](#trong-app-claude-desktop).
- Nếu claude.ai thay đổi lớn về giao diện, có thể có khung chưa được làm trong suốt. Khi đó, mở bảng `/theme` và chọn **Tắt** để trở lại bình thường.
- Hiệu ứng kính mờ (`backdrop-filter`) tốn GPU hơn một chút trên máy yếu. Tăng **Độ đục khung** lên tối đa để tắt hiệu ứng mờ.
