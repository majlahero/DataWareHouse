Sakila Data Warehouse Project
Dự án xây dựng Kho dữ liệu (Data Warehouse) dựa trên cơ sở dữ liệu mẫu Sakila, nhằm hỗ trợ phân tích xu hướng khách hàng và hiệu quả kinh doanh của cửa hàng cho thuê phim.

Tổng quan đề tài
Dự án tập trung vào việc chuyển đổi dữ liệu tác nghiệp (OLTP) sang mô hình kho dữ liệu (OLAP) để giải quyết các bài toán phân tích kinh doanh như:
Business Performance: Đánh giá doanh thu theo nhân viên và thế mạnh của từng nhân viên.
Rental Expense: Phân tích chi tiêu khách hàng theo khu vực địa lý và xác định "khung giờ vàng".
Film Actor Analysis: Phân tích sức hút thương mại của diễn viên đối với lượt thuê phim.
Film Inventory Analysis: Theo dõi tình trạng tồn kho và giá trị thuê theo thể loại phim.
Customer Segment: Phân khúc khách hàng dựa trên mô hình RFM (Recency, Frequency, Monetary).

Công cụ sử dụng
Hệ quản trị CSDL: SQL Server Management Studio 2019.
Công cụ ETL: Visual Studio tích hợp SQL Server Integration Services (SSIS).
Mô hình hóa đa chiều: SQL Server Analysis Services (SSAS)
Trực quan hóa dữ liệu: Power BI Desktop.
Kiến trúc kho dữ liệu
Dự án sử dụng lược đồ Galaxy Schema (Lược đồ giải ngân hà) bao gồm các bảng Fact và Dimension chính:

Bảng Fact:
FactBPerformance (Hiệu suất kinh doanh)
FactRentalExpense (Chi phí thuê phim)
FactFilmActor (Phân tích diễn viên)
FactFilmInventory (Phân tích tồn kho)
FactCustomerSegment (Phân khúc khách hàng)

Bảng Dimension:
DimDate, DimAddress, DimCustomers, DimRentals, DimStaffs, DimInventory, DimActors.

Quy trình triển khai
Thiết kế OLAP: Xác định các quy trình nghiệp vụ (Business Processes) và xây dựng Detailed Bus Matrix.
Xây dựng ETL (SSIS): * Trích xuất dữ liệu từ nguồn Sakila.
Staging dữ liệu để xử lý chuẩn hóa.
Sử dụng Slowly Changing Dimension (SCD) để load dữ liệu vào các bảng Dim và Fact.
Phân tích đa chiều (SSAS): * Xây dựng khối Cube.
Thiết lập các phân cấp (Hierarchy) như: Địa lý (Country > City > District > Address), Thời gian (Year > Quarter > Month > Date).


Trực quan hóa (Power BI): Xây dựng Dashboard trả lời các câu hỏi kinh doanh chiến lược.
Kết quả phân tích tiêu biểu
Thể loại phim: Sports dẫn đầu doanh thu (12.1K USD) trong khi Comedy có hiệu suất tốt nhất khi vừa nằm trong top doanh thu vừa có tỉ lệ tồn kho thấp.
Thị trường tiềm năng: Ấn Độ và Trung Quốc là hai thị trường trọng điểm mang lại nguồn thu lớn nhất.
Thời điểm kinh doanh: Quý 3 đóng góp tới 82.4% tổng doanh thu năm.
