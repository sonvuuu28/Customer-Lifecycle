# Customer 360 Analysis - Olist Dataset

## Tổng quan dự án

Mục tiêu của dự án là xây dựng **Customer 360 View** cho các khách hàng của Olist, cung cấp cái nhìn tổng quan về vòng đời khách hàng, hành vi mua sắm, chi tiêu, đánh giá và nguy cơ churn. Dự án kết hợp **phân tích dữ liệu, trực quan hóa, mô hình RFM/Clustering, dự đoán churn** và triển khai các công cụ để tương tác dữ liệu:

- **Streamlit App:** Người dùng click vào khách hàng sẽ xem toàn bộ vòng đời khách hàng.
- **n8n Chatbot:** Giải thích quy trình xử lý dữ liệu, trả lời câu hỏi và hiển thị vòng đời khách hàng.
- **PowerBI:** Báo cáo trực quan tổng hợp các insight từ dữ liệu khách hàng.

---

## Dataset

Sử dụng **Olist Brazilian E-Commerce dataset**:

- `customers.csv`: Thông tin khách hàng.
- `orders.csv`: Thông tin đơn hàng.
- `order_items.csv`: Chi tiết sản phẩm trong đơn.
- `products.csv`: Thông tin sản phẩm.
- `sellers.csv`: Thông tin người bán.
- `order_payments.csv`: Phương thức thanh toán, giá trị.
- `order_reviews.csv`: Đánh giá và feedback khách hàng.
- `geolocation.csv`: Thông tin địa lý.
- `product_category_name_translation.csv`: Dịch tên danh mục sản phẩm.

---

## Câu hỏi nghiên cứu (Research Questions)

1. **Thông tin cơ bản khách hàng**
   - Khách hàng tập trung ở vùng nào?  
   - Tổng số đơn hàng, tổng chi tiêu trung bình theo vùng?  

2. **Hành vi mua hàng (RFM)**
   - Khách hàng nào VIP? Khách hàng nào at-risk?  
   - Có outlier về tần suất hoặc giá trị đơn hàng không?  

3. **Lịch sử đơn hàng & sản phẩm**
   - Khách hàng mua sản phẩm nào thường xuyên?  
   - Có đơn hàng bất thường về số lượng hoặc giá trị không?  

4. **Đánh giá & Feedback**
   - Khách hàng nào đánh giá thấp?  
   - Thời gian giao hàng ảnh hưởng đến rating không?  

5. **Phân nhóm khách hàng**
   - Cluster khách hàng thành bao nhiêu nhóm hợp lý?  
   - Cluster nào có giá trị cao nhất?  
   - Nhóm khách hàng dễ churn?  

6. **Customer Churn**
   - Khách hàng nào có nguy cơ rời đi cao?  
   - Đặc điểm nào liên quan đến churn?  

7. **Tổng quan Customer 360**
   - Tạo bảng tổng hợp theo `customer_id` với RFM, lịch sử đơn, chi tiêu, đánh giá, cluster và trạng thái churn.  

---

## Triển khai

- **Streamlit:**  
  - Cho phép người dùng chọn khách hàng và hiển thị toàn bộ vòng đời khách hàng.
  - Dữ liệu được đọc từ file CSV/Parquet đã clean và tổng hợp từ bước EDA.

- **n8n Chatbot:**  
  - Trả lời câu hỏi về quy trình xử lý dữ liệu.
  - Hiển thị thông tin Customer 360 của từng khách hàng theo yêu cầu.

- **PowerBI:**  
  - Báo cáo trực quan tổng hợp phân tích khách hàng.
  - Dashboard tổng quan RFM, phân nhóm khách hàng, churn và hành vi mua hàng.

---

## Kết quả kỳ vọng

- Bản tổng quan **Customer 360 View** cho từng khách hàng.  
- Insight về hành vi mua hàng, giá trị khách hàng, khả năng churn.  
- Hệ thống tương tác: **click vào khách hàng → xem vòng đời → chatbot trả lời → báo cáo trực quan trên PowerBI**.  
