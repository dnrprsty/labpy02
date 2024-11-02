# Sistem Pembelian Tiket
Program sederhana untuk menghitung harga tiket berdasarkan jenis tiket dan status member.

## Deskripsi Program
Program ini memungkinkan pengguna untuk:

Memilih jenis tiket (VIP/Reguler)
Menentukan status member
Mendapatkan perhitungan harga tiket final dengan diskon jika memiliki kartu member

## Flowchart Ticket
````mermaid
flowchart TD
    A([Start]) --> B[Set Harga VIP = 100000]
    B --> C[Set Harga Reguler = 50000]
    C --> D[/Input Jenis Tiket/]
    
    D --> E{Jenis Tiket Valid?}
    E -->|VIP| F[Tetapkan Harga = 100000]
    E -->|Reguler| G[Tetapkan Harga = 50000]
    E -->|Tidak Valid| H[/Tampilkan Pesan Error/]
    
    F --> I[/Input Status Member/]
    G --> I
    H --> J([Exit])
    
    I --> K{Member?}
    K -->|Ya| N[harga_ticket -= harga_ticket * 0.20]
    K -->|Tidak| O[/Tampilkan Harga Akhir/]
    
    
    N --> O[/Tampilkan Harga Akhir/]
    O --> P([End])

````

## Contoh Output Program

![Output](output/outputticket.png)


## Cara Kerja Program:

1. Program menentukan harga awal:
   - Tiket VIP: Rp 100.000
   - Tiket Reguler: Rp 50.000

2. User diminta memilih jenis tiket:
   - Jika memilih "vip", harga diset Rp 100.000
   - Jika memilih "reguler", harga diset Rp 50.000
   - Jika input selain keduanya, program berhenti dengan pesan "Input tidak valid"

3. User diminta konfirmasi kepemilikan kartu member:
   - Jika memiliki kartu member (input "ya"), akan mendapat diskon 20%
   - Jika tidak memiliki (input "tidak"), tidak ada diskon

4. Program menampilkan harga akhir setelah perhitungan diskon

Contoh perhitungan:
- Jika pilih VIP dan punya member:
  Rp 100.000 - (20% × Rp 100.000) = Rp 80.000
- Jika pilih Reguler dan punya member:
  Rp 50.000 - (20% × Rp 50.000) = Rp 40.000
