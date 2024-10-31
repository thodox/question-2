# question-2

Develop a prototype system that can schedule a meeting for multiple users, based on their availability and constraints communicated through messages. For example: 

User A: "I am available every morning from 9 to 11 AM, except on Wednesdays." 

User B: "I am free on Tuesdays, but if possible, I prefer an early morning slot."

User C: "I already have a meeting booked on Friday from 2 to 4 PM." 

Outline the key design considerations and decisions you have made, providing reasoning for each choice. You should also clearly state any assumptions you have made during the design process.


# Thiết kế hệ thống sắp xếp cuộc họp


## Xác định đối tượng người dùng

•	Đối tượng sử dụng: Hệ thống sẽ phục vụ nhiều nhóm người dùng khác nhau, như nhân viên công ty, giảng viên, sinh viên, và nhóm nghiên cứu. Mỗi nhóm sẽ có những đặc thù và yêu cầu riêng về việc tổ chức họp. Cần phân loại người dùng theo các tiêu chí như: quan trọng, bình thường và vãng lai.

•	Lý do: Việc phân loại người dùng giúp hiểu rõ hơn về nhu cầu họp của từng nhóm, đặc biệt là các thành viên quan trọng, những người có vai trò quyết định trong các dự án. Đảm bảo sự có mặt của họ sẽ tăng cường hiệu quả cuộc họp. Hệ thống sẽ ưu tiên các lịch họp theo mức độ quan trọng của người dùng.
## Tính năng nhập dữ liệu

•	Nhập dữ liệu tự do: Người dùng có thể nhập thông tin về thời gian họp bằng ngôn ngữ tự do, không bị giới hạn bởi các mẫu nhập có sẵn.

•	Linh hoạt trong giao tiếp: Khả năng nhập liệu tự do cho phép người dùng diễn đạt thông tin một cách tự nhiên, linh hoạt, giúp quá trình tương tác trở nên thuận tiện hơn.
## Phân tích yêu cầu

•	Khả dụng: Hệ thống cần thu thập thông tin về thời gian rảnh của từng người dùng thông qua các câu nhắn trong quá trình nhập dữ liệu.

•	Ràng buộc: Cần xem xét các ràng buộc khác nhau, như thời gian người dùng không có mặt hoặc không thích một khoảng thời gian nhất định.

•	Thời gian và múi giờ: Hệ thống cần xử lý các múi giờ khác nhau nếu người dùng ở nhiều địa điểm khác nhau.

## Phân tích và chuyển đổi tính khả dụng

•	Xử lý ngôn ngữ tự nhiên (NLP): Áp dụng các thuật toán NLP để phân tích và trích xuất khoảng thời gian mà người dùng đã nhập bằng ngôn ngữ tự do.

•	Lý do sử dụng NLP: Công nghệ này giúp chuyển đổi và trích xuất thông tin từ dữ liệu người dùng nhập vào thành văn bản mà hệ thống có thể hiểu và xử lý yêu cầu cụ thể.

•	Ví dụ: Từ câu “Tôi rảnh vào tất cả các buổi sáng từ 9 giờ đến 11 giờ, trừ thứ Tư,” hệ thống sẽ trích xuất được khoảng thời gian từ 9 giờ đến 11 giờ sáng từ thứ Hai đến thứ Ba, thứ Năm và thứ Sáu.

## Quản lý đặt lịch

•	Cân nhắc: Kiểm tra lịch trình đã đặt trước để xác định khoảng thời gian mà người dùng đã có lịch riêng, đồng thời xác định mức độ quan trọng của họ trong cuộc họp.

•	Lý do: Việc này giúp tránh xung đột lịch trình, đảm bảo rằng không ai phải tham gia cuộc họp trong khi họ đã có kế hoạch khác và bảo đảm sự hiện diện của những người quan trọng.

•	Ví dụ: Nếu người dùng C đã đặt lịch họp vào thứ Sáu từ 2 đến 4 giờ chiều và là người quan trọng, hệ thống sẽ không đề xuất thời gian này cho cuộc họp mới.

## Gợi ý thời gian và biểu quyết
•	Cân nhắc: Dựa vào thông tin về tính khả dụng của mọi người, hệ thống sẽ gợi ý một hoặc nhiều thời gian họp phù hợp. Người dùng có thể đánh dấu tham gia cuộc họp nào trong hệ thống.

