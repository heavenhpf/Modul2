# Modul 2 Praktikum : Konsep Dasar Algoritma
## 1. Variabel (Materi Pendalaman)
### 1.1 Pengenalan Variabel
![image](image1)
**Variabel** dapat dianalogikan/diibaratkan sebagai sebuah gelas, di mana dapat menampung sebuah cairan. Cairan ini dianalogikan sebagai data. Dalam artian lain, Variabel adalah suatu tempat yang digunakan untuk menampung data atau nilai pada memori yang mempunyai nilai yang dapat berubah–ubah selama proses program. Dalam bahasa C, kita tidak akan terlepas dari penggunaan variabel, karena pada dasarnya sebuah program bekerja dengan melakukan pengolahan data.

### 1.2 Deklarasi Variabel
Seperti analogi gelas sebelumnya, gelas tersebut harus ada terlebih dahulu sebelum dapat diisi dan digunakan. Pada bahasa C, variabel harus dideklarasikan terlebih dahulu sebelum bisa digunakan. Untuk mendeklarasikan sebuah variabel, sintaksnya adalah sebagai berikut.
<tipe_data> <identifier>
Misalkan, potongan kode berikut mendeklarasikan variabel x yang bertipe int.
int x
Jika ingin mendeklarasikan lebih dari satu variabel dengan tipe yang sama, bisa menggunakan operator koma (,). Syntax nya dapat dituliskan sebagai berikut:
```c
<tipe_data> <variabel1>, <variabel2>, ... dst;
```
Contohnya seperti deklarasi variabel x dan y yang bertipe int. seperti berikut ini:
```c
int x, y;
```
### 1.3 Pengisian Nilai Variabel
Setelah dideklarasikan, variabel dapat diisi oleh sebuah nilai. Untuk melakukannya, gunakan operator assignment (simbol '='). Syntax nya dapat adalah sebagai berikut:
```c
identifier_variabel = <nilai yang bersesuaian>
```
Contohnya:
```c
int x, y;  
x = 7;  
y = -3; 
```
Dalam hal ini, variabel x dan y akan mempunyai nilai masing-masing 7 dan -3.

### 1.4 Inisialisasi Variabel
Deklarasi dan pengisian nilai pada variabel dapat dilakukan dalam satu instruksi sekaligus. Hal ini disebut dengan **inisialisasi**. Dengan melakukan inisialisasi variabel, berarti kita memberikan nilai awal pada variabel tersebut. Syntax nya dapat dituliskan sebagai berikut:
```c
tipe_data identifier_variabel = <nilai yang bersesuaian>;
```
Contohnya:
```c
int x = 7;
```

## 2. Operator Matematika Sederhana
Operator dapat dipahami sebagai sesuatu yang dapat melakukan operasi pada operan (variabel/nilai). Contohnya, operator '+' digunakan untuk operasi penjumlahan. Operator matematika sederhana dapat dibagi menjadi 2, yaitu Operator Assginment dan Operator Aritmatika.

### 2.1 Operator Assignment
Operator Assignment digunakan untuk mengisikan (assign) sebuah nilai ke variabel. Simbol yang biasa digunakan adalah tanda '=' (tanda sama dengan). Contohnya:

```c
int x, y;  
x = 4;  
y = 3;  
x = x + y; // x = 7  
y = x + x; // y = 14
```

### 2.2 Operator Aritmatika
Seperti namanya, operator aritmatika melakukan operasi layaknya pada matematika seperti penjumlahan, pengurangan, pembagian dsb. Beberapa operator menggunakan simbol yang sama pada matematika (penjumlahan dengan simbol ‘+’, pengurangan dengan ‘-‘, dst.). Operator-operator aritmatika pada bahasa C adalah sebagai berikut.
 

Contoh programnya adalah sebagai berikut:
```c
#include <stdio.h>

int main()
{
  int a = 10, b = 15;
  int result;

  result = a+b;
  printf("Addition: a+b = %d \n",result);
  result = a-b;
  printf("Subtraction: a-b = %d \n",result);
  result = a*b;
  printf("Multiplication: a*b = %d \n",result);
  result = a/b;
  printf("Division: a/b = %d \n",result);
  result = a%b;
  printf("Modulo Division: %d \n",result);
}
```
## 3. Operator-Operator Lainnya
