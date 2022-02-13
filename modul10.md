# Modul 10 Praktikum : Fungsi dan Rekursif

## Daftar Isi


## 1. Fungsi
### 1.1 Pengertian Fungsi
Dalam pemrograman C, **Fungsi** merupakan kode program yang dirancang untuk **menyelesaikan sebuah tugas tertentu**. Fungsi sering digunakan untuk membungkus program menjadi bagian-bagian kecil. Logika program yang ada di dalam fungsi **dapat kita gunakan kembali hanya dengan memanggilnya**, sehingga dapat digunakan lebih dari satu kali.

Contoh fungsi yang sudah tidak asing lagi karena sering kita buat adalah fungsi `main()`. Fungsi ini memang wajib ada di setiap program C karena akan dieksekusi pertama kali.

Berdasarkan siapa yang membuat, fungsi bisa dibedakan ke dalam 2 kelompok:

1. Built-In Function 
2. User Defined Function

**Built-In Function** adalah sebutan untuk fungsi yang sudah ada secara bawaan dari dalam bahasa pemrograman, sedangkan **User Defined Function** adalah fungsi yang kita (sebagai programmer) membuatnya sendiri. Bahasa C menyediakan banyak fungsi bawaan, belum termasuk yang bisa diakses dari berbagai library atau package pihak ketiga. Sebagai contoh, printf(), scanf() dan strcpy() adalah function bawaan bahasa C. Namun dalam tutorial kali ini yang akan kita bahas adalah jenis User Defined Function.

### 1.2 Deklarasi Fungsi
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

### 2.2 Implementasi Rekursif
### 2.3 Rekursif vs Fungsi Biasa

## Latihan Soal
