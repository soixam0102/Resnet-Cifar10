# Resnet-Cifar10

- Resnet là một mạng CNN được tạo ra từ việc sắp xếp hàng trăm lớp tích chập, điều mà các mạng CNN thông thường không làm được do xảy ra hiện tượng triệt tiêu đạo hàm khi xây dựng quá nhiều lớp CNN lên nhau. 
- Hiện tượng triệt tiêu đạo hàm trong quá trình huấn luyện. Do quá trình học tập mạng sẽ thông qua thuật toán backpropagation mà cập nhật các tham số, từ output layer đến input layer và tính toán đạo hàm của loss function tương ứng với từng tham số của mạng. Và gradient descent được dùng để cập nhật tham số cho từng parameter của mạng đó.
- Toàn bộ qúa trình trên được lặp đi lặp lại cho tới khi các trọng số parameter của mạng được hội tụ.
- Thông qua việc điều chỉnh các hyperparameter (số epoch, số lần mà tập dữ liệu được duyệt qua và các trọng số được cập nhật) để điều chỉnh qúa trình trên. 
- Nếu số lượng vòng epoch quá nhỏ, thì mạng có thể chưa đi được đến vị trí hội tụ cuối cùng. Nếu số epoch quá lớn sẽ dẫn đến tốn nhiều thời gian huấn luyện mà không tăng được kết quả và ngược  lại.
- Tuy nhiên các đạo hàm sẽ có giá trị nhỏ hơn khi xuống các lớp thấp hơn, dẫn đến việc  kết quả cập nhật được thực hiện bởi gradient descent không làm thay đổi nhiều weight của các layer đó và làm cho chúng không thể hội tụ và máng sẽ không thu được kết quả tốt.
- Bằng việc sử dụng một kết nối tắt đồng nhất xuyên qua nhiều một hay nhiều lớp. Một khói như vậy được gọi là residual block.
![img.png](img.png)
- Mũi tên cong biểu thị cho sự bổ xung của input X vào đầu ra, việc này để chống lại việc đạo hàm bằng 0 do vẫn cộng thêm với X. 
![img_1.png](img_1.png)
- Trong đó các đường cong nét liền thể hiện cho việc đầu vào và đầu ra là cùng kích thước, còn đường cong nét đứt tương ứng thể hiện rằng đầu vào và đầu ra không cùng kích thước, nên phải có phép biến đổi kích thước của đầu vào cho cùng với kích thước của đầu ra.