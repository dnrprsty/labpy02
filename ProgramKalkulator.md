# Program Kalkulator Sederhana
Program ini adalah kalkulator sederhana yang bisa melakukan operasi dasar seperti penjumlahan, pengurangan, perkalian, dan pembagian.
    
## Rincian Program :
#### 1. Fungsi Aritmatika
- Penjumlahan: Menambahkan dua angka.
- Pengurangan: Mengurangi angka kedua dari angka pertama.
- Perkalian: Mengalikan dua angka.
- Pembagian: Membagi angka pertama dengan angka kedua, dengan pengecekan agar tidak membagi dengan nol.

#### 2. Fungsi Utama kalkulator():
- Menampilkan menu pilihan operasi.
- Mengambil pilihan dari pengguna dan memvalidasi input.
- Meminta pengguna memasukkan dua angka dan memastikan input valid.
- Melakukan operasi sesuai pilihan dan menampilkan hasilnya.

#### 3. Menjalankan Program:
Program dimulai dengan memanggil fungsi kalkulator(), yang menjalankan semua langkah di atas.

#### *Fitur Tambahan
Program ini dapat menangani kesalahan input, seperti angka yang tidak valid atau pembagian dengan nol, sehingga memberikan informasi yang tepat kepada pengguna.

## Flowchart
````mermaid
flowchart TD
    A(Mulai) --> B[Tampilkan Menu]
    B --> C{Pilih Operasi}
    
    C -->|5 Keluar| D[Anda keluar dari kalkulator]
    C -->|>5 atau <=0 atau Kosong| E[Pilihan tidak valid! Keluar]
    C -->|1-4| F[Masukkan Angka Pertama]
    F --> G[Masukkan Angka Kedua]
    
    G --> H{Validasi Angka}
    H -->|Tidak Valid| I[Tidak Memasukkan Angka, Keluar]
    H -->|Valid| J{Pilihan Operasi}
    
    J -->|1 Penjumlahan| K[Hasil = Penjumlahan angka1, angka2]
    J -->|2 Pengurangan| L[Hasil = Pengurangan angka1, angka2]
    J -->|3 Perkalian| M[Hasil = Perkalian angka1, angka2]
    J -->|4 Pembagian| N{Apakah Angka Kedua = 0}
    
    N -->|Ya| O[Pembagian tidak bisa menggunakan 0]
    N -->|Tidak| P[Hasil = Pembagian angka1, angka2]
    
    K --> Q[Tampilkan Hasil]
    L --> Q
    M --> Q
    O --> Q
````

## Kode Program 
```python
# Mendefinisikan operasi aritmatika
def penjumlahan(a, b):
    return a + b

def pengurangan(a, b):
    return a - b

def perkalian(a, b):
    return a * b

def pembagian(a, b):
    if b != 0:
        return a / b
    else:
        return "Pembagian tidak bisa menggunakan 0"

# Fungsi utama untuk menjalankan kalkulator
def kalkulator():
    print("--------------------------")
    print("--- Kalkulator Sederhana ---")
    print("--------------------------")
    
    print("Pilih operasi:")
    print("1. Penjumlahan")
    print("2. Pengurangan")
    print("3. Perkalian")
    print("4. Pembagian")
    print("5. Keluar")
    
    # Memilih jenis operasi
    pilihan = input("Masukkan pilihan (1/2/3/4/5): ")
    
    # Cek pilihan untuk keluar atau pilihan yang tidak valid
    if pilihan == '5':
        print("Anda keluar dari kalkulator.")
        return
    elif pilihan > '5' or pilihan <= '0' or pilihan == '':
        print("Pilihan yang dipilih tidak valid!")
        return
    
    # Memasukkan angka dan validasi input
    try:
        angka1 = int(input("Masukkan angka pertama: "))
        angka2 = int(input("Masukkan angka kedua: "))
    except ValueError:
        print("Anda tidak memasukkan angka yang valid!")
        return
    
    # Proses dan hasil berdasarkan pilihan operasi
    if pilihan == '1':
        hasil = penjumlahan(angka1, angka2)
        print("Hasil penjumlahan =", hasil)
    elif pilihan == '2':
        hasil = pengurangan(angka1, angka2)
        print("Hasil pengurangan =", hasil)
    elif pilihan == '3':
        hasil = perkalian(angka1, angka2)
        print("Hasil perkalian =", hasil)
    elif pilihan == '4':
        hasil = pembagian(angka1, angka2)
        print("Hasil pembagian =", hasil)

# Menjalankan program kalkulator
kalkulator()
```

## Hasil Output Program

![output](Output_Kalkulator.png)

berikut adalah contoh output program apabila berhasil 
