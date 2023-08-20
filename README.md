# Phần mềm mô phỏng xe tự hành - UIT_CAR_RACING 2023 - UNITY 

[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/Untitled-1.png">](https://www.facebook.com/groups/543385419476851) 

Phầm mềm được sử dụng chính thức trong cuộc thi UIT CAR RACING - 2023

Thông tin cuộc thi: [here](https://ceday.uit.edu.vn/uit-car-racing/)

# Cài đặt phần mềm mô phỏng

Link tải map: [here](https://    )


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
git clone https://github.com/phonghongs/Unity-UIT_Car.git
cd /Unity-UIT_Car
pip install -r requirements.txt
```


# Hướng dẫn sử dụng

Sau khi cài đặt các thư viện cần thiết và có code giao tiếp vừa clone từ link git ở trên, ta bắt đầu vào chi tiết code

Cấu trúc Folder:    
                    Code test Simulation|

                        --------------------|Raw code|
                                                -------|client.py
                                                -------|client4docker.py


* client.py:
```
python client.py --ip <ip unity opened> --port <port unity opened in that ip>
# Sử dụng để test giải thuật trên máy tính cá nhân
```

* client4docker.py:
```
python client4docker.py --ip <ip unity opened> --port <port unity opened in that ip>
# Sử dụng để chạy trên môi trường docker gửi cho BTC
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
     - Contact me helper
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/facebook.png">](https://www.facebook.com/dung.caophantien.9) 
[<img src="https://github.com/dungcnttimd/UIT_CAR_2023/blob/main/Introduction/icon/youtube.png">](https://www.youtube.com/channel/UCcGFgzsdLvnejZKDTkGk-EA) 


* **Chu Thanh Nhan** - *Develope and Operation* - [thanhnhan](https://github.com/nhanuit02)
    - Contact me helper:

* **Ly Hong Phong** - *Develope and Operation* - [phonghongs](https://github.com/phonghongs)


## License
CEEC - UIT
