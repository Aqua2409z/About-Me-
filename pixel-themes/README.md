# pixel-themes (mod cho Claude Code)

Hình nền pixel/ASCII chuyển động cho **tab Code của app Claude Desktop** (cũng chạy trong VS Code và app điện thoại khi xem phiên Claude Code). Có 9 theme giống bản userscript cho claude.ai: Claude Code, Cloud Drift, Honu Lagoon, Koi Pond, Jellyfish, Paper Boats, Fireflies, Moonlit, Việt Nam.

Mod gồm ba phần:

- **Dải cảnh động** ngay trên ô chat.
- **Khung cảnh cao** mở bên cạnh khung chat.
- **Tô màu tin nhắn**: viền và nền nhạt theo màu của theme.

## Cài trong app Desktop

1. Trong tab **Code**, bấm **+** cạnh ô chat → **Plugins** → **Add marketplace**, nhập `aqua2409z/pixel-chat-themes`.
2. Chọn **pixel-themes** → **Add plugin**.
3. Gõ `/pixel` để mở bảng chọn.

Trong terminal: `claude plugin install pixel-themes --marketplace aqua2409z/pixel-chat-themes`.

## Lệnh

| Lệnh | Kết quả |
|---|---|
| `/pixel` | Mở bảng chọn có ảnh thu nhỏ của từng theme |
| `/pixel koi`, `/pixel trang`, `/pixel sua` | Đổi theme theo tên hoặc tên tiếng Việt không dấu |
| `/pixel off` | Tắt |
| `/pixel side` | Mở khung cảnh bên cạnh |
| `/pixel band` | Bật/tắt dải cảnh trên ô chat |
| `/pixel tint` | Bật/tắt tô màu tin nhắn |

Lệnh tên là `/pixel` vì `/theme` là lệnh có sẵn của Claude Code. Theme bạn chọn được lưu lại cho các phiên sau.

## Giới hạn

Mod chính thức chỉ vẽ được ở những vị trí app cho phép: dải trên ô chat, khung bên cạnh và quanh tin nhắn. Nó không vẽ được phía sau toàn bộ khung chat. Muốn hình nền phủ kín cả cửa sổ thì dùng userscript trong thư mục cha (claude.ai trên trình duyệt, hoặc tab Chat qua DevTools).

## Phát triển

```
hooks/register.tsx   lệnh /pixel, bảng chọn, dải cảnh, khung bên cạnh, tô màu tin nhắn
hooks/scenes.ts      9 cảnh pixel dạng SVG tự chuyển động (SMIL)
types/index.d.ts     kiểu của trạng thái đã lưu
tests/pixel.test.tsx kiểm thử trên terminal, desktop, vscode, mobile
```

Kiểm tra: `claude plugin validate .` và `claude plugin test .`

## Giấy phép và ủng hộ

[MIT](../LICENSE). Pixel Themes miễn phí. Nếu thấy hữu ích, bạn có thể ủng hộ tác giả tuỳ tâm qua **MB Bank `0923017526`**, hoặc bấm ⭐ Star cho [repo](https://github.com/aqua2409z/pixel-chat-themes).
