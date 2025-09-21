Ly Ly — Web flasher cho ESP32 (ESP Web Tools)

1) Thay 3 file mẫu bằng file .bin của H (đặt cùng thư mục với index.html):
   - bootloader.bin  -> ảnh bootloader (thường ở offset 0x1000)
   - partitions.bin  -> bảng phân vùng (thường ở offset 0x8000)
   - firmware.bin    -> app (thường ở offset 0x10000)

   Nếu H dùng layout khác, sửa offset tương ứng trong manifest.json.

2) Mở index.html trên Chrome/Edge (desktop). Nhấn nút "Install" để chọn cổng và nạp.

3) Tùy biến manifest.json:
   - "chipFamily": ESP32 | ESP32-S2 | ESP32-S3 | ESP32-C3 (đổi theo board H)
   - "parts": liệt kê nhiều file .bin với offset khác nhau nếu cần.
   - Có thể thêm nhiều "builds" cho nhiều dòng chip.

4) Host online (tùy chọn):
   - Dùng bất kỳ static hosting nào (GitHub Pages, Nginx, v.v.).
   - Truy cập từ HTTPS sẽ ổn định hơn (Web Serial/USB cần bảo mật).

5) Lưu ý:
   - Trình duyệt hỗ trợ Web Serial: Chrome/Edge desktop mới.
   - Một số máy cần driver USB‑Serial (CP210x/CH34x/FTDI).
