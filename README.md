# bai-thuc-hanh-01
# BÀI TẬP CHƯƠNG 1

## Bài 1: Giải phương trình ax² + bx + c = 0
```mermaid
graph TD
    Start([Bat dau]) --> Nhap[/Nhap a, b, c/]
    Nhap --> KiemTraA{a == 0?}
    
    %% Neu a = 0,  pt bac 1: bx + c = 0
    KiemTraA -- True --> KiemTraB{b == 0?}
    KiemTraB -- True --> KiemTraC{c == 0?}
    KiemTraC -- True --> VSN[/Pt vo so nghiem/]
    KiemTraC -- False --> VN1[/Pt vo nghiem/]
    KiemTraB -- False --> PtBac1[ x = -c / b] --> InX1[/In nghiem x/]
    
    %% Nếu a != 0
    KiemTraA -- False --> TinhDelta[ Delta = $\sqrt{b}$ - 4ac]
    TinhDelta --> KiemTraDelta{Delta < 0?}
    KiemTraDelta -- True --> VN2[/Pt vo nghiem/]
    KiemTraDelta -- False --> DeltaBang0{Delta == 0?}
    
    DeltaBang0 -- True --> TinhNghiemKep[ Tinh nghiem kep :x = -b / 2a] --> InKep[/In nghiem kep x/]
    DeltaBang0 -- False --> Tinh2Nghiem[Tinh x1 và x2 ] --> In2Nghiem[/In 2 nghiem x1, x2/]
    
    VSN --> End([Ket thuc])
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
