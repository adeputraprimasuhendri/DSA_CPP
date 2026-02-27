# 📘 Materi Kuliah: Algoritma dan Pemrograman
## Bahasa Pemrograman: C++
### Program Studi Teknik Informatika
---

> **Deskripsi Mata Kuliah:**  
> Mata kuliah ini membekali mahasiswa dengan kemampuan berpikir algoritmik dan implementasinya menggunakan bahasa C++. Mahasiswa akan mempelajari konsep dasar pemrograman hingga struktur data dan algoritma yang lebih kompleks.
>
> **Prasyarat:** Tidak ada  
> **SKS:** 3 SKS (2 Teori + 1 Praktikum)

---

## 📋 Rencana Perkuliahan 21 Pertemuan

| Pertemuan | Topik |
|-----------|-------|
| 1 | Pengantar Algoritma & Pengenalan C++ |
| 2 | Variabel, Tipe Data, dan Operator |
| 3 | Input/Output dan Percabangan |
| 4 | Perulangan (Looping) |
| 5 | Fungsi dan Prosedur |
| 6 | Array Satu Dimensi |
| 7 | Array Multi Dimensi |
| 8 | **UTS (Ujian Tengah Semester)** |
| 9 | String dan Manipulasi Teks |
| 10 | Pointer dan Referensi |
| 11 | Struct dan Enum |
| 12 | Rekursi |
| 13 | Sorting Algorithms |
| 14 | Searching Algorithms |
| 15 | Linked List |
| 16 | Stack dan Queue |
| 17 | Tree dan Binary Search Tree |
| 18 | Kompleksitas Algoritma (Big-O) |
| 19 | File Handling |
| 20 | Review & Studi Kasus |
| 21 | **UAS (Ujian Akhir Semester)** |

---

## 🟢 PERTEMUAN 1: Pengantar Algoritma & Pengenalan C++

### Tujuan Pembelajaran
Setelah pertemuan ini, mahasiswa mampu:
- Memahami konsep algoritma dan cara penulisannya
- Mengenal sejarah dan keunggulan C++
- Menulis dan menjalankan program C++ pertama

### 1.1 Apa itu Algoritma?

**Algoritma** adalah urutan langkah-langkah logis yang terdefinisi dengan baik untuk menyelesaikan suatu masalah.

**Sifat-sifat Algoritma:**
- **Finiteness** – Harus berhenti setelah langkah tertentu
- **Definiteness** – Setiap langkah harus jelas dan tidak ambigu
- **Input** – Memiliki nol atau lebih masukan
- **Output** – Menghasilkan satu atau lebih keluaran
- **Effectiveness** – Setiap langkah harus dapat dilakukan

**Contoh Algoritma (Membuat Mie Instan):**
```
1. Mulai
2. Siapkan air, panci, dan mie instan
3. Masak air hingga mendidih
4. Masukkan mie ke dalam air mendidih
5. Tunggu 3 menit
6. Angkat mie dan tiriskan
7. Campurkan bumbu
8. Sajikan
9. Selesai
```

### 1.2 Pseudocode dan Flowchart

**Pseudocode** - Deskripsi algoritma dalam bahasa semi-formal:
```
BEGIN
  INPUT nilai
  IF nilai >= 60 THEN
    OUTPUT "Lulus"
  ELSE
    OUTPUT "Tidak Lulus"
  END IF
END
```

### 1.3 Pengenalan C++

C++ adalah bahasa pemrograman general-purpose yang dikembangkan oleh **Bjarne Stroustrup** pada tahun 1979 sebagai pengembangan dari bahasa C.

**Keunggulan C++:**
- Performa tinggi
- Kontrol memori langsung
- Mendukung OOP (Object-Oriented Programming)
- Digunakan dalam game, sistem operasi, embedded system

### 1.4 Struktur Dasar Program C++

```cpp
#include <iostream>  // preprocessor directive
using namespace std;

int main() {         // fungsi utama
    // kode program
    cout << "Hello, World!" << endl;
    return 0;        // program berhasil
}
```

**Penjelasan:**
- `#include <iostream>` – Mengimpor library untuk input/output
- `using namespace std` – Menggunakan namespace standar
- `int main()` – Titik awal eksekusi program
- `cout` – Mencetak ke layar
- `return 0` – Mengembalikan nilai 0 (sukses) ke OS

### 1.5 Program Pertama: Hello World

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    cout << "Selamat datang di Pemrograman C++!" << endl;
    return 0;
}
```

**Output:**
```
Hello, World!
Selamat datang di Pemrograman C++!
```

### 💡 Latihan Pertemuan 1
1. Tulis algoritma untuk menghitung luas persegi panjang
2. Buat program C++ yang menampilkan nama dan NIM Anda

---

## 🟢 PERTEMUAN 2: Variabel, Tipe Data, dan Operator

### Tujuan Pembelajaran
- Memahami konsep variabel dan konstanta
- Mengenal berbagai tipe data dalam C++
- Menggunakan operator aritmatika, relasi, dan logika

### 2.1 Variabel dan Konstanta

**Variabel** adalah lokasi memori yang menyimpan data dan nilainya dapat berubah.

```cpp
// Deklarasi variabel
int usia;           // deklarasi saja
int nilai = 85;     // deklarasi + inisialisasi
double berat = 65.5;
char huruf = 'A';
bool aktif = true;

// Konstanta
const double PI = 3.14159;
const int MAX_NILAI = 100;
```

### 2.2 Tipe Data dalam C++

| Tipe Data | Ukuran | Range | Contoh |
|-----------|--------|-------|--------|
| `int` | 4 byte | -2,147,483,648 s/d 2,147,483,647 | 10, -5, 100 |
| `long long` | 8 byte | ±9.2 × 10^18 | 9999999999LL |
| `float` | 4 byte | ±3.4 × 10^38 | 3.14f |
| `double` | 8 byte | ±1.7 × 10^308 | 3.14159 |
| `char` | 1 byte | -128 s/d 127 | 'A', 'z' |
| `bool` | 1 byte | true / false | true |
| `string` | variabel | - | "Halo" |

### 2.3 Operator

**Operator Aritmatika:**
```cpp
int a = 10, b = 3;
cout << a + b;   // 13 (penjumlahan)
cout << a - b;   // 7  (pengurangan)
cout << a * b;   // 30 (perkalian)
cout << a / b;   // 3  (pembagian bulat)
cout << a % b;   // 1  (modulo/sisa bagi)
```

**Operator Relasi:**
```cpp
cout << (a > b);   // true (1)
cout << (a < b);   // false (0)
cout << (a == b);  // false (0)
cout << (a != b);  // true (1)
cout << (a >= b);  // true (1)
```

**Operator Logika:**
```cpp
bool x = true, y = false;
cout << (x && y);  // false (AND)
cout << (x || y);  // true  (OR)
cout << (!x);      // false (NOT)
```

**Operator Increment/Decrement:**
```cpp
int n = 5;
n++;   // n = 6 (post-increment)
n--;   // n = 5 (post-decrement)
++n;   // n = 6 (pre-increment)
```

### 2.4 Contoh Program Lengkap

```cpp
#include <iostream>
using namespace std;

int main() {
    // Deklarasi variabel
    int panjang, lebar;
    double luas, keliling;
    
    // Input
    cout << "Masukkan panjang: ";
    cin >> panjang;
    cout << "Masukkan lebar: ";
    cin >> lebar;
    
    // Proses
    luas = panjang * lebar;
    keliling = 2 * (panjang + lebar);
    
    // Output
    cout << "Luas: " << luas << endl;
    cout << "Keliling: " << keliling << endl;
    
    return 0;
}
```

### 💡 Latihan Pertemuan 2
1. Buat program konversi suhu dari Celsius ke Fahrenheit (F = C × 9/5 + 32)
2. Buat program menghitung luas dan keliling lingkaran

---

## 🟢 PERTEMUAN 3: Input/Output dan Percabangan

### Tujuan Pembelajaran
- Menggunakan cin dan cout secara efektif
- Memahami dan mengimplementasikan struktur percabangan

### 3.1 Input dan Output

```cpp
#include <iostream>
#include <iomanip>  // untuk formatting
using namespace std;

