---
tags: [google-workspace, google-drive, google-sheets, google-docs, migrasi, integrasi, tata-kelola, hybrid]
created: 2026-10-26
status: active
author: Tim Nirantara PLK UNY 2027
---

# 🚀 PANDUAN STRATEGIS MIGRASI & INTEGRASI GOOGLE WORKSPACE
## **Arsitektur Kolaborasi Hybrid: Antigravity IDE (Ketua) ⇄ Google Workspace (9 Anggota Tim)**
*Solusi Praktis Kolaborasi Lintas 4 Fakultas (FT, FEB, FMIPA, FIP) Tanpa Membebani Anggota dengan Tools Teknis*

---

## 💡 Mengapa Menggunakan Pendekatan "Hybrid Architecture"?

> [!NOTE]
> **Realitas Kondisi Tim Nirantara**:
> - **Fajar (Ketua Tim / PTI FT)**: Menggunakan **Antigravity IDE + Obsidian Vault** sebagai *Master Command Center* berbasis AI, analisis data mendalam, otomatisasi dokumen, dan git version control.
> - **9 Anggota Lain (PADP, Biologi, TP, PTI)**: Menggunakan ekosistem **Google Workspace (Google Drive, Docs, Sheets, Forms, Slides)** yang sudah sangat familiar di laptop maupun HP Android/iOS mereka.
> 
> **Prinsip Utama**: **Jangan paksa 9 anggota belajar Git atau Markdown.**  
> Fajar bertindak sebagai *System Architect & Bridge*. Anggota cukup bekerja di Google Docs & Sheets seperti biasa, dan seluruh datanya tetap 100% terstruktur, ter-backup, dan sinkron dengan master vault.

---

## 🏛️ Arsitektur Integrasi & Pembagian Peran Kerja

```
       ╔══════════════════════════════════════════════════════════════════╗
       ║            COMMAND CENTER KETUA (ANTIGRAVITY + OBSIDIAN)          ║
       ║  • Otomatisasi AI & Analisis Lapangan   • Git Versioning         ║
       ║  • Penjaga Master Data & Konsistensi    • Validasi Regulasi LPPM ║
       ╚══════════════════════════════════╦═══════════════════════════════╝
                                          ║
              [Sinkronisasi Otomatis via Google Drive for Desktop]
                                          ║
       ╔══════════════════════════════════╩═══════════════════════════════╗
       ║          GOOGLE WORKSPACE TIM (nirantara.plk.uny@gmail.com)       ║
       ║                                                                  ║
       ║  📁 GOOGLE DRIVE MASTER (Shared Folder ke Seluruh Anggota)       ║
       ║  ├── 📄 Master_Keuangan.xlsx  ──> Dikelola Bendahara (Fay & Zalfa)║
       ║  ├── 📄 Master_Logbook.xlsx   ──> Diisi 10 Anggota / Cek Veli    ║
       ║  ├── 📄 Master_Inventaris.xlsx──> Dikelola Perkap (Riski & Sandra║
       ║  ├── 📄 Master_Database.xlsx  ──> Data K3 & Stakeholders Desa    ║
       ║  ├── 📝 Draf Proposal (Docs)  ──> Disusun Sekre (Dinda & Veli)   ║
       ║  └── 📸 Folder Foto & Video   ──> Diunggah PDD (Vina & Intan)    ║
       ╚══════════════════════════════════════════════════════════════════╝
```

---

## 📊 File Master Google Sheets yang Sudah Siap Pakai

Semua spreadsheet di bawah ini telah selesai digenerate secara native (`.xlsx`) di folder lokal `DRIVE MASTER NIRANTARA PLK UNY 2027` dengan styling modern (*Emerald & Slate Theme*), formula otomatis, format mata uang, dan gridline siap pakai:

| Nama File Spreadsheet | Lokasi Folder di Google Drive | Tab / Sheet di Dalamnya | Fungsi & Penanggung Jawab |
| :--- | :--- | :--- | :--- |
| **1. `Master_Keuangan_Nirantara.xlsx`** | `02_KEBENDAHARAAN/` | 1. **Rekap Iuran Kas** (Status Lunas otomatis)<br>2. **Buku Kas Umum** (Cashflow saldo otomatis)<br>3. **RAB Induk** (Biaya posko & 4 prodi) | Dikelola **Bendahara 1 (Fay)** & **Bendahara 2 (Zalfa)** untuk mencatat iuran Rp 50.000,- dan pengeluaran nota. |
| **2. `Master_Inventaris_dan_Logistik_Posko.xlsx`** | `05_LOGISTIK_DAN_PERKAP/` | 1. **Kebutuhan Dianggarkan** (9 barang kas)<br>2. **Barang Bawaan Anggota** (Karpet bulu, dll)<br>3. **Audit Fisik Posko** (10 ruangan) | Dikelola **Perkap 1 (Riski)** & **Perkap 2 (Sandra)** untuk tracking pengadaan logistik pasca renovasi posko. |
| **3. `Master_Logbook_272_Jam_Kerja.xlsx`** | `01_KESEKRETARIATAN/03_Logbook_272_Jam/` | 1. **Rekap 272 Jam 10 Anggota** (Progres %)<br>2. **Template Log Harian Anggota** | Dipantau **Sekretaris 2 (Veli)**. Setiap anggota mengisi aktivitas untuk konversi SKS. |
| **4. `Master_Database_Profil_dan_K3_Tim.xlsx`** | `01_KESEKRETARIATAN/` | 1. **Biodata & Kontak 10 Anggota**<br>2. **Data K3 Medis & Kontak Darurat**<br>3. **Buku Kontak Stakeholders** (Pak RW, Kades, DPL) | Dipantau **Ketua (Fajar)** & **Riski (K3)** untuk keselamatan tim selama di Klaten. |
| **5. `NOTULENSI (PLK NIRANTARA 27)_SURVEI_24 OKT 26.docx`** | `01_KESEKRETARIATAN/05_NOTULA/` | Notulensi resmi survei Klaten | Dokumen word resmi siap buka di Google Docs untuk draf laporan/proposal. |

---

## 🛠️ Langkah-Langkah Migrasi Praktis (Step-by-Step)

### Langkah 1: Hubungkan Folder Lokal ke Google Drive Tim
Ada 2 pilihan cara sinkronisasi (Pilih salah satu):

#### Opsi A: Menggunakan Google Drive for Desktop (Sangat Direkomendasikan ⭐)
1. Unduh dan install aplikasi resmi **Google Drive for Desktop** di laptop.
2. Login menggunakan akun resmi tim: **`nirantara.plk.uny@gmail.com`**.
3. Di File Explorer Windows, akan muncul virtual drive baru (misal: `G:\My Drive` atau `G:\Shared drives`).
4. Cukup salin (*copy/paste*) seluruh folder:  
   `d:\KULIAH\UNY PLK\DRIVE MASTER NIRANTARA PLK UNY 2027`  
   ke dalam Google Drive tersebut.
5. **Keuntungan**: Setiap kali ada file yang diedit di laptop, Google Drive langsung otomatis mengunggah perubahan ke cloud tanpa perlu upload manual lewat web!

