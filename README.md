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
   <li><a href="#ketluan">Kết luận</a></li>
</ol>

<p name="modau">
	<h3><b>1. Mở đầu và khuyến nghị</b></h3><br>

Xin chào các bạn. Hôm nay tôi sẽ giới thiệu một command dd trong hệ thống Linux. Để có thể hiểu hết được ý nghĩa của câu lệnh này và các tùy chọn của câu lệnh trước tiên bạn cần phải có kiến thức và cách tổ chức lưu trư dữ liệu trong ô cứng, hiều về các sector,tracks, Cylinders,.. các th=uật ngũ liên quan đến ổ cứng, và kiến thức về MBR...<br>
</p>
<p name="khainiem">
	<h3><b>2. Khái niệm và ứng dụng của câu lệnh</b></h3><br>
  Câu lệnh dd trong linux là một trong những câu lệnh thường xuyên được sử dụng. Câu lệnh dd dùng để sử dụng trong các trường hợp sau:
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
	<h3><b>3. Cú pháp và các trường tùy chọn</b></h3><br>
<p name="cp1">
	<h4><b>Cú pháp</b></h4><br>
	#dd if=<địa chỉ đầu vào> of=<địa chỉ đầu ra> option
	
	Trong đó:
	
<li>if= địa chỉ nguồn của dữ liệu nó sẽ bắt đầu đọc</li>
<li>of= viết đầu ra của file</li>
<li>option : các tùy chọn cho câu lệnh</li>
</p>
<p name="cp2">
	<h3><b> Các tùy chọn</b></h3><br>
</p>
</p>

Tùy chọn | Ý nghĩa |
|-----|---------|
|bs=Bytes |Quá trình đọc (ghi) bao nhiêu byte một lần đọc (ghi) |
|cbs=Bytes|Chuyển đổi bao nhiêu byte một lần |
|count=Blocks | thực hiện bao nhiêu Block trong quá trình thực thi câu lệnh |
|if | Chỉ đường dẫn đọc đầu vào |
|of | Chỉ đường dẫn ghi đầu ra|
|ibs=bytes | Chỉ ra số byte một lần đọc |
|obs=bytes | Chỉ ra số byte một lần ghi |
|skip=blocks | Bỏ qua bao nhiêu block đầu vào |
|conv=Convs | Chỉ ra tác vụ cụ thể của câu lệnh, các tùy chọn được ghi dưới bảng sau đây |

**Các tùy chọn của conv**

|Tùy chọn | Tác dụng  |
|-----------|----------|
|ascii | Chuyển đôi từ mã EBCDIC sáng ASCII |
|ebcdic | Chuyển đổi từ mã ASCII sang EBCDIC |
|lcase | Chuyển đổi từ chữ thường lên hết thành chữ in hoa |
|ucase | Chuyển đổi từ chữ in hoa sang chữ thường |
|nocreat | Không tạo ra file đầu ra |
|noerror | Tiếp tục sao chép dữ liệu khi đầu vào bị lỗi |
|sync | Đồng bộ dữ liệu với ổ đang sao chép sang |



*Lưu ý:* Khi bạn định dạng số lượng byte mỗi lần đọc. Mặc định nó được tính theo đơn vị là kB. Bạn có thể thêm một số trường sau để báo định dạng khác:

- c = 1 byte
- w = 2 byte
- b = 512 byte
- kB = 1000 byte 
- K = 1024 byte 
- MB = 1000000 byte
- M = (1024 * 1024) byte
- GB = (1000 * 1000 * 1000) byte
- G = (1024 * 1024 * 1024) byte

<p name="vidu"></p>


#### 4. Các ví dụ trong hay được sử dụng trong thực tế:

<p name="vd1"></p>
###### a. Sao lưu - phục hồi toàn bộ ổ cứng hoặc phân vùng trong ổ cứng
- Sao lưu toàn bộ dữ liệu ổ cứng sao ổ cứng khác:
```
#dd if=/dev/sda of=/dev/sdb conv=noerror,sync
```
Câu lệnh này dùng dể sao lưu toàn bộ dữ liệu của ổ sda sang ổ sdb với tùy chọn trong trường conv=noerrom.sync với ý ngĩa vẫn tiếp tục sao lưu nếu dữ liệu đầu vào bị lỗi và tự động đồng bộ với dữ liệu sdb

- Tạo một file image cho ổ sda1. Các này sẽ nhanh hơn là viêc chuyển dữ liệu sao ổ khác
```
dd if=/dev/sda1 of=/root/sda1.img 
```
- Nếu muốn nén ảnh file anh vào bạn có thể sử dụng command sau
```
dd if=/dev/sda1 | gzip > /root/sda1.img.gz
```
-Sao lưu dữ liệu từ một phân vùng này đến một phân vùng khác
```
dd if=/dev/sda2 of=/dev/sdb2 bs=512 conv=noerror,sync
```
*Đối với câu lệnh này bs=512 có ý nghĩa mỗi lần đọc ghi nó đọc và ghi 512 byte*
- Phục hồi dữ liệu 
```
dd if=/root/sda1.img of=/dev/sda1
```
- Sao lưu từ đĩa CDroom
```
dd if=/dev/cdrom of=/root/cdrom.img conv=noerror
```