int main() {
    int umur;
    double ipk;
    string nama;
    
    // Input string dengan spasi
    cout << "Masukkan nama: ";
    getline(cin, nama);
    
    cout << "Masukkan umur: ";
    cin >> umur;
    
    cout << "Masukkan IPK: ";
    cin >> ipk;
    
    // Output dengan formatting
    cout << "\n===== DATA MAHASISWA =====" << endl;
    cout << "Nama  : " << nama << endl;
    cout << "Umur  : " << umur << " tahun" << endl;
    cout << fixed << setprecision(2);
    cout << "IPK   : " << ipk << endl;
    
    return 0;
}
```

### 3.2 Percabangan IF-ELSE

```cpp
// Struktur dasar
if (kondisi) {
    // jika kondisi benar
} else {
    // jika kondisi salah
}
```

**Contoh - Cek Kelulusan:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int nilai;
    cout << "Masukkan nilai (0-100): ";
    cin >> nilai;
    
    if (nilai >= 80) {
        cout << "Grade A - Sangat Memuaskan" << endl;
    } else if (nilai >= 70) {
        cout << "Grade B - Memuaskan" << endl;
    } else if (nilai >= 60) {
        cout << "Grade C - Cukup" << endl;
    } else if (nilai >= 50) {
        cout << "Grade D - Kurang" << endl;
    } else {
        cout << "Grade E - Tidak Lulus" << endl;
    }
    
    return 0;
}
```

### 3.3 Percabangan SWITCH-CASE

```cpp
#include <iostream>
using namespace std;

int main() {
    int hari;
    cout << "Masukkan nomor hari (1-7): ";
    cin >> hari;
    
    switch (hari) {
        case 1:
            cout << "Senin" << endl;
            break;
        case 2:
            cout << "Selasa" << endl;
            break;
        case 3:
            cout << "Rabu" << endl;
            break;
        case 4:
            cout << "Kamis" << endl;
            break;
        case 5:
            cout << "Jumat" << endl;
            break;
        case 6:
            cout << "Sabtu" << endl;
            break;
        case 7:
            cout << "Minggu" << endl;
            break;
        default:
            cout << "Nomor hari tidak valid!" << endl;
    }
    
    return 0;
}
```

### 3.4 Operator Ternary

```cpp
// kondisi ? nilai_benar : nilai_salah
int a = 10, b = 20;
int maks = (a > b) ? a : b;
cout << "Nilai terbesar: " << maks << endl;

// Cek genap/ganjil
int n = 7;
string hasil = (n % 2 == 0) ? "Genap" : "Ganjil";
cout << n << " adalah " << hasil << endl;
```

### 💡 Latihan Pertemuan 3
1. Buat kalkulator sederhana (+, -, ×, ÷) menggunakan switch-case
2. Buat program cek tahun kabisat

---

## 🟢 PERTEMUAN 4: Perulangan (Looping)

### Tujuan Pembelajaran
- Memahami tiga jenis loop: for, while, do-while
- Menggunakan break, continue, dan nested loop

### 4.1 Perulangan FOR

```cpp
// Sintaks dasar
for (inisialisasi; kondisi; update) {
    // kode yang diulang
}

// Contoh: cetak 1-10
for (int i = 1; i <= 10; i++) {
    cout << i << " ";
}
// Output: 1 2 3 4 5 6 7 8 9 10
```

### 4.2 Perulangan WHILE

```cpp
int i = 1;
while (i <= 10) {
    cout << i << " ";
    i++;
}
```

### 4.3 Perulangan DO-WHILE

```cpp
// Minimal satu kali dijalankan
int i = 1;
do {
    cout << i << " ";
    i++;
} while (i <= 10);
```

### 4.4 Break dan Continue

```cpp
// BREAK - menghentikan loop
for (int i = 1; i <= 10; i++) {
    if (i == 6) break;  // berhenti di 6
    cout << i << " ";
}
// Output: 1 2 3 4 5

// CONTINUE - melompati iterasi
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) continue;  // lewati genap
    cout << i << " ";
}
// Output: 1 3 5 7 9
```

### 4.5 Nested Loop (Loop Bersarang)

```cpp
// Mencetak tabel perkalian
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << "Tabel Perkalian 1-10:" << endl;
    for (int i = 1; i <= 10; i++) {
        for (int j = 1; j <= 10; j++) {
            cout << setw(4) << i * j;
        }
        cout << endl;
    }
    return 0;
}
```

### 4.6 Contoh: Pola Bintang

```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 5;
    
    // Segitiga siku-siku
    cout << "Segitiga Siku-Siku:" << endl;
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) {
            cout << "* ";
        }
        cout << endl;
    }
    
    // Piramida
    cout << "\nPiramida:" << endl;
    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) cout << " ";
        for (int j = 1; j <= 2*i-1; j++) cout << "*";
        cout << endl;
    }
    
    return 0;
}
```

### 4.7 Contoh: Bilangan Prima

```cpp
#include <iostream>
using namespace std;

int main() {
    int batas;
    cout << "Tampilkan bilangan prima hingga: ";
    cin >> batas;
    
    cout << "Bilangan prima: ";
    for (int n = 2; n <= batas; n++) {
        bool prima = true;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0) {
                prima = false;
                break;
            }
        }
        if (prima) cout << n << " ";
    }
    cout << endl;
    
    return 0;
}
```

### 💡 Latihan Pertemuan 4
1. Buat program menghitung faktorial dengan loop
2. Buat program deret Fibonacci
3. Tampilkan pola berlian dari bintang

---

## 🟢 PERTEMUAN 5: Fungsi dan Prosedur

### Tujuan Pembelajaran
- Memahami konsep modularisasi program
- Membuat dan memanggil fungsi
- Memahami scope variabel dan passing parameter

### 5.1 Konsep Fungsi

Fungsi adalah blok kode yang melakukan tugas tertentu dan dapat dipanggil berulang kali.

```cpp
// Sintaks fungsi
tipe_kembali namaFungsi(parameter) {
    // badan fungsi
    return nilai;
}
```

### 5.2 Fungsi Tanpa Return Value (void)

```cpp
#include <iostream>
using namespace std;

// Deklarasi fungsi (prototype)
void cetakGaris();
void sapa(string nama);

int main() {
    cetakGaris();
    sapa("Budi");
    cetakGaris();
    return 0;
}

void cetakGaris() {
    cout << "=========================" << endl;
}

void sapa(string nama) {
    cout << "Halo, " << nama << "!" << endl;
}
```

### 5.3 Fungsi dengan Return Value

```cpp
#include <iostream>
using namespace std;

int tambah(int a, int b) {
    return a + b;
}

double luasLingkaran(double r) {
    const double PI = 3.14159;
    return PI * r * r;
}

bool adalahGanjil(int n) {
    return (n % 2 != 0);
}

int main() {
    cout << "3 + 5 = " << tambah(3, 5) << endl;
    cout << "Luas lingkaran r=7: " << luasLingkaran(7) << endl;
    
    int n = 9;
    if (adalahGanjil(n))
        cout << n << " adalah bilangan ganjil" << endl;
    
    return 0;
}
```

### 5.4 Pass by Value vs Pass by Reference

```cpp
#include <iostream>
using namespace std;

// Pass by Value - nilai asli tidak berubah
void kaliDuaValue(int x) {
    x = x * 2;
    cout << "Di dalam fungsi: " << x << endl;
}

// Pass by Reference - nilai asli berubah
void kaliDuaRef(int &x) {
    x = x * 2;
    cout << "Di dalam fungsi: " << x << endl;
}

// Tukar dua nilai
void tukar(int &a, int &b) {
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int angka = 5;
    
    kaliDuaValue(angka);
    cout << "Setelah kaliDuaValue: " << angka << endl;  // 5 (tidak berubah)
    
    kaliDuaRef(angka);
    cout << "Setelah kaliDuaRef: " << angka << endl;    // 10 (berubah)
    
    int a = 3, b = 7;
    cout << "Sebelum tukar: a=" << a << " b=" << b << endl;
    tukar(a, b);
    cout << "Setelah tukar: a=" << a << " b=" << b << endl;
    
    return 0;
}
```

### 5.5 Fungsi dengan Default Parameter