#### Opsi B: Unggah Manual via Web Browser
1. Buka browser dan login ke [drive.google.com](https://drive.google.com) dengan `nirantara.plk.uny@gmail.com`.
2. Klik tombol **+ Baru (New)** $\rightarrow$ **Unggah Folder (Folder upload)**.
3. Pilih folder: `d:\KULIAH\UNY PLK\DRIVE MASTER NIRANTARA PLK UNY 2027`.
4. Tunggu proses unggah selesai (seluruh struktur subfolder dan file `.xlsx` / `.docx` akan langsung terbentuk rapi).

---

### Langkah 2: Buka & Konversi ke Native Google Sheets & Docs
Saat file `.xlsx` dan `.docx` sudah berada di Google Drive:
1. Klik kanan pada `Master_Keuangan_Nirantara.xlsx` $\rightarrow$ **Buka dengan (Open with)** $\rightarrow$ **Google Spreadsheet (Google Sheets)**.
2. Klik menu **File** $\rightarrow$ **Simpan sebagai Google Spreadsheet**.  
   *(Lakukan hal yang sama untuk Master Inventaris, Master Logbook, Master Database, dan Notulensi Word).*
3. Google Sheets/Docs versi cloud kini aktif dengan fitur kolaborasi *real-time* (bisa diedit bersamaan oleh 10 orang sekaligus).

---

### Langkah 3: Bagikan Akses (Sharing Permissions) ke 9 Anggota
Agar dokumen aman dari orang luar namun tetap mudah diakses anggota:
1. Klik kanan pada folder utama **`DRIVE MASTER NIRANTARA PLK UNY 2027`** di Google Drive web.
2. Pilih **Bagikan (Share)**.
3. Masukkan 10 email anggota tim (email Gmail pribadi atau email SSO `@student.uny.ac.id` masing-masing):
   - Fajar, Terry, Riski, Veli (FT)
   - Dinda, Faidatul (FEB)
   - Intan, Zalfa (FMIPA)
   - Vina, Sandra (FIP)
4. Berikan hak akses: **Editor**.
5. Centang **"Kirim notifikasi"** agar mereka menerima link undangan di email masing-masing.

---

### Langkah 4: Buat "One-Link Dashboard" (Pintasan di Grup WhatsApp)
Agar anggota tidak tersesat di dalam folder bertingkat-tingkat:
1. Buka file **`Master_Database_Profil_dan_K3_Tim`** di Google Sheets.
2. Tambahkan tab baru di urutan paling depan bernama: **`📌 DASHBOARD & QUICK LINKS`**.
3. Masukkan link pintasan (*hyperlink*) ke dokumen-dokumen penting:
   - 💰 [Buka Kas & Rekap Iuran Anggota]
   - 📝 [Buka Draf Proposal PLK 2027]
   - ⏱️ [Buka Logbook 272 Jam Kerja]
   - 📦 [Buka Inventaris & Kebutuhan Posko]
   - 📸 [Buka Folder Dokumentasi Survei & Proker]
   - 📞 [Buka Kontak Penting Pak Kades & Pak RW]
4. Ambil link share spreadsheet tersebut, lalu **Pin (Sematkan)** pesan tersebut di grup WhatsApp **NIRANTARA PLK UNY 2027**.
5. Kapan pun anggota butuh data atau ingin mengisi sesuatu, mereka cukup klik 1 link tersebut dari HP!

---

## 🔄 SOP Alur Pembaruan Data (Workflow Sinkronisasi Kedepannya)

Agar master data antara Google Workspace dan Vault Obsidian tetap konsisten:

| Skenario Aktivitas | Alur Kerja di Google Workspace | Peran Fajar & Antigravity IDE |
| :--- | :--- | :--- |
| **1. Pembayaran Iuran Kas** | Anggota transfer iuran $\rightarrow$ upload bukti transfer ke folder `02_KEBENDAHARAAN/01_Bukti_Transfer_Kas/` $\rightarrow$ Bendahara (Fay/Zalfa) mencentang di sheet *Rekap Iuran Kas*. | Fajar cukup melihat total saldo kas yang sudah terupdate otomatis di sheet untuk menyusun prioritas belanja posko. |
| **2. Penyusunan Draf Proposal** | Dinda (FEB) & Fajar menyusun Bab I–IV di Google Docs dengan format margin resmi UNY (4-4-3-3). | Fajar bisa meminta Antigravity untuk mereview, memvalidasi sitasi panduan, atau menyempurnakan redaksional proposal kapan saja. |
| **3. Pencatatan Logbook Jam Kerja** | Setiap selesai kegiatan, masing-masing dari 10 anggota mencatat jam kerja di sheet *Logbook 272 Jam*. Veli memantau persentase progres. | Antigravity membantu menganalisis apakah jam kerja daring/Jogja sudah memenuhi kriteria rasio aman untuk persetujuan DPL. |
| **4. Pengadaan Barang Posko** | Menjelang akhir Januari 2027 (pasca renovasi posko), Riski & Sandra membuka sheet *Master Inventaris*, membeli barang, dan mengunggah nota ke folder `02_Scan_Nota_SPJ_Operasional`. | Data otomatis tercatat di RAB dan pembukuan SPJ tanpa ada nota yang hilang. |

---

## 💡 Tips Tambahan untuk Menjaga Ketertiban Data
1. **Gunakan Google Drive Scanner di HP**:
   Edukasi Bendahara (Zalfa & Fay) dan Perkap (Riski) untuk memotret nota/struk belanja menggunakan fitur *Scan* di aplikasi Google Drive HP (bukan foto biasa). Format PDF hasil scan otomatis bersih, tajam, dan langsung masuk ke folder Drive yang tepat.
2. **Kunci Sel Tertentu (Protected Ranges)**:
   Pada sheet *Rekap Iuran Kas* dan *Buku Kas Umum*, kunci kolom rumus (seperti kolom Total, Saldo Berjalan, dan Status) agar formula tidak sengaja terhapus oleh anggota lain saat membuka dari layar HP yang kecil.
3. **Backup Otomatis Google Drive ke Git**:
   Karena folder `DRIVE MASTER NIRANTARA PLK UNY 2027` ada di dalam direktori proyek lokal laptop Fajar, setiap kali Fajar melakukan `git commit` & `push`, seluruh file dan dokumentasi tim otomatis ter-backup ke repositori GitHub privat tim secara permanen!

---

*Panduan ini disusun untuk memastikan seluruh anggota Tim NIRANTARA dapat bekerja dengan nyaman dan produktif menggunakan tools yang mereka kuasai, sementara kendali mutu, strategi, dan legalitas tetap terkelola secara presisi di master system.*
