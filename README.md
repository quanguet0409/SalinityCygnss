# SalinityCygnss

<div align="center">

![CYGNSS](https://img.shields.io/badge/CYGNSS-Satellite%20Data-blue?style=for-the-badge)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Prediction-green?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-Jupyter-orange?style=for-the-badge)

**Dự Đoán Xâm Nhập Mặn Bằng Dữ Liệu CYGNSS và Học Máy**

*Ứng dụng viễn thám vệ tinh và machine learning để giám sát xâm nhập mặn tại Đồng Bằng Sông Cửu Long*

---

[Giới Thiệu](#giới-thiệu) • [Quy Trình](#quy-trình-nghiên-cứu) • [Cài Đặt](#cài-đặt) • [Sử Dụng](#sử-dụng) • [Mô Hình](#các-mô-hình) • [Nguồn Dữ Liệu](#nguồn-dữ-liệu)

</div>

---

## Giới Thiệu

**SalinityCygnss** khai thác dữ liệu vệ tinh **CYGNSS** kết hợp **Machine Learning** (Random Forest, XGBoost, CatBoost) để lập bản đồ và dự đoán xâm nhập mặn tại Đồng Bằng Sông Cửu Long.

### Các Khu Vực Nghiên Cứu

- **Đồng Bằng Sông Cửu Long 2025** - Nghiên cứu toàn diện
- **Trà Vinh 2024** - Phân tích khu vực
- **Bến Tre 2020** - Dữ liệu lịch sử
- **Bạc Liêu 2019** - Nghiên cứu nền

### Tại Sao Quan Trọng?

Xâm nhập mặn đang ảnh hưởng nghiêm trọng đến ĐBSCL do biến đổi khí hậu, mực nước biển dâng và lượng nước ngọt giảm. Dự án này cung cấp giải pháp giám sát quy mô lớn, tiết kiệm chi phí với độ phân giải cao.

---

## Quy Trình Nghiên Cứu

<div align="center">

![Sơ đồ quy trình](flowchart.png)

</div>

### Các Bước Chính

1. **Thu Thập Dữ Liệu** → DEM, khí tượng, CYGNSS, viễn thám, thổ nhưỡng
2. **Dữ Liệu Thực Địa** → Đo mặn thực địa, kiểm chứng phòng thí nghiệm
3. **Tiền Xử Lý** → Làm sạch, chuẩn hóa, tạo bộ dữ liệu
4. **Mô Hình Hóa** → Random Forest, XGBoost, CatBoost
5. **Kiểm Định** → K-Fold Cross Validation
6. **Đánh Giá** → RMSE, MAE, R (hệ số tương quan)
7. **Kết Quả** → Bản đồ xâm nhập mặn, bản đồ phân bố độ mặn

---

## Cài Đặt

### Yêu Cầu

- Python 3.8+
- Jupyter Notebook
- Git

### Cài Đặt Nhanh

```bash
git clone https://github.com/quanguet0409/SalinityCygnss.git
cd SalinityCygnss
pip install -r requirements.txt
```

### Thư Viện Chính

`numpy` • `pandas` • `scikit-learn` • `xgboost` • `catboost` • `matplotlib` • `seaborn` • `geopandas` • `rasterio`

---

## Sử Dụng

### Chạy Mô Hình

```bash
cd Mekong2025/Model
jupyter notebook
```

Chọn một trong ba notebook:
- `RF.ipynb` - Random Forest
- `XGB.ipynb` - XGBoost  
- `CB.ipynb` - CatBoost

### Quy Trình Trong Notebook

1. Load dữ liệu → 2. Tiền xử lý → 3. Huấn luyện → 4. Đánh giá → 5. Dự đoán → 6. Trực quan hóa

---

## Cấu Trúc Dự Án

```
SalinityCygnss/
├── Mekong2025/              # ĐBSCL 2025 (mới nhất)
│   ├── Data/                # 91 files
│   ├── Model/               # RF, XGB, CB notebooks
│   ├── Model Results/       # 15 output files
│   ├── Results/             # Bản đồ dự đoán
│   └── SHP/                 # Shapefiles ĐBSCL
├── TraVinh2024/             # Trà Vinh
│   ├── Data/                # 19 files
│   └── SHP/                 # 8 shapefiles
├── BenTre2020/              # Bến Tre
│   ├── Data/                # 19 files
│   ├── Model/               # 3 models
│   └── Results/             # 3 outputs
├── BacLieu2019/             # Bạc Liêu
├── LICENSE
├── README.md
└── flowchart.png
```

---

## Các Mô Hình

### 1. Random Forest (RF)
Tổng hợp nhiều cây quyết định, kháng overfitting, xử lý mối quan hệ phi tuyến.

### 2. XGBoost (XGB)
Gradient boosting hiệu suất cao, điều chuẩn tự động, xử lý missing values.

### 3. CatBoost (CB)
Xử lý đặc trưng phân loại tốt, hỗ trợ GPU, tốc độ dự đoán nhanh.

### Đánh Giá Mô Hình

- **R** - Hệ số tương quan
- **RMSE** - Root Mean Square Error
- **MAE** - Mean Absolute Error
- **K-Fold Validation** - Kiểm định chéo

---

## Kết Quả

Mỗi nghiên cứu cung cấp:
- Mô hình đã huấn luyện
- Chỉ số hiệu suất (R, RMSE, MAE)
- Feature importance rankings
- Bản đồ dự đoán xâm nhập mặn
- Validation plots

*Chi tiết trong thư mục `Results/` và `Model Results/`*

---

## Nguồn Dữ Liệu

<div align="center">

![SAE Logo](sae_logo.png)

**VIỆN CÔNG NGHỆ HÀNG KHÔNG VŨ TRỤ**  
Trường Đại Học Công Nghệ - Đại Học Quốc Gia Hà Nội

</div>

### Dữ Liệu Chính

**Dữ Liệu CYGNSS**
- Nguồn: NASA CYGNSS Level 1 Science Data Record
- Cung cấp: **ThS. Hoàng Tích Phúc** - phucth@vnu.edu.vn
- Đơn vị: Viện Công Nghệ Hàng Không Vũ Trụ - ĐH Công Nghệ - ĐHQG Hà Nội

**Dữ Liệu Điểm Mặn Thực Địa**
- Đo đạc hiện trường và phân tích phòng thí nghiệm
- Cung cấp: **TS. Hà Minh Cường** - cuonghm@vnu.edu.vn
- Đơn vị: Viện Công Nghệ Hàng Không Vũ Trụ - ĐH Công Nghệ - ĐHQG Hà Nội

### Dữ Liệu Phụ Trợ

Mô hình số độ cao (DEM) • Sử dụng đất/lớp phủ • Tính chất đất • Biến khí hậu

---

## Giấy Phép

Dự án sử dụng giấy phép MIT - xem [LICENSE](LICENSE).

---

## Liên Hệ

**Tác Giả**: [Tên của bạn]  
**Email**: [email@example.com]  
**Tổ Chức**: Viện Công Nghệ Hàng Không Vũ Trụ - ĐH Công Nghệ - ĐHQG Hà Nội

**GitHub**: [https://github.com/quanguet0409/SalinityCygnss](https://github.com/quanguet0409/SalinityCygnss)

---

## Lời Cảm Ơn

- NASA CYGNSS mission
- TS. Hà Minh Cường và ThS. Hoàng Tích Phúc
- Viện Công Nghệ Hàng Không Vũ Trụ - ĐH Công Nghệ - ĐHQG Hà Nội
- Đội ngũ thực địa và cộng đồng mã nguồn mở

---

## Trích Dẫn

```bibtex
@software{SalinityCygnss2025,
  author = {Tên Của Bạn},
  title = {SalinityCygnss: Dự Đoán Xâm Nhập Mặn Bằng Dữ Liệu CYGNSS và Học Máy},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/quanguet0409/SalinityCygnss}
}
```

---

<div align="center">

⭐ **Nếu thấy hữu ích, hãy cho repo một ngôi sao!** ⭐

*Phát triển vì nông nghiệp bền vững tại Đồng Bằng Sông Cửu Long*

</div>