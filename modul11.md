# Modul 11 Praktikum: Alokasi Memori Dinamis

## Daftar Isi

- [1. Memori Dinamis](#1-memori-dinamis)
     - [1.1 Pengertian Memori Dinamis](#11-pengertian-memori-dinamis)
     - [1.2 Cara Kerja Memori Dinamis](#12-cara-kerja-memori-dinamis)
     - [1.3 Memori Statis vs Memori Dinamis](#13-memori-statis-vs-memori-dinamis)

- [2. Operator Malloc()](#21-operator-malloc)
     - [2.1 Pengertian malloc()](#21-operator-malloc)
     - [2.2 Syntax malloc()](#22-syntax-malloc)
     - [2.3 Implementasi malloc()](#23-implementasi-malloc)

- [Latihan Soal](#latihan-soal)

## 1 Memori Dinamis
### 1.1 Pengertian Memori Dinamis

<br>
<img src="image1" width="500">
<br>

**Dynamic Memory** atau dalam Bahasa Indonesia disebut **Memori dinamis**, adalah suatu teknik alokasi memori yang memungkinkan program memesan memori di saat program berjalan (runtime), bukan di saat eksekusi program.

### 1.2 Cara Kerja Memori Dinamis
Misalnya, jika program pada awalnya hanya memiliki memori statis yang sudah programmer pesan dan tulis saat pengkodingan, kemudian suatu saat pengguna program tersebut membutuhkan penyimpanan data lebih yang tak terduga, otomatis dia membutuhkan memori lagi untuk menyimpan data tersebut. Dengan teknik memori dinamis kita bisa memungkinkan pengguna dari program kita mendapatkan memori lebih. Memungkinkan kita untuk membuat program yang dapat meminta memori tambahan sebanyak yang diperlukan untuk penyimpanan data, dan penambahan memori itu dilakukan saat runtime.

### 1.3 Memori Statis vs Memori Dinamis
Terdapat perbedaan cara kerja dari alokasi memori statis yang sudah biasa kita terapkan dengan alokasi memori dinamis, diantaranya adalah sebagai berikut:

| No. | Perbandingan | Memori Statis | Memori Dinamis |
| ------ | ------ | ------ | ------ |
| 1. | Definisi | Alokasi memori statis adalah metode mengalokasikan memori dalam ukuran yang tetap (Fixed-Sized). | Alokasi memori dinamis adalah metode mengalokasikan memori, dan begitu memori dialokasikan, ukurannya masih dapat berubah sesuai kebutuhan. |
| 2. | Penerapan | Alokasi memori statis cukup mudah diimplementasikan. | Alokasi memori dinamis cenderung lebih rumit untuk diterapkan karena melibatkan sistem pointer. |
| 3. | Kecepatan | Dalam memori statis, eksekusi alokasi lebih cepat daripada alokasi memori dinamis. | Dalam memori dinamis, eksekusi alokasi lebih lambat daripada alokasi memori statis. |
| 4. | Pemanfaatan Memori | Dalam alokasi memori statis, tidak dapat menggunakan kembali memori yang tidak digunakan. | Alokasi memori dinamis memungkinkan penggunaan kembali memori. Programmer dapat mengalokasikan lebih banyak memori bila diperlukan. Dia dapat melepaskan memori bila perlu. |

Kesimpulan:
Dalam pemrograman, alokasi memori statis dan alokasi memori dinamis adalah dua mekanisme untuk mengalokasikan memori. Perbedaan antara alokasi memori statis dan dinamis adalah bahwa dalam alokasi memori statis setelah memori dialokasikan, ukuran memori ditetapkan. Sementara dalam alokasi memori dinamis, setelah memori dialokasikan, ukuran memori dapat diubah. Programmer dapat memutuskan apakah memori harus statis atau dinamis tergantung pada pengaplikasiannya.

## 2.1 Operator malloc()
Fungsi `malloc()` (Memory Allocation) digunakan untuk mengalokasikan jumlah byte yang dibutuhkan dalam memori. Ukurannya mewakili memori yang dibutuhkan dalam satuan ukuran **byte**. Fungsi malloc mengembalikan pointer kosong, sehingga operator transmisi digunakan untuk mengembalikan tipe pointer sesuai dengan tipe data yang diperlukan.

Fungsi `malloc()` mengalokasikan memori secara dinamis di sub segmen memori tumpukan (stack) dan umurnya sepanjang lama operasi sedang alokasi data-nya hanya seumur fungsi `malloc()` tadi. Fungsi `malloc()` dapat digunakan setelah kita menginisialisasikan library C bernama `<stdlib.h>`. Setelah fungsi `malloc()` sudah tidak kita perlukan, kita dapat membebaskan pengalokasian memori yang digunakan oleh `malloc()` menggunakan fungsi bernama `free()`.

### 2.2 Syntax malloc()
Berikut merupakan syntax dari fungsi `malloc()`.
```c
void *malloc(size_t size)
```

### 2.3 Implementasi malloc()
**Contoh 1**
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h> // Library stdlib untuk memanggil fungsi malloc() dan free()

int main()
{
     char *dynamicMem; // Deklarasi pointer dynamicMem bertipe data char
     dynamicMem = malloc( 20 * sizeof(char)); // Mengalokasikan memori dinamis sebesar 20 kali ukuran tipe data char
     
     // Jika memori dinamis gagal dialokasikan
     if(dynamicMem == NULL)
     {
        printf("Gagal mengalokasikan memory\n");
     }
     
     // Jika memori dinamis berhasil teralokasi
     else
     {
        printf("Alamat Memory = %u\n", dynamicMem); // Menampilkan alamat pengalokasian memori
        strcpy(dynamicMem, "Aku Adalah String"); // Memasukkan string 17 byte "Aku Adalah String" ke dynamicMem
     }
     
     printf("Memory yang dialokasikan : %s\n", dynamicMem );
     free(dynamicMem);  // Membebaskan alokasi memori
}
```

**Contoh 2**
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h> // library stdlib untuk memanggil fungsi malloc() dan free()
 
int main()
{
    char *str;
 
    // Initialisasi alokasi memori
    str = (char *) malloc(16); // Alokasi 16 byte
    strcpy(str, "akuadalahstring"); // Memasukkan string sebesar 15 byte */
    printf("String = %s,  Address = %u\n", str, str);
 
    // Re-alokasi memori
    str = (char *) realloc(str, 35); // Ubah ukuran memori yang dialokasikan menjadi 35 byte
    strcat(str, "hehehe"); // String bertambah menjadi 21 byte
    printf("String = %s,  Address = %u\n", str, str);
 
    free(str);
 
    return(0);
}
```

**Nb: Perlu diingat bahwa alamat pengalokasian memori menggunakan ukuran bit**

## Latihan Soal
1. Buatlah program C untuk mencari angka terbesar yang diinputkan menggunakan alokasi memori dinamis. Pada input baris pertama merupakan jumlah angka yang ingin dimasukkan. Kemudian, baris kedua dituliskan baris-baris angkanya.

<br>
<img src="" width="500">
<br>

> **Contoh Input:**
> 5
> 5 7 2 9 8

> **Contoh Output:**
> 9
