# Materi Kuliah: Algoritma dan Pemrograman dengan Rust
**Program Studi:** Teknik Informatika  
**Mata Kuliah:** Algoritma dan Pemrograman  
**Bahasa Pemrograman:** Rust  
**Jumlah Pertemuan:** 21 Pertemuan  

---

## Deskripsi Mata Kuliah

Mata kuliah ini memperkenalkan konsep dasar algoritma dan pemrograman menggunakan bahasa Rust. Mahasiswa akan mempelajari fondasi pemrograman sistem, manajemen memori, struktur data, hingga algoritma lanjutan melalui paradigma Rust yang unik dan modern.

---

## Capaian Pembelajaran

1. Memahami konsep dasar pemrograman dan algoritma.
2. Mampu menulis program Rust yang aman dan efisien.
3. Memahami konsep ownership, borrowing, dan lifetime pada Rust.
4. Mampu mengimplementasikan struktur data dan algoritma klasik.
5. Mampu menulis kode Rust yang bersih, idiomatis, dan teruji.

---

## Peta Pertemuan

| Pertemuan | Topik |
|-----------|-------|
| 1 | Pengenalan Rust & Setup Lingkungan |
| 2 | Tipe Data, Variabel, dan Operasi Dasar |
| 3 | Kontrol Alur: if, loop, while, for |
| 4 | Fungsi dan Modul |
| 5 | Ownership dan Borrowing |
| 6 | Struct dan Enum |
| 7 | Pattern Matching |
| 8 | Collections: Vec, HashMap, HashSet |
| 9 | Error Handling |
| 10 | Traits dan Generics |
| 11 | **Ujian Tengah Semester (UTS)** |
| 12 | Algoritma Pencarian (Searching) |
| 13 | Algoritma Pengurutan (Sorting) |
| 14 | Rekursi dan Divide & Conquer |
| 15 | Stack dan Queue |
| 16 | Linked List |
| 17 | Tree dan Binary Search Tree |
| 18 | Graf dan BFS/DFS |
| 19 | Dynamic Programming |
| 20 | Concurrency dengan Rust |
| 21 | **Ujian Akhir Semester (UAS) & Review** |

---

## Pertemuan 1: Pengenalan Rust & Setup Lingkungan

### Tujuan Pembelajaran
- Memahami sejarah dan keunggulan Rust.
- Menginstal Rust dan toolchain yang diperlukan.
- Menulis dan menjalankan program Rust pertama.

### Materi

#### 1.1 Mengapa Rust?
Rust adalah bahasa pemrograman sistem yang dikembangkan oleh Mozilla Research. Keunggulan utama Rust:
- **Memory Safety** tanpa Garbage Collector.
- **Zero-cost Abstractions**: abstraksi tinggi tanpa overhead performa.
- **Concurrency** yang aman dari race condition.
- Digunakan di sistem operasi, WebAssembly, embedded systems, dan lainnya.

#### 1.2 Instalasi Rust

```bash
# Install rustup (toolchain manager)
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Verifikasi instalasi
rustc --version
cargo --version
```

#### 1.3 Cargo: Build System & Package Manager

```bash
# Membuat project baru
cargo new hello_rust
cd hello_rust

# Struktur project
# hello_rust/
# ├── Cargo.toml   <- konfigurasi project
# └── src/
#     └── main.rs  <- kode utama

# Menjalankan project
cargo run

# Kompilasi saja
cargo build

# Kompilasi release (optimized)
cargo build --release
```

#### 1.4 Program Pertama

```rust
// src/main.rs
fn main() {
    println!("Halo, Dunia!");
    println!("Selamat datang di Rust!");
}
```

**Penjelasan:**
- `fn main()` adalah entry point program.
- `println!` adalah *macro* untuk mencetak ke konsol.
- Setiap statement diakhiri tanda titik koma `;`.

#### 1.5 Komentar di Rust

```rust
fn main() {
    // Ini komentar satu baris

    /* Ini komentar
       multi baris */

    /// Komentar dokumentasi (untuk fungsi/modul publik)
    println!("Rust sangat keren!");
}
```

### Latihan
1. Install Rust di komputer Anda.
2. Buat project baru bernama `perkenalan`.
3. Ubah program agar mencetak nama dan NIM Anda.

---

## Pertemuan 2: Tipe Data, Variabel, dan Operasi Dasar

### Tujuan Pembelajaran
- Memahami sistem tipe statis Rust.
- Mendeklarasikan variabel mutable dan immutable.
- Menggunakan operasi aritmatika, logika, dan string.

### Materi

#### 2.1 Variabel

```rust
fn main() {
    // Immutable (default)
    let x = 5;
    // x = 6; // ERROR! tidak bisa diubah

    // Mutable
    let mut y = 10;
    y = 20; // OK

    // Shadowing
    let z = 5;
    let z = z + 1; // z sekarang = 6
    let z = z * 2; // z sekarang = 12
    println!("z = {}", z);

    // Konstanta
    const MAX_NILAI: u32 = 100;
    println!("Nilai maksimum: {}", MAX_NILAI);
}
```

#### 2.2 Tipe Data Skalar

```rust
fn main() {
    // Integer
    let a: i8  = -128;         // signed 8-bit
    let b: u8  = 255;          // unsigned 8-bit
    let c: i32 = -1_000_000;   // signed 32-bit (default)
    let d: u64 = 1_000_000_000;// unsigned 64-bit
    let e: isize = 42;         // sesuai arsitektur OS

    // Floating Point
    let f: f32 = 3.14;
    let g: f64 = 3.141592653589793; // default

    // Boolean
    let benar: bool = true;
    let salah: bool = false;

    // Karakter (Unicode)
    let huruf: char = 'A';
    let emoji: char = '😊';

    println!("{} {} {} {} {} {} {} {} {} {}", 
             a, b, c, d, e, f, g, benar, salah, huruf);
}
```

#### 2.3 Tipe Data Komposit

```rust
fn main() {
    // Tuple: kumpulan nilai dengan tipe berbeda
    let tuple: (i32, f64, char) = (42, 3.14, 'z');
    let (angka, pi, karakter) = tuple; // destructuring
    println!("Tuple: {} {} {}", angka, pi, karakter);
    println!("Elemen kedua: {}", tuple.1);

    // Array: ukuran tetap, tipe sama
    let arr: [i32; 5] = [1, 2, 3, 4, 5];
    let zeros = [0; 10]; // 10 elemen bernilai 0
    println!("Elemen pertama: {}", arr[0]);
    println!("Panjang array: {}", arr.len());
}
```

#### 2.4 Operasi Dasar

```rust
fn main() {
    // Aritmatika
    let a = 10;
    let b = 3;
    println!("Penjumlahan : {} + {} = {}", a, b, a + b);
    println!("Pengurangan : {} - {} = {}", a, b, a - b);
    println!("Perkalian   : {} * {} = {}", a, b, a * b);
    println!("Pembagian   : {} / {} = {}", a, b, a / b); // integer division
    println!("Modulus     : {} % {} = {}", a, b, a % b);

    // Operasi logika
    let p = true;
    let q = false;
    println!("AND: {}", p && q);
    println!("OR : {}", p || q);
    println!("NOT: {}", !p);

    // Perbandingan
    println!("{} > {} : {}", a, b, a > b);
    println!("{} == {} : {}", a, b, a == b);
}
```

#### 2.5 String

```rust
fn main() {
    // &str: string slice (immutable, di stack)
    let s1: &str = "Halo";

    // String: owned string (mutable, di heap)
    let mut s2 = String::from("Halo");
    s2.push_str(", Dunia!");
    s2.push('!');

    println!("{}", s1);
    println!("{}", s2);

    // Format string
    let nama = "Budi";
    let umur = 20;
    let pesan = format!("Nama: {}, Umur: {}", nama, umur);
    println!("{}", pesan);

    // Panjang string
    println!("Panjang: {}", s2.len());
}
```

### Latihan
1. Buat program yang menghitung luas dan keliling lingkaran (input jari-jari dari variabel).
2. Buat program yang menampilkan informasi mahasiswa (nama, NIM, IPK) menggunakan tuple.

---

## Pertemuan 3: Kontrol Alur

### Tujuan Pembelajaran
- Menggunakan ekspresi `if`, `else if`, `else`.
- Menggunakan loop `loop`, `while`, dan `for`.
- Menggunakan `break` dan `continue`.

### Materi

#### 3.1 Ekspresi if

```rust
fn main() {
    let nilai = 75;

    // if-else biasa
    if nilai >= 80 {
        println!("Grade A");
    } else if nilai >= 70 {
        println!("Grade B");
    } else if nilai >= 60 {
        println!("Grade C");
    } else {
        println!("Grade D");
    }

    // if sebagai ekspresi (mengembalikan nilai)
    let grade = if nilai >= 80 { "A" } else if nilai >= 70 { "B" } else { "C" };
    println!("Grade: {}", grade);
}
```

#### 3.2 Loop

```rust
fn main() {
    // loop: berjalan selamanya sampai break
    let mut counter = 0;
    let result = loop {
        counter += 1;
        if counter == 10 {
            break counter * 2; // mengembalikan nilai
        }
    };
    println!("Hasil: {}", result); // 20

    // while
    let mut n = 1;
    while n < 10 {
        print!("{} ", n);
        n += 1;
    }
    println!();

    // for dengan range
    for i in 0..5 {
        print!("{} ", i); // 0 1 2 3 4
    }
    println!();

    for i in 0..=5 {
        print!("{} ", i); // 0 1 2 3 4 5
    }
    println!();

    // for iterasi array
    let buah = ["apel", "mangga", "jeruk"];
    for b in &buah {
        println!("Buah: {}", b);
    }

    // for dengan enumerate
    for (index, b) in buah.iter().enumerate() {
        println!("[{}] {}", index, b);
    }
}
```

