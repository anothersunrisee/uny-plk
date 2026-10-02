---
tags: [oprec, form, spreadsheet, screening, plk]
created: 2026-09-30
status: active
---

# Panduan Form, Matriks Spreadsheet, & Prompt AI Screening Oprec

Dokumen ini berisi arsitektur lengkap sistem seleksi calon anggota tim PLK UNY Mengabdi 2027:
1. **Daftar Pertanyaan Google Form** (Input untuk calon pendaftar agar data di Spreadsheet seragam dan terstruktur).
2. **Setup Kolom & Formula Google Sheets** (Matriks penilaian otomatis untuk tim inti).
3. **Prompt AI Screening** (Tinggal copy-paste data spreadsheet ke ChatGPT/Gemini/Claude untuk ranking otomatis).

---

## BAGIAN 1: Struktur Pertanyaan Google Form (Input Calon Pendaftar)

*Buat Google Form dengan pertanyaan berikut agar hasil respon di Spreadsheet rapi, berformat angka/pilihan ganda, dan mudah di-filter.*

### Bagian A: Data Diri Dasar
1. **Nama Lengkap**: *(Jawaban singkat - Wajib)*
2. **Nama Panggilan**: *(Jawaban singkat - Wajib)*
3. **NIM**: *(Jawaban singkat - Wajib)*
4. **Program Studi & Fakultas**: *(Dropdown / Pilihan Ganda - Wajib)*
   - Ilmu Komunikasi (FISHIPOL)
   - Manajemen (FEB)
   - Pendidikan Administrasi Perkantoran / PADP (FEB)
   - Statistika (FMIPA)
   - Biologi / Pendidikan Biologi (FMIPA)
5. **Jenis Kelamin**: *(Pilihan Ganda - Wajib)*
   - Laki-laki
   - Perempuan
6. **Nomor WhatsApp Aktif**: *(Jawaban singkat - Wajib)*
7. **Akun Instagram / LinkedIn**: *(Jawaban singkat - Opsional)*

---

### Bagian B: Syarat Mutlak / Hard Requirements (Filter Gugur Otomatis)
8. **Apakah kamu bersedia berkomitmen mengikuti kegiatan PLK di Kabupaten Klaten (skema akhir pekan: Sabtu dan Minggu)?** *(Pilihan Ganda - Wajib)*
   - [ ] Ya, bersedia penuh
   - [ ] Tidak bersedia *(Otomatis Gugur)*
9. **Apakah kamu memiliki sepeda motor pribadi dan SIM C aktif yang siap digunakan untuk perjalanan Yogya-Klaten?** *(Pilihan Ganda - Wajib)*
   - [ ] Ya, punya motor pribadi dan SIM C aktif
   - [ ] Punya motor tapi tidak ada SIM C
   - [ ] Tidak memiliki kendaraan pribadi
10. **Apakah kamu siap menginap di basecamp rumah kerabat anggota tim di Klaten secara gratis (tanpa biaya sewa posko)?** *(Pilihan Ganda - Wajib)*
   - [ ] Ya, siap dan fleksibel
   - [ ] Ragu-ragu / Tidak
11. **Komitmen Kerja Tim: Kami menerapkan aturan tegas no drama, aktif berkoordinasi, dan pantang menghilang tanpa kabar (no ghosting). Seberapa yakin kamu bisa memegang komitmen ini?** *(Skala Linier 1 s.d. 5 - Wajib)*
   - 1 = Kurang yakin
   - 5 = Sangat yakin dan siap bertanggung jawab penuh

---

### Bagian C: Pilihan Formasi & Kualifikasi Spesifik
12. **Formasi Peran yang Kamu Lamar**: *(Pilihan Ganda - Wajib)*
   - [ ] Ilmu Komunikasi: Humas Desa, Komunikasi Publik, & PDD Media
   - [ ] Manajemen / PADP: Bendahara Keuangan, RAB, & Administrasi/LPJ
   - [ ] Biologi / Statistika: Data Analis Potensi Desa & Program Lingkungan Warga

