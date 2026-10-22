---
tags: [workspace, tools, sekretaris, bendahara, notion, google-workspace, tim]
created: 2026-10-16
status: active
---

# 💻 Panduan Workspace & Kolaborasi Tim NIRANTARA
**Solusi Manajemen Kerja Bersama, Kesekretariatan, & Kebendaharaan**

Dokumen ini menjawab kebutuhan platform kolaborasi tim dan membandingkan opsi terbaik antara **Google Workspace** dan **Notion** untuk operasional Tim NIRANTARA.

---

## ❓ Apakah Google Workspace Punya Fitur Mirip Notion?

**JAWABANNYA: YA, ADA (Tetapi Berbentuk Fitur Terdistribusi).**

Google Workspace telah berevolusi dan memiliki beberapa fitur yang meniru Notion:

### 1. Google Docs "Smart Canvas" (Paling Mirip Dokumen Notion)
Di dalam dokumen Google Docs (menggunakan akun `nirantara.plk.uny@gmail.com`), kamu cukup mengetik simbol **`@`** untuk memunculkan fitur-fitur pintar:
* **Dropdown Status Interaktif**: Bisa membuat status `[ Belum Dimulai ]`, `[ In Progress ]`, `[ Selesai ]` dengan warna-warni layaknya Notion.
* **Building Blocks (Project Tracker)**: Template tabel siap pakai untuk memantau siapa PIC tugas dan deadline-nya.
* **Checklist Interaktif**: Daftar tugas yang bisa dicentang langsung oleh anggota.
* **Collapsible Headings**: Judul bab yang bisa di-expand/collapse untuk menyembunyikan detail teks yang panjang.
* **Mention Orang & File**: Menautkan anggota tim (`@nama`) atau dokumen lain (`@Proposal`).

### 2. Google Sites (Wiki Portal Internal Tim)
Bisa dibuat dalam 15 menit menggunakan email tim secara gratis. Berfungsi sebagai **Landing Page / Dashboard Posko** yang menampilkan link pintasan ke folder Drive, kalender Google kegiatan Klaten, dan nomor kontak darurat.

---

## ⚖️ Komparasi 2 Opsi Workspace Terbaik untuk Tim NIRANTARA

### Opsi A: NOTION PLUS EDUCATION PLAN (⭐ 100% GRATIS Pakai Email Kampus UNY)
Banyak mahasiswa belum mengetahui bahwa **Notion memberikan lisensi "Plus Plan" seharga $10/bulan menjadi 100% GRATIS UNLIMITED** untuk mahasiswa ber-email universitas!

* **Kelebihan**:
  * Tampilan sangat modern, estetik, dan rapi.
  * Memiliki fitur **Kanban Board** (papan kartu geser gaya Trello) untuk memantau tugas posko.
  * Database fleksibel: Satu tabel bisa diubah tampilannya menjadi Kalender, Galeri Foto, atau Board.
  * Aplikasi mobile (Android/iOS) sangat responsif untuk mencatat ide kilat di posko Klaten.