#### 3.3 Break dan Continue

```rust
fn main() {
    // continue: lewati iterasi saat ini
    for i in 0..10 {
        if i % 2 == 0 {
            continue;
        }
        print!("{} ", i); // 1 3 5 7 9
    }
    println!();

    // break dengan label (untuk nested loop)
    'luar: for i in 0..5 {
        for j in 0..5 {
            if i + j == 6 {
                println!("Break di i={}, j={}", i, j);
                break 'luar;
            }
        }
    }
}
```

### Latihan
1. Buat program FizzBuzz: cetak angka 1-100, tetapi cetak "Fizz" untuk kelipatan 3, "Buzz" untuk kelipatan 5, dan "FizzBuzz" untuk keduanya.
2. Buat program untuk mencari bilangan prima dari 2 sampai N.
3. Buat tabel perkalian 10x10 menggunakan nested loop.

---

## Pertemuan 4: Fungsi dan Modul

### Tujuan Pembelajaran
- Mendefinisikan dan memanggil fungsi.
- Memahami parameter dan nilai kembalian.
- Mengorganisasi kode dengan modul.

### Materi

#### 4.1 Fungsi Dasar

```rust
fn main() {
    sapa("Budi");
    let hasil = tambah(5, 3);
    println!("5 + 3 = {}", hasil);

    let (luas, keliling) = hitung_lingkaran(7.0);
    println!("Luas: {:.2}, Keliling: {:.2}", luas, keliling);
}

// Fungsi tanpa return value
fn sapa(nama: &str) {
    println!("Halo, {}!", nama);
}

// Fungsi dengan return value
fn tambah(a: i32, b: i32) -> i32 {
    a + b // ekspresi terakhir = nilai return (tanpa titik koma)
}

// Fungsi dengan multiple return (tuple)
fn hitung_lingkaran(r: f64) -> (f64, f64) {
    let pi = std::f64::consts::PI;
    let luas = pi * r * r;
    let keliling = 2.0 * pi * r;
    (luas, keliling)
}
```

#### 4.2 Fungsi Rekursif

```rust
fn main() {
    println!("5! = {}", faktorial(5));
    println!("fib(10) = {}", fibonacci(10));
}

fn faktorial(n: u64) -> u64 {
    if n <= 1 {
        1
    } else {
        n * faktorial(n - 1)
    }
}

fn fibonacci(n: u32) -> u64 {
    match n {
        0 => 0,
        1 => 1,
        _ => fibonacci(n - 1) + fibonacci(n - 2),
    }
}
```

#### 4.3 Modul

```rust
// src/main.rs
mod matematika {
    pub fn luas_persegi(sisi: f64) -> f64 {
        sisi * sisi
    }

    pub fn luas_segitiga(alas: f64, tinggi: f64) -> f64 {
        0.5 * alas * tinggi
    }

    // Modul bersarang
    pub mod konversi {
        pub fn celsius_ke_fahrenheit(c: f64) -> f64 {
            c * 9.0 / 5.0 + 32.0
        }

        pub fn km_ke_mil(km: f64) -> f64 {
            km * 0.621371
        }
    }
}

use matematika::konversi;

fn main() {
    println!("Luas persegi 5x5 = {}", matematika::luas_persegi(5.0));
    println!("Luas segitiga = {}", matematika::luas_segitiga(6.0, 4.0));
    println!("25°C = {}°F", konversi::celsius_ke_fahrenheit(25.0));
    println!("100 km = {} mil", konversi::km_ke_mil(100.0));
}
```

#### 4.4 Closure (Fungsi Anonim)

```rust
fn main() {
    // Closure sederhana
    let kuadrat = |x: i32| x * x;
    println!("4² = {}", kuadrat(4));

    // Closure menangkap variabel dari lingkup luar
    let faktor = 3;
    let kali_faktor = |x| x * faktor;
    println!("7 × 3 = {}", kali_faktor(7));

    // Closure dengan blok multi-baris
    let hitung = |a: i32, b: i32| {
        let jumlah = a + b;
        let kali = a * b;
        (jumlah, kali)
    };
    let (j, k) = hitung(4, 5);
    println!("Jumlah: {}, Kali: {}", j, k);
}
```

### Latihan
1. Buat fungsi untuk konversi suhu (Celsius, Fahrenheit, Kelvin) antar satu sama lain.
2. Buat modul `statistika` yang berisi fungsi: `rata_rata`, `nilai_max`, `nilai_min`.
3. Buat fungsi rekursif untuk menghitung pangkat: `pangkat(basis, eksponen)`.

---

## Pertemuan 5: Ownership dan Borrowing

### Tujuan Pembelajaran
- Memahami konsep ownership sebagai inti Rust.
- Memahami rules borrowing (peminjaman referensi).
- Memahami slice sebagai referensi ke bagian data.

### Materi

#### 5.1 Ownership Rules

> **Tiga Aturan Ownership:**
> 1. Setiap nilai di Rust memiliki satu *owner*.
> 2. Hanya boleh ada satu owner pada satu waktu.
> 3. Ketika owner keluar dari scope, nilai di-*drop* (memori dibebaskan).

```rust
fn main() {
    // Ownership pada tipe heap (String)
    let s1 = String::from("halo");
    let s2 = s1; // s1 DIPINDAH (moved) ke s2
    // println!("{}", s1); // ERROR: s1 tidak valid lagi!
    println!("{}", s2); // OK

    // Clone (menyalin data heap secara eksplisit)
    let s3 = String::from("dunia");
    let s4 = s3.clone();
    println!("s3={}, s4={}", s3, s4); // keduanya valid

    // Tipe Copy (stack): tidak di-move, melainkan di-copy otomatis
    let x = 5;
    let y = x;
    println!("x={}, y={}", x, y); // keduanya valid (i32 implements Copy)
}
```

#### 5.2 Ownership dan Fungsi

```rust
fn main() {
    let s = String::from("halo");
    ambil_ownership(s); // s dipindah ke fungsi
    // println!("{}", s); // ERROR!

    let x = 5;
    buat_copy(x); // x di-copy
    println!("x masih valid: {}", x); // OK

    // Mengembalikan ownership
    let s1 = buat_string();
    println!("{}", s1);

    let s2 = String::from("halo");
    let s3 = ambil_dan_kembalikan(s2);
    println!("{}", s3);
}

fn ambil_ownership(s: String) {
    println!("{}", s);
} // s di-drop di sini

fn buat_copy(x: i32) {
    println!("{}", x);
}

fn buat_string() -> String {
    String::from("string baru")
}

fn ambil_dan_kembalikan(s: String) -> String {
    s // kembalikan ownership
}
```

#### 5.3 Referensi dan Borrowing

```rust
fn main() {
    let s1 = String::from("halo");

    // Immutable reference: pinjam tanpa ambil ownership
    let panjang = hitung_panjang(&s1);
    println!("Panjang '{}' = {}", s1, panjang); // s1 masih valid!

    // Mutable reference
    let mut s2 = String::from("halo");
    ubah_string(&mut s2);
    println!("{}", s2);

    // ATURAN: hanya SATU mutable reference sekaligus
    let r1 = &mut s2;
    // let r2 = &mut s2; // ERROR!
    println!("{}", r1);
}

fn hitung_panjang(s: &String) -> usize {
    s.len()
} // s tidak di-drop (hanya dipinjam)

fn ubah_string(s: &mut String) {
    s.push_str(", dunia!");
}
```

#### 5.4 Slice

```rust
fn main() {
    let s = String::from("halo dunia");

    // String slice
    let halo = &s[0..4];   // "halo"
    let dunia = &s[5..10]; // "dunia"
    println!("{} {}", halo, dunia);

    // Fungsi yang bekerja dengan slice
    let kata_pertama = ambil_kata_pertama(&s);
    println!("Kata pertama: {}", kata_pertama);

    // Array slice
    let arr = [1, 2, 3, 4, 5];
    let slice = &arr[1..3];
    println!("{:?}", slice); // [2, 3]
}

fn ambil_kata_pertama(s: &str) -> &str {
    let bytes = s.as_bytes();
    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }
    &s[..]
}
```

### Latihan
1. Tulis fungsi yang menerima `&String` dan mengembalikan jumlah kata dalam string.
2. Demonstrasikan perbedaan antara `move`, `copy`, dan `clone`.
3. Buat fungsi yang menerima `&mut Vec<i32>` dan menambahkan elemen ke dalamnya.

---

## Pertemuan 6: Struct dan Enum

### Tujuan Pembelajaran
- Mendefinisikan dan menggunakan struct.
- Mengimplementasikan metode dengan `impl`.
- Mendefinisikan dan menggunakan enum.

### Materi

#### 6.1 Struct

```rust
// Struct klasik
#[derive(Debug)]
struct Mahasiswa {
    nama: String,
    nim: String,
    ipk: f64,
    semester: u8,
}

// Tuple struct
struct Koordinat(f64, f64);

// Unit struct
struct Penanda;

fn main() {
    let mhs = Mahasiswa {
        nama: String::from("Budi Santoso"),
        nim: String::from("2023001"),
        ipk: 3.75,
        semester: 3,
    };

    println!("Nama: {}", mhs.nama);
    println!("IPK : {}", mhs.ipk);
    println!("{:#?}", mhs); // pretty debug print

    // Update syntax
    let mhs2 = Mahasiswa {
        nama: String::from("Ani"),
        nim: String::from("2023002"),
        ..mhs // sisanya salin dari mhs
    };
    println!("{:?}", mhs2);

    let titik = Koordinat(3.0, 4.0);
    println!("Koordinat: ({}, {})", titik.0, titik.1);
}
```