13. **Keahlian & Pengalaman Relevan**:
   *(Berdasarkan formasi yang kamu pilih di atas, jelaskan pengalaman organisasi, kepanitiaan, atau keahlian teknis yang kamu miliki!)*
   *(Paragraf - Wajib)*

14. **Ide Awal Program Kerja**:
   *(Jika bergabung, program atau kontribusi apa yang paling ingin kamu terapkan untuk warga desa di Klaten sesuai bidang studimu?)*
   *(Paragraf - Wajib)*

15. **Tautan Portofolio / Berkas Pendukung (Opsional)**:
   *(Cantumkan link Google Drive berisi CV, desain, contoh tulisan, foto/video karya, atau berkas pendukung lainnya jika ada).*
   *(Jawaban singkat - Opsional)*

---

### Bagian D: Aset Fisik & Nilai Tambah (Nilai Plus)
16. **Kepemilikan Alat Dokumentasi**: *(Pilihan Ganda - Wajib)*
   - [ ] Memiliki Kamera DSLR / Mirrorless pribadi dan siap dibawa kegiatan
   - [ ] Memiliki Stabilizer / Gimbal video
   - [ ] Memiliki Keduanya (Kamera + Gimbal)
   - [ ] Hanya kamera HP
17. **Kemampuan Video Editing**: *(Pilihan Ganda - Wajib)*
   - [ ] Mahir (Terbiasa Premiere Pro, DaVinci Resolve, atau CapCut lanjutan)
   - [ ] Tingkat Dasar (CapCut standar untuk reels/TikTok)
   - [ ] Tidak bisa editing video
18. **Kemampuan Berbahasa Jawa**: *(Pilihan Ganda - Wajib)*
   - [ ] Lancar berbahasa Jawa Krama Inggil (halus)
   - [ ] Hanya bisa bahasa Jawa Ngoko (sehari-hari)
   - [ ] Kurang paham bahasa Jawa

---

## BAGIAN 2: Setup Kolom Spreadsheet & Formula Evaluasi Tim

Ketika Google Form dihubungkan ke Google Sheets, respon pendaftar akan masuk di Kolom A sampai Kolom R.

Tambahkan 6 kolom evaluasi di sebelah kanan data responden (mulai Kolom S):

| Kolom | Nama Header Kolom | Tipe Isian | Keterangan & Rumus Formula |
| :---: | :--- | :---: | :--- |
| **S** | **Filter Mutlak** | Formula Otomatis | Cek apakah syarat Klaten & Kendaraan terpenuhi.<br>`=IF(AND(H2="Ya, bersedia penuh", LEFT(I2,2)="Ya", J2="Ya, siap dan fleksibel", K2>=4), "LOLOS", "GUGUR")` |
| **T** | **Nilai Skill (1–40)** | Input Manual Reviewer | Nilai kecocokan keahlian & ide proker pendaftar (dinilai 10 s.d. 40 oleh Fajar/Terry/Veli). |
| **U** | **Nilai Plus Alat (1–30)** | Formula Otomatis | Bonus otomatis jika punya kamera/motor/krama.<br>`=(IF(P2<>"Hanya kamera HP", 15, 0) + IF(Q2="Mahir (Terbiasa Premiere Pro, DaVinci Resolve, atau CapCut lanjutan)", 10, IF(Q2="Tingkat Dasar (CapCut standar untuk reels/TikTok)", 5, 0)) + IF(R2="Lancar berbahasa Jawa Krama Inggil (halus)", 5, 0))` |
| **V** | **Nilai Komitmen (1–30)** | Input Manual Reviewer | Berdasarkan rekam jejak, jawaban deskripsi, dan kesiapan aktif (dinilai 10 s.d. 30). |
| **W** | **Total Skor (0–100)** | Formula Otomatis | `=IF(S2="GUGUR", 0, SUM(T2:V2))` |
| **X** | **Status Rekomendasi** | Formula Otomatis | `=IF(S2="GUGUR", "🔴 DISKUALIFIKASI", IF(W2>=75, "🟢 PRIORITAS WAWANCARA", IF(W2>=60, "🟡 CADANGAN", "🔴 TOLAK")))` |
| **Y** | **Reviewer & Catatan** | Teks Manual | Nama anggota tim penilai dan catatan khusus saat screening. |

