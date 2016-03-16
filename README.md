# dd_command

<h3 name="top">Mục lục</h3>
<ol>
  <li><a href="#modau">Mở đầu và khuyến nghị</a></li>
  <li><a href="#khainiem">Khái niệm và ứng dụng của câu lệnh</a></li>
  <li><a href="#cuphap">Cú pháp và các trường tùy chọn</a></li>
			<ol type="a" >
			<li><a href="#cp1">Cú pháp</a></li>
			<li><a href="#cp2">Các tùy chọn</a></li>
			</ol>
   <li><a href="#vidu">Các ví dụ trong hay được sử dụng trong thực tế:</a></li>
			<ol type="a">
			<li><a href="#vd1">Sao lưu - phục hồi toàn bộ ổ cứng hoặc phân vùng trong ổ cứng</a></li>
			<li><a href="#vd2">.Sao lưu phục hồi MBR</a></li>
			<li><a href="#vd3">Chuyển đổi chữ thường thành chữ in hoa</a></li>
			<li><a href="#vd4">Tạo một file có dung lượng cố định</a></li>
			</ol>
   <li><a href="#thucte">Các tình huống áp dụng trong thực tế</a></li>
   <li><a href="#top">Kết luận</a></li>
</ol>

<p name="modau">
	<h3><b>1. Mở đầu và khuyến nghị</b></h3><br>

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các th=uật ngũ liên quan đến ổ cứng, và kiến thức về MBR...<br>
</p>
<p name="khainiem">
	<h3><b>2. Khái niệm và ứng dụng của câu lệnh</b></h3><br>
  Câu lệnh `````dd`````` trong linux là một trong những câu lệnh thường xuyên được sử dụng. Câu lệnh dd dùng để sử dụng trong các trường hợp sau:
<ul>
<li>Sao lưu và phục hồi toàn bộ dữ liệu ổ cứng hoặc một partition</li>
<li>Chuyển đổi định dạng dữ liệu từ ASCII sang EBCDIC hoặc ngược lại</li>
<li>Sao lưu lại MBR trong máy (MBR là một file dữ liệu rất quan trong nó chứa các lệnh để LILO hoặc GRUB nạp hệ điều hành)</li>
<li>Chuyển đổi chữ thường sang chữ hoa và ngược lại</li>
<li>Tạo một file với kích cỡ cố định</li>
<li>Tạo một file ISO</li>
</ul>
</p>
<p name="cuphap">
	<h3><b>1. Mở đầu và khuyến nghị</b></h3><br>

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các thuật ngũ liên quan đến ổ cứng, và kiến thức về MBR...<br>
</p>
<p name="cp1">
	<h3><b>1. Mở đầu và khuyến nghị</b></h3><br>

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các thuật ngũ liên quan đến ổ cứng, và kiến thức về MBR...<br>
</p>
<p name="cp2">
	<h3><b>1. Mở đầu và khuyến nghị</b></h3><br>

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các thuật ngũ liên quan đến ổ cứng, và kiến thức về MBR...<br>
</p>
<p name="khainiem"></p>
<p name="cuphap"></p>