```cpp
#include <iostream>
using namespace std;

void perkenalan(string nama, int umur = 18, string kota = "Jakarta") {
    cout << "Nama: " << nama << ", Umur: " << umur << ", Kota: " << kota << endl;
}

int main() {
    perkenalan("Andi", 20, "Bandung");
    perkenalan("Budi", 22);
    perkenalan("Cici");
    return 0;
}
```

### 5.6 Function Overloading

```cpp
#include <iostream>
using namespace std;

int luas(int sisi) {                   // luas persegi
    return sisi * sisi;
}

int luas(int p, int l) {               // luas persegi panjang
    return p * l;
}

double luas(double r) {                // luas lingkaran
    return 3.14159 * r * r;
}

int main() {
    cout << "Luas persegi (5): " << luas(5) << endl;
    cout << "Luas persegi panjang (4,6): " << luas(4, 6) << endl;
    cout << "Luas lingkaran (3.5): " << luas(3.5) << endl;
    return 0;
}
```

### 💡 Latihan Pertemuan 5
1. Buat fungsi mencari nilai maksimum dari tiga angka
2. Buat fungsi mengecek bilangan prima
3. Buat kalkulator menggunakan fungsi terpisah

---

## 🟢 PERTEMUAN 6: Array Satu Dimensi

### Tujuan Pembelajaran
- Memahami konsep dan deklarasi array
- Melakukan operasi dasar pada array
- Menggunakan array sebagai parameter fungsi

### 6.1 Konsep Array

Array adalah kumpulan elemen bertipe sama yang disimpan secara berurutan di memori.

```cpp
// Deklarasi array
int nilai[5];                          // array 5 elemen, belum diinisialisasi
int skor[5] = {85, 90, 78, 92, 88};   // dengan inisialisasi
int data[] = {1, 2, 3, 4, 5};         // ukuran otomatis

// Akses elemen (indeks mulai dari 0)
cout << skor[0];   // 85 (elemen pertama)
cout << skor[4];   // 88 (elemen terakhir)
skor[2] = 80;      // mengubah elemen ke-3
```

### 6.2 Operasi Dasar Array

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 5;
    int nilai[N];
    
    // Input array
    cout << "Masukkan " << N << " nilai:" << endl;
    for (int i = 0; i < N; i++) {
        cout << "Nilai ke-" << (i+1) << ": ";
        cin >> nilai[i];
    }
    
    // Menampilkan array
    cout << "\nData nilai: ";
    for (int i = 0; i < N; i++) {
        cout << nilai[i] << " ";
    }
    
    // Mencari nilai maksimum dan minimum
    int maks = nilai[0], min = nilai[0];
    double total = 0;
    
    for (int i = 0; i < N; i++) {
        if (nilai[i] > maks) maks = nilai[i];
        if (nilai[i] < min) min = nilai[i];
        total += nilai[i];
    }
    
    cout << "\n\nStatistik:" << endl;
    cout << "Nilai Maks : " << maks << endl;
    cout << "Nilai Min  : " << min << endl;
    cout << "Rata-rata  : " << total/N << endl;
    
    return 0;
}
```

### 6.3 Array sebagai Parameter Fungsi

```cpp
#include <iostream>
using namespace std;

void tampilkan(int arr[], int n) {
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
}

int jumlah(int arr[], int n) {
    int total = 0;
    for (int i = 0; i < n; i++)
        total += arr[i];
    return total;
}

void balik(int arr[], int n) {
    for (int i = 0; i < n/2; i++) {
        int temp = arr[i];
        arr[i] = arr[n-1-i];
        arr[n-1-i] = temp;
    }
}

int main() {
    int data[] = {3, 1, 4, 1, 5, 9, 2, 6};
    int n = sizeof(data) / sizeof(data[0]);
    
    cout << "Array awal: ";
    tampilkan(data, n);
    
    cout << "Jumlah: " << jumlah(data, n) << endl;
    
    balik(data, n);
    cout << "Array terbalik: ";
    tampilkan(data, n);
    
    return 0;
}
```

### 6.4 Contoh: Frekuensi Nilai

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 10;
    int data[N];
    int frekuensi[101] = {0};  // untuk nilai 0-100
    
    cout << "Masukkan " << N << " nilai (0-100):" << endl;
    for (int i = 0; i < N; i++) {
        cin >> data[i];
        frekuensi[data[i]]++;
    }
    
    cout << "\nFrekuensi nilai:" << endl;
    for (int i = 0; i <= 100; i++) {
        if (frekuensi[i] > 0)
            cout << "Nilai " << i << ": " << frekuensi[i] << " kali" << endl;
    }
    
    return 0;
}
```

### 💡 Latihan Pertemuan 6
1. Buat program mencari dua nilai terbesar dalam array
2. Buat program menghitung jumlah elemen genap dan ganjil

---

## 🟢 PERTEMUAN 7: Array Multi Dimensi

### Tujuan Pembelajaran
- Memahami array 2D dan 3D
- Melakukan operasi matriks (penjumlahan, perkalian)
- Menggunakan array 2D untuk representasi data

### 7.1 Array Dua Dimensi

```cpp
// Deklarasi
int matriks[3][4];                          // 3 baris, 4 kolom
int grid[2][3] = {{1,2,3}, {4,5,6}};

// Akses elemen
grid[0][0] = 10;   // baris 0, kolom 0
cout << grid[1][2]; // baris 1, kolom 2 = 6
```

### 7.2 Operasi Matriks

```cpp
#include <iostream>
using namespace std;

const int MAKS = 10;

void inputMatriks(int A[][MAKS], int m, int n, string nama) {
    cout << "Input matriks " << nama << " (" << m << "x" << n << "):" << endl;
    for (int i = 0; i < m; i++)
        for (int j = 0; j < n; j++) {
            cout << nama << "[" << i << "][" << j << "]: ";
            cin >> A[i][j];
        }
}

void cetakMatriks(int A[][MAKS], int m, int n) {
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++)
            cout << "\t" << A[i][j];
        cout << endl;
    }
}

void tambahMatriks(int A[][MAKS], int B[][MAKS], int C[][MAKS], int m, int n) {
    for (int i = 0; i < m; i++)
        for (int j = 0; j < n; j++)
            C[i][j] = A[i][j] + B[i][j];
}

void kaliMatriks(int A[][MAKS], int B[][MAKS], int C[][MAKS], int m, int n, int p) {
    for (int i = 0; i < m; i++)
        for (int j = 0; j < p; j++) {
            C[i][j] = 0;
            for (int k = 0; k < n; k++)
                C[i][j] += A[i][k] * B[k][j];
        }
}

int main() {
    int A[MAKS][MAKS], B[MAKS][MAKS], C[MAKS][MAKS];
    int m = 2, n = 2;
    
    inputMatriks(A, m, n, "A");
    inputMatriks(B, m, n, "B");
    
    tambahMatriks(A, B, C, m, n);
    cout << "\nA + B =" << endl;
    cetakMatriks(C, m, n);
    
    kaliMatriks(A, B, C, m, n, n);
    cout << "\nA × B =" << endl;
    cetakMatriks(C, m, n);
    
    return 0;
}
```

### 7.3 Transpose Matriks

```cpp
void transpose(int A[][MAKS], int T[][MAKS], int m, int n) {
    for (int i = 0; i < m; i++)
        for (int j = 0; j < n; j++)
            T[j][i] = A[i][j];
}
```

### 💡 Latihan Pertemuan 7
1. Buat program determinan matriks 2x2 dan 3x3
2. Buat program game papan sederhana (catur sederhana)

---

## ⚠️ PERTEMUAN 8: UTS (Ujian Tengah Semester)

**Materi yang diujikan:** Pertemuan 1 - 7

**Bentuk Soal:**
- Pilihan Ganda (20 soal) – 40%
- Uraian Pendek (5 soal) – 30%
- Praktik Coding (2 soal) – 30%

---

## 🟢 PERTEMUAN 9: String dan Manipulasi Teks

### Tujuan Pembelajaran
- Memahami perbedaan C-string dan std::string
- Menggunakan fungsi manipulasi string
- Melakukan parsing dan pemrosesan teks

### 9.1 C-String vs std::string

