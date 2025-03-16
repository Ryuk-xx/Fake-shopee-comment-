# Dự án phân loại bình luận Shopee giả mạo do máy tạo
Đây là dự án sử dụng các mô hình llm được huấn luyện trên dữ liệu thực tế là bình luận của người dùng trên nền tảng mua sắm trực tuyến Shopee để phân loại các bình luận giả mạo do máy tính tạo ra. Từ đó có thể loại bỏ các bình luận này để tăng tính chân thật cho đánh giá sản phẩm.

## Cấu trúc dự án

```
├── shopee.ipynb                   # Script lấy mẫu và tiền xử lý dữ liệu comments trên shopee 
├── create_fine_tuned_gpt2.ipynb   # Script fine tune model LLM GPT2 trên dữ liệu shopee
├── create_data_generation         # Script sử dụng fine-tuned GPT2 để sinh các fake comments
├── main.ipynb                     # Xây dựng các mô hình phân loại comments giả mạo
└── shopee_data/                   # Thư mục chứa dữ liệu comments sau khi tiền xử lý và sinh bởi LLM
```

## Cài đặt
### 1. Cài đặt các thư viện Python
```
pip install -r requirements.txt
```

### 2. Tải bộ dữ liệu comments shopee từ kaggle
```
!pip install kagglehub
import kagglehub

# Download latest version
path = kagglehub.dataset_download("thinhtran2045/shopee-data")

print("Path to dataset files:", path)
```
Hoặc tải trực tiếp từ đường dẫn: https://www.kaggle.com/datasets/thinhtran2045/shopee-data

## Hướng dẫn sử dụng
### 1. Quy trình hoạt động 
####   a. Tải các thư viện và bộ dữ liệu như trên
####   b. Xử lý và lấy mẫu dữ liệu
Chạy script shopee.ipynb
####   c. Fine tune mô hình GPT2-vn trên tập huấn luyện
Chạy script create_fine_tuned_gpt2.ipynb 
####   d. Tạo bình luận giả mạo bằng LLM
Chạy script create_data_generation.ipynb
####   e. Xây dựng model phân loại bình luận giả mạo 
Chạy script main.ipynb

## Chú ý:
- Việc huấn luyện trên mô hình lớn cần GPU đủ mạnh, khuyến khích sử dụng kaggle notebook hoặc gg colab để huấn luyện
- Trong main.ipynb đang sử dụng mặc định là model NlpHUST/bert-base-vn trên HunggingFace, có thể sử dụng một số mô hình khác: vinai/phobert-base-v2, FacebookAI/xlm-roberta-base