•	Lý do: Cung cấp nhiều tùy chọn thời gian giúp người dùng dễ dàng tìm được thời gian phù hợp với lịch trình của tất cả mọi người. Hệ thống cũng sẽ tối ưu hóa lịch họp dựa trên các yếu tố như thời tiết, cơ sở vật chất hoặc tình trạng chỗ ngồi.

•	Tích hợp AI: Hệ thống có thể sử dụng AI để phân tích lịch sử họp và hành vi của người dùng nhằm gợi ý thời gian họp tối ưu hơn. AI có thể tự động học từ dữ liệu trước đó và điều chỉnh các đề xuất dựa trên phản hồi của người dùng, nhằm tối ưu hóa quy trình sắp xếp cuộc họp.

8. Giao diện người dùng

•	Cân nhắc: Thiết kế giao diện cần thân thiện, đơn giản và dễ sử dụng, kèm theo hướng dẫn rõ ràng cho người dùng.

•	Lý do: Một giao diện dễ sử dụng sẽ giảm thiểu nhầm lẫn và sai sót trong quá trình nhập dữ liệu, giúp người dùng nhanh chóng làm quen với hệ thống.

•	Tính năng:

o	Form nhập liệu: Cung cấp một biểu mẫu cho phép người dùng nhập thông tin một cách dễ dàng và trực quan.

o	Lịch hiển thị: Một lịch thể hiện các cuộc họp đã đặt và thời gian trống, giúp người dùng dễ dàng hình dung.

o	Thông báo: Gửi thông báo về thời gian họp qua email cho người dùng.

o	Tính năng tương tác AI: Người dùng có thể đặt câu hỏi và nhận phản hồi từ hệ thống AI về các cuộc họp, giúp họ nhanh chóng giải quyết các vấn đề liên quan đến việc đặt lịch.





# Giả Định Trong Quá Trình Thiết Kế
1.Người dùng có kiến thức cơ bản về công nghệ: Giả định rằng người dùng có khả năng sử dụng máy tính và thiết bị di động. Điều này sẽ giúp giảm thiểu nhu cầu đào tạo và tạo điều kiện thuận lợi cho việc sử dụng hệ thống.
2. Sự chấp nhận của người dùng đối với tính năng AI: Người dùng được kỳ vọng sẽ chấp nhận việc sử dụng AI để hỗ trợ trong việc sắp xếp cuộc họp. Sự chấp nhận này sẽ ảnh hưởng đến khả năng áp dụng các thuật toán và tính năng tự động trong hệ thống.
3. Dữ liệu đầu vào đầy đủ và chính xác: Người dùng sẽ nhập thông tin một cách đầy đủ và chính xác. Việc thiếu thông tin hoặc sai sót trong dữ liệu có thể ảnh hưởng đến kết quả của hệ thống.
4.  Khả năng tích hợp với các lịch trình hiện tại: Hệ thống sẽ có khả năng tích hợp và đồng bộ hóa với các ứng dụng lịch mà người dùng đang sử dụng như Google Calendar hay Outlook. Điều này sẽ giúp người dùng dễ dàng quản lý cuộc họp hơn.
5. Mọi người dùng có thời gian rảnh tương đương: Giả định rằng trong một số tình huống, thời gian rảnh của các thành viên trong nhóm sẽ được phân phối đều. Tuy nhiên, điều này cần được kiểm tra lại trong thực tế.
6. Tính năng thông báo được đáp ứng kịp thời: Hệ thống sẽ gửi thông báo về thời gian họp một cách kịp thời. Điều này giúp người dùng không bỏ lỡ cuộc họp và cải thiện hiệu quả tổ chức.
7. Khả năng phân tích thời gian thực: Hệ thống có khả năng phân tích thông tin theo thời gian thực để đưa ra gợi ý chính xác, yêu cầu hệ thống phải có khả năng truy cập và xử lý dữ liệu liên tục.
8.  Sự đa dạng trong địa điểm và múi giờ: Người dùng có thể ở nhiều địa điểm khác nhau và sử dụng các múi giờ khác nhau, do đó hệ thống cần có khả năng tự động chuyển đổi múi giờ.
9. Tính linh hoạt trong lịch trình cuộc họp: Người dùng có thể thay đổi lịch trình hoặc yêu cầu họp vào những thời điểm khác nhau. Hệ thống cần phải thích ứng nhanh với những thay đổi này.

