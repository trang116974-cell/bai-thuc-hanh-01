# bai-thuc-hanh-01
# BÀI TẬP CHƯƠNG 1

## Bài 1: Giải phương trình ax^2 + bx + c = 0
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
    KiemTraA -- False --> TinhDelta[ Delta = b^2 - 4ac]
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
    Start([Bat dau]) --> Nhap[/Nhap so nguyen n/]
    Nhap --> KiemTraN{n < 2?}
    
    KiemTraN -- True --> KhongPhai1[/Khong là so nguyen to/] --> End([Kết thúc])
    
    KiemTraN -- False --> KhoiTao[ i = 2]
    KhoiTao --> VongLap{i * i <= n?}
    
    VongLap -- True --> ChiaHet{n chia het cho 2 ?}
    ChiaHet -- True --> KhongPhai2[/Khong la so nguyen to/] --> End
    ChiaHet -- False --> TangI[ i + 1 ] --> VongLap
    
    VongLap -- False --> LaSNT[/La so nguyen to/] --> End
```
## Bài 3: Tìm số lớn nhất trong dãy số
```mermaid
graph TD
    Start([1.Bat dau]) --> Nhap[/2.Nhap so luong tu n va day so gom n so /]
    
    %% Bước đặt giả định ban đầu
    Nhap --> KhoiTao[ Dat max = So thu nhat <br> Dat vi tri tiep theo: i = 2]
    
    %% Kiem tra vong lap tung so :
    KhoiTao --> VongLap{ Kiem tra <br> het day chua ? <br> i > n?}
    
    VongLap -- Chua xet het --> SoSanh{ So o vi tri thu i <br> lon hon max ko ?}
    
    %% Cap nhat max moi
    SoSanh -- Lon hon --> CapNhat[Doi max moi = so thu i] --> TangI[ Chuyen sang so tiep theo: i = i + 1]
    SoSanh -- Ko lon hon --> TangI
    TangI --> VongLap
    
    %% Ket thuc khi het day
    VongLap -- Het day --> InKetQua[/In ra so lon nhat max khi xet het day/]
    InKetQua --> End([Ket thuc])
```
## Bài 4: Tìm Bội số chung nhỏ nhất (BCNN)
```mermaid
graph TD  
    Start([Bat dau]) --> Nhap[/Nhap 2 so duong a va b/]
    Nhap --> LuuTich[ Tich = a * b]
    
    LuuTich --> VongLap{ b != 0? }
    VongLap -- Đúng --> ChiaDu[Tinh so du r = a chia lay du cho b]
    ChiaDu --> GanA[ a = b]
    GanA --> GanB[ b = r] --> VongLap
    
    VongLap -- Sai --> TinhBCNN[ BCNN = Tich / a]
    TinhBCNN --> InBCNN[/In ket qua BCNN/] --> End([Ket thuc])
```
