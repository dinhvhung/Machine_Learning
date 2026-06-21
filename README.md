# Machine Learning Project


## Mục Lục

- [Giới thiệu](#giới-thiệu)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Các dự án](#các-dự-án)
- [Cài đặt](#cài-đặt)

## Giới thiệu

Project này là một tập hợp các thuật toán Học máy được triển khai, nhằm mục đích:

- Học tập và thực hành các thuật toán ML cổ điển
- So sánh hiệu năng giữa các mô hình khác nhau
- Nghiên cứu các kỹ thuật xử lý dữ liệu và feature engineering
- Phân tích mô hình thông qua SHAP values
- Khám phá ensemble methods và advanced techniques


## Công nghệ sử dụng

- **Python 3.x**
- **Jupyter Notebook**
- **Scikit-learn**
- **XGBoost**
- **SHAP**
- **Pandas**
- **NumPy**
- **Matplotlib & Seaborn**

## Các dự án

### 1. Linear Regression (Hồi quy Tuyến tính)

**Thư mục:** `Linear Regression/`

Nghiên cứu về hồi quy tuyến tính cho dự đoán giá nhà:
- Xây dựng mô hình dự đoán giá nhà
- Đánh giá hiệu năng mô hình
- Xuất kết quả dự đoán ra file CSV

**File chính:** `testing.ipynb`

---

### 2. KNN + MLP + SVM + XGBoost

**Thư mục:** `KNN + MLP + SVM + XG/`

So sánh 4 thuật toán machine learning trên dataset California Housing:

#### K-Nearest Neighbors (KNN)
- **File:** `KNN_(K_Nearest_Neighbors).ipynb`
- Thuật toán phân loại dựa trên khoảng cách
- Thích hợp cho các bài toán phân loại nhỏ đến vừa

#### Multi-Layer Perceptron (MLP)
- **File:** `MLP_(Multi_Layer_Perceptron).ipynb`
- Mạng nơ-ron nhân tạo đa tầng
- Khả năng học các mô hình phi tuyến tính

#### Support Vector Machine (SVM)
- **File:** `SVM_(Support_Vector_Machine).ipynb`
- Máy vector hỗ trợ cho phân loại và hồi quy
- Hiệu quả với dữ liệu high-dimensional

#### XGBoost (Extreme Gradient Boosting)
- **File:** `XGBoost.ipynb`
- Thuật toán gradient boosting advanced
- Thường đạt kết quả tốt nhất trong các cuộc thi
- Bao gồm: training, tuning hyperparameter, feature importance

#### Data Preprocessing
- **File:** `ML_DataPreprocessing.ipynb`
- Xử lý dữ liệu thiếu, chuẩn hóa, feature scaling
- Feature engineering techniques
- EDA (Exploratory Data Analysis)

#### Model Explainability
- **File:** `SHAP_20_Scenarios_Full_Report.csv`
- SHAP values để giải thích các dự đoán của mô hình
- Phân tích đóng góp của từng feature

**Dataset:** California Housing (20,640 samples, 8 features)

---

### 3. Random Forest

**Thư mục:** `Random Forest/`

**File:** `RandomForest_completed.ipynb`

- Triển khai Random Forest trên housing dataset
- Ensemble learning với multiple decision trees
- Đánh giá hiệu năng và feature importance
- So sánh với các mô hình khác

**Dataset:** `housing.csv`

---

## Cài đặt

### Yêu cầu
- Python 3.7 hoặc cao hơn
- pip hoặc conda

### Các bước cài đặt

1. **Clone repository:**
```bash
git clone https://github.com/dinhvhung/Machine_Learning.git
cd Machine_Learning
```

2. **Cài đặt dependencies:**
```
pip install jupyter numpy pandas scikit-learn matplotlib seaborn xgboost shap
```

3. **Khởi chạy jupyter:**
```
jupyter notebook
```
