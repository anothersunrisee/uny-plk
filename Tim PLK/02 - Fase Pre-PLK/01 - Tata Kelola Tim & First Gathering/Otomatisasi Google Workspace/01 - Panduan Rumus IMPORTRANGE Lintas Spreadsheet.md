---
tags: [google-sheets, importrange, otomatisasi, dashboard, formula, cross-sheet]
created: 2026-10-26
status: active
author: Tim Nirantara PLK UNY 2027
---

# 🔗 PANDUAN FORMULA =IMPORTRANGE() LINTAS SPREADSHEET
## **Sinkronisasi Data Real-Time Antar-File Google Sheets Tanpa Copy-Paste Manual**

---

## 💡 Apa Itu IMPORTRANGE?

`IMPORTRANGE` adalah formula bawaan Google Sheets yang memungkinkan suatu spreadsheet mengambil data dari spreadsheet lain secara **live dan otomatis**.

Ketika bendahara mengupdate kas di spreadsheet keuangan, saldo di spreadsheet dashboard ketua akan **langsung terupdate detik itu juga**.

---

## 📐 Sintaks Dasar Formula

```excel
=IMPORTRANGE("SPREADSHEET_URL_ATAU_ID", "Nama_Sheet!Range_Sel")
```

- **Argumen 1 (URL/ID)**: URL lengkap spreadsheet sumber, atau cukup ID spreadsheet-nya (bagian acak huruf & angka di antara `/d/` dan `/edit`).
  *Contoh*: `"https://docs.google.com/spreadsheets/d/1a2b3c4d5e6f7g8h9i0j/edit"` atau cukup `"1a2b3c4d5e6f7g8h9i0j"`.
- **Argumen 2 (Sheet & Range)**: Nama tab sheet sumber diikuti tanda seru `!` dan koordinat sel.
  *Contoh*: `"'Rekap Iuran Kas'!J15"` atau `"'Buku Kas Umum'!A5:J50"`.

> [!WARNING]
> Kedua argumen **WAJIB diapit tanda petik dua (`"..."`)**! Jika tidak diberi tanda petik, rumus akan menghasilkan error `#NAME?`.

---

## 🔑 Langkah Wajib: Otorisasi "Allow Access" (Izinkan Akses)

Saat pertama kali mengetik rumus `IMPORTRANGE` antara dua file yang belum pernah terhubung, sel akan menampilkan error **`#REF!`**. Ini **bukan rusak**, melainkan mekanisme keamanan Google.

### Cara Membuka Izin Akses (Cukup 1 Kali Saja):
1. Arahkan kursor mouse ke sel yang menampilkan tulisan **`#REF!`**.
2. Akan muncul kotak dialog pop-up bertuliskan:  
   *"You need to connect these sheets. (Anda perlu menghubungkan sheet ini.)"*
3. Klik tombol biru **"Allow access" (Izinkan akses)**.
4. Tunggu 2–3 detik, tulisan `#REF!` akan hilang dan data otomatis muncul!

```
┌────────────────────────────────────────────────────────┐
│  #REF!                                                 │
├────────────────────────────────────────────────────────┤
│  You need to connect these sheets.                     │
│                                                        │
│                  [ Allow access ]                      │
└────────────────────────────────────────────────────────┘
```

---

## 🎯 4 Contoh Implementasi Konkret untuk Tim Nirantara

### 1. Menampilkan Total Kas Terkumpul di Dashboard Ketua
Misal di file `Master_Dashboard_Ketua.xlsx`, kamu ingin menampilkan total uang kas yang sudah disetor 10 anggota dari file `Master_Keuangan_Nirantara.xlsx` (sel J15 pada sheet 'Rekap Iuran Kas'):

```excel
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/ID_FILE_KEUANGAN_KAMU/edit", "'Rekap Iuran Kas'!J15")
```
*Hasil*: Langsung muncul nominal `Rp 500.000` (atau saldo terkini). Jika ada anggota bayar dan dicentang oleh Faidatul/Zalfa, angka di dashboard ketua langsung berubah sendiri!

---

### 2. Menampilkan Saldo Kas Berjalan (Kas di Tangan)
Mengambil saldo akhir kas dari sheet 'Buku Kas Umum' (misal baris terakhir berada di kolom H):

```excel
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/ID_FILE_KEUANGAN_KAMU/edit", "'Buku Kas Umum'!H5")
```

---

### 3. Menampilkan Rekap Progres 272 Jam 10 Anggota ke Dashboard
Menarik seluruh tabel rekapitulasi progres 10 mahasiswa dari file `Master_Logbook_272_Jam_Kerja.xlsx` (kolom Nama, Jam Jogja, Jam Klaten, Total, dan Persentase):

```excel
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/ID_FILE_LOGBOOK_KAMU/edit", "'Rekap 272 Jam 10 Anggota'!B4:K14")
```
*Hasil*: Seluruh tabel 10 orang otomatis tampil utuh di dashboard ketua lengkap dengan persentase kelulusan logbook-nya!

---

### 4. Menampilkan Total Estimasi Biaya Pengadaan Posko
Menarik subtotal belanja perlengkapan posko dari file `Master_Inventaris_dan_Logistik_Posko.xlsx` (sel F14 pada sheet 'Kebutuhan Dianggarkan'):

```excel
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/ID_FILE_INVENTARIS_KAMU/edit", "'Kebutuhan Dianggarkan'!F14")
```
*Hasil*: Otomatis muncul nominal `Rp 455.000,-`.

---

## 🚀 Trik Tingkat Lanjut (Power-Ups)

### A. Membungkus dengan `=IFERROR()` (Tampilan Bersih & Rapi)
Agar saat internet lambat atau file sedang loading tidak muncul tulisan `#LOADING...` atau `#REF!`, bungkus rumusmu:

```excel
=IFERROR(IMPORTRANGE("URL_SPREADSHEET", "'Sheet1'!A1"), "Menghubungkan...")
```

### B. Memfilter Data Live Menggunakan `=QUERY()`
Jika kamu hanya ingin menarik baris anggota yang **Status Pembayarannya = "LUNAS"**:

```excel
=QUERY(
  IMPORTRANGE("URL_SPREADSHEET_KEUANGAN", "'Rekap Iuran Kas'!B5:L14"),
  "SELECT Col1, Col2, Col9, Col11 WHERE Col11 = 'LUNAS'"
)
```

---

## ⚠️ Batasan & Best Practices
1. **Jangan Berlebihan**: Satu file Google Sheets maksimal disarankan menampung 20–30 rumus `IMPORTRANGE`. Untuk tim PLK kita (4–5 spreadsheet), kinerjanya akan sangat cepat dan mulus.
2. **Format Sel Sumber**: Format mata uang (Rp) atau tanggal sebaiknya disetel di sheet tujuan agar tampilannya seragam.
3. **Akses File**: Akun yang membuka dashboard harus memiliki hak akses (minimal *Viewer*) terhadap spreadsheet sumber. Karena semua file ada di shared folder `DRIVE MASTER NIRANTARA`, seluruh anggota otomatis punya akses!
