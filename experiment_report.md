# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600703
**Name:** Phạm Quang Dũng
**Date:** 10/06/2026

---

## 1. Kết quả thí nghiệm

Chạy `agent_simulation.py` với 2 bộ dữ liệu và ghi lại kết quả:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Dữ liệu đã được validate và transform, nên câu trả lời hợp lý. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Dữ liệu rác có outlier rất lớn, làm Agent chọn sai sản phẩm. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai sau khi dung Gaarbage Data?

Khi dùng Garbage Data, Agent trả lời sai vì dữ liệu đầu vào có nhiều lỗi chất lượng. Ví dụ `Nuclear Reactor` có giá `999999`, đây là outlier quá lớn nên logic tìm sản phẩm electronics giá cao nhất sẽ chọn nó thay vì sản phẩm hợp lý. Ngoài ra dữ liệu rác còn có duplicate ID, sai kiểu dữ liệu như `ten dollars`, giá bằng 0 và giá trị null. Những lỗi này làm Agent đưa ra kết quả không đáng tin cậy dù prompt có viết tốt.

---

## 3. Kết luận

**Quality Data > Quality Prompt?** (Đồng ý hay không? Giải thích ngắn gọn.)

Đồng ý. Prompt tốt không thể sửa được việc Agent đọc từ dữ liệu sai. Cần làm sạch, validate và transform dữ liệu trước khi đưa vào pipeline AI.
