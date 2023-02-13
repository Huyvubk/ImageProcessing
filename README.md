# ImageProcessing
Bài viết đề câp đến một số phương pháp xử lý ảnh số cơ bản từ đó giúp mọi người có thể hiểu cơ bản về xử lí ảnh để tiếp cận vào Học Máy(Machine Learning) và Học Sâu(Deep Learning) tốt hơn. Một số  kỹ thuật xử ảnh gồm:
  1.Cải Thiện Ảnh:
    - Các phép toán điểm ảnh: s=T(r) với s,r lần lượt là ảnh sau và trước khi biến đổi; T là phép biến đổi ảnh
      + Phép đảo ảnh: r = [0,255] => s = 255-r
      + Biến đổi logarit : s = c*log(1+r) với c > 0 là tham số được chọn theo thực nghiệm
      + Biến đổi mũ(Gamma): s = c*(r^^y) với c > 0, y > 0 là 2 tham số được chọn theo thực nghiệm
      + Cắt ngưỡng : Thực chất là chuyển ảnh nhị phân nếu s>ngưỡng thì s = 225 còn s < ngưỡng thì s = 0      
    -
  2.Khôi Phục Ảnh
  3.Phân Đoạn Ảnh 
