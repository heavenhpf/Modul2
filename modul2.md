# Modul 2 Praktikum : Konsep Dasar Algoritma

## Daftar Isi
- [1. Variabel (Materi Pendalaman)](#1-variabel-materi-pendalaman)
     - [1.1 Pengenalan Variabel](#11-pengenalan-variabel)
     - [1.2 Deklarasi Variabel](#12-deklarasi-variabel)
     - [1.3 Pengisian Nilai Variabel](#13-pengisian-nilai-variabel)
     - [1.4 Inisialisasi Variabel](#14-inisialisasi-variabel)
 
- [2. Operator Matematika Sederhana](#2-operator-matematika-sederhana)
     - [2.1 Operator Assignment](#21-operator-assignment)
     - [2.2 Operator Aritmatika](#22-operator-aritmatika)

- [3. Operator-Operator Lainnya](#3-operator-operator-lainnya)
     - [3.1 Operator Increment dan Decrement](#31-operator-increment-dan-decrement)
     - [3.2 Operator Relasional](#32-operator-relasional)
     - [3.3 Operator Logika](#33-operator-logika)
     - [3.4 Operator Bitwise](#34-operator-bitwise)
     - [3.5 Operator Gabungan](#35-operator-gabungan)
     - [3.6 Operator sizeof()](#36-operator-sizeof)
     - [3.7 Operator Address-of (&)](#37-operator-address-of-)
     - [3.8. Operator Deference (*)](#38-operator-deference-)
     - [3.9 Operator Kondisional (? :)](#39-operator-kondisional--)
     - [3.10 Operator Koma (,)](#310-operator-koma-)
     - [3.11 Operator Subscript ( [] )](#311-operator-subscript---)

## 1. Variabel (Materi Pendalaman)
### 1.1 Pengenalan Variabel
<br>
<img src="https://user-images.githubusercontent.com/62087953/151223376-fa9031b2-9a9e-4c24-b2c3-415db37b17b6.jpg" width="500">
<br>

**Variabel** dapat dianalogikan/diibaratkan sebagai sebuah gelas, di mana dapat menampung sebuah cairan. Cairan ini dianalogikan sebagai data. Dalam artian lain, Variabel adalah suatu tempat yang digunakan untuk menampung data atau nilai pada memori yang mempunyai nilai yang dapat berubah–ubah selama proses program. Dalam bahasa C, kita tidak akan terlepas dari penggunaan variabel, karena pada dasarnya sebuah program bekerja dengan melakukan pengolahan data.

### 1.2 Deklarasi Variabel
Seperti analogi gelas sebelumnya, gelas tersebut harus ada terlebih dahulu sebelum dapat diisi dan digunakan. Pada bahasa C, variabel harus dideklarasikan terlebih dahulu sebelum bisa digunakan. Untuk mendeklarasikan sebuah variabel, sintaksnya adalah sebagai berikut.
```c
<tipe_data> <identifier>
```
Misalkan, potongan kode berikut mendeklarasikan variabel x yang bertipe int.
```c
int x;
```
Namun, apabila ingin mendeklarasikan lebih dari satu variabel dengan tipe yang sama, bisa menggunakan operator koma (,). Syntax nya dapat dituliskan sebagai berikut:
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
Operator dapat dipahami sebagai sesuatu yang dapat melakukan operasi pada operan (variabel/nilai). Contohnya, operator '+' digunakan untuk operasi penjumlahan. Operator matematika sederhana dapat dibagi menjadi 2, yaitu Operator Assignment dan Operator Aritmatika.

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

| Simbol | Operasi | Contoh |
| :------: | ------ | :------: |
| + | Penjumlahan pada dua operan | `a + b` |
| - | Pengurangan pada dua operan | `a - b` |
| * | Perkalian pada dua operan | `a * b` |
| / | Pembagian pada dua operan | `a / b` |
| % | Menghitung sisa pembagian dua operan (operasi modulo) | `a % b` |
 
Apabila diimplementasikan dalam program, bisa dilihat contohnya sebagai berikut:
```c
#include <stdio.h>

int main()
{
  int a = 10, b = 15;
  int result;

  result = a+b;
  printf("Hasil penambahan a oleh b: a+b = %d \n",result);
  result = a-b;
  printf("Hasil pengurangan a oleh b: a-b = %d \n",result);
  result = a*b;
  printf("Hasil perkalian a oleh b: a*b = %d \n",result);
  result = a/b;
  printf("Hasil pembagian a oleh b: a/b = %d \n",result);
  result = a%b;
  printf("Hasil operasi mod a oleh b = %d \n",result);
}
```

## 3. Operator-Operator Lainnya
Selain operator-operator yang sudah disebutkan di atas, terdapat operator-operator yang dapat digunakan, diantaranya:

- Operator Increment dan Decrement
-	Operator Relasional
-	Operator Logika
-	Operator Bitwise
-	Operator Gabungan
-	Operator sizeof()
-	Operator Address-of (&)
-	Operator Deference (*)
-	Operator Kondisional (? :)
-	Operator Koma (,)
-	Operator Subscript ( [] )

Setiap operator akan dijelaskan lebih lanjut di bawah ini.

### 3.1 Operator Increment dan Decrement
Operator increment dan decrement adalah sebutan untuk operasi seperti `a++` dan `a--`. Ini sebenarnya penulisan singkat dari operasi `a = a + 1` serta `a = a – 1`. 

Increment digunakan untuk menambah variabel sebanyak 1 angka, sedangkan decrement digunakan untuk mengurangi variabel sebanyak 1 angka. Penulisannya menggunakan tanda tambah 2 kali untuk increment, dan tanda kurang 2 kali untuk decrement. Penempatan tanda tambah atau kurang ini boleh di awal seperti `++a` dan `--a`, atau di akhir variabel seperti `a++` dan `a--`.

Dengan demikian, terdapat 4 jenis increment dan decrement dalam bahasa C:
| Operator | Penjelasan | Contoh |
| :------: | ------ | :------: |
| Pre-increment | Tambah a sebanyak 1 angka, lalu tampilkan hasilnya | `++a` |
| Post-increment | Tampilkan nilai a, lalu tambah a sebanyak 1 angka | `a++` |
| Pre-decrement | Kurangi a sebanyak 1 angka, lalu tampilkan hasilnya | `--a` |
| Post-decrement | Tampilkan nilai a, lalu kurangi a sebanyak 1 angka | `a--` |

**Pre-increment** maupun **pre-decrement** bekerja dengan menambahkan/mengurangi nilai variabel sebanyak satu terlebih dahulu, sebelum operan tersebut digunakan pada operasi lainnya pada sekuens intstruksi yang sama. Untuk lebih jelasnya, perhatikan potongan kode berikut:

```c
int a, b;  
a = 5;  
b = ++a; // Nilai b sekarang adalah 6  
a = --b; // Nilai a sekarang adalah 5 
```

Di sini, saat instruksi `b = ++a;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` ditambahkan satu terlebih dahulu, kemudian baru di-assign nilainya ke variabel `b`.

Sedangkan pada **post-increment** maupun **post-decrement**, mereka bekerja dengan meletakkan operator increment/decrement di belakang nama variabel. Cara kerja dari operator increment/decrement postfix berbeda dari prefix. Pada postfix, nilai variabel akan ditambah satu setelah operan digunakan pada operasi lainnya pada sekuens instruksi yang sama. Perhatikan potongan kode berikut.

```c
int a, b;  
a = 5;  
b = a++; // Nilai b sekarang adalah 5  
a = b--; // Nilai a sekarang adalah 5 
```

Di sini, saat instruksi `b = a++;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` akan di-assign terlebih dahulu ke variabel `b`, kemudian baru ditambahkan satu. Karena itulah variabel `b` mendapat nilai dari `a` sebelum terjadi penambahan.

### 3.2 Operator Relasional
**Operator Relasional** digunakan untuk memeriksa relasi dan membandingkan nilai dari dua operan. Jika benar akan menghasilkan nilai `TRUE` (direpresentasikan angka 1), jika salah maka akan menghasilkan nilai `FALSE` (direpresentasikan angka 0).

Berikut merupakan operator-operator relasional dalam bahasa C.

<table role="table">
<thead>
<tr>
<th>Operator</th>
<th align="center">Simbol</th>
<th>Keterangan</th>
<th>Contoh</th>
</tr>
</thead>
<tbody>
<tr>
<td>Sama dengan</td>
<td align="center">==</td>
<td>Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang sama.</td>
<td>5 == 2 (FALSE)<br>5 == 5 (TRUE)</td>
</tr>
<tr>
<td>Tidak Sama dengan</td>
<td align="center">!=</td>
<td>Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang tidak sama.</td>
<td>5 != 2 (TRUE)<br>5 != 5 (FALSE)</td>
</tr>
<tr>
<td>Lebih besar</td>
<td align="center">&gt;</td>
<td>Digunakan untuk membandingkan apakah operan pertama lebih besar nilainya dari operan kedua.</td>
<td>5 &gt; 2 (TRUE)<br>5 &gt; 5 (FALSE)<br>2 &gt; 4 (FALSE)</td>
</tr>
<tr>
<td>Lebih kecil</td>
<td align="center">&lt;</td>
<td>Digunakan untuk membandingkan apakah operan pertama lebih kecil nilainya dari operan kedua.</td>
<td>5 &lt; 2 (FALSE)<br>5 &lt; 5 (FALSE)<br>2 &lt; 4 (TRUE)</td>
</tr>
<tr>
<td>Lebih besar sama dengan</td>
<td align="center">&gt;=</td>
<td>Digunakan untuk membandingkan apakah operan pertama lebih besar atau sama nilainya dari operan kedua.</td>
<td>5 &gt;= 2 (TRUE)<br>5 &gt;= 5 (TRUE)<br>2 &gt;= 4 (FALSE)</td>
</tr>
<tr>
<td>Lebih kecil sama dengan</td>
<td align="center">&lt;=</td>
<td>Digunakan untuk membandingkan apakah operan pertama lebih kecil atau sama nilainya dari operan kedua.</td>
<td>5 &lt;= 2 (FALSE)<br>5 &lt;= 5 (TRUE)<br>2 &lt;= 4 (TRUE)</td>
</tr>
</tbody>
</table>

### 3.3 Operator Logika
**Operator Logika** digunakan untuk melakukan tes pada kondisi/ekspresi, apakah kondisi tersebut benar atau salah. Operator logika hanya akan menghasilkan nilai `TRUE` (jika benar) atau `FALSE` (jika salah). `TRUE` direpresentasikan oleh angka 1, sedangkan `FALSE` oleh angka 0.

Operator-operator logika dalam bahasa C adalah sebagai berikut.

<table role="table">
<thead>
<tr>
<th>Operator</th>
<th align="center">Simbol</th>
<th>Keterangan</th>
<th>Nilai Kebenaran</th>
</tr>
</thead>
<tbody>
<tr>
<td>Logical NOT</td>
<td align="center">!</td>
<td>Operator NOT digunakan untuk membalikkan kondisi, TRUE menjadi FALSE dan FALSE menjadi TRUE.</td>
<td>
<code>!1 = 0</code><br><code>!0 = 1</code>
</td>
</tr>
<tr>
<td>Logical AND</td>
<td align="center">&amp;&amp;</td>
<td>Operator AND akan menghasilkan nilai TRUE jika kedua operan mempunyai nilai TRUE.</td>
<td>
<code>1 &amp;&amp; 1 = 1</code><br><code>0 &amp;&amp; 1 = 0</code><br><code>1 &amp;&amp; 0 = 0</code><br><code>0 &amp;&amp; 0 = 0</code>
</td>
</tr>
<tr>
<td>Logical OR</td>
<td align="center">||</td>
<td>Operator OR akan menghasilkan nilai TRUE jika salah satu operan mempunyai nilai TRUE.</td>
<td>
<code>1 || 1 = 1</code><br><code>0 || 1 = 1</code><br><code>1 || 0 = 1</code><br><code>0 || 0 = 0</code>
</td>
</tr>
</tbody>
</table>

Operator Logika `NOT` merupakan operator **unary** yang artinya hanya pada bekerja pada satu operan.

Operator logika pada umumnya digunakan bersamaan dengan operator relasional untuk melakukan tes pada ekspresi yang berhubungan dengan kebenaran suatu kondisi. Penggunaan paling umum adalah untuk melakukan percabangan/branching (akan dipelajari di bagian modul selanjutnya).

Contoh:
```c
int a, b, c, d;  
a = 11;  
b = 24;  
c = 11;  
d = ((a == c) && (b > a));               // 1 (TRUE)  
d = ((a >= b) || (a < c));               // 0 (FALSE)  
d = ((b != b) || (b > c)) && (c == a);   // 1 (TRUE) 
```
### 3.4 Operator Bitwise
**Operator Bitwise**, seperti namanya digunakan untuk melakukan operasi pada dua operan dalam skala biner (bilangan basis 2). Sebelum mempelajari lebih lanjut cara kerja operasi bitwise, sebaiknya kamu harus paham terlebih dahulu mengenai bilangan dalam basis biner.

Terdapat 6 jenis operator bitwise, yakni `AND`, `OR`, `XOR`, `COMPELEMENT`, `SHIFT LEFT`, dan `SHIFT RIGHT`. Untuk lebih memahami perbedaan cara kerja operator bitwise, perhatikan tabel berikut.

<table role="table">
<thead>
<tr>
<th>Operator</th>
<th align="center">Simbol</th>
<th>Keterangan</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bitwise AND</td>
<td align="center">&amp;</td>
<td>Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila keduanya 1, jika tidak menghasilkan nilai 0.</td>
</tr>
<tr>
<td>Bitwise OR</td>
<td align="center">|</td>
<td>Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila salah satu nilainya 1, jika keduanya 0, maka menghasilkan nilai 0.</td>
</tr>
<tr>
<td>Bitwise XOR</td>
<td align="center">^</td>
<td>Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila bit pada kedua operan nilainya berbeda. Jika sama, maka menghasilkan nilai 0.</td>
</tr>
<tr>
<td>Bitwise COMPLEMENT</td>
<td align="center">~</td>
<td>Membalik semua nilai bit, dari 1 menjadi 0 dan 0 menjadi 1 (dalam panjang bit).</td>
</tr>
<tr>
<td>Bitwise SHIFT LEFT</td>
<td align="center">&lt;&lt;</td>
<td>Menggeser bit ke kiri sebanyak n (operan kedua).</td>
</tr>
<tr>
<td>Bitwise SHIFT RIGHT</td>
<td align="center">&gt;&gt;</td>
<td>Menggeser bit ke kanan sebanyak n (operan kedua).</td>
</tr>
</tbody>
</table>

Contoh penggunaan operator bitwise:

Misal 12 dan 5. Representasi 12 dan 5 dalam basis biner adalah 12 = (1100) dan 5 = (0101). Maka, operasi bitwise adalah sebagai berikut.

**Bitwise AND**
```c
12 = (1100)
 5 = (0101)
------------ &
 4 = (0100)
```
**Bitwise OR**
```c
12 = (1100)
 5 = (0101)
------------ | 
13 = (1101)
```
**Bitwise XOR**
```c
12 = (1100)
 5 = (0101)
------------ ^
 9 = (1001)
```
**Bitwise COMPLEMENT**
```c
 12 = (1100)
~12 = (0011)
```

**Bitwise SHIFT LEFT**

Misal kita hendak menggeser bit bilangan 13 ke kiri sebanyak 2, maka 13 << 2.
```c
     13 = (001101)
13 << 2 = (110100) 
```
Bisa diperhatikan, bit paling kanan setelah digeser akan diisi oleh 0. Maka hasil dari 13 << 2 = 52.

**Bitwise SHIFT RIGHT**

Misal kita hendak menggeser bit bilangan 13 ke kanan sebanyak 2, maka 13 >> 2.
```c
     13 = (001101)
13 >> 2 = (000011)
```
Bisa diperhatikan, bit paling kiri setelah digeser akan diisi oleh 0. Maka hasil dari 13 >> 2 = 3.
### 3.5 Operator Gabungan
**Operator gabungan** atau bisa disebut juga operator assignment gabungan adalah cara penulisan singkat operator assignment yang digabung dengan operator lain.

Sebagai contoh, operasi `a = a + 1` bisa disingkat (dan digabung) menjadi `a += 1`. Contoh lain operasi `b >>= 1` adalah penulisan singkat dari `b = b >> 1`. Tidak ada pengaruh apa-apa dari penulisan singkat seperti ini, anda boleh memilih penulisan yang panjang seperti `a = a + 1`, atau di singkat menjadi `a += 1`.

Tabel berikut merangkum semua operator assignment dalam bahasa C++:

<table role="table">
<thead>
<tr>
<th align="center">Operator</th>
<th align="center">Contoh</th>
<th align="center">Ekuivalen Dengan</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">+=</td>
<td align="center"><code>a += b</code></td>
<td align="center"><code>a = a + b</code></td>
</tr>
<tr>
<td align="center">-=</td>
<td align="center"><code>a -= b</code></td>
<td align="center"><code>a = a - b</code></td>
</tr>
<tr>
<td align="center">*=</td>
<td align="center"><code>a *= b</code></td>
<td align="center"><code>a = a * b</code></td>
</tr>
<tr>
<td align="center">/=</td>
<td align="center"><code>a /= b</code></td>
<td align="center"><code>a = a / b</code></td>
</tr>
<tr>
<td align="center">%=</td>
<td align="center"><code>a %= b</code></td>
<td align="center"><code>a = a % b</code></td>
</tr>
<tr>
<td align="center">&amp;=</td>
<td align="center"><code>a &amp;= b</code></td>
<td align="center"><code>a = a &amp; b</code></td>
</tr>
<tr>
<td align="center">|=</td>
<td align="center"><code>a |= b</code></td>
<td align="center"><code>a = a | b</code></td>
</tr>
<tr>
<td align="center">^=</td>
<td align="center"><code>a ^= b</code></td>
<td align="center"><code>a = a ^ b</code></td>
</tr>
<tr>
<td align="center">&gt;&gt;=</td>
<td align="center"><code>a &gt;&gt;= b</code></td>
<td align="center"><code>a = a &gt;&gt; b</code></td>
</tr>
<tr>
<td align="center">&lt;&lt;=</td>
<td align="center"><code>a &lt;&lt;= b</code></td>
<td align="center"><code>a = a &lt;&lt; b</code></td>
</tr>
</tbody>
</table>

### 3.6 Operator sizeof()
Walaupun mempunyai bentuk seperti sebuah fungsi, namun dalam standardisasi bahasa C menganggap operator `sizeof()` sebagai operator. Kegunaan dari operator ini adalah untuk mengetahui besarnya alokasi memori sebuah operan (berupa variabel atau tipe data) dalam satuan byte.

Contoh:
```c
sizeof(int);
```

### 3.7 Operator Address-of (&)
Operator ini mengembalikan alamat memori dari sebuah operan berupa variabel.

Contoh:
```c
int var;
printf("%d\n", &var);
```
### 3.8. Operator Deference (*)
Berbeda dari operator address-of (`&`), operator deference (`*`) mengembalikan nilai dari variabel pointer (akan dijelaskan pada modul pointer).

Meskipun menggunakan simbol yang sama seperti operator perkalian, operator deference mempunyai fungsi yang benar-benar berbeda dari operator perkalian.

### 3.9 Operator Kondisional (? :)
**Operator kondisial** merupakan satu-satunya operator ternary (bekerja pada tiga operan) dalam bahasa C. Fungsi dari operator kondisional layaknya percabangan menggunakan if - else (akan dijelaskan pada modul percabangan).

### 3.10 Operator Koma (,)
Tanda koma (`,`) sebagai operator dalam bahasa C merupakan binary operator yang akan mengevaluasi operan pertama, kemudian akan membuang hasilnya. Lalu mengevaluasi operan kedua dan akan mengembalikan nilainya.
```c
int number = (5, 23);   // number bernilai 23, bukan 5
```
Selain berfungsi sebagai operator, tanda koma (`,`) juga berfungsi sebagai separator (pemisah) antar statement. Misalkan saat deklarasi lebih dari satu variabel.

```c
int var1, var2, var3;   // Menggunakan tanda koma untuk memisahkan deklarasi tiap variabel
```

**Catatan: Tidak semua statement dapat dipisahkan oleh tanda koma.**

### 3.11 Operator Subscript ( [] )
Penggunaan paling umum operator ini adalah untuk melakukan pengaksesan terhadap elemen suatu array (akan dibahas pada modul array).

Operator lainnya yang belum disebutkan pada modul ini akan dijelaskan di modul-modul selanjutnya.

## Soal Latihan
1. Buatlah program yang dapat mengonversi suhu derajat Celcius (C) di bawah ini menjadi Reamur (R), Fahrenheit (F), dan Kelvin (K):

     A. 100° C
     
     B. 0° C
     
     C. -24° C
     
     D. 75.86° C

2. Buatlah program menggunakan operator relasional yang dapat membandingkan kedua bilangan di bawah ini:

     A. -45 dengan 31
     
     B. 0.31 dengan -0.513
     
3. Operasikan kedua bilangan berikut ini menggunakan setiap operator bitwise:

     A. 6 dan 3
     
     B. 2 dan -7

4. Sebuah variabel `a` bertipe data integer bernilai 8 masuk ke dalam cuplikan program rumit berikut:

```c
a++; 
++a;
--a;
// no. 1
a--;
--a;
++a;
++a;
a--;
// no. 2
a--;
--a;
// no. 3
```

Tentukan nilai a pada 3 nomor yang diberikan!
      
**Selamat Mengerjakan!**
