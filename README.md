# bai-thuc-hanh-01
## bai 1: So do khoi giai phuong trinh ax^2+bx+c=0
```mermaid
graph TD
   A([Begin]) --> B[/a, b, c/]
    B --> C{a = 0} 
    %% Neu a=0 dung (True)
    C -- True --> D[pt bac 1: bx+c=0]
    D --> End([End]) 
    %% Neu a=0 sai(False) 
    C -- False --> E["Δ = $b^2$ - 4ac"]
    E --> F{Δ < 0} 
    %% Neu Delta < 0 dung (True)
    F -- True --> G[/VN/]
    G --> End
    %% Neu Delta < 0 sai (False)
    F -- False --> H{Delta = 0}
    %% Neu Delta = 0 dung (True)
    H -- True --> I["$x_1$ = $x_2$ = -b / 2a<br>(nghiem kep)"]
    H -- True --> I["$x_1$ = $x_2$ = -b / 2a<br>(nghiem kep)"]
    I --> J[/$x_1$,$x_2$ /]
    J --> End
    %% Neu Delta = 0 sai (False)
    H -- False --> K[" = (-b - √Δ) / 2a<br> = (-b + $\sqrt{Delta}$ ) / 2"]
    K --> L[/$x_1$<br>$x_2$/]
    L --> End
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
## bai 3: Tim so lon nhat trong mang n so nguyen
```mermaid
graph TD
   A([Begin]) --> B[/Nhap n va day so a1,a2,...,an/]

