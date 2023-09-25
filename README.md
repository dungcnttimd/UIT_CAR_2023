# Phần mềm mô phỏng xe tự hành - UIT_CAR_RACING 2023 - UNITY 

[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/Untitled-1.png">](https://www.facebook.com/groups/543385419476851) 

Phầm mềm được sử dụng chính thức trong cuộc thi UIT CAR RACING - 2023

Thông tin cuộc thi: [here](https://ceday.uit.edu.vn/uit-car-racing/)

# Cài đặt phần mềm mô phỏng


Các bạn tải map về và giải nén sẽ thu đc 2 folder:

* Folder Windows: dùng cho các bạn sử dụng nền tảng window, chạy file [tên map].exe (vd: 3D_MAP1-V2.exe)

* Folder Linux: dùng cho các bạn sử dụng nền tảng Linux (Khuyến nghị: Ubuntu 18.04), chạy file [tên map].x86_64 (vd: Map_1.x86_64)
    + Trước khi chạy file mô phỏng trên linux, các bạn bấm chuột phải vào file thực thi -> Properties -> Permissions -> tick vào ô Execute: Allow executing file as program

* Folder MacOS.app: truy cập và chạy file chứa trong đường dẫn .\MacOS.app\Contents\MacOS

# Cài đặt các thư viện bắt buộc - Python

### Phần mềm mô phỏng cuộc thi UIT CAR RACING sử dụng phương thức giao tiếp Socket-Io 
### Để giao tiếp với phần mềm mô phỏng btc sử dụng ngôn ngữ Python (Đối với các đội sử dụng ngôn ngữ khác để giao tiếp với phần mềm mô phỏng, btc không có trách nhiệm hỗ trợ)

Để đảm bảo tránh xung đột với môi trường chung của hệ thống, các bạn có thể tạo môi trường mới python 3.7 (mình sử dụng Anaconda) để chạy các lệnh sau nhé.

* python 3.7
```
git clone https://github.com/dungcnttimd/UIT_CAR_2023.git
cd /UIT_CAR_2023
pip install -r requirements.txt
```


# Hướng dẫn sử dụng

Sau khi cài đặt các thư viện cần thiết và có code giao tiếp vừa clone từ link git ở trên, ta bắt đầu vào chi tiết code

Cấu trúc Folder:
```
----|UIT_CAR_2023|
--------|4Linux|
------------|Map|
----------------|<MapName>|
----------------|<|<MapName>_Data|
----------------|<|<MapName>.x86_64|             (#)
----------------|<|UnityPlayer.so|
------------|Code|
----------------|code.py|
----------------|uit_ce_ceec_uitcarracing2023.so|

------------|4Windows|
----------------|Map|
--------------------|<MapName>|
------------------------|MonoBleedingEdge|
------------------------|<MapName>_Data|
------------------------|<MapName>.exe|             (#)
------------------------|UnityCrashHandler64.exe|
------------------------|UnityPlayer.dll|
----------------|Code|
--------------------|code.py|
--------------------|uit_ce_ceec_uitcarracing2023.so|
```




```
from uit_ce_ceec_uitcarracing2023 import uitcarracing
car = uitcarracing()    #init car
car.connect("127.0.0.1", 1111)

car.help()
```
* code.py:
```
python code.py
# Sử dụng để test giải thuật trên máy tính cá nhân
```



```
from uit_ce_ceec_uitcarracing2023 import uitcarracing
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("--port", type=int, help="Specify the port number")
parser.add_argument("--ip", type=str, help="Specify the port number")
args = parser.parse_args()
ip = args.ip
port = args.port

car = uitcarracing()    #init car
car.connect(ip, port)

car.help()
```
* code.py:
```
python code.py --ip <ip unity opened> --port <port unity opened in that ip>
# Sử dụng để test giải thuật trên máy tính cá nhân
```


Code này chứa mẫu giao tiếp với phần mềm mô phỏng, các đội nên code vào những phần mà đã gợi ý dưới đây

    - Chương trình đưa cho bạn 1 giá trị đầu vào:
            * image: hình ảnh trả về từ xe
            * current_speed: vận tốc hiện tại của xe
            * current_angle: góc bẻ lái hiện tại của xe

    - Bạn phải dựa vào giá trị đầu vào này để tính toán và gán lại góc lái và tốc độ xe vào 2 biến:
        * Biến điều khiển: sendBack_angle, sendBack_Speed
        Trong đó:
            + sendBack_angle (góc điều khiển): [-25, 25]  NOTE: ( âm là góc trái, dương là góc phải)
            + sendBack_Speed (tốc độ điều khiển): [-150, 150] NOTE: (âm là lùi, dương là tiến)

# Kết thúc

## Chúc các bạn hoàn thành tốt lượt thi của mình

## Authors
* **Cao Phan Tien Dung** - *Develope and Operation* - [dungcnttimd](https://github.com/dungcnttimd)
     - Contact me helper:
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/linkin.png">](https://www.linkedin.com/in/caophantiendung8) 
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/facebook.png">](https://www.facebook.com/dung.caophantien.9) 
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/youtube.png">](https://www.youtube.com/channel/UCcGFgzsdLvnejZKDTkGk-EA) 


* **Chu Thanh Nhan** - *Develope and Operation* - [thanhnhan](https://github.com/nhanuit02)
    - Contact me helper:
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/facebook.png">](https://www.facebook.com/Thanh.Nhan.428204)

* **Ly Hong Phong** - *Develope and Operation* - [phonghongs](https://github.com/phonghongs)
    - Contact me helper:
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/facebook.png">](https://www.facebook.com/hongphong.ly.7)

* **Nguyen Anh Quoc** - *Develope* - [QuocAnhNguyenDL](https://github.com/QuocAnhNguyenDL)
    - Contact me helper:
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/facebook.png">](https://www.facebook.com/profile.php?id=100039482056792)

## License
CEEC - UIT
