# ImageProcessing
Bài viết đề câp đến một số phương pháp xử lý ảnh số cơ bản từ đó giúp mọi người có thể hiểu cơ bản về xử lí ảnh để tiếp cận vào Học Máy(Machine Learning) và Học Sâu(Deep Learning) tốt hơn.
Một số  kỹ thuật xử ảnh gồm:
  1.Cải Thiện Ảnh:
    - Các phép toán điểm ảnh: s=T(r) với s,r lần lượt là ảnh sau và trước khi biến đổi; T là phép biến đổi ảnh
      + Phép đảo ảnh: r = [0,255] => s = 255-r
      + Biến đổi logarit : s = c*log(1+r) với c > 0 là tham số được chọn theo thực nghiệm
      + Biến đổi mũ(Gamma): s = c*(r^^y) với c > 0, y > 0 là 2 tham số được chọn theo thực nghiệm
      + Cắt ngưỡng : Thực chất là chuyển ảnh nhị phân nếu s>ngưỡng thì s = 225 còn s < ngưỡng thì s = 0  
      
    - Lát cắt mặt phẳng Bit( bit plane sciling): Là phép toán chuyển ma trận các giá trị điểm ảnh về giá trị nhị phân
      + Bước 1: Chuyển ảnh đa cấp xám sang ma trận mà mỗi phần tử chứa chuỗi bit (ảnh số biểu diễn tối đa 8 bit)
      + Bước 2: Tách thành các na trận mặt phẳng bit, mỗi ma trận nhỏ chứ 1 bit
      + Bước 3: Tái tạo ảnh:chuyển ảnh nhị phân thành đa cấp xám 
      
     - Kỹ thuật Histogram: chỉ ra phân bố mức xám trên ảnh
        + r(i) là mức xám của pixel thứ i của ảnh f(x,y) có L mức xám với i = [0,255]
        + n(r(i)) = n(i) với n(i) là tổng số pixel có giá trị mức xám là r(i)
        + p(r(i)) = n(i)/(M*N) là histogram chuẩn hóa với M,n là số hàng, cột của ma trận ảnh
        
      -  Lọc ảnh trong miền không gian:
      
        @ Làm mịn ảnh :sử dụng ma trận vuông kt m*m ví dụ 3*3,4*4,... thường được gọi là kernel,filter,mask
          + Lọc trung bình : (1/m*m)* (ma trận vuông kích thước m*m với các giá trị đều =1)
            * Giúp loại bỏ nhiễu, làm nổi các chi tiết lớn
          + Lọc trung vị(median) :Trung vị là số ở giữa của tập dữ liệu, giúp cải thiện sự ảnh hưởng của giá trị outlier so với trung bình
            * Gúp loại bỏ nhiễu
          + Lọc min: tương tự như 2 bộ lọc trên nhưng giá trị nhân là giá trị min
          + Lọc max: tương tự như 2 bộ lọc trên nhưng giá trị nhân là giá trị max
          + Bộ lọc Gaussian :
          
         @ Làm sắc nét ảnh : làm nổi bật các chi tiết trong ảnh tức làm nổi các biên ảnh
         + Lọc đạo hàm bậc 1 : Robert cross gradient, bộ lọc Sobe;
         + Lọc đạo hàm bậc 2 : Bộ lọc Laplacian     
  2.Khôi Phục Ảnh :
    Nhiễu xuất hiện trong quá trình thu nhận ảnh, số hóa và truyền
    
    - Nhiễu Gaussian : do mạch điện tử, cảm biến, ánh sáng kém, phân bố xác suất của nhiều tính bằng hàm Gaussian
    - Nhiễu Xung : Đặc trưng bởi 1 điểmn ảnh có giá trị mức xám khác biệt so với những điểm lân cận
    - Nhiễu Reyliegh:
    - Nhiễu Erlang(gammar):
    - Nhiễu hàm mũ:
    - Nhiễu đồng nhât(Uniform):
    
    Khôi phục ảnh: là thu nhận 1 ảnh càng gần với ảnh gốc thông qua việc bỏ nhiễu
    Các bộ lọc trong miền không gian:
    - Lọc trung bình (số học) : làm mịn đơn giản , làm mở ảnh để loại nhiễu
    - Lọc trung bình (hình học) : làm mịn giống như số học nhưng ít làm mất chi tiết ảnh hơn
    
    
  3.Phân Đoạn Ảnh 