```cpp
#include <iostream>
#include <string>
#include <cstring>  // untuk C-string functions
using namespace std;

int main() {
    // C-string (array of char)
    char cStr[] = "Hello";
    cout << strlen(cStr) << endl;     // panjang: 5
    
    // std::string (lebih mudah digunakan)
    string str = "Hello, World!";
    cout << str.length() << endl;    // 13
    cout << str.size() << endl;      // sama dengan length()
    
    return 0;
}
```

### 9.2 Operasi std::string

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s1 = "Hello";
    string s2 = " World";
    
    // Concatenation
    string s3 = s1 + s2;             // "Hello World"
    s1 += "!";                       // "Hello!"
    
    // Akses karakter
    cout << s3[0] << endl;           // 'H'
    cout << s3.at(6) << endl;        // 'W'
    
    // Substring
    cout << s3.substr(0, 5) << endl; // "Hello"
    cout << s3.substr(6) << endl;    // "World"
    
    // Pencarian
    int pos = s3.find("World");
    if (pos != string::npos)
        cout << "Ditemukan di posisi: " << pos << endl;
    
    // Replace
    s3.replace(6, 5, "C++");        // "Hello C++"
    
    // Convert
    cout << s3.toupper();            // ERROR - harus pakai algorithm
    
    // Upper/Lower case
    string kata = "Hello";
    for (char& c : kata) c = toupper(c);
    cout << kata << endl;            // "HELLO"
    
    return 0;
}
```

### 9.3 String Input dengan Spasi

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string nama, alamat;
    
    cout << "Masukkan nama: ";
    getline(cin, nama);
    
    cout << "Masukkan alamat: ";
    getline(cin, alamat);
    
    cout << "Nama: " << nama << endl;
    cout << "Alamat: " << alamat << endl;
    
    return 0;
}
```

### 9.4 Contoh: Cek Palindrom

```cpp
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

bool isPalindrom(string s) {
    // Ubah ke lowercase dan hapus non-alpha
    string bersih = "";
    for (char c : s) {
        if (isalpha(c)) bersih += tolower(c);
    }
    
    string terbalik = bersih;
    reverse(terbalik.begin(), terbalik.end());
    
    return bersih == terbalik;
}

int main() {
    string kata;
    cout << "Masukkan kata: ";
    getline(cin, kata);
    
    if (isPalindrom(kata))
        cout << "\"" << kata << "\" adalah palindrom" << endl;
    else
        cout << "\"" << kata << "\" bukan palindrom" << endl;
    
    return 0;
}
```

### 💡 Latihan Pertemuan 9
1. Buat program menghitung jumlah kata dalam sebuah kalimat
2. Buat program enkripsi Caesar cipher sederhana

---

## 🟢 PERTEMUAN 10: Pointer dan Referensi

### Tujuan Pembelajaran
- Memahami konsep pointer dan alamat memori
- Menggunakan pointer untuk manipulasi data
- Memahami hubungan pointer dengan array

### 10.1 Konsep Pointer

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    
    // Pointer - menyimpan alamat memori
    int *ptr = &x;   // ptr menunjuk ke x
    
    cout << "Nilai x        : " << x << endl;
    cout << "Alamat x (&x)  : " << &x << endl;
    cout << "Nilai ptr      : " << ptr << endl;   // sama dengan &x
    cout << "Nilai di ptr   : " << *ptr << endl;  // dereferencing = 10
    
    // Mengubah nilai melalui pointer
    *ptr = 20;
    cout << "Nilai x setelah *ptr=20: " << x << endl;  // 20
    
    return 0;
}
```

### 10.2 Pointer dan Array

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int *ptr = arr;   // ptr menunjuk ke elemen pertama
    
    // Akses elemen menggunakan pointer
    cout << *ptr << endl;       // 10
    cout << *(ptr+1) << endl;   // 20
    cout << *(ptr+2) << endl;   // 30
    
    // Pointer arithmetic
    for (int i = 0; i < 5; i++) {
        cout << *(arr + i) << " ";  // sama dengan arr[i]
    }
    cout << endl;
    
    // Traversal dengan pointer
    for (int *p = arr; p < arr + 5; p++) {
        cout << *p << " ";
    }
    
    return 0;
}
```

### 10.3 Dynamic Memory Allocation

```cpp
#include <iostream>
using namespace std;

int main() {
    // Alokasi memori dinamis
    int *p = new int;       // alokasi 1 integer
    *p = 42;
    cout << *p << endl;
    delete p;               // bebaskan memori
    
    // Alokasi array dinamis
    int n;
    cout << "Masukkan ukuran array: ";
    cin >> n;
    
    int *arr = new int[n];  // alokasi array
    
    for (int i = 0; i < n; i++) {
        cout << "Masukkan arr[" << i << "]: ";
        cin >> arr[i];
    }
    
    cout << "Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    
    delete[] arr;           // bebaskan array
    
    return 0;
}
```

### 10.4 Pointer to Pointer

```cpp
int x = 5;
int *p = &x;
int **pp = &p;

cout << x << endl;     // 5
cout << *p << endl;    // 5
cout << **pp << endl;  // 5
```

### 💡 Latihan Pertemuan 10
1. Buat program menggunakan pointer untuk mencari elemen terbesar
2. Buat program array dinamis yang ukurannya ditentukan user

---

## 🟢 PERTEMUAN 11: Struct dan Enum

### Tujuan Pembelajaran
- Membuat dan menggunakan struct
- Memahami kegunaan enum
- Membangun program dengan struct kompleks

### 11.1 Struct

```cpp
#include <iostream>
#include <string>
using namespace std;

// Definisi struct
struct Mahasiswa {
    int nim;
    string nama;
    string jurusan;
    double ipk;
};

void tampilkan(Mahasiswa mhs) {
    cout << "NIM     : " << mhs.nim << endl;
    cout << "Nama    : " << mhs.nama << endl;
    cout << "Jurusan : " << mhs.jurusan << endl;
    cout << "IPK     : " << mhs.ipk << endl;
}

int main() {
    // Membuat objek struct
    Mahasiswa mhs1;
    mhs1.nim = 12345;
    mhs1.nama = "Andi Budi";
    mhs1.jurusan = "Teknik Informatika";
    mhs1.ipk = 3.75;
    
    // Inisialisasi langsung
    Mahasiswa mhs2 = {67890, "Citra Dewi", "Sistem Informasi", 3.82};
    
    tampilkan(mhs1);
    cout << "---" << endl;
    tampilkan(mhs2);
    
    return 0;
}
```

### 11.2 Array of Struct

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Produk {
    int kode;
    string nama;
    double harga;
    int stok;
};

int main() {
    const int N = 3;
    Produk barang[N];
    
    // Input
    for (int i = 0; i < N; i++) {
        cout << "--- Produk " << (i+1) << " ---" << endl;
        cout << "Kode  : "; cin >> barang[i].kode;
        cin.ignore();
        cout << "Nama  : "; getline(cin, barang[i].nama);
        cout << "Harga : "; cin >> barang[i].harga;
        cout << "Stok  : "; cin >> barang[i].stok;
    }
    
    // Tampilkan
    cout << "\n===== DAFTAR PRODUK =====" << endl;
    cout << "Kode\tNama\t\tHarga\t\tStok" << endl;
    for (int i = 0; i < N; i++) {
        cout << barang[i].kode << "\t"
             << barang[i].nama << "\t\t"
             << barang[i].harga << "\t\t"
             << barang[i].stok << endl;
    }
    
    return 0;
}
```

### 11.3 Enum

```cpp
#include <iostream>
using namespace std;

enum Hari {SENIN=1, SELASA, RABU, KAMIS, JUMAT, SABTU, MINGGU};
enum Status {AKTIF, NONAKTIF, LULUS, CUTI};

