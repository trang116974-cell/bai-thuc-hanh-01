# bai-thuc-hanh-01
# Bai tap chuong 1

## Bai 1: Giai phuong trinh ax^2 + bx + c = 0
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
    %% Neu a != 0
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
#include <stdio.h>
#include <math.h>
void Giaiphuongtrinhbac2(float a,float b, float c)
{
	printf("Giai phuong trinh: %.2fx^2 + %.2fx + %.2f = 0\n",a,b,c);
	if(a==0){
		if(b==0){
			if(c==0){
				printf("Phuong trinh co vo so nghiem\n");
			}
			else{
				printf("Phuong trinh vo nghiem\n");
			}
		}else {
			float x = -c/b;
			printf("Phuong trinh co nghiem duy nhat %.2f\n",x);
		}
	}
	else {
		float delta = b*b - 4*a*c;
		printf("%2.f\n",delta);
		if(delta<0){
			printf("Phuong trinh vo nghiem\n");
		}else{
			float x1= (-b-sqrt(delta) / 2*a);
			float x2= (-b+sqrt(delta) / 2*a);
			printf("Phuong trinh co hai nghiem phan biet\n");
			printf("x1= %.2f\n",x1);
			printf("x2= %.2f\n",x2);	
		}
	}	
}
int main()
{
	float a,b,c;
	printf("Nhap he so a,b,c:");
	scanf("%f %f %f",&a,&b,&c);
	Giaiphuongtrinhbac2(a,b,c);
	return 0;
}
## Bai 2: Ktra so nguyen to
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
## Bai 3: Tim so lon nhat trong day so
```mermaid
graph TD
    Start([Bat dau]) --> Nhap[/Nhap so luong tu n va day so gom n so /]
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
## Bai 4: Tim boi chung nho nhat (BCNN)
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
