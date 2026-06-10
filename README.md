# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.dungpq2@vinuni.edu.vn
**Name:** Phạm Quang Dũng

---

## Mô tả

Bài lab xây dựng ETL pipeline cho `raw_data.json`: extract dữ liệu, validate record lỗi, transform category và discounted price, sau đó load kết quả ra `processed_data.csv`. Em cũng chạy agent simulation để so sánh Clean Data và Garbage Data.

---

## Cách chạy (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chạy ETL Pipeline
```bash
python solution.py
```

### Chạy Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```

---

## Cấu trúc thư mục

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output của pipeline
├── experiment_report.md     # Báo cáo thí nghiệm
└── README.md                # File này
```

---

## Kết quả

Pipeline đọc `raw_data.json`, giữ lại 3 records hợp lệ và loại 2 records lỗi. Ví dụ 2 loại records khác nhau:

- `id = 3`: Price <= 0
- `id = 4`: Missing Category

Sau transform, 3 records được lưu vào `processed_data.csv`. Khi chạy agent simulation, Clean Data trả về `Laptop at $1200`, còn Garbage Data trả về `Nuclear Reactor at $999999` do outlier.