* **Cara Mengaktifkan Notion Gratis untuk 10 Anggota:**
  1. Salah satu anggota (misal: Fajar / Dinda / Veli) mendaftar/login ke [notion.so](https://notion.so) menggunakan email SSO UNY (`...@student.uny.ac.id`).
  2. Buka menu **Settings & Members** $\rightarrow$ **Plans / Upgrade**.
  3. Scroll ke bawah, pilih **"Get free Education Plan"**.
  4. Seketika workspace menjadi **Plus Plan Unlimited**. Undang 9 anggota lainnya (pakai email student UNY masing-masing).

---

### Opsi B: GOOGLE WORKSPACE MURNI (Google Drive + Docs + Sheets)
* **Kelebihan**:
  * Terhubung langsung dengan akun master yang baru dibuat: `nirantara.plk.uny@gmail.com`.
  * Tidak perlu mendaftar akun baru, semua 10 orang sudah terbiasa dengan Google Docs & Drive.
  * Format dokumen (.docx, .xlsx, .pdf) adalah **format wajib resmi** yang diminta oleh dosen PIC, DPL, LPPM UNY, dan Kepala Desa.
* **Kelemahan**: Manajemen tugas terasa lebih manual dibandingkan Notion.

---

## 🏆 Rekomendasi Solusi: "Sistem Hybrid" (Paling Efektif & Anti-Ribet)

Untuk menghindari kebingungan anggota, tim disarankan membagi fungsi workspace:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   ARSITEKTUR KERJA TIM NIRANTARA                       │
├───────────────────────────────────┬────────────────────────────────────┤
│   MANAJEMEN TUGAS & NOTULENSI     │   DOKUMEN RESMI, ARSIP & FINANSIAL │
│         (Notion / Discord)        │       (Google Workspace Drive)     │
├───────────────────────────────────┼────────────────────────────────────┤
│ • Timeline & Checklist Mingguan   │ • File Proposal & LPJ (.docx/.pdf) │
│ • Kalender Jadwal Menginap Klaten │ • Master Kas & RAB (.xlsx)         │
│ • Catatan Cepat Rapat Internal    │ • Arsip Kuitansi & Nota SPJ (.pdf) │
│ • Brainstorming Konten PDD        │ • Surat Pengantar & Izin Kesbangpol│
└───────────────────────────────────┴────────────────────────────────────┘
```

---

## 📁 Blueprint Struktur Folder Google Drive `nirantara.plk.uny@gmail.com`

Sekretaris (Dinda & Veli) dapat langsung menyusun struktur folder master di Google Drive bersama sebagai berikut:

```text
📁 DRIVE MASTER NIRANTARA PLK UNY 2027/
│
├── 📁 01_KESEKRETARIATAN/
│   ├── 📁 01_Surat_Menyurat/ (Surat Izin Observasi, Kesbangpol, Tembusan Dinas)
│   ├── 📁 02_Draft_Proposal/ (Draf Bab I-IV, Biodata Dosen/Mhs, Lembar Pengesahan)
│   ├── 📁 03_Logbook_272_Jam/ (Spreadsheet rekap jam harian 10 anggota)
│   └── 📁 04_Laporan_Akhir_LPJ/ (Template laporan pertanggungjawaban)
│
├── 📁 02_KEBENDAHARAAN/
│   ├── 📄 Master_Keuangan_Nirantara.xlsx (Sheet 1: RAB, Sheet 2: Arus Kas, Sheet 3: Rekap Iuran)
│   ├── 📁 01_Bukti_Transfer_Kas/ (Screenshot bukti transfer iuran anggota)
│   ├── 📁 02_Scan_Nota_SPJ_Operasional/ (Foto bon belanja dapur, bensin, obat P3K)
│   └── 📁 03_Scan_Nota_SPJ_Proker/ (Kuitansi belanja bahan eco-enzyme, modul ajar, benih)
│
├── 📁 03_PDD_DAN_BRANDING/
│   ├── 📁 01_Aset_Logo_Identity/ (Logo .ai, .png transparan, palet warna, font)
│   ├── 📁 02_Desain_Feeds_Instagram/ (Mockup carousel, feeds perkenalan, poster)
│   ├── 📁 03_Dokumentasi_Foto_Raw/ (Foto per pekan: W1, W2, W3... di Klaten)
│   └── 📁 04_Rilis_Berita_Jurnalistik/ (Draft naskah berita 5W1H karya Intan)
│
├── 📁 04_DIVISI_PROKER/
│   ├── 📁 Divisi_Teknologi_IT/ (Source code web desa, materi Canva Karang Taruna)
│   ├── 📁 Divisi_Administrasi_UMKM/ (Draft pembukuan UMKM, berkas BUMDes)
│   ├── 📁 Divisi_Lingkungan_Kesehatan/ (SOP Eco-Enzyme, materi kompos)
│   └── 📁 Divisi_Pendidikan_Media_Ajar/ (Modul ajar interaktif, materi bimbel)
│
└── 📁 05_LOGISTIK_DAN_PERKAP/
    ├── 📄 Inventaris_Alat_Posko.xlsx (Daftar laptop, proyektor, kabel roll, sound)
    └── 📄 Rekap_Ukuran_Rompi_Atribut.xlsx (Ukuran rompi 12 pcs, vendor konveksi)
```

---

## 📊 Setup Workspace Khusus Bendahara (Fai & Zalfa)

Bendahara disarankan membuat **1 File Google Sheets Master** di folder `02_KEBENDAHARAAN` dengan 3 Tab:

1. **Tab 1: `RAB_PROPOSAL`**
   * Format standar pengajuan dana kampus/sponsor (Nama Barang, Volume, Satuan, Harga Satuan, Total, Justifikasi Pemakaian).
2. **Tab 2: `CASHFLOW_KAS_HARIAN`**
   * Kolom: Tanggal | Kategori (Iuran / Belanja Posko / Proker) | Uraian | Pemasukan (Debit) | Pengeluaran (Kredit) | Saldo Akhir | Link Foto Nota.
3. **Tab 3: `REKAP_IURAN_ANGGOTA`**
   * Tabel 10 nama anggota dengan checklist pembayaran iuran kas bulanan / termin DP atribut (Rp 0 s.d. Lunas).

---

← [[Notulensi Resmi First Gathering NIRANTARA]] | [[Panduan First Gathering & Lembar Kerja Tim]] | [[Home]]
