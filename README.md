# Hướng Dẫn Cài Đặt Miner SixGPT

Bài hướng dẫn này chủ yếu dành cho việc cài đặt để đào **SixGPT ($SIX)** trên Linux. Nếu bạn muốn chạy trên Windows, vui lòng tìm hiểu thêm về **Docker Desktop** và **WSL 2**.


---

Trước khi thực hiện các bước cài đặt, bạn cần:

- Truy cập [SixGPT](https://sixgpt.xyz/) kết nối ví **EVM** và tài khoản **Google**. 
  **Lưu ý:** Sử dụng **ví phụ** và **Google clone** để đảm bảo an toàn
- VPS chạy hệ điều hành Linux (Ubuntu/Debian).
- Đã cài đặt `git` và có kiến thức cơ bản về terminal.
- Private Key hợp lệ cho ví của bạn.

---

## Các Bước Cài Đặt

1. **Clone Repository và Chuẩn Bị Môi Trường**
   ```bash
   git clone https://github.com/sixgpt/miner.git && cd miner
   sudo apt update && sudo apt install -y docker.io docker-compose
   ```

2. **Thiết Lập Biến Môi Trường**
   Tạo file `.env` với nội dung sau:
   ```bash
   echo -e "VANA_PRIVATE_KEY=0x_demo_privatekey\nVANA_NETWORK=mainet\nOLLAMA_API_URL=http://ollama:11434/api" > .env
   ```

   - Thay thế `0x_demo_privatekey` bằng **Private Key** của ví bạn.

3. **Khởi Động Miner**
   Chạy lệnh sau để cài đặt và khởi động quá trình đào:
   ```bash
   docker-compose up -d
   ```

   Hệ thống sẽ tự động tải các image cần thiết và khởi động miner ở chế độ nền.

---

## Quản Lý Miner

- **Dừng Miner**
  ```bash
  docker-compose down
  ```

- **Kiểm Tra Log và Trạng Thái Quá Trình**
  ```bash
  docker-compose logs -f
  ```

---

## Lưu Ý

- Đảm bảo VPS của bạn có đủ tài nguyên để chạy Docker và quá trình đào.
- Bảo mật Private Key của bạn và không chia sẻ với bất kỳ ai.

Để biết thêm chi tiết hoặc hỗ trợ, vui lòng tham khảo [repository chính thức](https://github.com/sixgpt/miner)

# [TopAME | Bullish - Cheerful](https://t.me/xTopAME) | Airdrop - Retroactive 