int main() {
    Hari today = RABU;
    
    if (today == RABU) {
        cout << "Hari ini adalah Rabu (hari ke-" << today << ")" << endl;
    }
    
    Status statusMhs = AKTIF;
    switch(statusMhs) {
        case AKTIF:    cout << "Status: Aktif" << endl; break;
        case NONAKTIF: cout << "Status: Non-aktif" << endl; break;
        case LULUS:    cout << "Status: Lulus" << endl; break;
        case CUTI:     cout << "Status: Cuti" << endl; break;
    }
    
    return 0;
}
```

### 11.4 Struct dengan Pointer

```cpp
struct Node {
    int data;
    Node *next;  // pointer ke struct yang sama
};
```

### 💡 Latihan Pertemuan 11
1. Buat sistem manajemen buku (struct Buku dengan CRUD sederhana)
2. Buat program rapor siswa menggunakan struct

---

## 🟢 PERTEMUAN 12: Rekursi

### Tujuan Pembelajaran
- Memahami konsep rekursi dan stack call
- Mengidentifikasi base case dan recursive case
- Mengimplementasikan algoritma rekursif klasik

### 12.1 Konsep Rekursi

Rekursi adalah teknik pemrograman di mana sebuah fungsi memanggil dirinya sendiri.

**Komponen wajib:**
1. **Base case** – kondisi berhenti
2. **Recursive case** – pemanggilan diri sendiri

```
f(n) = f(n-1) + 1   <-- recursive case
f(0) = 0            <-- base case
```

### 12.2 Faktorial Rekursif

```cpp
#include <iostream>
using namespace std;

// Iteratif
long long faktorialIter(int n) {
    long long hasil = 1;
    for (int i = 1; i <= n; i++)
        hasil *= i;
    return hasil;
}

// Rekursif
long long faktorialRek(int n) {
    if (n == 0 || n == 1)  // base case
        return 1;
    return n * faktorialRek(n - 1);  // recursive case
}

int main() {
    for (int i = 0; i <= 10; i++)
        cout << i << "! = " << faktorialRek(i) << endl;
    
    return 0;
}
```

**Visualisasi faktorial(4):**
```
faktorial(4)
  = 4 * faktorial(3)
  = 4 * 3 * faktorial(2)
  = 4 * 3 * 2 * faktorial(1)
  = 4 * 3 * 2 * 1
  = 24
```

### 12.3 Fibonacci Rekursif

```cpp
#include <iostream>
using namespace std;

// Rekursif (kurang efisien)
int fibRek(int n) {
    if (n <= 1) return n;  // base case
    return fibRek(n-1) + fibRek(n-2);
}

// Dengan memoization (lebih efisien)
int memo[100] = {-1};
int fibMemo(int n) {
    if (n <= 1) return n;
    if (memo[n] != -1) return memo[n];
    return memo[n] = fibMemo(n-1) + fibMemo(n-2);
}

int main() {
    // Inisialisasi memo
    fill(memo, memo+100, -1);
    
    cout << "Deret Fibonacci:" << endl;
    for (int i = 0; i < 15; i++)
        cout << fibMemo(i) << " ";
    cout << endl;
    
    return 0;
}
```

### 12.4 Menara Hanoi

```cpp
#include <iostream>
using namespace std;

void hanoi(int n, char dari, char ke, char bantu) {
    if (n == 1) {
        cout << "Pindahkan cakram 1 dari " << dari << " ke " << ke << endl;
        return;
    }
    hanoi(n-1, dari, bantu, ke);
    cout << "Pindahkan cakram " << n << " dari " << dari << " ke " << ke << endl;
    hanoi(n-1, bantu, ke, dari);
}

int main() {
    int n;
    cout << "Jumlah cakram: ";
    cin >> n;
    hanoi(n, 'A', 'C', 'B');
    cout << "\nTotal langkah: " << (int)pow(2, n) - 1 << endl;
    return 0;
}
```

### 12.5 Binary Search Rekursif

```cpp
int binarySearch(int arr[], int low, int high, int target) {
    if (low > high) return -1;  // base case: tidak ditemukan
    
    int mid = (low + high) / 2;
    
    if (arr[mid] == target) return mid;
    else if (arr[mid] < target) return binarySearch(arr, mid+1, high, target);
    else return binarySearch(arr, low, mid-1, target);
}
```

### 💡 Latihan Pertemuan 12
1. Buat fungsi rekursif untuk menghitung pangkat (power)
2. Buat fungsi rekursif untuk membalik string

---

## 🟢 PERTEMUAN 13: Sorting Algorithms

### Tujuan Pembelajaran
- Memahami konsep sorting
- Mengimplementasikan berbagai algoritma sorting
- Membandingkan kompleksitas waktu algoritma sorting

### 13.1 Bubble Sort

```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        bool swapped = false;
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                swap(arr[j], arr[j+1]);
                swapped = true;
            }
        }
        if (!swapped) break;  // optimasi: sudah terurut
    }
}

void cetakArray(int arr[], int n) {
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int data[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(data) / sizeof(data[0]);
    
    cout << "Sebelum: "; cetakArray(data, n);
    bubbleSort(data, n);
    cout << "Sesudah: "; cetakArray(data, n);
    
    return 0;
}
```

### 13.2 Selection Sort

```cpp
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        int minIdx = i;
        for (int j = i+1; j < n; j++)
            if (arr[j] < arr[minIdx])
                minIdx = j;
        swap(arr[minIdx], arr[i]);
    }
}
```

### 13.3 Insertion Sort

```cpp
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = key;
    }
}
```

### 13.4 Merge Sort

```cpp
#include <iostream>
using namespace std;

void merge(int arr[], int low, int mid, int high) {
    int n1 = mid - low + 1;
    int n2 = high - mid;
    
    int L[n1], R[n2];
    for (int i = 0; i < n1; i++) L[i] = arr[low + i];
    for (int j = 0; j < n2; j++) R[j] = arr[mid + 1 + j];
    
    int i = 0, j = 0, k = low;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) arr[k++] = L[i++];
        else arr[k++] = R[j++];
    }
    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];
}

void mergeSort(int arr[], int low, int high) {
    if (low < high) {
        int mid = (low + high) / 2;
        mergeSort(arr, low, mid);
        mergeSort(arr, mid+1, high);
        merge(arr, low, mid, high);
    }
}
```

### 13.5 Quick Sort

```cpp
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    
    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i+1], arr[high]);
    return i + 1;
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi-1);
        quickSort(arr, pi+1, high);
    }
}
```

### 13.6 Perbandingan Kompleksitas

| Algoritma | Best | Average | Worst | Space |
|-----------|------|---------|-------|-------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) |

### 💡 Latihan Pertemuan 13
1. Implementasikan counting sort untuk data integer 0-100
2. Bandingkan waktu eksekusi bubble sort vs quick sort

---

## 🟢 PERTEMUAN 14: Searching Algorithms

### Tujuan Pembelajaran
- Mengimplementasikan linear search dan binary search
- Memahami kapan menggunakan masing-masing algoritma
- Menganalisis kompleksitas algoritma pencarian

### 14.1 Linear Search

```cpp
#include <iostream>
using namespace std;

// Mengembalikan indeks, -1 jika tidak ditemukan
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}

// Mengembalikan semua indeks yang cocok
void linearSearchAll(int arr[], int n, int target) {
    bool found = false;
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            cout << "Ditemukan di indeks: " << i << endl;
            found = true;
        }
    }
    if (!found) cout << "Tidak ditemukan" << endl;
}

int main() {
    int data[] = {5, 3, 8, 2, 9, 1, 7, 4, 6, 8};
    int n = 10;
    
    int target = 8;
    int idx = linearSearch(data, n, target);
    
    if (idx != -1)
        cout << target << " ditemukan di indeks " << idx << endl;
    
    cout << "Semua posisi " << target << ":" << endl;
    linearSearchAll(data, n, target);
    
    return 0;
}
```

### 14.2 Binary Search (Iteratif)

```cpp
// Array HARUS sudah terurut!
int binarySearch(int arr[], int n, int target) {
    int low = 0, high = n - 1;
    
    while (low <= high) {
        int mid = low + (high - low) / 2;  // hindari overflow
        
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            low = mid + 1;
        else
            high = mid - 1;
    }
    
    return -1;
}
```

### 14.3 Binary Search pada String

```cpp
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

int binarySearchString(string arr[], int n, string target) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

