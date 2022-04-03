# Modul 16 Praktikum: Quick Sort

## Daftar Isi

- [1. Pengertian Quick Sort](#1-pengertian-quick-sort)
- [2. Kelebihan Quick Sort](#2-kelebihan-quick-sort)
- [3. Kekurangan Quick Sort](#3-kekurangan-quick-sort)
- [4. Cara Kerja Quick Sort](#4-cara-kerja-quick-sort)
- [5. Implementasi Quick Sort](#5-implementasi-quick-sort)

## 1. Pengertian Quick Sort
**Quick Sort** adalah salah satu algoritma pengurutan data yang paling cepat, yaitu dengan membagi list menggunakan sebuah **pivot**. Quick Sort juga menggunakan rekursif dalam algoritmanya. Data yang kurang dari pivot sudah ditentukan ditaruh disebelah kirinya pivot sedangkan data yang lebih besar dari pivot maka ditaruh disebelah kanan pivot. Metode dari algoritma ini adalah divide and conquer (bagi dan kuasai), dimana sebuah List akan dibagi menjadi 2 bagian berdasarkan pivot, yaitu elemen yang lebih kecil dari pivot dan elemen yang lebih kecil dari pivot. Lalu, elemen tersebut dibagi kembali dengan mengguanakn pivot baru sampai semua elemen berhasil di sorting.

Algoritma quick sort diperkenalkan pertama kali oleh C.A.R. Hoare pada tahun 1960, dan dimuat sebagai artikel di “Computer Journal 5” pada April 1962. Quick sort adalah algoritma sorting yang berdasarkan pembandingan dengan metoda divide-and-conqueror. Disebut Quick Sort, karena Algoritma quick sort mengurutkan dengan sangat cepat.

## 2. Kelebihan Quick Sort
Secara umum, quick sort memiliki dibandingkan dengan algoritma sorting lainnya, diantaranya adalah sebagai berikut:
1. Secara umum memiliki kompleksitas O(n log n).
2. Algoritmanya sederhana dan mudah diterapkan pada berbagai bahasa pemrograman dan arsitektur mesin secara efisien.
3. Dalam prakteknya adalah yang tercepat dari berbagai algoritma pengurutan dengan perbandingan, seperti mergesort dan heapsort.
4. Melakukan proses langsung pada input (in-place) dengan sedikit tambahan memori.
5. Bekerja dengan baik pada berbagai jenis input data (seperti angka dan karakter).

## 3. Kekurangan Quick Sort
Di samping kelebihan yang ada, terdapat juga beberapa kekurangan dari penggunaan algoritma quick sort. Diantaranya adalah sebagai berikut:
1. Sedikit kesalahan dalam penulisan program membuatnya bekerja tidak beraturan (hasilnya tidak benar atau tidak pernah selesai).
2. Memiliki ketergantungan terhadap data yang dimasukkan, yang dalam kasus terburuk memiliki kompleksitas O(n2).
3. Secara umum bersifat tidak stable, yaitu mengubah urutan input dalam hasil akhirnya (dalam hal inputnya bernilai sama).
4. Pada penerapan secara rekursif (memanggil dirinya sendiri) bila terjadi kasus terburuk dapat menghabiskan stack dan memacetkan program.

## 4. Cara Kerja Quick Sort
### Langkah 1. Menentukan Pivot

Sebelum menggunakan algoritma quick sort, langkah pertama yang harus dilakukan adalah menentukan **pivot** yang digunakan terlebih dahulu. Terdapat 3 metode untuk memilih pivot, yaitu:

- **Pivot** berasal dari **elemen pertama atau akhir** dari sebuah list. Pivot jenis ini bisa kita gunakan apaliba List yang akan disusun memiliki angka yang benar benar acak. dan sebaliknya pivot jenis ini sangat buruk jika kita memiliki list yang sebagian/sepenuhnya sudah tersusun.
- **Pivot** dipilih secara **acak**, pivot jenis ini sering digunakan bila kita tidak mengenal List yang akan di susun, hasilnya pun akan random, terkadang performanya baik, namun terkadang performanya juga buruk.
- **Pivot** berasal dari **median tabel**. cara ini yang paling sering digunakan, karena pivot ini bersifat seimbang dimana semua elemen akan dibagi rata dan hasilnya pun cukup baik untuk data yang sebagian sudah di sort ataupun semua data masih acak.

### Langkah 2. Sorting

Misal, di sini kita memiliki sebuah array yang memiliki baris array sebagai berikut:
```c
arr[] = {10, 80, 30, 90, 40, 50, 70};
```

Proses kunci dalam quickSort adalah saat mempartisi. Target dari partisi ini adalah, diberikan array dan elemen x dari array sebagai pivot, letakkan x pada posisi yang benar dalam array yang diurutkan dan letakkan semua elemen yang lebih kecil (lebih kecil dari x) sebelum x, dan letakkan semua elemen yang lebih besar (lebih besar dari x) setelahnya x. Semua ini harus dilakukan dalam waktu linier/bersamaan.

Skema urutan sorting dari `arr[]` yang didefinisikan tadi adalah sebagai berikut:

<br>
<img src="image1" width="500">
<br>

## 5. Implementasi Quick Sort
Berikut merupakan implementasi dari Quick Sort:
```c
#include <bits/stdc++.h>
using namespace std;

// Fungsi untuk memindah antara 2 elemen dalam array
void swap(int* a, int* b)
{
	int t = *a;
	*a = *b;
	*b = t;
}

/* Fungsi untuk mengambil elemen terakhir sebagai pivot,
menaruh elemen pivot ke posisi yang urut, dan menempatkan
semua elemen yang lebih kecil dari pivot ke sebelah kiri
pivot dan sebaliknya. */
int partition (int arr[], int low, int high)
{
	int pivot = arr[high]; // pivot
	int i = (low - 1); // Index of smaller element and indicates the right position of pivot found so far

	for (int j = low; j <= high - 1; j++)
	{
		// If current element is smaller than the pivot
		if (arr[j] < pivot)
		{
			i++; // increment index of smaller element
			swap(&arr[i], &arr[j]);
		}
	}
	swap(&arr[i + 1], &arr[high]);
	return (i + 1);
}

/* Fungsi utama QuickSort
arr[] --> Array to be sorted,
low --> Starting index,
high --> Ending index */
void quickSort(int arr[], int low, int high)
{
	if (low < high)
	{
		/* pi is partitioning index, arr[p] is now
		at right place */
		int pi = partition(arr, low, high);

		// Separately sort elements before
		// partition and after partition
		quickSort(arr, low, pi - 1);
		quickSort(arr, pi + 1, high);
	}
}

/* Fungsi untuk print output dari array hasil sorting */
void printArray(int arr[], int size)
{
	int i;
	for (i = 0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}

int main()
{
	int arr[] = {10, 7, 8, 9, 1, 5};
	int n = sizeof(arr) / sizeof(arr[0]);
	quickSort(arr, 0, n - 1);
	cout << "Sorted array: \n";
	printArray(arr, n);
	return 0;
}
```
