# Machine_Learning
# Hồi quy tuyến tính (Linear Regression) - Dự đoán giá nhà

## Giới thiệu
Thư mục này chứa mã nguồn và tài liệu liên quan đến việc triển khai mô hình **Hồi quy tuyến tính (Linear Regression)** để dự đoán giá nhà dựa trên bộ dữ liệu California Housing (`housing.csv`). 

Mục tiêu của dự án nhỏ này không chỉ là xây dựng một mô hình Hồi quy tuyến tính cơ bản, mà còn áp dụng các kỹ thuật Kỹ thuật đặc trưng (Feature Engineering) phức tạp và Điều chuẩn (Regularization) để ép mô hình tuyến tính đạt được hiệu năng cao nhất có thể đối với một bài toán có tính phi tuyến tính cao.

## Các file chính
- `testing.ipynb`: Jupyter Notebook chính chứa toàn bộ mã nguồn từ bước đọc dữ liệu, phân tích, tiền xử lý, huấn luyện mô hình đến đánh giá kết quả.
- `housing.csv`: Tập dữ liệu gốc được sử dụng (California Housing Dataset).
- `ket_qua_du_doan_gia_nha.csv`: File đầu ra chứa kết quả so sánh trực tiếp giữa giá nhà thực tế và giá nhà do mô hình dự đoán (được sinh ra sau khi chạy notebook).

## Các kỹ thuật áp dụng

### 1. Tiền xử lý & Trích xuất đặc trưng (Feature Engineering)
Nhằm khắc phục nhược điểm "quá đơn giản" của Hồi quy tuyến tính, bộ dữ liệu đã được biến đổi sâu:
- **Xử lý dữ liệu thiếu:** Điền giá trị trung vị (median) cho các trường bị thiếu (`total_bedrooms`).
- **Tạo đặc trưng mới (Domain Knowledge):**
  - Các tỷ lệ quan trọng: `rooms_per_household`, `bedrooms_per_room`, `population_per_household`, `income_per_room`.
  - Đặc trưng địa lý: Tính toán khoảng cách tuyến tính đến các trung tâm kinh tế lớn (Los Angeles, San Francisco) dựa trên kinh độ/vĩ độ.
  - **Phân cụm (Clustering):** Sử dụng thuật toán **K-Means (k=10)** để phân mảnh vị trí địa lý thành các cụm (`geo_cluster`), giúp mô hình nắm bắt được sự phân hóa giá nhà theo khu vực (Vùng Vịnh, Thung lũng trung tâm, v.v.).
- **Mã hóa & Chuẩn hóa:** Sử dụng One-Hot Encoding (`pd.get_dummies`) cho các biến phân loại và `StandardScaler` để đưa toàn bộ dữ liệu về cùng một thang đo.

### 2. Xây dựng và Nâng cấp Mô hình
- **Linear Regression (Baseline):** Mô hình hồi quy tuyến tính cơ bản tạo điểm chuẩn.
- **Polynomial Regression (Đa thức):** Sinh ra các đặc trưng đa thức để bắt các mối quan hệ phi tuyến tính và sự tương tác giữa các biến.
- **Ridge Regression (Chuẩn L2):** Áp dụng để hạn chế Overfitting khi số lượng đặc trưng mới được tạo ra quá nhiều, giúp phân bổ trọng số đồng đều.
- **Lasso Regression (Chuẩn L1):** Tự động đưa trọng số của các đặc trưng nhiễu hoặc kém quan trọng về 0, thực hiện chức năng chọn lọc đặc trưng (Feature Selection).

## Kết quả thực nghiệm
- **Mô hình cơ bản:** Đạt điểm $R^2 \\approx 0.64$ và RMSE $\\approx 68,938$.
- **Mô hình nâng cấp:** Sau khi áp dụng tối đa các kỹ thuật Feature Engineering và Polynomial/Regularization, điểm số trên tập huấn luyện đã tăng lên $\\approx 0.658$, chứng minh mô hình đã tiếp thu được các mối quan hệ phức tạp hơn trong dữ liệu.

## Hướng dẫn cài đặt và sử dụng

1. **Yêu cầu thư viện:**
   Đảm bảo bạn đã cài đặt các thư viện Python cần thiết:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```
2. **Chạy dự án**
   Mở terminal tại thư mục này và khởi chạy Jupyter Notebook:
   ```bash
   jupyter notebook testing.ipynb
   ```
   Chạy toàn bộ các cell (Run All) để xem quá trình huấn luyện và xuất ra file kết quả ket_qua_du_doan_gia_nha.csv.
