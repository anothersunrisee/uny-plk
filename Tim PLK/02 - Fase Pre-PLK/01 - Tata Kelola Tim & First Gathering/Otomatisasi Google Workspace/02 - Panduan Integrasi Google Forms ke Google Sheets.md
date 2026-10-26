---
tags: [google-forms, google-sheets, integrasi, otomatisasi, screening, oprec, kuisioner, spj]
created: 2026-10-26
status: active
author: Tim Nirantara PLK UNY 2027
---

# 📝 PANDUAN INTEGRASI GOOGLE FORMS KE GOOGLE SHEETS
## **Otomatisasi Input Data dari Smartphone ke Spreadsheet Tanpa Ketik Ulang**

---

## 💡 Mengapa Menggunakan Google Forms yang Terintegrasi Sheets?

1. **Anti-Repot untuk Pengguna HP**: Mengisi tabel Google Sheets di layar HP seringkali sulit dan rawan salah pencet sel. Dengan Google Forms, anggota atau responden luar cukup mengisi kuesioner lewat tampilan form sederhana.
2. **Data Masuk Real-Time**: Detik saat responden menekan tombol **Kirim (Submit)**, seluruh jawaban otomatis menjadi baris baru (*new row*) di Google Sheets lengkap dengan tanggal dan jam pengisian (*Timestamp*).
3. **Upload File Otomatis Tersimpan di Google Drive**: Foto kuitansi, nota bensin, atau dokumen proposal otomatis masuk ke folder Google Drive dan menghasilkan link yang bisa diklik langsung di spreadsheet.

---

## 🎯 3 Use Case Utama untuk Tim NIRANTARA

```
                ┌───────────────────────────────────────────────┐
                │          3 IMPLEMENTASI GOOGLE FORMS          │
                └───────────────────────┬───────────────────────┘
                                        │
        ┌───────────────────────────────┼───────────────────────────────┐
        ▼                               ▼                               ▼
┌───────────────────────┐ ┌───────────────────────────┐ ┌───────────────────────┐
│  1. OPREC MITRA DESA  │ │  2. FORM PELAPORAN NOTA   │ │  3. SURVEI DATA WARGA │
│ • Pendaftaran Klp 2   │ │ • Upload foto bon belanja │ │ • Pemetaan UMKM/QRIS  │
│ • Skema A vs Skema B  │ │ • Tagihan kas operasional │ │ • Kuisioner sampah    │
│ • Seleksi otomatis    │ │ • Rekap SPJ bendahara     │ │ • Media ajar TK/TPA   │
└───────────────────────┘ └───────────────────────────┘ └───────────────────────┘
```

---

## 🛠️ Panduan Pembuatan & Struktur Pertanyaan

### 1. Form Oprec Kemitraan Kelompok 2 (Desa Wonosari)
*Dibuat oleh Sekretaris / Humas untuk menjaring kelompok mitra kedua*:

| No | Judul Pertanyaan di Form | Tipe Input | Wajib Diisi? | Keterangan / Pilihan |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Nama Ketua Kelompok | Jawaban Singkat | Ya | Nama lengkap & panggilan |
| 2 | Program Studi & Fakultas Asal | Jawaban Singkat | Ya | Contoh: Pendidikan Geografi (FISIPOL) |
| 3 | Nomor WhatsApp Ketua | Jawaban Singkat | Ya | wa.me/628... |
| 4 | Jumlah Total Anggota Kelompok | Angka | Ya | Minimal 8 – 10 Mahasiswa |
| 5 | Komposisi Gender Anggota | Pilihan Ganda | Ya | Jumlah Laki-laki & Perempuan |
| 6 | Pilihan Skema Kemitraan di Desa Wonosari | Pilihan Ganda | Ya | • **Skema A (Recommended)**: Mitra 1 Desa — Posko Mandiri (Sewa Sendiri)<br>• **Skema B**: Mitra 1 Desa — 1 Posko Bersama (Free Rent & Bersyarat MoU) |
| 7 | Apakah Kelompok Bersedia Menandatangani Komitmen Bersama? | Kotak Centang | Ya | Bersedia mematuhi aturan desa & koordinasi proker akbar |

---

### 2. Form Pelaporan Nota & Kuitansi Pengeluaran (Kas Tim)
*Dibuat oleh Bendahara (Faidatul & Zalfa) untuk memudahkan anggota klaim belanja tanpa nota hilang*:

