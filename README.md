Các ghi chép về MaxScale MariaDB
Maxscale là gì ?
Có hai mô hình cân bằng tải: lớp transport và lớp application. HAProxy là một cân bằng tải TCP tuyệt vời, nhưng nó lại có những hạn chế về khả năng của mình để giải quyết các vấn đề mở rộng quy mô nhất định trong môi trường cơ sở dữ liệu phân tán. Trong thế giới mã nguồn mở, có được một vài cân bằng tải cho SQL, cụ thể là MySQL Proxy, ProxySQL và MaxScale, nhưng tất cả đều là bản beta và không thích hợp để sử dụng trong môi trường production. Vì vậy, trong bài viết này tôi muốn muốn chia sẻ về đội ngũ MariaDB phát hành một phiên bản GA của MaxScale đầu năm nay.
MariaDB MaxScale là thế hệ tiếp theo database proxy dùng để quản lý an ninh, khả năng mở rộng và tính sẵn sàng cao trong quá trình triển khai. Sử dụng MaxScale, quản lý các tiến trình cơ sở dữ liệu đang chạy mà không gây hại đến hoạt động của ứng dụng. Kiến trúc MariaDB MaxScale được thiết kế để tăng tính linh hoạt và tùy biến.
Tại sao lại sử dụng MariaDB MaxScale
Bảo vệ cơ sở dữ liệu của bạn
MaxScale ngăn chặn các cuộc tấn công bảo mật như SQL injection và DDoS.
Cơ sở dữ liệu sẽ luôn luôn là một mục tiêu cho tin tặc tìm cách để truy cập thông tin nhạy cảm. MaxScale giúp giảm thiểu truy cập không mong muốn và cung cấp các tính năng cơ sở dữ liệu tường lửa tiên tiến đảm bảo cơ sở dữ liệu của bạn ở mọi cấp độ.
•	Hỗ trợ SSL end-to-end để truy cập dữ liệu an toàn
•	Ngăn chặn các cuộc tấn công SQL injection với whitelist và blacklist
•	Giảm thiểu các cuộc tấn công DDoS bằng cách cấu hình quy tắc tỷ lệ hạn chế
Quản lý Scale-Out
Quản lý truy cập 1 cách tập trung. MaxScale là proxy cơ sở dữ liệu, cho phép mở rộng quy mô cơ sở dữ liệu theo chiều ngang trong trường hợp cần bảo trì hệ thống. MariaDB MaxScale cung cấp khả năng mở rộng transaction , khả năng mở rộng dữ liệu và mở rộng binlog thông qua:
•	Thời gian đáp ứng truy vấn nhanh hơn thông qua SQL-aware router
•	sharding dữ liệu đơn giản với định tuyến truy vấn
•	Tăng thêm hiệu năng khi mở rộng với Binlog server
Đảm bảo tính sẵn sàng cao
Giảm downtime, MaxScale tự động failover và đồng bộ.