#### 6.2 Impl (Metode pada Struct)

```rust
#[derive(Debug)]
struct Lingkaran {
    jari_jari: f64,
}

impl Lingkaran {
    // Associated function (seperti static method)
    fn baru(r: f64) -> Lingkaran {
        Lingkaran { jari_jari: r }
    }

    // Method (&self = immutable borrow)
    fn luas(&self) -> f64 {
        std::f64::consts::PI * self.jari_jari * self.jari_jari
    }

    fn keliling(&self) -> f64 {
        2.0 * std::f64::consts::PI * self.jari_jari
    }

    // Method mutable (&mut self)
    fn perbesar(&mut self, faktor: f64) {
        self.jari_jari *= faktor;
    }
}

fn main() {
    let mut l = Lingkaran::baru(5.0);
    println!("Luas    : {:.2}", l.luas());
    println!("Keliling: {:.2}", l.keliling());

    l.perbesar(2.0);
    println!("Setelah diperbesar 2x, luas: {:.2}", l.luas());
}
```

#### 6.3 Enum

```rust
#[derive(Debug)]
enum Arah {
    Utara,
    Selatan,
    Timur,
    Barat,
}

// Enum dengan data
#[derive(Debug)]
enum Bentuk {
    Lingkaran(f64),
    Persegi(f64),
    Persegipanjang(f64, f64),
}

impl Bentuk {
    fn luas(&self) -> f64 {
        match self {
            Bentuk::Lingkaran(r)       => std::f64::consts::PI * r * r,
            Bentuk::Persegi(s)         => s * s,
            Bentuk::Persegipanjang(p, l) => p * l,
        }
    }
}

fn main() {
    let arah = Arah::Utara;
    println!("{:?}", arah);

    let b1 = Bentuk::Lingkaran(5.0);
    let b2 = Bentuk::Persegi(4.0);
    let b3 = Bentuk::Persegipanjang(6.0, 3.0);

    println!("Luas lingkaran    : {:.2}", b1.luas());
    println!("Luas persegi      : {:.2}", b2.luas());
    println!("Luas persegipanjang: {:.2}", b3.luas());
}
```

#### 6.4 Option\<T\> dan Result\<T, E\>

```rust
fn main() {
    // Option: nilai mungkin ada atau tidak
    let some_number: Option<i32> = Some(5);
    let no_number: Option<i32> = None;

    if let Some(n) = some_number {
        println!("Angkanya: {}", n);
    }

    // unwrap_or untuk nilai default
    println!("{}", no_number.unwrap_or(0));

    // Fungsi yang bisa gagal
    let hasil = bagi(10, 2);
    match hasil {
        Ok(n)  => println!("Hasil: {}", n),
        Err(e) => println!("Error: {}", e),
    }

    let gagal = bagi(10, 0);
    println!("{:?}", gagal);
}

fn bagi(a: i32, b: i32) -> Result<i32, String> {
    if b == 0 {
        Err(String::from("Pembagian oleh nol!"))
    } else {
        Ok(a / b)
    }
}
```

### Latihan
1. Buat struct `BankAccount` dengan metode: `setor`, `tarik`, `cek_saldo`.
2. Buat enum `StatusMahasiswa` (Aktif, Cuti, Lulus, DO) dan gunakan dalam struct `Mahasiswa`.
3. Implementasikan fungsi yang mengembalikan `Option<&Mahasiswa>` untuk mencari mahasiswa berdasarkan NIM.

---

## Pertemuan 7: Pattern Matching

### Tujuan Pembelajaran
- Memahami ekspresi `match` secara mendalam.
- Menggunakan `if let` dan `while let`.
- Menggunakan destructuring pada berbagai tipe data.

### Materi

#### 7.1 Match Komprehensif

```rust
fn main() {
    // Match dengan nilai tunggal
    let angka = 3;
    match angka {
        1       => println!("Satu"),
        2 | 3   => println!("Dua atau Tiga"),
        4..=9   => println!("Antara 4-9"),
        _       => println!("Lainnya"),
    }

    // Match dengan binding (@)
    let x = 5;
    match x {
        n @ 1..=10 => println!("{} ada di antara 1-10", n),
        n @ 11..=20 => println!("{} ada di antara 11-20", n),
        _ => println!("Di luar range"),
    }

    // Match dengan guard
    let pair = (2, -2);
    match pair {
        (x, y) if x == y       => println!("Sama"),
        (x, y) if x + y == 0   => println!("Berlawanan"),
        (x, _)                 => println!("x adalah {}", x),
    }
}
```

#### 7.2 Destructuring

```rust
struct Titik { x: i32, y: i32 }

enum Pesan {
    Keluar,
    Pindah { x: i32, y: i32 },
    Tulis(String),
    WarnaBaru(u8, u8, u8),
}

fn main() {
    // Destructuring struct
    let t = Titik { x: 10, y: 20 };
    let Titik { x, y } = t;
    println!("x={}, y={}", x, y);

    // Destructuring enum
    let pesan = Pesan::WarnaBaru(255, 128, 0);
    match pesan {
        Pesan::Keluar => println!("Keluar"),
        Pesan::Pindah { x, y } => println!("Pindah ke ({},{})", x, y),
        Pesan::Tulis(teks) => println!("Tulis: {}", teks),
        Pesan::WarnaBaru(r, g, b) => println!("Warna: ({},{},{})", r, g, b),
    }

    // Destructuring tuple bersarang
    let ((a, b), c) = ((1, 2), 3);
    println!("{} {} {}", a, b, c);
}
```

#### 7.3 if let dan while let

```rust
fn main() {
    let koin = Some(25u32);

    // if let: lebih singkat dari match untuk satu pola
    if let Some(nilai) = koin {
        println!("Koin bernilai: {}", nilai);
    } else {
        println!("Tidak ada koin");
    }

    // while let
    let mut stack = Vec::new();
    stack.push(1);
    stack.push(2);
    stack.push(3);

    while let Some(top) = stack.pop() {
        println!("Pop: {}", top);
    }
}
```

### Latihan
1. Buat program kalkulator sederhana menggunakan enum `Operasi` dan `match`.
2. Buat fungsi yang menerima `Option<i32>` dan menggandakan nilainya jika ada (kembalikan `Option<i32>`).
3. Implementasikan parser sederhana: parsing string "tambah 5 dan 3" menggunakan pattern matching.

---

## Pertemuan 8: Collections

### Tujuan Pembelajaran
- Menggunakan Vec\<T\> sebagai array dinamis.
- Menggunakan HashMap dan HashSet.
- Memahami iterator dan metode fungsional.

### Materi

#### 8.1 Vec\<T\>

```rust
fn main() {
    // Membuat Vec
    let mut v: Vec<i32> = Vec::new();
    let v2 = vec![1, 2, 3, 4, 5]; // macro

    // Menambah elemen
    v.push(10);
    v.push(20);
    v.push(30);

    // Mengakses elemen
    println!("{}", v[0]);
    println!("{:?}", v.get(1)); // Some(20) - aman

    // Iterasi
    for val in &v {
        print!("{} ", val);
    }
    println!();

    // Operasi umum
    println!("Panjang: {}", v.len());
    v.pop();    // hapus terakhir
    v.insert(1, 15); // sisipkan di indeks 1
    v.remove(0);     // hapus indeks 0

    // Slicing
    let slice = &v2[1..3];
    println!("{:?}", slice);

    // Sort
    let mut angka = vec![5, 2, 8, 1, 9, 3];
    angka.sort();
    println!("{:?}", angka);
    angka.sort_by(|a, b| b.cmp(a)); // descending
    println!("{:?}", angka);
}
```

#### 8.2 HashMap

```rust
use std::collections::HashMap;

fn main() {
    let mut nilai: HashMap<String, f64> = HashMap::new();

    // Insert
    nilai.insert(String::from("Matematika"), 85.0);
    nilai.insert(String::from("Fisika"), 78.5);
    nilai.insert(String::from("Kimia"), 90.0);

    // Akses
    if let Some(n) = nilai.get("Matematika") {
        println!("Nilai Matematika: {}", n);
    }

    // Entry API (insert jika belum ada)
    nilai.entry(String::from("Biologi")).or_insert(75.0);

    // Iterasi
    for (mata_kuliah, n) in &nilai {
        println!("{}: {}", mata_kuliah, n);
    }

    // Frekuensi kata
    let teks = "apel mangga apel jeruk mangga apel";
    let mut frekuensi: HashMap<&str, u32> = HashMap::new();

    for kata in teks.split_whitespace() {
        let count = frekuensi.entry(kata).or_insert(0);
        *count += 1;
    }
    println!("{:?}", frekuensi);
}
```

#### 8.3 HashSet

```rust
use std::collections::HashSet;

fn main() {
    let mut set1: HashSet<i32> = HashSet::new();
    set1.insert(1);
    set1.insert(2);
    set1.insert(3);
    set1.insert(2); // duplikat diabaikan

    let set2: HashSet<i32> = vec![2, 3, 4, 5].into_iter().collect();

    // Operasi himpunan
    let irisan: HashSet<_> = set1.intersection(&set2).collect();
    let gabungan: HashSet<_> = set1.union(&set2).collect();
    let selisih: HashSet<_> = set1.difference(&set2).collect();

    println!("Irisan  : {:?}", irisan);
    println!("Gabungan: {:?}", gabungan);
    println!("Selisih : {:?}", selisih);

    println!("Apakah 2 ada? {}", set1.contains(&2));
}
```