int main() {
    string nama[] = {"Andi", "Budi", "Citra", "Doni", "Eva"};
    int n = 5;
    
    // sudah terurut alfabetis
    string cari = "Citra";
    int hasil = binarySearchString(nama, n, cari);
    
    if (hasil != -1)
        cout << cari << " ditemukan di indeks " << hasil << endl;
    
    return 0;
}
```

### 14.4 Perbandingan Linear vs Binary Search

```cpp
#include <iostream>
#include <ctime>
using namespace std;

int main() {
    const int N = 1000000;
    int *arr = new int[N];
    for (int i = 0; i < N; i++) arr[i] = i;
    
    int target = 999999;
    
    // Linear Search
    clock_t start = clock();
    int idx1 = linearSearch(arr, N, target);
    clock_t end = clock();
    cout << "Linear Search: " << (double)(end-start)/CLOCKS_PER_SEC << "s" << endl;
    
    // Binary Search
    start = clock();
    int idx2 = binarySearch(arr, N, target);
    end = clock();
    cout << "Binary Search: " << (double)(end-start)/CLOCKS_PER_SEC << "s" << endl;
    
    delete[] arr;
    return 0;
}
```

### 💡 Latihan Pertemuan 14
1. Implementasikan interpolation search
2. Buat program direktori mahasiswa dengan fitur pencarian

---

## 🟢 PERTEMUAN 15: Linked List

### Tujuan Pembelajaran
- Memahami konsep linked list dan keunggulannya vs array
- Mengimplementasikan singly dan doubly linked list
- Melakukan operasi insert, delete, dan traversal

### 15.1 Konsep Linked List

```
[10|*] -> [20|*] -> [30|*] -> [40|NULL]
```

Setiap **node** memiliki:
- **Data** – nilai yang disimpan
- **Next** – pointer ke node berikutnya

### 15.2 Singly Linked List

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node *next;
    
    Node(int val) : data(val), next(nullptr) {}
};

class LinkedList {
private:
    Node *head;
    
public:
    LinkedList() : head(nullptr) {}
    
    // Tambah di depan
    void pushFront(int val) {
        Node *baru = new Node(val);
        baru->next = head;
        head = baru;
    }
    
    // Tambah di belakang
    void pushBack(int val) {
        Node *baru = new Node(val);
        if (!head) {
            head = baru;
            return;
        }
        Node *curr = head;
        while (curr->next) curr = curr->next;
        curr->next = baru;
    }
    
    // Hapus dari depan
    void popFront() {
        if (!head) return;
        Node *temp = head;
        head = head->next;
        delete temp;
    }
    
    // Hapus berdasarkan nilai
    void hapus(int val) {
        if (!head) return;
        if (head->data == val) {
            popFront();
            return;
        }
        Node *curr = head;
        while (curr->next && curr->next->data != val)
            curr = curr->next;
        if (curr->next) {
            Node *temp = curr->next;
            curr->next = temp->next;
            delete temp;
        }
    }
    
    // Tampilkan
    void tampilkan() {
        Node *curr = head;
        while (curr) {
            cout << curr->data;
            if (curr->next) cout << " -> ";
            curr = curr->next;
        }
        cout << " -> NULL" << endl;
    }
    
    // Ukuran
    int ukuran() {
        int count = 0;
        Node *curr = head;
        while (curr) { count++; curr = curr->next; }
        return count;
    }
    
    // Destructor
    ~LinkedList() {
        while (head) popFront();
    }
};

int main() {
    LinkedList ll;
    
    ll.pushBack(10);
    ll.pushBack(20);
    ll.pushBack(30);
    ll.pushFront(5);
    
    cout << "List: ";
    ll.tampilkan();
    
    ll.hapus(20);
    cout << "Setelah hapus 20: ";
    ll.tampilkan();
    
    cout << "Ukuran: " << ll.ukuran() << endl;
    
    return 0;
}
```

### 15.3 Doubly Linked List

```cpp
struct NodeDL {
    int data;
    NodeDL *prev;
    NodeDL *next;
    
    NodeDL(int val) : data(val), prev(nullptr), next(nullptr) {}
};
```

### 💡 Latihan Pertemuan 15
1. Implementasikan circular linked list
2. Buat program membalik linked list

---

## 🟢 PERTEMUAN 16: Stack dan Queue

### Tujuan Pembelajaran
- Memahami konsep LIFO (Stack) dan FIFO (Queue)
- Mengimplementasikan stack dan queue dengan array dan linked list
- Menerapkan stack/queue pada masalah nyata

### 16.1 Stack (LIFO - Last In First Out)

```cpp
#include <iostream>
using namespace std;

class Stack {
private:
    int data[100];
    int top;
    
public:
    Stack() : top(-1) {}
    
    bool isEmpty() { return top == -1; }
    bool isFull() { return top == 99; }
    
    void push(int val) {
        if (isFull()) { cout << "Stack penuh!" << endl; return; }
        data[++top] = val;
    }
    
    int pop() {
        if (isEmpty()) { cout << "Stack kosong!" << endl; return -1; }
        return data[top--];
    }
    
    int peek() {
        if (isEmpty()) return -1;
        return data[top];
    }
    
    void tampilkan() {
        cout << "Stack (top->bottom): ";
        for (int i = top; i >= 0; i--)
            cout << data[i] << " ";
        cout << endl;
    }
};

// Contoh: cek keseimbangan kurung
bool cekKurung(string ekspresi) {
    Stack s;
    for (char c : ekspresi) {
        if (c == '(' || c == '[' || c == '{')
            s.push(c);
        else if (c == ')' || c == ']' || c == '}') {
            if (s.isEmpty()) return false;
            char top = s.pop();
            if ((c == ')' && top != '(') ||
                (c == ']' && top != '[') ||
                (c == '}' && top != '{'))
                return false;
        }
    }
    return s.isEmpty();
}

int main() {
    Stack s;
    s.push(1); s.push(2); s.push(3); s.push(4);
    s.tampilkan();
    cout << "Pop: " << s.pop() << endl;
    s.tampilkan();
    
    // Cek kurung
    string test1 = "{[()]}";
    string test2 = "{[(])}";
    cout << test1 << " : " << (cekKurung(test1) ? "Seimbang" : "Tidak Seimbang") << endl;
    cout << test2 << " : " << (cekKurung(test2) ? "Seimbang" : "Tidak Seimbang") << endl;
    
    return 0;
}
```

### 16.2 Queue (FIFO - First In First Out)

```cpp
#include <iostream>
using namespace std;

class Queue {
private:
    int data[100];
    int front, rear, ukuran;
    
public:
    Queue() : front(0), rear(-1), ukuran(0) {}
    
    bool isEmpty() { return ukuran == 0; }
    bool isFull() { return ukuran == 100; }
    
    void enqueue(int val) {
        if (isFull()) { cout << "Queue penuh!" << endl; return; }
        rear = (rear + 1) % 100;  // circular queue
        data[rear] = val;
        ukuran++;
    }
    
    int dequeue() {
        if (isEmpty()) { cout << "Queue kosong!" << endl; return -1; }
        int val = data[front];
        front = (front + 1) % 100;
        ukuran--;
        return val;
    }
    
    int peek() {
        if (isEmpty()) return -1;
        return data[front];
    }
    
    void tampilkan() {
        cout << "Queue (front->rear): ";
        for (int i = 0; i < ukuran; i++)
            cout << data[(front + i) % 100] << " ";
        cout << endl;
    }
};

int main() {
    Queue q;
    q.enqueue(10); q.enqueue(20); q.enqueue(30); q.enqueue(40);
    q.tampilkan();
    
    cout << "Dequeue: " << q.dequeue() << endl;
    q.tampilkan();
    
    return 0;
}
```

### 16.3 Stack dengan STL

```cpp
#include <stack>
#include <queue>
using namespace std;

// Stack STL
stack<int> s;
s.push(1); s.push(2); s.push(3);
cout << s.top() << endl;  // 3
s.pop();

// Queue STL
queue<int> q;
q.push(10); q.push(20);
cout << q.front() << endl;  // 10
q.pop();
```

### 💡 Latihan Pertemuan 16
1. Implementasikan konversi infix ke postfix menggunakan stack
2. Buat simulasi antrian bank dengan queue

---

## 🟢 PERTEMUAN 17: Tree dan Binary Search Tree

