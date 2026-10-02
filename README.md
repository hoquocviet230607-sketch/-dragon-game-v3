# Dragon Game V3 Online

## Tính năng
- Đăng ký/đăng nhập
- JWT session
- Database SQLite
- WebSocket multiplayer realtime
- Nhiều iPhone cùng vào một thế giới
- Di chuyển server-authoritative
- Quái và đánh quái
- EXP, level, HP, vàng
- Lưu nhân vật

## Deploy server
Server cần một host Node.js hỗ trợ WebSocket và persistent disk nếu muốn dữ liệu SQLite không mất khi restart/deploy.

Thiết lập:
- PORT: host tự cấp hoặc 8080
- JWT_SECRET: chuỗi bí mật dài
- DATA_DIR: thư mục persistent, nếu host hỗ trợ

Chạy:
npm install
npm start

## Deploy client
Đưa toàn bộ thư mục client lên một static hosting HTTPS.

Sau khi có domain server, mở:
client/game.js

và đổi:
wss://YOUR-SERVER-DOMAIN

thành:
wss://domain-server-cua-ban

Ví dụ:
wss://dragon-server.example.com

## Quan trọng
Không để JWT_SECRET mặc định khi public.
Client phải dùng wss:// khi website chạy HTTPS.
Bản này là prototype; production nên thêm rate limit, anti-cheat, validation sâu hơn, reconnect, heartbeat, logging và backup database.

## Chạy chỉ bằng iPhone
Bạn vẫn có thể triển khai bằng các dịch vụ cloud có giao diện web/mobile, nhưng server phải được host online. iPhone chỉ là thiết bị quản lý/khởi chạy và chơi game; server không chạy bền vững trong Safari.
