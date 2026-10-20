# bai-thuc-hanh-01
# BÀI TẬP CHƯƠNG 1

## Bài 1: Giải phương trình ax² + bx + c = 0
```mermaid
graph TD
    Start([Bắt đầu]) --> Nhap[/Nhập 3 số: a, b, c/]
    Nhap --> KiemTraA{a == 0?}
    
    %% Nếu a = 0, trở thành pt bậc 1: bx + c = 0
    KiemTraA -- Đúng --> KiemTraB{b == 0?}
    KiemTraB -- Đúng --> KiemTraC{c == 0?}
    KiemTraC -- Đúng --> VSN[/Phương trình có Vô Số Nghiệm/]
    KiemTraC -- Sai --> VN1[/Phương trình Vô Nghiệm/]
    KiemTraB -- Sai --> PtBac1[Tính nghiệm: x = -c / b] --> InX1[/In nghiệm x/]
    
    %% Nếu a != 0, giải phương trình bậc 2 thông thường
    KiemTraA -- Sai --> TinhDelta[Tính Delta = b² - 4ac]
    TinhDelta --> KiemTraDelta{Delta < 0?}
    KiemTraDelta -- Đúng --> VN2[/Phương trình Vô Nghiệm/]
    KiemTraDelta -- Sai --> DeltaBang0{Delta == 0?}
    
    DeltaBang0 -- Đúng --> TinhNghiemKep[Tính nghiệm kép: x = -b / 2a] --> InKep[/In nghiệm kép x/]
    DeltaBang0 -- Sai --> Tinh2Nghiem[Tính x1 và x2 theo công thức] --> In2Nghiem[/In 2 nghiệm x1, x2/]
    
    VSN --> End([Kết thúc])
    VN1 --> End
    InX1 --> End
    VN2 --> End
    InKep --> End
    In2Nghiem --> End
```
## Bài 2: Kiểm tra Số Nguyên Tố
```mermaid
graph TD
    Start([Bắt đầu]) --> Nhap[/Nhập số nguyên n/]
    Nhap --> KiemTraN{n < 2?}
    
    KiemTraN -- Đúng --> KhongPhai1[/KHÔNG PHẢI số nguyên tố/] --> End([Kết thúc])
    
    KiemTraN -- Sai --> KhoiTao[Đặt biến i = 2]
    KhoiTao --> VongLap{i * i <= n?}
    
    VongLap -- Đúng --> ChiaHet{n có chia hết cho i không?}
    ChiaHet -- Đúng --> KhongPhai2[/KHÔNG PHẢI số nguyên tố/] --> End
    ChiaHet -- Sai --> TangI[Tăng i thêm 1 đơn vị] --> VongLap
    
    VongLap -- Sai --> LaSNT[/LÀ số nguyên tố/] --> End
```
## Bài 3: Tìm số lớn nhất trong dãy số
```mermaid
graph TD
    Start([1. Bắt đầu]) --> Nhap[/2. Nhập số lượng phần tử n <br> và dãy số gồm n số/]
    
    %% Bước đặt giả định ban đầu
    Nhap --> KhoiTao[3. Tạm coi số đầu tiên là lớn nhất: Đặt max = Số đầu tiên <br> Đặt vị trí kiểm tra tiếp theo: i = 2]
    
    %% Vòng lặp kiểm tra từng số một
    KhoiTao --> VongLap{4. Đã kiểm tra <br> hết dãy số chưa? <br> biến i > n?}
    
    VongLap -- Chưa xét hết --> SoSanh{5. Số ở vị trí thứ i <br> có lớn hơn max không?}
    
    %% Nhánh cập nhật max mới
    SoSanh -- Có, lớn hơn --> CapNhat[6. Đổi max mới = Số thứ i] --> TangI[7. Chuyển sang số tiếp theo: i = i + 1]
    SoSanh -- Không lớn hơn --> TangI
    TangI --> VongLap
    
    %% Nhánh kết thúc khi đã xem hết các số
    VongLap -- Đã xét hết --> InKetQua[/8. In ra số lớn nhất lưu trong biến max/]
    InKetQua --> End([9. Kết thúc])
```
## Bài 4: Tìm Bội số chung nhỏ nhất (BCNN)
```mermaid
graph TD  
    Start([Bắt đầu]) --> Nhap[/Nhập 2 số nguyên dương a và b/]
    Nhap --> LuuTich[Tính và lưu Tích = a * b]
    
    LuuTich --> VongLap{b khác 0?}
    VongLap -- Đúng --> ChiaDu[Tính số dư r = a chia lấy dư cho b]
    ChiaDu --> GanA[Gán a = b]
    GanA --> GanB[Gán b = r] --> VongLap
    
    VongLap -- Sai --> TinhBCNN[Tính BCNN = Tích / a]
    TinhBCNN --> InBCNN[/In kết quả BCNN/] --> End([Kết thúc])
```