### Tujuan Pembelajaran
- Memahami struktur data pohon (tree)
- Mengimplementasikan Binary Search Tree (BST)
- Melakukan traversal: inorder, preorder, postorder

### 17.1 Konsep Tree

```
         50
        /  \
       30   70
      / \   / \
     20  40 60  80
```

**Terminologi:**
- **Root** – node paling atas (50)
- **Leaf** – node tanpa anak (20, 40, 60, 80)
- **Height** – tinggi tree (3)
- **Parent/Child** – hubungan orang tua/anak

### 17.2 Binary Search Tree (BST)

**Properti BST:**
- Node kiri < node saat ini
- Node kanan > node saat ini

```cpp
#include <iostream>
using namespace std;

struct NodeBST {
    int data;
    NodeBST *left, *right;
    NodeBST(int val) : data(val), left(nullptr), right(nullptr) {}
};

class BST {
private:
    NodeBST *root;
    
    NodeBST* insert(NodeBST *node, int val) {
        if (!node) return new NodeBST(val);
        if (val < node->data) node->left = insert(node->left, val);
        else if (val > node->data) node->right = insert(node->right, val);
        return node;
    }
    
    bool search(NodeBST *node, int val) {
        if (!node) return false;
        if (val == node->data) return true;
        if (val < node->data) return search(node->left, val);
        return search(node->right, val);
    }
    
    void inorder(NodeBST *node) {
        if (!node) return;
        inorder(node->left);
        cout << node->data << " ";
        inorder(node->right);
    }
    
    void preorder(NodeBST *node) {
        if (!node) return;
        cout << node->data << " ";
        preorder(node->left);
        preorder(node->right);
    }
    
    void postorder(NodeBST *node) {
        if (!node) return;
        postorder(node->left);
        postorder(node->right);
        cout << node->data << " ";
    }
    
    int height(NodeBST *node) {
        if (!node) return 0;
        return 1 + max(height(node->left), height(node->right));
    }
    
public:
    BST() : root(nullptr) {}
    
    void insert(int val) { root = insert(root, val); }
    bool search(int val) { return search(root, val); }
    
    void inorder() {
        cout << "Inorder: ";
        inorder(root);
        cout << endl;
    }
    
    void preorder() {
        cout << "Preorder: ";
        preorder(root);
        cout << endl;
    }
    
    void postorder() {
        cout << "Postorder: ";
        postorder(root);
        cout << endl;
    }
    
    int height() { return height(root); }
};

int main() {
    BST tree;
    int data[] = {50, 30, 70, 20, 40, 60, 80};
    
    for (int val : data)
        tree.insert(val);
    
    tree.inorder();    // terurut ascending
    tree.preorder();   // root dulu
    tree.postorder();  // leaf dulu
    
    cout << "Height: " << tree.height() << endl;
    
    cout << "Cari 40: " << (tree.search(40) ? "Ada" : "Tidak ada") << endl;
    cout << "Cari 99: " << (tree.search(99) ? "Ada" : "Tidak ada") << endl;
    
    return 0;
}
```

### 💡 Latihan Pertemuan 17
1. Implementasikan delete node pada BST
2. Buat program mencari nilai minimum dan maksimum di BST

---

## 🟢 PERTEMUAN 18: Kompleksitas Algoritma (Big-O Notation)

### Tujuan Pembelajaran
- Memahami konsep kompleksitas waktu dan ruang
- Menghitung dan menganalisis Big-O notation
- Membandingkan efisiensi algoritma

### 18.1 Apa itu Big-O Notation?

Big-O menggambarkan **laju pertumbuhan** waktu/ruang yang dibutuhkan suatu algoritma relatif terhadap ukuran input (n).

### 18.2 Kelas Kompleksitas Umum

| Notasi | Nama | Contoh |
|--------|------|--------|
| O(1) | Konstan | Akses array[i] |
| O(log n) | Logaritmik | Binary Search |
| O(n) | Linear | Linear Search |
| O(n log n) | Linearitmik | Merge Sort |
| O(n²) | Kuadratik | Bubble Sort |
| O(2ⁿ) | Eksponensial | Fibonacci naif |
| O(n!) | Faktorial | Permutasi semua |

### 18.3 Contoh Analisis

```cpp
// O(1) - waktu konstan
int getFirst(int arr[]) {
    return arr[0];  // selalu 1 operasi
}

// O(n) - waktu linear
int jumlah(int arr[], int n) {
    int total = 0;
    for (int i = 0; i < n; i++)  // n iterasi
        total += arr[i];
    return total;
}

// O(n²) - waktu kuadratik
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n; i++)       // n iterasi
        for (int j = 0; j < n-i; j++) // n-i iterasi
            if (arr[j] > arr[j+1])
                swap(arr[j], arr[j+1]);
}

// O(log n) - waktu logaritmik
int binarySearch(int arr[], int n, int target) {
    int low = 0, high = n - 1;
    while (low <= high) {   // log₂(n) iterasi
        int mid = (low + high) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

### 18.4 Aturan Big-O

```
1. Drop constants: O(2n) → O(n)
2. Drop lower terms: O(n² + n) → O(n²)
3. Nested loops multiply: O(n) dalam O(n) = O(n²)
4. Sequential operations add: O(n) + O(n) = O(n), bukan O(2n)
```

### 18.5 Perbandingan Pertumbuhan

Untuk n = 1000:

| O(1) | O(log n) | O(n) | O(n log n) | O(n²) |
|------|----------|------|------------|-------|
| 1 | ~10 | 1,000 | ~10,000 | 1,000,000 |

### 18.6 Space Complexity

```cpp
// O(1) space
void printArr(int arr[], int n) {
    for (int i = 0; i < n; i++)
        cout << arr[i];
}

// O(n) space
int* duplikat(int arr[], int n) {
    int *baru = new int[n];  // alokasi n elemen baru
    for (int i = 0; i < n; i++)
        baru[i] = arr[i];
    return baru;
}
```

### 💡 Latihan Pertemuan 18
1. Analisis kompleksitas waktu setiap fungsi yang Anda buat di pertemuan sebelumnya
2. Buat eksperimen mengukur waktu eksekusi untuk input berbeda ukuran

---

## 🟢 PERTEMUAN 19: File Handling

### Tujuan Pembelajaran
- Membaca dan menulis file teks
- Menangani file biner
- Menggunakan file untuk persistensi data

### 19.1 Menulis File Teks

```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
    // Menulis file
    ofstream fileOut("data.txt");
    
    if (!fileOut) {
        cerr << "Error membuka file!" << endl;
        return 1;
    }
    
    fileOut << "Halo, ini adalah file teks." << endl;
    fileOut << "Baris kedua." << endl;
    fileOut << "Baris ketiga." << endl;
    
    fileOut.close();
    cout << "File berhasil ditulis." << endl;
    
    return 0;
}
```

### 19.2 Membaca File Teks

```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
    ifstream fileIn("data.txt");
    
    if (!fileIn) {
        cerr << "File tidak ditemukan!" << endl;
        return 1;
    }
    
    string baris;
    while (getline(fileIn, baris)) {
        cout << baris << endl;
    }
    
    fileIn.close();
    return 0;
}
```

### 19.3 File CSV - Sistem Nilai Mahasiswa

```cpp
#include <iostream>
#include <fstream>
#include <string>
#include <sstream>
using namespace std;

struct Mahasiswa {
    string nim, nama;
    double nilai;
    string grade;
};

string tentukanGrade(double nilai) {
    if (nilai >= 80) return "A";
    if (nilai >= 70) return "B";
    if (nilai >= 60) return "C";
    if (nilai >= 50) return "D";
    return "E";
}

void simpanCSV(Mahasiswa data[], int n, string filename) {
    ofstream f(filename);
    f << "NIM,Nama,Nilai,Grade" << endl;
    for (int i = 0; i < n; i++) {
        data[i].grade = tentukanGrade(data[i].nilai);
        f << data[i].nim << "," << data[i].nama << ","
          << data[i].nilai << "," << data[i].grade << endl;
    }
    f.close();
    cout << "Data disimpan ke " << filename << endl;
}