#### 8.4 Iterator dan Metode Fungsional

```rust
fn main() {
    let v = vec![1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

    // map: transformasi setiap elemen
    let kuadrat: Vec<i32> = v.iter().map(|x| x * x).collect();
    println!("{:?}", kuadrat);

    // filter: saring elemen
    let genap: Vec<&i32> = v.iter().filter(|&&x| x % 2 == 0).collect();
    println!("{:?}", genap);

    // map + filter + collect
    let hasil: Vec<i32> = v.iter()
        .filter(|&&x| x % 2 == 0)
        .map(|&x| x * x)
        .collect();
    println!("{:?}", hasil);

    // fold/reduce: akumulasi
    let jumlah: i32 = v.iter().sum();
    let kali: i32 = v.iter().product();
    println!("Jumlah: {}, Kali: {}", jumlah, kali);

    // any dan all
    println!("Ada > 9? {}", v.iter().any(|&x| x > 9));
    println!("Semua > 0? {}", v.iter().all(|&x| x > 0));

    // find dan position
    let found = v.iter().find(|&&x| x > 5);
    println!("Pertama > 5: {:?}", found);
}
```

### Latihan
1. Buat program manajemen daftar tugas (todo list) menggunakan `Vec<String>`.
2. Buat program yang menghitung frekuensi kemunculan setiap huruf dalam sebuah kalimat.
3. Gunakan iterator untuk menghitung rata-rata, nilai max, dan min dari sebuah Vec.

---

## Pertemuan 9: Error Handling

### Tujuan Pembelajaran
- Memahami perbedaan `panic!` dan `Result`.
- Menggunakan operator `?` untuk propagasi error.
- Membuat tipe error kustom.

### Materi

#### 9.1 Panic

```rust
fn main() {
    // panic! untuk error yang tidak dapat dipulihkan
    // panic!("Sesuatu yang buruk terjadi!");

    let v = vec![1, 2, 3];
    // v[99]; // panic: index out of bounds

    // Menggunakan get() untuk akses aman
    match v.get(99) {
        Some(val) => println!("Nilai: {}", val),
        None      => println!("Indeks di luar batas"),
    }
}
```

#### 9.2 Result\<T, E\>

```rust
use std::fs;
use std::num::ParseIntError;

fn main() {
    // Membaca file (bisa gagal)
    match fs::read_to_string("file.txt") {
        Ok(isi)  => println!("Isi: {}", isi),
        Err(e)   => println!("Error: {}", e),
    }

    // Parse string ke angka
    let angka: Result<i32, _> = "42".parse();
    println!("{:?}", angka); // Ok(42)

    let bukan_angka: Result<i32, ParseIntError> = "abc".parse();
    println!("{:?}", bukan_angka); // Err(...)

    // Rantai operasi Result
    let hasil = parse_dan_tambah("10", "20");
    println!("{:?}", hasil);
}

fn parse_dan_tambah(a: &str, b: &str) -> Result<i32, ParseIntError> {
    let x = a.parse::<i32>()?; // ? propagasi error jika gagal
    let y = b.parse::<i32>()?;
    Ok(x + y)
}
```

#### 9.3 Operator ? dan Error Kustom

```rust
use std::fmt;

// Error kustom
#[derive(Debug)]
enum AppError {
    ParseError(String),
    DivisionByZero,
    NegativeNumber(i32),
}

impl fmt::Display for AppError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        match self {
            AppError::ParseError(s)     => write!(f, "Parse error: {}", s),
            AppError::DivisionByZero    => write!(f, "Pembagian oleh nol"),
            AppError::NegativeNumber(n) => write!(f, "Angka negatif: {}", n),
        }
    }
}

fn hitung_akar(s: &str) -> Result<f64, AppError> {
    let n: i32 = s.parse()
        .map_err(|_| AppError::ParseError(s.to_string()))?;

    if n < 0 {
        return Err(AppError::NegativeNumber(n));
    }

    Ok((n as f64).sqrt())
}

fn main() {
    let kasus = ["16", "-4", "abc"];
    for k in &kasus {
        match hitung_akar(k) {
            Ok(hasil) => println!("√{} = {:.2}", k, hasil),
            Err(e)    => println!("Error untuk '{}': {}", k, e),
        }
    }
}
```

### Latihan
1. Buat fungsi yang membaca file CSV sederhana dan mem-parse datanya (gunakan Result dan `?`).
2. Buat custom error type untuk aplikasi manajemen inventori (stok tidak cukup, item tidak ditemukan, dll).

---

## Pertemuan 10: Traits dan Generics

### Tujuan Pembelajaran
- Mendefinisikan dan mengimplementasikan trait.
- Menulis fungsi dan struct generik.
- Memahami trait bounds.

### Materi

#### 10.1 Traits

```rust
// Mendefinisikan trait
trait HewanPeliharaan {
    fn nama(&self) -> &str;
    fn suara(&self) -> &str;

    // Method default
    fn perkenalan(&self) {
        println!("Saya adalah {} dan saya bersuara: {}!", self.nama(), self.suara());
    }
}

struct Kucing { nama: String }
struct Anjing { nama: String }

impl HewanPeliharaan for Kucing {
    fn nama(&self) -> &str { &self.nama }
    fn suara(&self) -> &str { "Meong" }
}

impl HewanPeliharaan for Anjing {
    fn nama(&self) -> &str { &self.nama }
    fn suara(&self) -> &str { "Guk" }
}

fn main() {
    let kucing = Kucing { nama: String::from("Mochi") };
    let anjing = Anjing { nama: String::from("Rex") };

    kucing.perkenalan();
    anjing.perkenalan();

    // Trait sebagai parameter
    bicaralah(&kucing);
    bicaralah(&anjing);
}

fn bicaralah(hewan: &impl HewanPeliharaan) {
    println!("{} berkata: {}", hewan.nama(), hewan.suara());
}
```

#### 10.2 Generics

```rust
// Fungsi generik
fn terbesar<T: PartialOrd>(list: &[T]) -> &T {
    let mut largest = &list[0];
    for item in list {
        if item > largest {
            largest = item;
        }
    }
    largest
}

// Struct generik
struct Pasangan<T> {
    pertama: T,
    kedua: T,
}

impl<T: std::fmt::Display + PartialOrd> Pasangan<T> {
    fn baru(pertama: T, kedua: T) -> Self {
        Pasangan { pertama, kedua }
    }

    fn cetak_terbesar(&self) {
        if self.pertama >= self.kedua {
            println!("Terbesar: {}", self.pertama);
        } else {
            println!("Terbesar: {}", self.kedua);
        }
    }
}

fn main() {
    let angka = vec![34, 50, 25, 100, 65];
    println!("Terbesar: {}", terbesar(&angka));

    let huruf = vec!['y', 'm', 'a', 'q'];
    println!("Terbesar: {}", terbesar(&huruf));

    let p = Pasangan::baru(5, 10);
    p.cetak_terbesar();
}
```

#### 10.3 Trait Bounds dan where

```rust
use std::fmt::{Display, Debug};

// Trait bounds dengan where
fn cetak_info<T>(item: T) where T: Display + Debug {
    println!("Display: {}", item);
    println!("Debug  : {:?}", item);
}

// Implementasi bersyarat
struct Wrapper<T>(Vec<T>);

impl<T: Display> Display for Wrapper<T> {
    fn fmt(&self, f: &mut std::fmt::Formatter) -> std::fmt::Result {
        let items: Vec<String> = self.0.iter()
            .map(|x| x.to_string())
            .collect();
        write!(f, "[{}]", items.join(", "))
    }
}

fn main() {
    cetak_info(42);
    cetak_info("halo");

    let w = Wrapper(vec![1, 2, 3, 4, 5]);
    println!("{}", w);
}
```

### Latihan
1. Buat trait `Bentuk2D` dengan metode `luas()` dan `keliling()`, implementasikan untuk lingkaran, persegi, dan segitiga.
2. Buat struct generik `Stack<T>` dengan metode `push`, `pop`, `peek`, `is_empty`.
3. Implementasikan trait `Iterator` untuk struct kustom.

---

## Pertemuan 11: Ujian Tengah Semester (UTS)

**Cakupan Materi:** Pertemuan 1 – 10

**Format Ujian:**
- Pilihan Ganda (30%)
- Soal Analisis Kode (30%)
- Coding (40%)

**Contoh Soal Coding UTS:**
1. Buat struct `Perpustakaan` dengan koleksi buku. Implementasikan metode untuk menambah, menghapus, dan mencari buku berdasarkan judul atau pengarang.
2. Buat program konversi bilangan dari desimal ke biner, oktal, dan heksadesimal menggunakan fungsi generik.
3. Implementasikan algoritma bubble sort pada `Vec<T>` menggunakan generics dan trait bounds.

---

## Pertemuan 12: Algoritma Pencarian (Searching)

### Tujuan Pembelajaran
- Mengimplementasikan Linear Search dan Binary Search.
- Memahami kompleksitas waktu O(n) dan O(log n).
- Mengaplikasikan algoritma pencarian pada berbagai tipe data.

### Materi

#### 12.1 Linear Search