<p name="vd2"></p>

###### b.Sao lưu phục hồi MBR
Việc sao lưu lại MBR là việc làm cần thiết đối với hệ thống linux. nó đề phòng cho việc khi virus có thể nhảy được hẳn vào vùng MBR. Lúc bày bất kì một phần mềm diệt virus nào cũng không diệt được con virus này. Cách hay nhất là cài đặt lại MBR và lúc đó việc sao chép MBR lúc trước khi nhiễm sẽ phát huy tác dụng:
- Sao chép MBR
```
dd if=/dev/sda1 of=/root/mbr.txt bs=512 count=1
```

<img src="http://www.mediafire.com/convkey/488e/f841i516de79fqxzg.jpg" > </img>

- Phục hồi lại MBR
```
dd if=/root/mbr.txt of=/dev/sda1
```

<p name="vd3"></p>
###### c. Chuyển đổi chữ thường thành chữ in hoa
- Chuyển chữ thường thành chữ in hoa
```
dd if=/root/test.doc of=/root/test1.doc conv=ucase
```
<img class="image__pic js-image-pic" src="http://www.mediafire.com/convkey/a72c/7yfo3pxytbj5t97zg.jpg" alt="" id="screenshot-image">

- Chuyển chứ hoa thành chứ thường
```
dd if=/root/test1.doc of=/test2.doc conv=lcase,sycn
```
<p name="vd4"></p>

###### d. Tạo một file có dung lượng cố định 
Tạo ra một file có kích thước 100M
```
dd if=/dev/zero of=/root/file1 bs=100M count=1
```
<img class="image__pic js-image-pic" src="http://www.mediafire.com/convkey/c6a9/ha3jf4zkdkk19ifzg.jpg" alt="" id="screenshot-image">
<p name="thucte"></p>

#### 5. Các tình huống áp dụng trong thực tế

Các ví dụ tôi vừa nêu trên đều sử dụng rất nhiều trong thực tế. Ngoài ra còn kết hợp với một số câu lệnh để làm thêm tác vụ khác như:

- VD1: Kết hợp với câu lệnh mkswap để tạo phân vùng swap cho máy 
    - Sử dụng câu lênh dd để tạo một phân vùng trống có kích cỡ 1G:
```
dd if=/dev/zero of=/root/swap bs=1024M count=1
```


  - Gán quyền cho nó chỉ root mới vào xem được
```
chmod 600 /root/swap
```
- Chỉ cho đến vùng swap
```
mkswap /root/swap
```
```
swapon /root/swap 
```
 
 Lúc này tổng dung lượng phân vùng swap sẽ là 2G ( do trước đó tôi cài đặt cho phân vùng swap là 1G trước rồi )
 
 Nếu bạn muốn tạo vùng swap không bị mất khi reboot lại máy. Bạn vào file này rồi chỉnh sửa như sau:
 ```
 vi /etc/fstab
 rồi chỉnh sửa:
 /root/swap                 swap                    swap                defaults        0  0
 ```
 <img class="image__pic js-image-pic" src="http://www.mediafire.com/convkey/849a/hhb2i7zrke3z9y3zg.jpg" alt="" id="screenshot-image">
 
 
 VD2: Ngoài ra bạn còn có thể kết hợp với câu lênh crontab để có thể lâp lịch sao chép dữ liêu ổ cứng của bạn theo định kì
Đầu tiên vào một file sh để chạy
```
vi dd_command.sh
với nội dung là:
dd if=/dev/sda1 of=/dev/sdb1 conv=noerror,sync
```
Tạo một crotab cho file chạy

```
crontab 0 10 * * * sh dd_command.sh
```
Lúc này đến 10h hàng ngày quá trình sao chép dữ liệu giữa ổ sda1 sang ổ sdb1 được thực hiện
<p name="ketluan"></p>
#### 6. Kết luận

Bài viết trên đây tôi đã giới thiệu cho các bạn về câu lệnh dd một câu lệnh thường xuyên được sử dụng trong quản trị hệ thống Linux. Ngoài những tùy chọn tổi liệt kê là những tùy chọn thường xuyên được sử dụng trong thực tế thì vẫn còn một số tùy chọn khác thêm nữa. [Các bạn có thể xem đây đủ tại đây](http://www.computerhope.com/unix/dd.htm).
Tài liệu tham khảo:

[Link 1](http://www.computerhope.com/unix/dd.htm)

[Link 2](http://linoxide.com/linux-command/linux-dd-command-create-1gb-file/)

[Link 3](http://www.thegeekstuff.com/2010/10/dd-command-examples/)

[Link wiki](http://en.wikipedia.org/wiki/Dd_(Unix))

