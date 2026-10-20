# bai-thuc-hanh-01
## bai 1: So do khoi giai phuong trinh ax^2+bx+c=0
```mermaid
flowchart TD
    Start([Bắt đầu]) --> Input[/Nhập a, b, c/]
    Input --> CondA{a == 0?}
    
    %% Nhánh a == 0
    CondA -- Đúng --> PtBac1[Giải phương trình bậc nhất: bx + c = 0]
    PtBac1 --> End([Kết thúc])
    
    %% Nhánh a != 0
    CondA -- Sai --> CalcDelta[Tính Delta = b^2 - 4ac]
    CalcDelta --> CondDelta{Delta < 0?}
    
    CondDelta -- Đúng --> TxtVN[/Phương trình vô nghiệm/]
    TxtVN --> End
    
    CondDelta -- Sai --> CondDeltaZero{Delta == 0?}
    
    CondDeltaZero -- Đúng --> TxtNK[/Nghiệm kép: x = -b / 2a/]
    TxtNK --> End
    
    CondDeltaZero -- Sai --> Txt2N[/2 Nghiệm phân biệt:<br>x1 = -b + căn Delta / 2a<br>x2 = -b - căn Delta / 2a/]
    Txt2N --> End
```
## bai 2: Kiem tra so nguyen duong n co phai so nguyen to khong
```mermaid
graph TD
   A([Begin]) --> B[/Nhap so nguyen duong n/]
   B-->C["count = 0<br>i=2"]
%% Vong lap chinh
   C-->D{i<=$\sqrt{n}$}
%% Neu i<=$\sqrt{n}$ dung (True)
   D--True-->E{n % i == 0}
%% Neu n % i == 0 dung(True)
   E--True-->F[count++]
   F-->G[i++]
%% Neu n % i == 0 sai(False)
   E--False-->G
   G-->D
%% Neu i<=$\sqrt{n}$ sai(False)
   D--False-->H{count == 0}
%% Neu count == 0 dung(True)
   H--True-->I[/n la so nguyen so/]
%% Neu count == 0 sai (False)
   H--False-->J[/n ko laf so nguyen to/]
   I-->K([End])
   J-->K
```