```rust
fn linear_search<T: PartialEq>(arr: &[T], target: &T) -> Option<usize> {
    for (index, item) in arr.iter().enumerate() {
        if item == target {
            return Some(index);
        }
    }
    None
}

fn main() {
    let data = vec![64, 25, 12, 22, 11];
    let target = 22;

    match linear_search(&data, &target) {
        Some(idx) => println!("Ditemukan di indeks: {}", idx),
        None      => println!("Tidak ditemukan"),
    }

    // Pada Vec<String>
    let nama = vec!["Budi", "Ani", "Citra", "Deni"];
    println!("{:?}", linear_search(&nama, &"Citra"));

    // Kompleksitas: O(n) - worst case
    println!("Linear Search: O(n)");
}
```

#### 12.2 Binary Search

```rust
fn binary_search<T: Ord>(arr: &[T], target: &T) -> Option<usize> {
    let mut low = 0;
    let mut high = arr.len();

    while low < high {
        let mid = low + (high - low) / 2;
        match arr[mid].cmp(target) {
            std::cmp::Ordering::Equal   => return Some(mid),
            std::cmp::Ordering::Less    => low = mid + 1,
            std::cmp::Ordering::Greater => high = mid,
        }
    }
    None
}

fn binary_search_recursive<T: Ord>(arr: &[T], target: &T, low: usize, high: usize) -> Option<usize> {
    if low >= high {
        return None;
    }
    let mid = low + (high - low) / 2;
    match arr[mid].cmp(target) {
        std::cmp::Ordering::Equal   => Some(mid),
        std::cmp::Ordering::Less    => binary_search_recursive(arr, target, mid + 1, high),
        std::cmp::Ordering::Greater => binary_search_recursive(arr, target, low, mid),
    }
}

fn main() {
    let data = vec![11, 12, 22, 25, 64, 80, 95]; // HARUS TERURUT

    println!("{:?}", binary_search(&data, &25));
    println!("{:?}", binary_search(&data, &50));

    // Recursive
    let n = data.len();
    println!("{:?}", binary_search_recursive(&data, &22, 0, n));

    // Bawaan Rust
    println!("{:?}", data.binary_search(&64));

    // Kompleksitas: O(log n)
    println!("Binary Search: O(log n)");
}
```

#### 12.3 Perbandingan Performa

```rust
use std::time::Instant;

fn main() {
    let n = 1_000_000;
    let data: Vec<i32> = (0..n).collect();
    let target = n - 1; // worst case untuk linear

    // Linear search
    let start = Instant::now();
    let _ = data.iter().position(|&x| x == target);
    println!("Linear Search: {:?}", start.elapsed());

    // Binary search
    let start = Instant::now();
    let _ = data.binary_search(&target);
    println!("Binary Search: {:?}", start.elapsed());
}
```

### Latihan
1. Implementasikan fungsi `cari_semua` yang mengembalikan semua indeks di mana target ditemukan.
2. Implementasikan Binary Search untuk mencari string dalam slice yang terurut.
3. Buat benchmark perbandingan Linear vs Binary Search untuk berbagai ukuran data.

---

## Pertemuan 13: Algoritma Pengurutan (Sorting)

### Tujuan Pembelajaran
- Mengimplementasikan Bubble, Selection, dan Insertion Sort.
- Mengimplementasikan Merge Sort dan Quick Sort.
- Memahami dan membandingkan kompleksitas algoritma pengurutan.

### Materi

#### 13.1 Bubble Sort – O(n²)

```rust
fn bubble_sort(arr: &mut Vec<i32>) {
    let n = arr.len();
    for i in 0..n {
        let mut swapped = false;
        for j in 0..n - 1 - i {
            if arr[j] > arr[j + 1] {
                arr.swap(j, j + 1);
                swapped = true;
            }
        }
        if !swapped { break; } // sudah terurut
    }
}

fn main() {
    let mut data = vec![64, 34, 25, 12, 22, 11, 90];
    println!("Sebelum: {:?}", data);
    bubble_sort(&mut data);
    println!("Sesudah: {:?}", data);
}
```

#### 13.2 Selection Sort – O(n²)

```rust
fn selection_sort(arr: &mut Vec<i32>) {
    let n = arr.len();
    for i in 0..n {
        let mut min_idx = i;
        for j in (i + 1)..n {
            if arr[j] < arr[min_idx] {
                min_idx = j;
            }
        }
        arr.swap(i, min_idx);
    }
}
```

#### 13.3 Insertion Sort – O(n²) / O(n) terbaik

```rust
fn insertion_sort(arr: &mut Vec<i32>) {
    let n = arr.len();
    for i in 1..n {
        let kunci = arr[i];
        let mut j = i;
        while j > 0 && arr[j - 1] > kunci {
            arr[j] = arr[j - 1];
            j -= 1;
        }
        arr[j] = kunci;
    }
}
```

#### 13.4 Merge Sort – O(n log n)

```rust
fn merge_sort(arr: &[i32]) -> Vec<i32> {
    if arr.len() <= 1 {
        return arr.to_vec();
    }
    let mid = arr.len() / 2;
    let kiri = merge_sort(&arr[..mid]);
    let kanan = merge_sort(&arr[mid..]);
    merge(&kiri, &kanan)
}

fn merge(kiri: &[i32], kanan: &[i32]) -> Vec<i32> {
    let mut hasil = Vec::with_capacity(kiri.len() + kanan.len());
    let (mut i, mut j) = (0, 0);

    while i < kiri.len() && j < kanan.len() {
        if kiri[i] <= kanan[j] {
            hasil.push(kiri[i]);
            i += 1;
        } else {
            hasil.push(kanan[j]);
            j += 1;
        }
    }
    hasil.extend_from_slice(&kiri[i..]);
    hasil.extend_from_slice(&kanan[j..]);
    hasil
}
```

#### 13.5 Quick Sort – O(n log n) rata-rata

```rust
fn quick_sort(arr: &mut Vec<i32>, low: usize, high: usize) {
    if low < high {
        let pivot_idx = partisi(arr, low, high);
        if pivot_idx > 0 {
            quick_sort(arr, low, pivot_idx - 1);
        }
        quick_sort(arr, pivot_idx + 1, high);
    }
}

fn partisi(arr: &mut Vec<i32>, low: usize, high: usize) -> usize {
    let pivot = arr[high];
    let mut i = low;

    for j in low..high {
        if arr[j] <= pivot {
            arr.swap(i, j);
            i += 1;
        }
    }
    arr.swap(i, high);
    i
}

fn main() {
    let mut data = vec![64, 34, 25, 12, 22, 11, 90];
    let n = data.len();
    quick_sort(&mut data, 0, n - 1);
    println!("{:?}", data);

    // Tabel kompleksitas
    println!("\n=== Kompleksitas Algoritma Sorting ===");
    println!("{:<20} {:<15} {:<15} {:<15}", "Algoritma", "Best", "Average", "Worst");
    println!("{:<20} {:<15} {:<15} {:<15}", "Bubble Sort",    "O(n)",      "O(n²)", "O(n²)");
    println!("{:<20} {:<15} {:<15} {:<15}", "Selection Sort", "O(n²)",     "O(n²)", "O(n²)");
    println!("{:<20} {:<15} {:<15} {:<15}", "Insertion Sort", "O(n)",      "O(n²)", "O(n²)");
    println!("{:<20} {:<15} {:<15} {:<15}", "Merge Sort",     "O(n log n)","O(n log n)","O(n log n)");
    println!("{:<20} {:<15} {:<15} {:<15}", "Quick Sort",     "O(n log n)","O(n log n)","O(n²)");
}
```

### Latihan
1. Modifikasi semua algoritma sorting agar bisa mengurutkan secara descending.
2. Buat sorting generik `fn sort<T: Ord>(arr: &mut Vec<T>)` menggunakan merge sort.
3. Bandingkan performa semua algoritma untuk data besar (n=10.000) menggunakan `Instant`.

---

## Pertemuan 14: Rekursi dan Divide & Conquer

### Tujuan Pembelajaran
- Memahami konsep rekursi dan stack call.
- Mengimplementasikan algoritma Divide & Conquer.
- Mengoptimalkan rekursi dengan memoization.

### Materi

#### 14.1 Konsep Rekursi

```rust
fn main() {
    // Faktorial rekursif vs iteratif
    println!("10! = {}", faktorial_rekursif(10));
    println!("10! = {}", faktorial_iteratif(10));

    // Fibonacci dengan memoization
    let mut memo = vec![-1i64; 50];
    println!("fib(40) = {}", fib_memo(40, &mut memo));
}

fn faktorial_rekursif(n: u64) -> u64 {
    if n <= 1 { 1 } else { n * faktorial_rekursif(n - 1) }
}

fn faktorial_iteratif(n: u64) -> u64 {
    (1..=n).product()
}

fn fib_memo(n: usize, memo: &mut Vec<i64>) -> i64 {
    if n <= 1 { return n as i64; }
    if memo[n] != -1 { return memo[n]; }
    memo[n] = fib_memo(n - 1, memo) + fib_memo(n - 2, memo);
    memo[n]
}
```

#### 14.2 Divide and Conquer: Binary Exponentiation

```rust
// Pangkat cepat: O(log n) vs O(n) biasa
fn pangkat_cepat(basis: i64, exp: u32) -> i64 {
    if exp == 0 { return 1; }
    if exp % 2 == 0 {
        let setengah = pangkat_cepat(basis, exp / 2);
        setengah * setengah
    } else {
        basis * pangkat_cepat(basis, exp - 1)
    }
}

fn main() {
    println!("2^10 = {}", pangkat_cepat(2, 10));
    println!("3^5  = {}", pangkat_cepat(3, 5));
}
```

#### 14.3 Tower of Hanoi