---

## BAGIAN 3: Prompt AI untuk Screening Cepat di Spreadsheet

*Cara Pakai:*
1. Buka spreadsheet Google Form yang sudah terisi pendaftar.
2. Blok dan copy baris data responden (misal: 10–20 baris pertama).
3. Buka AI (ChatGPT, Claude, atau Gemini).
4. Paste prompt di bawah ini bersama tabel data pendaftar.

```text
Kamu adalah asisten HR dan rekrutmen untuk Tim PLK (Pembelajaran Luar Kampus setara KKN) UNY Mengabdi 2027.

Profil Tim Kami:
- Tim Inti: 4 mahasiswa Pendidikan Teknik Informatika (FT) UNY Angkatan 2024 (3 Cowok, 1 Cewek).
- Kesiapan Tim: Infrastruktur digital desa/website profil desa sudah di-handle 100% oleh anak PTI, sudah ada calon lokasi di Kab. Klaten, sudah ada tempat singgah/basecamp gratis (rumah kerabat), dan sudah ada armada 3 motor prima.
- Skema Kerja: Weekend warrior (fokus Sabtu dan Minggu di Klaten, hari biasa kuliah reguler di Jogja).

Target Kuota yang Dicari (Total 6 Orang, masing-masing 2 orang):
1. ILMU KOMUNIKASI (2 Orang): Butuh skill komunikasi publik (lobi warga/desa) dan PDD media (foto/video/konten).
2. MANAJEMEN / PADP (2 Orang): Butuh skill manajemen administrasi tim (surat, arsip, LPJ) dan Bendahara (RAB, kas tim, nota).
3. BIOLOGI / STATISTIKA (2 Orang): Butuh data analyst potensi desa (Statistika) atau inisiator program fisik lingkungan/UMKM (Biologi).

Syarat Mutlak:
- Siap kegiatan akhir pekan di Klaten.
- Punya kendaraan motor pribadi dan SIM C aktif.
- Siap basecamp rumah kerabat.
- Komitmen tinggi, no drama, dan pantang menghilang (no ghosting).

Nilai Tambah Super Prioritas:
- Memiliki kamera DSLR / Mirrorless / Gimbal.
- Mahir video editing.
- Lancar bahasa Jawa Krama Inggil.

Berikut adalah data mentah calon pendaftar dari spreadsheet pendaftaran:
[PASTE DATA TABEL DARI GOOGLE SHEETS DI SINI]

Tugas Kamu:
1. Saring kandidat: Tandai siapapun yang TIDAK memenuhi syarat mutlak (langsung diskualifikasi dan beri alasannya).
2. Kelompokkan kandidat yang lolos ke dalam 3 formasi prodi (Ilkom, Manajemen/PADP, Biologi/Statistika).
3. Buatkan tabel pemeringkatan (ranking) dari skor tertinggi ke terendah per prodi, dengan kolom:
   - Nama & NIM
   - Prodi
   - Keunggulan Utama (Hard skill & aset kamera/kendaraan)
   - Titik Lemah / Risiko
   - Status: Prioritas Wawancara / Cadangan / Ditolak
4. Pilih 2 KANDIDAT TERBAIK untuk masing-masing prodi (Total 6 orang ideal) yang kombinasinya paling saling melengkapi dan menutup kekurangan tim inti.
5. Berikan 3 pertanyaan wawancara spesifik yang wajib kami tanyakan kepada masing-masing kandidat terpilih tersebut untuk menguji keaslian portofolio dan komitmennya.
```