void bacaCSV(string filename) {
    ifstream f(filename);
    string baris;
    getline(f, baris);  // skip header
    
    cout << "Data dari file:" << endl;
    cout << "NIM\t\tNama\t\tNilai\tGrade" << endl;
    cout << string(50, '-') << endl;
    
    while (getline(f, baris)) {
        stringstream ss(baris);
        string nim, nama, nilai, grade;
        getline(ss, nim, ',');
        getline(ss, nama, ',');
        getline(ss, nilai, ',');
        getline(ss, grade, ',');
        cout << nim << "\t\t" << nama << "\t\t" << nilai << "\t" << grade << endl;
    }
    f.close();
}

int main() {
    Mahasiswa mhs[] = {
        {"12001", "Andi", 85.0},
        {"12002", "Budi", 72.5},
        {"12003", "Citra", 91.0},
        {"12004", "Doni", 55.0}
    };
    int n = 4;
    
    simpanCSV(mhs, n, "nilai.csv");
    bacaCSV("nilai.csv");
    
    return 0;
}
```

### 19.4 Mode Pembukaan File

```cpp
// ios::out   - menulis (hapus isi lama)
// ios::app   - append (tambah di akhir)
// ios::in    - membaca
// ios::binary - mode biner

ofstream f("log.txt", ios::app);  // tambah di akhir
```

### 💡 Latihan Pertemuan 19
1. Buat sistem buku tamu yang menyimpan data ke file
2. Buat program backup dan restore data array ke file

---

## 🟢 PERTEMUAN 20: Review & Studi Kasus

### Tujuan Pembelajaran
- Mengintegrasikan semua materi yang telah dipelajari
- Membangun aplikasi yang lebih kompleks
- Mempersiapkan diri untuk UAS

### 20.1 Studi Kasus: Sistem Manajemen Perpustakaan

```cpp
#include <iostream>
#include <string>
#include <fstream>
#include <vector>
using namespace std;

struct Buku {
    int id;
    string judul;
    string penulis;
    int tahun;
    bool tersedia;
};

class Perpustakaan {
private:
    vector<Buku> koleksi;
    int nextId;
    
    void simpan() {
        ofstream f("buku.txt");
        for (auto& b : koleksi) {
            f << b.id << "|" << b.judul << "|" << b.penulis
              << "|" << b.tahun << "|" << b.tersedia << endl;
        }
    }
    
    void muat() {
        ifstream f("buku.txt");
        if (!f) return;
        string baris;
        while (getline(f, baris)) {
            // parsing...
        }
    }
    
public:
    Perpustakaan() : nextId(1) { muat(); }
    
    void tambahBuku(string judul, string penulis, int tahun) {
        Buku b = {nextId++, judul, penulis, tahun, true};
        koleksi.push_back(b);
        simpan();
        cout << "Buku \"" << judul << "\" berhasil ditambahkan." << endl;
    }
    
    void tampilkanSemua() {
        cout << "\n===== KOLEKSI BUKU =====" << endl;
        cout << "ID\tJudul\t\t\tPenulis\t\tTahun\tStatus" << endl;
        cout << string(70, '-') << endl;
        for (auto& b : koleksi) {
            cout << b.id << "\t" << b.judul << "\t\t\t"
                 << b.penulis << "\t\t" << b.tahun << "\t"
                 << (b.tersedia ? "Tersedia" : "Dipinjam") << endl;
        }
    }
    
    void cariJudul(string keyword) {
        cout << "\nHasil pencarian \"" << keyword << "\":" << endl;
        bool found = false;
        for (auto& b : koleksi) {
            if (b.judul.find(keyword) != string::npos) {
                cout << "ID: " << b.id << " | " << b.judul << " | " << b.penulis << endl;
                found = true;
            }
        }
        if (!found) cout << "Tidak ditemukan." << endl;
    }
    
    void pinjam(int id) {
        for (auto& b : koleksi) {
            if (b.id == id) {
                if (b.tersedia) {
                    b.tersedia = false;
                    simpan();
                    cout << "Buku \"" << b.judul << "\" berhasil dipinjam." << endl;
                } else {
                    cout << "Buku sedang dipinjam." << endl;
                }
                return;
            }
        }
        cout << "Buku tidak ditemukan." << endl;
    }
    
    void kembalikan(int id) {
        for (auto& b : koleksi) {
            if (b.id == id) {
                b.tersedia = true;
                simpan();
                cout << "Buku \"" << b.judul << "\" berhasil dikembalikan." << endl;
                return;
            }
        }
        cout << "Buku tidak ditemukan." << endl;
    }
};

int main() {
    Perpustakaan lib;
    int pilihan;
    
    do {
        cout << "\n====== MENU ======" << endl;
        cout << "1. Tambah Buku" << endl;
        cout << "2. Tampilkan Semua" << endl;
        cout << "3. Cari Buku" << endl;
        cout << "4. Pinjam Buku" << endl;
        cout << "5. Kembalikan Buku" << endl;
        cout << "0. Keluar" << endl;
        cout << "Pilihan: ";
        cin >> pilihan;
        
        if (pilihan == 1) {
            string judul, penulis;
            int tahun;
            cin.ignore();
            cout << "Judul: "; getline(cin, judul);
            cout << "Penulis: "; getline(cin, penulis);
            cout << "Tahun: "; cin >> tahun;
            lib.tambahBuku(judul, penulis, tahun);
        } else if (pilihan == 2) {
            lib.tampilkanSemua();
        } else if (pilihan == 3) {
            string keyword;
            cin.ignore();
            cout << "Cari: "; getline(cin, keyword);
            lib.cariJudul(keyword);
        } else if (pilihan == 4) {
            int id; cout << "ID Buku: "; cin >> id;
            lib.pinjam(id);
        } else if (pilihan == 5) {
            int id; cout << "ID Buku: "; cin >> id;
            lib.kembalikan(id);
        }
        
    } while (pilihan != 0);
    
    cout << "Terima kasih!" << endl;
    return 0;
}
```

### 20.2 Tips Persiapan UAS

**Pastikan Anda memahami:**
1. Semua jenis loop dan penggunaannya
2. Rekursi dengan base case yang benar
3. Operasi dasar array dan string
4. Implementasi Linked List, Stack, Queue
5. Algoritma sorting dan kompleksitasnya
6. Binary Search Tree dan traversalnya
7. Analisis Big-O

**Tips coding:**
- Selalu uji kasus tepi (array kosong, n=0, dll.)
- Gunakan komentar yang jelas
- Beri nama variabel yang bermakna
- Pisahkan logika ke dalam fungsi

---

## ⚠️ PERTEMUAN 21: UAS (Ujian Akhir Semester)

**Materi yang diujikan:** Pertemuan 9 - 20 (dengan referensi ke materi sebelumnya)

**Bentuk Soal:**
- Pilihan Ganda (20 soal) – 30%
- Analisis Kode (3 soal) – 30%
- Praktik Coding (2 soal) – 40%

**Contoh soal praktik UAS:**
1. Implementasikan BST dengan operasi insert, search, delete, dan tampilkan semua data secara terurut
2. Buat program manajemen data mahasiswa menggunakan Linked List dengan fitur: tambah, hapus, cari, dan simpan ke file

---

## 📚 Referensi

1. Sedgewick, R. & Wayne, K. (2011). *Algorithms, 4th Edition*. Addison-Wesley.
2. Cormen, T. H. et al. (2009). *Introduction to Algorithms, 3rd Edition*. MIT Press.
3. Stroustrup, B. (2013). *The C++ Programming Language, 4th Edition*. Addison-Wesley.
4. Horowitz, E. & Sahni, S. (1978). *Fundamentals of Data Structures in C++*. Computer Science Press.
5. **cppreference.com** – Referensi standar C++
6. **cplusplus.com** – Tutorial dan dokumentasi C++

---

## 📊 Penilaian

| Komponen | Bobot |
|----------|-------|
| Kehadiran | 10% |
| Tugas Mingguan | 20% |
| Praktikum | 20% |
| UTS | 25% |
| UAS | 25% |

**Syarat kelulusan:** Nilai akhir ≥ 50 dan kehadiran ≥ 75%

---

*Materi ini disusun untuk mata kuliah Algoritma dan Pemrograman, Program Studi Teknik Informatika. Semua contoh kode telah diuji dengan kompiler G++ (C++11 dan lebih baru).*