```rust
fn hanoi(n: u32, dari: &str, ke: &str, via: &str) {
    if n == 1 {
        println!("Pindah disk 1 dari {} ke {}", dari, ke);
        return;
    }
    hanoi(n - 1, dari, via, ke);
    println!("Pindah disk {} dari {} ke {}", n, dari, ke);
    hanoi(n - 1, via, ke, dari);
}

fn main() {
    println!("=== Tower of Hanoi (3 disk) ===");
    hanoi(3, "A", "C", "B");
    // Jumlah gerakan = 2^n - 1
    println!("\nJumlah gerakan untuk n disk: 2^n - 1");
}
```

#### 14.4 Closest Pair of Points

```rust
#[derive(Clone, Copy, Debug)]
struct Titik {
    x: f64,
    y: f64,
}

fn jarak(a: &Titik, b: &Titik) -> f64 {
    ((a.x - b.x).powi(2) + (a.y - b.y).powi(2)).sqrt()
}

fn closest_pair_brute(titik: &[Titik]) -> f64 {
    let n = titik.len();
    let mut min_jarak = f64::INFINITY;
    for i in 0..n {
        for j in (i + 1)..n {
            let d = jarak(&titik[i], &titik[j]);
            if d < min_jarak { min_jarak = d; }
        }
    }
    min_jarak
}

fn main() {
    let titik = vec![
        Titik { x: 0.0, y: 0.0 },
        Titik { x: 3.0, y: 4.0 },
        Titik { x: 1.0, y: 1.0 },
        Titik { x: 5.0, y: 2.0 },
    ];
    println!("Jarak terdekat: {:.4}", closest_pair_brute(&titik));
}
```

### Latihan
1. Implementasikan pencarian biner menggunakan rekursi.
2. Buat fungsi rekursif untuk mencetak semua permutasi dari sebuah string.
3. Implementasikan algoritma Karatsuba untuk perkalian bilangan besar.

---

## Pertemuan 15: Stack dan Queue

### Tujuan Pembelajaran
- Memahami konsep LIFO (Stack) dan FIFO (Queue).
- Mengimplementasikan Stack dan Queue dari awal.
- Menggunakan Stack/Queue untuk memecahkan masalah.

### Materi

#### 15.1 Stack dengan Vec

```rust
struct Stack<T> {
    data: Vec<T>,
}

impl<T> Stack<T> {
    fn baru() -> Self {
        Stack { data: Vec::new() }
    }

    fn push(&mut self, item: T) {
        self.data.push(item);
    }

    fn pop(&mut self) -> Option<T> {
        self.data.pop()
    }

    fn peek(&self) -> Option<&T> {
        self.data.last()
    }

    fn kosong(&self) -> bool {
        self.data.is_empty()
    }

    fn ukuran(&self) -> usize {
        self.data.len()
    }
}

fn main() {
    let mut stack: Stack<i32> = Stack::baru();
    stack.push(1);
    stack.push(2);
    stack.push(3);

    println!("Peek: {:?}", stack.peek()); // Some(3)
    println!("Pop : {:?}", stack.pop());  // Some(3)
    println!("Ukuran: {}", stack.ukuran());
}
```

#### 15.2 Aplikasi Stack: Cek Kurung Seimbang

```rust
fn kurung_seimbang(s: &str) -> bool {
    let mut stack = Vec::new();
    for c in s.chars() {
        match c {
            '(' | '[' | '{' => stack.push(c),
            ')' => { if stack.pop() != Some('(') { return false; } }
            ']' => { if stack.pop() != Some('[') { return false; } }
            '}' => { if stack.pop() != Some('{') { return false; } }
            _ => {}
        }
    }
    stack.is_empty()
}

fn main() {
    let kasus = ["(())", "{[]}", "([)]", "((()"];
    for k in &kasus {
        println!("\"{}\" seimbang: {}", k, kurung_seimbang(k));
    }
}
```

#### 15.3 Queue dengan VecDeque

```rust
use std::collections::VecDeque;

struct Queue<T> {
    data: VecDeque<T>,
}

impl<T> Queue<T> {
    fn baru() -> Self {
        Queue { data: VecDeque::new() }
    }

    fn enqueue(&mut self, item: T) {
        self.data.push_back(item);
    }

    fn dequeue(&mut self) -> Option<T> {
        self.data.pop_front()
    }

    fn front(&self) -> Option<&T> {
        self.data.front()
    }

    fn kosong(&self) -> bool {
        self.data.is_empty()
    }
}

fn main() {
    let mut q: Queue<&str> = Queue::baru();
    q.enqueue("Antrian 1");
    q.enqueue("Antrian 2");
    q.enqueue("Antrian 3");

    while !q.kosong() {
        println!("Dilayani: {:?}", q.dequeue());
    }
}
```

#### 15.4 Aplikasi: Evaluasi Ekspresi Postfix

```rust
fn evaluasi_postfix(ekspresi: &str) -> f64 {
    let mut stack: Vec<f64> = Vec::new();

    for token in ekspresi.split_whitespace() {
        match token {
            "+" | "-" | "*" | "/" => {
                let b = stack.pop().unwrap();
                let a = stack.pop().unwrap();
                let hasil = match token {
                    "+" => a + b,
                    "-" => a - b,
                    "*" => a * b,
                    "/" => a / b,
                    _   => unreachable!(),
                };
                stack.push(hasil);
            }
            angka => stack.push(angka.parse().unwrap()),
        }
    }
    stack.pop().unwrap()
}

fn main() {
    // "3 4 + 2 *" = (3+4)*2 = 14
    println!("{}", evaluasi_postfix("3 4 + 2 *")); // 14
    // "5 1 2 + 4 * + 3 -" = 5 + (1+2)*4 - 3 = 14
    println!("{}", evaluasi_postfix("5 1 2 + 4 * + 3 -")); // 14
}
```

### Latihan
1. Implementasikan Stack menggunakan Linked List (bukan Vec).
2. Buat konverter ekspresi infix ke postfix menggunakan stack.
3. Simulasikan antrian pelayanan bank menggunakan Queue.

---

## Pertemuan 16: Linked List

### Tujuan Pembelajaran
- Memahami struktur data Linked List.
- Mengimplementasikan Singly dan Doubly Linked List di Rust.
- Memahami penggunaan `Box<T>` untuk alokasi heap.

### Materi

#### 16.1 Singly Linked List

```rust
// Rust idiom: gunakan Option<Box<Node>>
#[derive(Debug)]
struct Node {
    nilai: i32,
    berikut: Option<Box<Node>>,
}

struct LinkedList {
    kepala: Option<Box<Node>>,
    ukuran: usize,
}

impl LinkedList {
    fn baru() -> Self {
        LinkedList { kepala: None, ukuran: 0 }
    }

    // Tambah di depan: O(1)
    fn tambah_depan(&mut self, nilai: i32) {
        let node = Box::new(Node {
            nilai,
            berikut: self.kepala.take(),
        });
        self.kepala = Some(node);
        self.ukuran += 1;
    }

    // Hapus dari depan: O(1)
    fn hapus_depan(&mut self) -> Option<i32> {
        self.kepala.take().map(|node| {
            self.kepala = node.berikut;
            self.ukuran -= 1;
            node.nilai
        })
    }

    // Cetak semua elemen
    fn cetak(&self) {
        let mut current = &self.kepala;
        print!("HEAD -> ");
        while let Some(node) = current {
            print!("{} -> ", node.nilai);
            current = &node.berikut;
        }
        println!("NULL");
    }

    fn panjang(&self) -> usize {
        self.ukuran
    }
}

fn main() {
    let mut list = LinkedList::baru();
    list.tambah_depan(3);
    list.tambah_depan(2);
    list.tambah_depan(1);
    list.cetak(); // HEAD -> 1 -> 2 -> 3 -> NULL

    println!("Hapus: {:?}", list.hapus_depan()); // Some(1)
    list.cetak(); // HEAD -> 2 -> 3 -> NULL
    println!("Panjang: {}", list.panjang());
}
```

#### 16.2 Operasi Lanjutan Linked List

```rust
impl LinkedList {
    // Tambah di belakang: O(n)
    fn tambah_belakang(&mut self, nilai: i32) {
        let node = Box::new(Node { nilai, berikut: None });
        if self.kepala.is_none() {
            self.kepala = Some(node);
        } else {
            let mut current = self.kepala.as_mut().unwrap();
            while current.berikut.is_some() {
                current = current.berikut.as_mut().unwrap();
            }
            current.berikut = Some(node);
        }
        self.ukuran += 1;
    }

    // Cari nilai: O(n)
    fn cari(&self, target: i32) -> bool {
        let mut current = &self.kepala;
        while let Some(node) = current {
            if node.nilai == target { return true; }
            current = &node.berikut;
        }
        false
    }

    // Balik linked list: O(n)
    fn balik(&mut self) {
        let mut prev = None;
        let mut current = self.kepala.take();
        while let Some(mut node) = current {
            let next = node.berikut.take();
            node.berikut = prev;
            prev = Some(node);
            current = next;
        }
        self.kepala = prev;
    }
}
```

### Latihan
1. Implementasikan Circular Linked List.
2. Buat fungsi untuk menghapus node dengan nilai tertentu.
3. Buat fungsi untuk menggabungkan dua sorted linked list menjadi satu sorted linked list.

---

## Pertemuan 17: Tree dan Binary Search Tree

### Tujuan Pembelajaran
- Memahami konsep tree dan terminologinya.
- Mengimplementasikan Binary Search Tree (BST).
- Mengimplementasikan tree traversal (inorder, preorder, postorder).

