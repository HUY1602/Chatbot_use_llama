# Chatbot dùng Llama 3.1

Ứng dụng chatbot chạy trên web, xây dựng bằng Python và Solara. Mô hình Llama 3.1 được chạy cục bộ qua Ollama và tích hợp với giao diện bằng LangChain.

## Tính năng

- Gửi câu hỏi và nhận phản hồi từ Llama 3.1.
- Giao diện chat web tạo bằng Solara.
- Chạy mô hình qua Ollama trên máy của bạn.

## Yêu cầu

- Python 3.10 trở lên.
- [Ollama](https://ollama.com/) đã cài đặt và đang chạy.
- Mô hình `llama3.1:8b` đã được tải về.

## Cài đặt và chạy

```bash
# Tạo và kích hoạt môi trường ảo
python -m venv .venv

# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate

# Cài các thư viện của dự án
pip install -r requirements.txt

# Solara được dùng để chạy giao diện
pip install solara

# Tải mô hình (chỉ cần thực hiện một lần)
ollama pull llama3.1:8b

# Khởi chạy ứng dụng
solara run main.py
```

Sau khi chạy, mở địa chỉ URL Solara hiển thị trong terminal (thường là `http://localhost:8765`).

## Cấu trúc dự án

```text
.
├── app/
│   ├── components/     # Thành phần giao diện chat
│   ├── layouts/        # Bố cục ứng dụng
│   ├── pages/          # Trang chat và cấu hình model
│   ├── router.py       # Định tuyến
│   └── setting.py      # Cấu hình chung
├── main.py             # Điểm khởi chạy
└── requirements.txt    # Các thư viện LangChain
```

## Ghi chú

- Giữ Ollama hoạt động khi sử dụng ứng dụng.
- Ứng dụng hiện cấu hình model `llama3.1:8b` trong `app/pages/home_page.py`; nếu dùng model khác, cần đổi cấu hình tương ứng.
- Lịch sử hội thoại hiện chỉ được giữ trong bộ nhớ của ứng dụng, không lưu lâu dài.
