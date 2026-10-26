---
tags: [readme, otomatisasi, google-workspace, sheets, forms, gas, importrange]
created: 2026-10-26
status: active
author: Tim Nirantara PLK UNY 2027
---

# ⚡ DIREKTORI PANDUAN OTOMATISASI GOOGLE WORKSPACE
## **Koleksi Formula, Integrasi Form, & Script Otomatisasi Cloud Tim NIRANTARA**

Folder ini berisi 3 panduan teknis operasional untuk menghubungkan dan mengotomatisasi dokumen Google Workspace tim agar bekerja cerdas tanpa perlu update manual satu per satu:

---

## 📚 Daftar Panduan di Folder Ini:

### 1. 🔗 [[01 - Panduan Rumus IMPORTRANGE Lintas Spreadsheet]]
- **Fungsi**: Menghubungkan sel/tabel dari Sheet A ke Sheet B secara *live* tanpa copy-paste.
- **Implementasi**: Menarik total saldo kas bendahara, akumulasi jam logbook 272 jam, dan estimasi biaya posko langsung ke Dashboard Utama Ketua.
- **Highlight**: Cara mengatasi error `#REF!` via tombol *Allow Access* dan trik kombinasi `=QUERY()` & `=IFERROR()`.

### 2. 📝 [[02 - Panduan Integrasi Google Forms ke Google Sheets]]
- **Fungsi**: Mengubah input kuesioner dari smartphone menjadi baris data spreadsheet secara *real-time*.
- **Implementasi**:
  1. *Form Oprec Mitra Desa* (penjaringan kelompok 2 Wonosari).
  2. *Form Pelaporan Nota & Kuitansi Pengeluaran* (upload struk kas agar tidak hilang).
  3. *Form Survei Data Warung & UMKM Warga* (pemetaan Google Maps & QRIS).
- **Highlight**: Cara menautkan Form ke Master Spreadsheet yang sudah ada tanpa membuat file baru yang berantakan.

### 3. 🤖 [[03 - Script Google Apps Script (GAS) Notifikasi & Webhook]]
- **Fungsi**: Otomatisasi berbasis JavaScript di cloud Google (gratis 24/7 tanpa server).
- **Implementasi**:
  1. Script notifikasi pesan WhatsApp otomatis saat ada anggota submit nota pengeluaran.
  2. Script notifikasi email otomatis ke `nirantara.plk.uny@gmail.com`.
  3. Script *Auto-Timestamp* otomatis mencatat jam verifikasi saat kotak centang `[x]` diklik.
- **Highlight**: Tutorial 2 menit memasang trigger *On form submit* di menu Extensions $\rightarrow$ Apps Script.

---

## 🧭 Alur Kerja Terintegrasi

```
[Smartphone Anggota / Responden]
               │
               ▼ (Isi Google Form)
┌──────────────────────────────┐
│        GOOGLE FORMS          │
└──────────────┬───────────────┘
               │ (Otomatis masuk baris baru)
               ▼
┌──────────────────────────────┐       Trigger GAS       ┌──────────────────────────────┐
│   GOOGLE SHEETS DATABASE     ├────────────────────────>│  NOTIFIKASI WHATSAPP / EMAIL │
└──────────────┬───────────────┘  (Kirim pesan otomatis) └──────────────────────────────┘
               │
               ▼ (Rumus =IMPORTRANGE())
┌──────────────────────────────┐
│  DASHBOARD UTAMA KETUA / TIM │  <── Semua data tersaji live di 1 layar!
└──────────────────────────────┘
```

---

← Kembali ke: [[Panduan Migrasi & Integrasi Google Workspace]] | [[Panduan Workspace & Kolaborasi Tim]] | [[Home]]