### Materi

#### 17.1 Binary Search Tree

```rust
#[derive(Debug)]
struct BST {
    akar: Option<Box<Node>>,
}

#[derive(Debug)]
struct Node {
    nilai: i32,
    kiri: Option<Box<Node>>,
    kanan: Option<Box<Node>>,
}

impl Node {
    fn baru(nilai: i32) -> Box<Self> {
        Box::new(Node { nilai, kiri: None, kanan: None })
    }
}

impl BST {
    fn baru() -> Self {
        BST { akar: None }
    }

    fn insert(&mut self, nilai: i32) {
        Self::insert_node(&mut self.akar, nilai);
    }

    fn insert_node(node: &mut Option<Box<Node>>, nilai: i32) {
        match node {
            None => *node = Some(Node::baru(nilai)),
            Some(n) => {
                if nilai < n.nilai {
                    Self::insert_node(&mut n.kiri, nilai);
                } else if nilai > n.nilai {
                    Self::insert_node(&mut n.kanan, nilai);
                }
            }
        }
    }

    fn cari(&self, nilai: i32) -> bool {
        Self::cari_node(&self.akar, nilai)
    }

    fn cari_node(node: &Option<Box<Node>>, nilai: i32) -> bool {
        match node {
            None => false,
            Some(n) => {
                if nilai == n.nilai { true }
                else if nilai < n.nilai { Self::cari_node(&n.kiri, nilai) }
                else { Self::cari_node(&n.kanan, nilai) }
            }
        }
    }

    // Inorder: kiri - akar - kanan (menghasilkan urutan tersorting)
    fn inorder(&self) {
        Self::inorder_node(&self.akar);
        println!();
    }

    fn inorder_node(node: &Option<Box<Node>>) {
        if let Some(n) = node {
            Self::inorder_node(&n.kiri);
            print!("{} ", n.nilai);
            Self::inorder_node(&n.kanan);
        }
    }

    // Preorder: akar - kiri - kanan
    fn preorder_node(node: &Option<Box<Node>>) {
        if let Some(n) = node {
            print!("{} ", n.nilai);
            Self::preorder_node(&n.kiri);
            Self::preorder_node(&n.kanan);
        }
    }

    // Postorder: kiri - kanan - akar
    fn postorder_node(node: &Option<Box<Node>>) {
        if let Some(n) = node {
            Self::postorder_node(&n.kiri);
            Self::postorder_node(&n.kanan);
            print!("{} ", n.nilai);
        }
    }

    fn tinggi(&self) -> usize {
        Self::tinggi_node(&self.akar)
    }

    fn tinggi_node(node: &Option<Box<Node>>) -> usize {
        match node {
            None => 0,
            Some(n) => {
                1 + Self::tinggi_node(&n.kiri).max(Self::tinggi_node(&n.kanan))
            }
        }
    }
}

fn main() {
    let mut bst = BST::baru();
    for val in [50, 30, 70, 20, 40, 60, 80] {
        bst.insert(val);
    }

    print!("Inorder  : "); bst.inorder();
    print!("Preorder : "); BST::preorder_node(&bst.akar); println!();
    print!("Postorder: "); BST::postorder_node(&bst.akar); println!();

    println!("Cari 40: {}", bst.cari(40));
    println!("Cari 55: {}", bst.cari(55));
    println!("Tinggi : {}", bst.tinggi());
}
```

### Latihan
1. Implementasikan fungsi `hapus(nilai)` pada BST.
2. Buat fungsi untuk mencari nilai minimum dan maksimum dalam BST.
3. Implementasikan Level-Order Traversal (BFS) pada BST.

---

## Pertemuan 18: Graf dan BFS/DFS

### Tujuan Pembelajaran
- Merepresentasikan graf dengan adjacency list.
- Mengimplementasikan BFS dan DFS.
- Aplikasi BFS: Shortest Path; DFS: Topological Sort.

### Materi

#### 18.1 Representasi Graf

```rust
use std::collections::{HashMap, HashSet, VecDeque};

struct Graf {
    adjacency: HashMap<usize, Vec<usize>>,
    terarah: bool,
}

impl Graf {
    fn baru(terarah: bool) -> Self {
        Graf { adjacency: HashMap::new(), terarah }
    }

    fn tambah_simpul(&mut self, v: usize) {
        self.adjacency.entry(v).or_insert_with(Vec::new);
    }

    fn tambah_sisi(&mut self, u: usize, v: usize) {
        self.adjacency.entry(u).or_default().push(v);
        if !self.terarah {
            self.adjacency.entry(v).or_default().push(u);
        }
    }

    fn tetangga(&self, v: usize) -> &[usize] {
        self.adjacency.get(&v).map(|v| v.as_slice()).unwrap_or(&[])
    }
}
```

#### 18.2 BFS (Breadth-First Search)

```rust
impl Graf {
    fn bfs(&self, awal: usize) -> Vec<usize> {
        let mut dikunjungi = HashSet::new();
        let mut queue = VecDeque::new();
        let mut urutan = Vec::new();

        dikunjungi.insert(awal);
        queue.push_back(awal);

        while let Some(v) = queue.pop_front() {
            urutan.push(v);
            for &tetangga in self.tetangga(v) {
                if !dikunjungi.contains(&tetangga) {
                    dikunjungi.insert(tetangga);
                    queue.push_back(tetangga);
                }
            }
        }
        urutan
    }

    // Jarak terpendek (BFS)
    fn jarak_terpendek(&self, awal: usize, tujuan: usize) -> Option<usize> {
        let mut jarak = HashMap::new();
        let mut queue = VecDeque::new();

        jarak.insert(awal, 0);
        queue.push_back(awal);

        while let Some(v) = queue.pop_front() {
            if v == tujuan { return Some(jarak[&v]); }
            for &tetangga in self.tetangga(v) {
                if !jarak.contains_key(&tetangga) {
                    jarak.insert(tetangga, jarak[&v] + 1);
                    queue.push_back(tetangga);
                }
            }
        }
        None
    }
}
```

#### 18.3 DFS (Depth-First Search)

```rust
impl Graf {
    fn dfs(&self, awal: usize) -> Vec<usize> {
        let mut dikunjungi = HashSet::new();
        let mut urutan = Vec::new();
        self.dfs_helper(awal, &mut dikunjungi, &mut urutan);
        urutan
    }

    fn dfs_helper(&self, v: usize, dikunjungi: &mut HashSet<usize>, urutan: &mut Vec<usize>) {
        dikunjungi.insert(v);
        urutan.push(v);
        for &tetangga in self.tetangga(v) {
            if !dikunjungi.contains(&tetangga) {
                self.dfs_helper(tetangga, dikunjungi, urutan);
            }
        }
    }
}

fn main() {
    let mut g = Graf::baru(false);
    // Graf:  0-1-2-3-4
    //        |   |
    //        5---6
    for (u, v) in [(0,1),(0,5),(1,2),(2,3),(2,6),(3,4),(5,6)] {
        g.tambah_sisi(u, v);
    }

    println!("BFS dari 0: {:?}", g.bfs(0));
    println!("DFS dari 0: {:?}", g.dfs(0));
    println!("Jarak 0->4: {:?}", g.jarak_terpendek(0, 4));
}
```

### Latihan
1. Implementasikan deteksi siklus pada graf menggunakan DFS.
2. Implementasikan Topological Sort menggunakan DFS.
3. Implementasikan algoritma Dijkstra untuk weighted shortest path.

---

## Pertemuan 19: Dynamic Programming

### Tujuan Pembelajaran
- Memahami konsep memoization dan tabulation.
- Mengimplementasikan algoritma DP klasik.
- Mengidentifikasi masalah yang cocok diselesaikan dengan DP.

### Materi

#### 19.1 Fibonacci dengan DP

```rust
fn main() {
    // Top-Down (Memoization)
    fn fib_memo(n: usize, memo: &mut Vec<Option<u64>>) -> u64 {
        if n <= 1 { return n as u64; }
        if let Some(val) = memo[n] { return val; }
        let hasil = fib_memo(n - 1, memo) + fib_memo(n - 2, memo);
        memo[n] = Some(hasil);
        hasil
    }

    // Bottom-Up (Tabulation)
    fn fib_tab(n: usize) -> u64 {
        if n <= 1 { return n as u64; }
        let mut dp = vec![0u64; n + 1];
        dp[1] = 1;
        for i in 2..=n {
            dp[i] = dp[i-1] + dp[i-2];
        }
        dp[n]
    }

    let mut memo = vec![None; 50];
    println!("fib(45) memo = {}", fib_memo(45, &mut memo));
    println!("fib(45) tab  = {}", fib_tab(45));
}
```

#### 19.2 Knapsack Problem (0/1)

```rust
fn knapsack(kapasitas: usize, berat: &[usize], nilai: &[usize], n: usize) -> usize {
    let mut dp = vec![vec![0usize; kapasitas + 1]; n + 1];

    for i in 1..=n {
        for w in 0..=kapasitas {
            dp[i][w] = dp[i-1][w]; // tidak ambil item i
            if berat[i-1] <= w {
                dp[i][w] = dp[i][w].max(dp[i-1][w - berat[i-1]] + nilai[i-1]);
            }
        }
    }
    dp[n][kapasitas]
}

fn main() {
    let berat = vec![2, 3, 4, 5];
    let nilai = vec![3, 4, 5, 6];
    let kapasitas = 8;
    let n = berat.len();

    println!("Nilai maksimum knapsack: {}", knapsack(kapasitas, &berat, &nilai, n));
}
```

