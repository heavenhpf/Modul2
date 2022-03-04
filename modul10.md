# Modul 10 Praktikum : Fungsi dan Rekursif

## Daftar Isi
- [1. Fungsi](#1-fungsi)
     - [1.1 Pengertian Fungsi](#11-pengertian-fungsi)
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

## 1. Fungsi
### 1.1 Pengertian Fungsi
Dalam pemrograman C, **Fungsi** merupakan kumpulan dari beberapa kode program yang dirancang untuk **menyelesaikan sebuah tugas tertentu**. Fungsi sering digunakan untuk membungkus program menjadi bagian-bagian kecil. Logika program yang ada di dalam fungsi **dapat kita gunakan kembali hanya dengan memanggilnya**, sehingga dapat digunakan lebih dari satu kali.

Contoh fungsi yang sudah tidak asing lagi karena sering kita buat adalah fungsi `main()`. Fungsi ini memang wajib ada di setiap program C karena akan dieksekusi pertama kali.

Berdasarkan siapa yang membuat, fungsi bisa dibedakan ke dalam 2 kelompok:

1. Built-In Function 
2. User Defined Function

**Built-In Function** adalah sebutan untuk fungsi yang sudah ada secara bawaan dari dalam bahasa pemrograman, sedangkan **User Defined Function** adalah fungsi yang kita (sebagai programmer) membuatnya sendiri. Bahasa C menyediakan banyak fungsi bawaan, belum termasuk yang bisa diakses dari berbagai library atau package pihak ketiga. Sebagai contoh, printf(), scanf() dan strcpy() adalah function bawaan bahasa C. Namun dalam tutorial kali ini yang akan kita bahas adalah jenis User Defined Function.

### 1.2 Implementasi Fungsi
Secara garis besar, syntax fungsi adalah sebagai berikut:
```c
<tipe_data> <nama_fungsi> (<parameter1>, <parameter2>, dst..){
    statement1;
    statement2;
    dst..
    
    return <value>
}
```

Bagian **<tipe_data>** diisi dengan tipe data nilai yang dikembalikan sebuah fungsi. Tipe data ini sudah kita pelajari pada modul sebelumnya, contohnya adalah seperti `int`, `double` atau `char`.

Jika suatu fungsi tidak mengembalikan nilai, **<tipe_data>** ditulis sebagai `void`. Sebuah fungsi yang tidak mengembalikan nilai kadang disebut juga sebagai **procedure**.

Penulisan **<nama_fungsi>** boleh bebas, tidak ada standar penamaan tertentu untuk fungsi bahasa C selama mengikuti aturan penulisan identifier, yakni tidak boleh di awali angka dan tidak boleh mengandung spasi.

#### Contoh Program 1

Berikut adalah contoh program sederhana implementasi fungsi yang mencetak string **"Halo, selamat belajar string!"**:
```c
#include <stdio.h>

// Deklarasi fungsi "belajarfungsi"
void belajarfungsi(){
    printf("Halo, Selamat Belajar Fungsi!");
}

int main(){
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    return 0;
}
```

Sehingga menghasilkan output sebagai berikut:
```c
Halo, Selamat Belajar Fungsi!
```

#### Contoh Program 2

Fungsi `belajarfungsi()` dapat digunakan berkali-kali sesuai dengan kebutuhan, contohnya adalah program berikut:
```c
#include <stdio.h>

// Deklarasi fungsi "belajarfungsi"
void belajarfungsi(){
    printf("Halo, Selamat Belajar Fungsi!");
}

int main(){
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    belajarfungsi(); // Memanggil "belajarfungsi" ke dalam fungsi main
    return 0;
}
```

Sehingga menghasilkan output sebagai berikut:
```c
Halo, Selamat Belajar Fungsi!
Halo, Selamat Belajar Fungsi!
Halo, Selamat Belajar Fungsi!
Halo, Selamat Belajar Fungsi!
Halo, Selamat Belajar Fungsi!
```

#### Contoh Program 3

Berikut adalah contoh penerapan **<parameter>** pada fungsi untuk menyimpan variabel `a` dan `b` untuk menghitung operasi tambah:
```c
#include <stdio.h>
 
void tambahkan(int a, int b)
{
    int hasil = a + b;
    printf("%d\n", hasil);
}
 
int main()
{
    tambahkan(5,3);
    tambahkan(9,5);
    tambahkan(7,8);
    return 0;
}  
```

#### Contoh Program 4 (Prototype Fungsi)
  
Selain menggunakan pendefisian langsung seperti cara sebelumnya, fungsi juga dapat dibuat dengan prototipe. **Prototipe fungsi** (atau biasa disebut interface fungsi) adalah deklarasi dari sebuah fungsi tanpa definisinya. Deklarasi sebuah fungsi berisi return type, nama fungsi, dan parameter yang terlibat.

Untuk menuliskan prototipe fungsi, sintaksnya sebagai berikut:

```c
// Deklarasi
<return_type> <nama_fungsi>(<parameter1>, <parameter2>, ...);
```

```c
Contoh kode program menggunakan prototipe fungsi:

// Prototipe Fungsi
void cetak();
 
int main()
{
    cetak();
    return 0;
}

// Definisi Fungsi cetak()
void cetak()
{
    printf("Aku Sebuah Fungsi\n");
}
```  
  
#### Contoh Program 5 (Return Fungsi)
  
Jika kita menginginkan fungsi yang kita jalankan menghasilkan sebuah nilai atau sederhananya menghasilkan sebuah output, kita bisa menambahkan keyword return dan mendefinisikan return type dari fungsi tersebut. Fungsi yang memiliki return type selain `void` pasti memiliki **return value**. Nilai yang dikembalikan oleh fungsi tersebut memiliki tipe data yang bersesuaian dengan return type-nya.

Saat menemui statement return pada fungsi, maka fungsi tersebut akan berhenti dari titik dimana return tersebut terdapat, kemudian kembali ke bagian kode yang memanggil fungsi tersebut.

Misal kita ingin mendapatkan hasil dari penjumlahan dua bilangan menggunakan fungsi bernama jumlah():
  
```c
#include <stdio.h>
 
int jumlah(int a, int b);
 
int main()
{
    int x = 2, y = 3, hasil;
    hasil = jumlah(x, y);
    printf("%d\n", hasil);
    return 0;
}
 
int jumlah(int a, int b)
{
    int hasil = a;
    hasil += b;
    return hasil;
}
```
## 2. Rekursif
### 2.1 Pengertian Rekursif
	
<br>
<img src=https://user-images.githubusercontent.com/62087953/156751286-59ac6946-4978-4fda-a563-9eafb636ec26.jpg width = "500">
<br>

Pengertian dari fungsi **rekursif** dapat dianalogikan seperti lukisan di atas. Terdapat sebuah lukisan tangan yang sedang menggambar dan gambar didalamnya menggambarkan hal yang sama secara berulang-ulang sehingga gambar tersebut mengecil dan mengecil. Gambar tersebut akan berhenti sampai pelukis tidak mampu menggambarkan hal serupa dikarenakan kanvas dan alat lukis yang tidak memadahi.
	
Berdasarkan penganalogian tersebut, secara garis besar **Rekursif** merupakan suatu proses dari fungsi yang memanggil dirinya secara berulang kali. Dikarenakan prosesnya dilakukan secara berulang-ulang, maka harus ada kondisi atau validasi yang dapat mengakhiri proses dari rekursif. Jika tidak, maka proses rekursif tidak akan berhenti sampai memori yang digunakan tidak dapat menampung lagi.

Rekursif adalah konsep penting pada bahasa c penggunaan rekursif seringkali digunakan pada struktur data dan algoritma, contohnya adalah untuk menggunakan rekursif dalam masalah seperti traversal tree.
	
### 2.2 Implementasi Rekursif

Berikut adalah syntax dari implementasi fungsi rekursif:
```c
#include <stdio.h>

// Deklarasi Fungsi Rekursif
<tipe_data> <fungsi_rekursif>()
{
    ... .. ... //kode
    rekursif();
    ... .. ... //kode
}

int main()
{
    ... .. ... //kode
    rekursif(); // Pemanggilan Fungsi Rekursif
    ... .. ... //kode
}	
```	

Catatan mengenai rekursif:
	
1. Rekursif akan berlanjut sampai beberapa kondisi terpenuhi untuk menghentikan prosesnya. Kondisi tersebut dinamakan **Base Case**.

2. Untuk menghentikan rekursif tak terbatas, dapat menggunakan pernyataan `if/else` (atau pendekatan serupa) dapat digunakan di mana satu cabang membuat panggilan rekursif, dan yang lainnya tidak.
	
Berikut adalah contoh implementasi program rekursif untuk menghitung bilangan faktorial:

```c
#include <stdio.h>

// Fungsi Rekursif
int faktorial(int angka){
    if(angka <= 1){
        return 1;   
    }
    else{
        return angka * faktorial(angka-1);
    }   
}
 
int main(){
    int angka = 4;
    printf("faktorial dari %d = %d\n", angka, faktorial(angka)); // Pemanggilan Fungsi Rekursif "faktorial"
    return 0;
}	
```

Penjelasan mengenai program di atas:
		 
1. Pada function faktorial terdapat penggunaan `if else` yang bergunakan untuk melanjutkan atau menghentikan rekursif, dikarenakan rekursif akan melakukan sebuah proses secara berulang – ulang.

2. Pada code di atas, `if` berfungsi me-return value 1 jika nilai angka <= 1.

3. Sedangkan, `else` berfungsi jika angka yang di input valid atau dapat diproses, maka akan melakukan proses faktorial.

4. Pada fungsi `main` terdapat deklarasi variabel data yang ingin kita periksa faktorialnya dan memanggil function faktorial.

## Latihan Soal
1. Diberikan baris bilangan 1, 3, 5, 7, 9, 11, ... dst. Buatlah program yang mengimplementasikan fungsi rekursif yang dapat menentukan bilangan ke-n dari baris tersebut.
	
Contoh Input:
```c
4	
```
Contoh Output:
```c
7	
```

2. Diberikan deret aritmatika dari bilangan fibbonacci 1, 1, 2, 3, 5, 8, 13, 21, ... dst. Buatlah program yang mengimplementasikan fungsi rekursif yang dapat menentukan jumlah deret bilangan ke-n dari baris tersebut.
	
Contoh Input 1:
```c
3	
```
Contoh Output 1:
```c
4
```
	
Contoh Input 2:
```c
5	
```
Contoh Output 2:
```c
12
```
	
3. Buatlah program dengan menggunakan rekursif yang saat menghasilkan output sebagai berikut:
```c
mundur 3
mundur 2
mundur 1
maju 1
maju 2
maju 3	
```
