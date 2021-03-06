# Pfsense



###1.	Giới thiệu về tường lửa.

Tường lửa, firewall, là rào chắn mà một số cá nhân, tổ chức, doanh nghiệp thiết lập để ngăn chặn người dùng mạng Internet truy cập các thông tin không mong muốn hoặc/và ngăn chặn người dùng từ bên ngoài truy nhập các thông tin bảo mật nằm trong mạng nội bộ. Nói cách khác, tường lửa là một thiết bị giúp kiểm soát các truy cập giữa mạng công cộng và mạng nội bộ, để bảo đảm an toàn cho sự vận hành của mạng nội bộ.

### 2.	Giới thiệu về Pfsense.

PfSense là tường lửa mềm, tức là bạn chỉ cần một máy tính bất kì, hoặc tốt hơn là một máy chủ, rồi cài đặt pfSense là đã có ngay một tường lửa mạnh mẽ cho hệ thống mạng trong doanh nghiệp. 

Trong phân khúc tường lửa cho doanh nghiệp vừa và nhỏ, với khoảng dưới 1000 người sử dụng, pfSense được đánh giá là tường lửa nguồn mở tốt nhất hiện nay với khả năng đáp ứng lên tới hàng triệu kết nối đồng thời. 

### 3.	Tính năng của Pfsense.

####3.1	Alias.

Alias là một cách để ta có thể Group nhiều Port hoặc nhiều Network lại với nhau. Lợi ích của Aliases giúp ta có thể làm cho bảng Rule trở nên gọn hơn nhờ việc tạo ít Rule hơn.

#### 3.2	NAT.

NAT trên Pfsense để cho các user đi được Internet đã được tạo ra một cách tự động. Công việc NAT này là để cho ta NAT một server ra ngoài internet hay còn gọi là NAT outside.

##### 3.3	Rules.

Tạo Rules để cho phép ta quản lý traffic đi qua cổng LAN hoặc WAN của PFSENSE. Ta có thể Block, Pass hoặc Reject một traffic khi nó đi qua interface được áp dụng Rules.

#### 3.4	Traffic shaper.

Traffic shaper giúp bạn theo dõi và quản lí bang thông mạng dễ dàng và hiệu quả hơn.

Traffic shaping là phương pháp tối ưu hóa kết nối internet. Nó tăng tối đa tốc độ trong khi đảm bảo tối thiểu thời gian trễ.

Khi sử dụng những gói dữ liệu ACK dduwoj sắp xếp thứ tự ưu tiên trong đường truyền tải lên, điều này cho phép tiến trình tải về được tiếp tục với tốc độ tối đa.

#### 3.5	Firewall Schedules.

Các firewall rule có thể được sắp xếp để nó chỉ có thể hoạt động vào các hời điểm nhất định trong ngày hoặc vào những ngày nhất định cụ thể hoặc các ngày trong tuần.


#### 3.6 Virtual IPs.

Một virtual IPs có thể sử dụng bất kỳ địa chỉ IP của pfsense, đó không phải là một địa chỉ IP chính. Trong các tính huống khác nhau, mỗi trog số đó có các tính năng riêng của nó. 

###4.	Một số dịch vụ của Pfsense.
#### 4.1	VPN.

-	OpenVPN
-	PPTP
-	L2TP
-	IPSEC

####4.2	DHCP server 

DHCP server chỉnh cấu hình cho mạng TCP/IP bằng cách tự động gán các địa chỉ IP cho khách hàng khi họ vào mạng.

#### 4.3	Load Balancer.

Chức năng cân bằng tải của Pfsense có những đặc điểm:

**Ưu điểm:**

-	Miễn phí
-	Có khả năng bổ sung thêm tính năng bằng gói dịch vụ cộng thêm
-	Dễ cài đặt, cấu hình

**Hạn chế:**

-	Phải trang bị thêm modem nếu không có sẵn
-	Không được hỗ trò từ nhà sản xuất như các thiết bị cân bằng tải khác
-	Vẫn chưa có tính năng lọc URL như các thiết bị thương mại.
-	Đòi hỏi người sử dụng phải có kiến thức cơ bản về mạng để cấu hình.


### 5. Hướng dẫn lab mô hình client to site OpenVPN trên Pfsense

**Mô hình** 

<img src = "http://i.imgur.com/cbUMoj8.png">

**Yêu cầu**

- Một máy Pfsense server có hai card mạng, 1 card bridge và 1 card private
-	Một máy client- window 7


**Cài đặt:** 

-	Cài gói Openvpn Client Export Ultility trên Pfsense

<img src = "http://i.imgur.com/BMRSivp.png">

<img src = "http://i.imgur.com/Ujv5cdY.png">

Màn hình báo như này nghĩa là bạn đã cài đặt thành công: 

<img src = "http://i.imgur.com/8k7SPUT.png">

- Tạo chứng thực CAs để cấp phát cho Server và client ( chứng thực khi openvpn) 

<img src = "http://i.imgur.com/ReG8x0K.png">

<img src = "http://i.imgur.com/yeq5bsr.png">

<img src = "http://i.imgur.com/at5UILF.png">

- Tạo user 

<img src = "http://i.imgur.com/lhNziWd.png">

<img src = "http://i.imgur.com/febDoqO.png">

<img src = "http://i.imgur.com/bO6LpDF.png">

***Chú ý:*** Chọn Certificate Authority chính là CAs bạn vừa tạo

<img src = "http://i.imgur.com/NoKMbFk.png">

-	Cấu hình trên Pfsense server:

<img src = "http://i.imgur.com/XRk6Kao.png">

<img src = "http://i.imgur.com/wca6wvB.png">

<img src = "http://i.imgur.com/HvEo4cI.png">

<img src = "http://i.imgur.com/wca6wvB.png">

<img src = "http://i.imgur.com/lc3QFBp.png">

<img src = "http://i.imgur.com/btHcLjh.png">

<img src = "http://i.imgur.com/v9Lm1Rg.png">

<img src = "http://i.imgur.com/0Sf4Lg9.png">

<img src = " http://i.imgur.com/WVSoTfA.png">

<img src = " http://i.imgur.com/OEz3BQS.png">

<img src = "http://i.imgur.com/NcvZ7hS.png">

<img src = "http://i.imgur.com/ZSkefwC.png">

Chọn tab Client export để export file :

<img src = "http://i.imgur.com/Focau06.png">

Chọn file phù hợp để cài đặt vào máy client. Ở đây, chọn Windows Installer : x64-win6 
Sau đó copy sang máy client file vừa tải về từ Pfsense server 

<img src = "http://i.imgur.com/6GO5Me8.png">

<img src = "http://i.imgur.com/ktpLkZ7.png">

Click chuột phải vào OpenVPN GUI -> Run as administrator 

<img src = "http://i.imgur.com/cg6KEM1.png">

<img src = "http://i.imgur.com/Hqr7zF1.png">

Điền username " thomhanu" password: 123456: chính là user tạo ở trên.

<img src = "http://i.imgur.com/LPypzKN.png">

Kết nói OpenVPN thành công, client nhận địa chỉ ip từ server là 10.10.10.6

<img src = "http://i.imgur.com/43l8irg.png">