#### 19.3 Longest Common Subsequence (LCS)

```rust
fn lcs(s1: &str, s2: &str) -> usize {
    let a: Vec<char> = s1.chars().collect();
    let b: Vec<char> = s2.chars().collect();
    let (m, n) = (a.len(), b.len());
    let mut dp = vec![vec![0usize; n + 1]; m + 1];

    for i in 1..=m {
        for j in 1..=n {
            dp[i][j] = if a[i-1] == b[j-1] {
                dp[i-1][j-1] + 1
            } else {
                dp[i-1][j].max(dp[i][j-1])
            };
        }
    }
    dp[m][n]
}

fn main() {
    println!("LCS(\"ABCBDAB\", \"BDCAB\") = {}", lcs("ABCBDAB", "BDCAB")); // 4
    println!("LCS(\"algoritma\", \"altruisme\") = {}", lcs("algoritma", "altruisme"));
}
```

#### 19.4 Coin Change Problem

```rust
fn koin_minimum(jumlah: usize, koin: &[usize]) -> Option<usize> {
    let inf = usize::MAX / 2;
    let mut dp = vec![inf; jumlah + 1];
    dp[0] = 0;

    for i in 1..=jumlah {
        for &k in koin {
            if k <= i && dp[i - k] != inf {
                dp[i] = dp[i].min(dp[i - k] + 1);
            }
        }
    }

    if dp[jumlah] == inf { None } else { Some(dp[jumlah]) }
}

fn main() {
    let koin = vec![1, 5, 10, 25];
    let jumlah = 41;
    match koin_minimum(jumlah, &koin) {
        Some(min) => println!("Koin minimum untuk {}: {}", jumlah, min),
        None      => println!("Tidak bisa membuat jumlah {}", jumlah),
    }
}
```

### Latihan
1. Implementasikan Edit Distance (Levenshtein Distance) menggunakan DP.
2. Buat program untuk menentukan apakah sebuah string adalah palindrom terpanjang (Longest Palindromic Subsequence).
3. Implementasikan Matrix Chain Multiplication.

---

## Pertemuan 20: Concurrency dengan Rust

### Tujuan Pembelajaran
- Memahami konsep thread dan concurrency.
- Menggunakan `std::thread` untuk multithreading.
- Menggunakan `Mutex`, `Arc`, dan `channel` untuk komunikasi aman antar thread.

### Materi

#### 20.1 Thread Dasar

```rust
use std::thread;
use std::time::Duration;

fn main() {
    // Membuat thread baru
    let handle = thread::spawn(|| {
        for i in 1..=5 {
            println!("Thread: angka {}", i);
            thread::sleep(Duration::from_millis(10));
        }
    });

    // Thread utama
    for i in 1..=3 {
        println!("Utama: angka {}", i);
        thread::sleep(Duration::from_millis(15));
    }

    handle.join().unwrap(); // tunggu thread selesai
    println!("Semua thread selesai");
}
```

#### 20.2 Move Closure dan Thread

```rust
use std::thread;

fn main() {
    let v = vec![1, 2, 3];

    // 'move' untuk transfer ownership ke thread
    let handle = thread::spawn(move || {
        println!("Vec di thread: {:?}", v);
    });

    handle.join().unwrap();
    // println!("{:?}", v); // ERROR: v sudah dipindah
}
```

#### 20.3 Mutex dan Arc (Shared State)

```rust
use std::sync::{Mutex, Arc};
use std::thread;

fn main() {
    // Arc: Atomic Reference Count (shared ownership)
    // Mutex: mutual exclusion (hanya satu thread yang bisa akses)
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];

    for _ in 0..10 {
        let counter_clone = Arc::clone(&counter);
        let h = thread::spawn(move || {
            let mut num = counter_clone.lock().unwrap();
            *num += 1;
        });
        handles.push(h);
    }

    for h in handles {
        h.join().unwrap();
    }

    println!("Counter: {}", *counter.lock().unwrap()); // 10
}
```

#### 20.4 Channel (Message Passing)

```rust
use std::sync::mpsc; // multi-producer, single-consumer
use std::thread;

fn main() {
    let (tx, rx) = mpsc::channel();

    // Multiple producers
    for i in 0..5 {
        let tx_clone = tx.clone();
        thread::spawn(move || {
            let pesan = format!("Pesan dari thread {}", i);
            tx_clone.send(pesan).unwrap();
        });
    }
    drop(tx); // drop original sender

    // Receiver
    for pesan in rx {
        println!("Diterima: {}", pesan);
    }
    println!("Semua pesan diterima");
}
```

#### 20.5 Parallel Sort dengan Rayon

```rust
// Tambahkan di Cargo.toml: rayon = "1.0"
// use rayon::prelude::*;
// 
// fn main() {
//     let mut data: Vec<i32> = (0..1_000_000).rev().collect();
//     data.par_sort(); // sort paralel otomatis
//     println!("Sorted {} elemen", data.len());
// }
```

### Latihan
1. Buat program yang menggunakan thread untuk menghitung jumlah elemen ganjil dan genap secara bersamaan.
2. Implementasikan producer-consumer problem menggunakan `mpsc::channel`.
3. Buat thread pool sederhana yang menjalankan sekumpulan tugas secara paralel.

---

## Pertemuan 21: Ujian Akhir Semester (UAS) & Review

### Review Materi

#### Ringkasan Algoritma dan Kompleksitasnya

| Algoritma | Tipe | Kompleksitas Waktu | Kompleksitas Ruang |
|-----------|------|-------------------|-------------------|
| Linear Search | Pencarian | O(n) | O(1) |
| Binary Search | Pencarian | O(log n) | O(1) |
| Bubble Sort | Pengurutan | O(n²) | O(1) |
| Selection Sort | Pengurutan | O(n²) | O(1) |
| Insertion Sort | Pengurutan | O(n²) | O(1) |
| Merge Sort | Pengurutan | O(n log n) | O(n) |
| Quick Sort | Pengurutan | O(n log n) avg | O(log n) |
| BFS | Graf | O(V+E) | O(V) |
| DFS | Graf | O(V+E) | O(V) |
| Dijkstra | Graf Berbobot | O((V+E) log V) | O(V) |
| Fibonacci DP | DP | O(n) | O(n) |
| Knapsack | DP | O(nW) | O(nW) |

#### Konsep Inti Rust

```rust
// Rangkuman konsep penting Rust

// 1. Ownership
let s1 = String::from("halo");
let s2 = s1; // s1 tidak valid lagi

// 2. Borrowing
let s3 = String::from("dunia");
let r = &s3; // borrow
println!("{} {}", s3, r); // keduanya valid

// 3. Lifetime (implisit dalam banyak kasus)
fn terpanjang<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() { s1 } else { s2 }
}

// 4. Traits
trait Cetak {
    fn cetak(&self);
}

// 5. Generics
fn identitas<T>(x: T) -> T { x }

// 6. Error Handling
fn bisa_gagal() -> Result<i32, String> {
    Ok(42)
}

fn main() {
    println!("{}", terpanjang("halo", "dunia"));
    println!("{:?}", bisa_gagal());
    println!("{}", identitas(42));
}
```

---

### Format UAS

**Durasi:** 120 menit  
**Bobot Nilai:**
- Bagian A – Analisis Kode & Kompleksitas (30%)
- Bagian B – Implementasi Algoritma (40%)
- Bagian C – Proyek Mini (30%)

**Contoh Soal UAS:**

**Bagian B:**
1. Implementasikan algoritma Dijkstra untuk graf berbobot menggunakan `BinaryHeap`.
2. Buat fungsi `cari_pasangan(arr: &[i32], target: i32) -> Vec<(i32, i32)>` yang mengembalikan semua pasangan elemen yang jumlahnya sama dengan target, dengan kompleksitas O(n).
3. Implementasikan AVL Tree dengan operasi insert dan auto-balancing.

**Bagian C (Proyek Mini – pilih salah satu):**
1. Implementasi sistem manajemen tugas (Task Manager) CLI dengan fitur: tambah, hapus, tandai selesai, dan prioritas.
2. Implementasi Mini Calculator dengan parser ekspresi matematika menggunakan Stack.
3. Implementasi simulasi sistem antrian rumah sakit dengan prioritas darurat.

---

## Referensi

1. **The Rust Programming Language** – Steve Klabnik & Carol Nichols (https://doc.rust-lang.org/book/)
2. **Rust by Example** – https://doc.rust-lang.org/rust-by-example/
3. **Rustlings** – Latihan interaktif Rust (https://github.com/rust-lang/rustlings)
4. **Introduction to Algorithms** – Cormen, Leiserson, Rivest, Stein (CLRS)
5. **Algorithm Design** – Jon Kleinberg & Éva Tardos
6. **Rust Standard Library Docs** – https://doc.rust-lang.org/std/

---

## Sistem Penilaian

| Komponen | Bobot |
|----------|-------|
| Kehadiran | 10% |
| Tugas/Latihan | 20% |
| UTS | 30% |
| UAS | 40% |
| **Total** | **100%** |

**Konversi Nilai:**

| Rentang | Grade | Keterangan |
|---------|-------|------------|
| 85 – 100 | A | Sangat Baik |
| 75 – 84 | B | Baik |
| 65 – 74 | C | Cukup |
| 55 – 64 | D | Kurang |
| < 55 | E | Tidak Lulus |

---

*Disusun oleh: Dosen Teknik Informatika*  
*Mata Kuliah: Algoritma dan Pemrograman – Bahasa Rust*  
*Semester Genap 2025/2026*
