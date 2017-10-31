Midterm – TH2014

Với mục tiêu mở rộng thêm đối tượng khách hàng, công ty vận chuyển BARG
cung cấp thêm cho khách hàng phương thức đặt xe máy thông qua hệ thống
tổng đài điện thoại. Hệ thống hoạt động như sau:
 Khách gọi điện thoại đến tổng đài qua hotline xxx-xxx-xxxx, điện thoại viên
nghe máy, ghi nhận thông tin yêu cầu xe từ khách (loại xe: xe thường hay
xe Premium giá cao, địa chỉ đón, 1 số ghi chú khác) và chuyển vào hệ
thống xử lý. Do số lượng cuộc gọi đến là rất nhiều, nên điện thoại viên
không có nhiều thời gian để thực hiện thêm những thao tác khác.
 Hệ thống hỗ trợ tìm xe gần khách nhất (theo đường xe máy, không phải
đường chim bay), gửi thông tin khách cho xe.
 Xe đến đón khách và bắt đầu chuyến đi.
Nhóm sinh viên cần thiết kế và xây dựng bộ ứng dụng (gồm nhiều app client và
server) để phục vụ cho hệ thống tổng đài đặt xe nêu trên. Cụ thể, bộ ứng dụng
cần đáp ứng được các phần sau:

1 App điện thoại viên

 App desktop-based hoặc web-based (khuyến khích dùng desktop-
based, nhằm mục đích dễ dàng kết nối vào hệ thống phone thực tế).

 Nhận cuộc gọi, ghi nhận thông tin khách (từ sau này gọi là “điểm”)
† Địa chỉ đón khách
† Loại xe (thường hoặc PREMIUM)

2 App định vị toạ độ khách
 Web-based, kết nối dịch vụ bản đồ Google Maps
 Lần lượt thể hiện thông tin các điểm được ghi nhận bởi app điện thoại
viên => nhân viên xác định 1 cách tương đối vị trí khách trên bản đồ
(dựa vào địa chỉ & ghi chú được điện thoại viên ghi nhận)
† Nhân viên có thể sử dụng GEOCODING để xác định nhanh toạ độ dựa vào địa chỉ
† Nhân viên có thể di chuyển vị trí khách trên bản đồ 1 cách tự do, địa
chỉ khách khi đó phải được cập nhật lại tương ứng (REVERSE
GEOCODING). Lưu ý: địa chỉ gửi cho xe là địa chỉ gốc được ghi nhận
bởi điện thoại viên, không phải địa chỉ được reverse geocode.
† Trên bản đồ phải có thể hiện thông tin 10 xe gần khách nhất, giúp
nhân viên dễ dàng thao tác hơn.

3 App quản lý trạng thái điểm
 Web-based
 Thể hiện danh sách điểm cùng trạng thái tương ứng (chưa được định vị,
đã định vị xong, đã có xe nhận)
† Trong TH điểm đã có xe nhận, nhân viên có thể chọn xem đường đi
ngắn nhất từ xe đến khách trên bản đồ, thông tin tài xế nhận cũng
được thể hiện đầy đủ trên danh sách

4 Lưu ý
 Sinh viên phát sinh toạ độ khoảng 100 xe, nằm rải rác các khu vực
trung tâm TP. HCM để thử nghiệm hệ thống.
 Hệ thống chỉ tìm xe “đang sẵn sàng” để gửi điểm, không tìm xe “đang
chở khách”. Tiêu chí chọn xe cho 1 điểm là xe “đang sẵn sàng” và có
đường đi đến vị trí khách là ngắn nhất.
 Hệ thống chỉ tìm 3 lần cho 1 điểm. Nếu đủ 3 lần mà không có xe nhận,
điểm được ghi nhận là “KHÔNG CÓ XE”. Ở mỗi lần, bán kính tìm xe là
khác nhau (vd lần đầu tìm 1 xe trong bán kính 300m, lần 2 tìm trong bán
kính 600m, lần 3 tìm trong bán kính 1km).
 Có tất cả M điện thoại viên và N định vị viên làm việc đồng thời.
 Khi khách gọi lại, app điện thoại viên phải thể hiện được lịch sử các
điểm trước đây của khách cùng trạng thái tương ứng của các điểm
(chưa xác định toạ độ, đang tìm xe, không có xe nhận, ...) để điện thoại
viên phản hồi thông tin cho khách.
 Nếu khách gọi lại và yêu cầu đón tại 1 điểm đã định vị thành công trước
đây, hệ thống tự động điều xe với toạ độ định vị lần trước mà KHÔNG
chuyển sang app định vị.
 Thông tin điểm được lưu chuyển trong các app là realtime, sử dụng
Firebase hoặc SocketIO/SignalR để cài đặt.

5 Yêu cầu thêm
 Làm nhóm 2 thành viên
 Thời gian thực hiện: 3 tuần
 Cấu trúc bài nộp
† src
† db
† video (các clip quay lại các luồng xử lý chính/phụ của hệ thống)
 mỗi clip dài không quá 15s
† documents
 mô tả đầy đủ các chức năng đã thực hiện được và các chức
năng còn chưa hoàn thiện
 ảnh chụp giao diện tương ứng của các app