| No | Judul Pertanyaan di Form | Tipe Input | Wajib Diisi? | Keterangan / Pilihan |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Tanggal Transaksi / Belanja | Tanggal | Ya | Sesuai tanggal yang tertera di struk |
| 2 | Nama Anggota yang Membeli | Dropdown | Ya | Pilihan 10 Nama Anggota Nirantara |
| 3 | Kategori Pengeluaran | Dropdown | Ya | • Operasional Posko (Sapu/Pel/Air/Listrik/Bensin)<br>• Proker Biologi (Kompos/Eco-Enzyme)<br>• Proker PTI (Web/Hosting/QRIS)<br>• Proker PADP (BUMDes/Administrasi)<br>• Proker TP (Modul Ajar TK/TPA)<br>• Kesekretariatan (Kertas/Map/Print) |
| 4 | Uraian Barang yang Dibeli | Paragraf Singkat | Ya | Contoh: Beli 2 Galon Air Minum + 1 Sabun Pel |
| 5 | Total Nominal Pembelian (Rp) | Angka | Ya | Contoh: 75000 (tanpa titik/Rp) |
| 6 | Unggah Foto / Scan Struk Nota Fisik | **Upload File** | Ya | Foto tegak lurus, jelas terbaca (Maks. 10 MB) |
| 7 | Metode Pembayaran Asal | Pilihan Ganda | Ya | • Uang Pribadi (Minta Penggantian/Reimburse)<br>• Menggunakan Uang Kas di Tangan |

---

### 3. Form Kuisioner Data Warung UMKM Desa Wonosari
*Dibuat oleh Divisi PTI & PADP saat survei door-to-door ke pemilik warung*:

| No | Judul Pertanyaan di Form | Tipe Input | Wajib Diisi? | Keterangan / Pilihan |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Nama Warung / Usaha | Jawaban Singkat | Ya | Contoh: Warung Kelontong Bu Sri |
| 2 | Nama Pemilik Usaha | Jawaban Singkat | Ya | Nama warga |
| 3 | Lokasi RT di Dukuh Majegan | Dropdown | Ya | RT 01 s.d. RT 06 |
| 4 | Produk Utama yang Dijual | Paragraf | Ya | Sembako, makanan matang, mebel kayu, dll |
| 5 | Apakah Usaha Sudah Ada di Google Maps? | Pilihan Ganda | Ya | • Sudah Ada<br>• Belum Ada (Minta Dibantu Buatkan) |
| 6 | Apakah Sudah Menyediakan Pembayaran QRIS?| Pilihan Ganda | Ya | • Sudah Ada<br>• Belum Ada (Berminat Didaftarkan) |
| 7 | Foto Depan Warung / Usaha | Upload File | Tidak | Untuk kebutuhan upload foto Google Maps |

---

## 🔗 Langkah Menghubungkan Google Form ke Google Sheets yang Ada

Jangan biarkan Google Form membuat spreadsheet baru yang terpisah. Sambungkan langsung ke **Master Spreadsheet** yang sudah ada:

1. Buka formulir di [forms.google.com](https://forms.google.com) menggunakan akun `nirantara.plk.uny@gmail.com`.
2. Klik tab **Tanggapan (Responses)** di bagian atas formulir.
3. Klik ikon hijau **Google Sheets (Tautkan ke Spreadsheet / Link to Sheets)**.
4. Pilih opsi:  
   👉 **"Pilih spreadsheet yang ada" (Select existing spreadsheet)** $\rightarrow$ Klik **Pilih**.
5. Pilih file tujuanmu (contoh: pilih `Master_Keuangan_Nirantara` untuk form nota, atau `Master_Database_Profil_dan_K3_Tim`).
6. Selesai! Google Sheets akan otomatis membuat tab baru bernama **`Tanggapan Formulir 1`** yang terhubung secara permanen.

---

## 💡 Trik Praktis Menjaga Rapi Data di Google Sheets

> [!TIP]
> **Aturan Emas Google Forms**:  
> Tab respon bawaan form (`Tanggapan Formulir 1`) **jangan diedit-edit barisnya secara manual** karena Google Forms akan selalu menyisipkan baris baru di bawahnya.

### Cara Mengolah Data Respon:
1. **Buat Tab Pengolahan Terpisah**:
   Buat tab baru di spreadsheet yang sama, misal bernama: `Rekap Verifikasi Nota`.
2. **Tarik Data Respon dengan Rumus Otomatis**:
   Gunakan rumus array untuk menarik data tanpa merusak sheet asli:
   ```excel
   ={'Tanggapan Formulir 1'!A1:G}
   ```
3. **Tambahkan Kolom Status & Centang**:
   Di tab pengolahan tersebut, Bendahara bisa bebas menambahkan kolom:
   - Kolom H: `[x] Status Verifikasi Nota`
   - Kolom I: `[x] Status Sudah Ditransfer / Reimburse`
   - Kolom J: `Catatan Bendahara`
