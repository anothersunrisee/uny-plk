---
tags: [meta, agents, konteks]
created: 2026-09-29
status: active
---

# AGENTS.md — PLK UNY Mengabdi 2026/2027

Ini adalah panduan konteks untuk AI agent yang membantu proyek PLK UNY Mengabdi.
Baca file ini sebelum memulai analisa apapun di vault ini.

---

## Konteks Proyek

**Program**: PLK (Pembelajaran Luar Kampus) — UNY Mengabdi 2027, Semester 6
**Institusi**: Universitas Negeri Yogyakarta (UNY)
**Angkatan**: 2024 (akan menjalani PLK di Semester 6)
**Lokasi Incaran**: Kabupaten Klaten, Jawa Tengah (Jalur Lintas Provinsi)
**Status Tim**: Terkumpul 8 dari 10 orang

## Komposisi Tim Saat Ini

- **4 orang fix**: Pendidikan Teknik Informatika (PTI, FT) — Fajar, Terry, Riski, Veli
- **2 orang lock-in**: Pendidikan Administrasi Perkantoran (PADP, FEB) — Dinda Amelia Putri & Faidatul Anugraheni M.
- **2 orang lock-in**: Biologi (FMIPA) — Intan Milansari & (Partner Biologi 2)
- **2 slot tersisa (Dibutuhkan)**: Ilmu Komunikasi (FISHIPOL) untuk slot Konten/Humas.

## Struktur Vault Ini

```text
d:\KULIAH\UNY PLK\          ← Vault root (buka folder ini di Obsidian)
├── index.md                 ← Dashboard utama & landing page Quartz Web
├── Home.md                  ← Dashboard alternatif / Obsidian view
├── AGENTS.md                ← File ini — konteks untuk AI agent
│
├── Riset/
│   ├── analisa oprec.md     ← Analisa 36 posting open recruitment
│   └── Daftar Fakultas dan Prodi S1 UNY.md  ← Data resmi 60 prodi UNY
│
├── Panduan/
│   ├── Panduan PLK 2025 UNY.md       ← Panduan resmi PLK dari UNY
│   ├── WIP - Panduan Dashboard PLK.md ← Panduan penggunaan dashboard PLK
│   ├── WIP - Sosialisasi Mahasiswa.md ← Materi sosialisasi ke mahasiswa
│   └── UNY Mengabdi - Panduan Lengkap.md ← Kompilasi panduan lengkap
│
├── Tim PLK/                 ← Folder operasional tim
│   ├── 01 - Fase Oprec/     ← File rekrutmen, SPK pendaftar, dan form screening
│   ├── 02 - Fase Pre-PLK/   ← Draft survei Klaten, profil kesehatan tim, simulasi logbook
│   └── 03 - Fase PLK/       ← (WIP) Logbook kegiatan, notulensi rapat harian posko
│
└── _templates/              ← Template untuk note baru
```

## Fakta Penting yang Harus Diketahui Agent

### Tentang PLK UNY
- PLK = setara KKN, konversi 10-20 SKS (Minimal 272 Jam Kerja Efektif, via Logbook)
- Tim harus terdiri dari **minimal 10 orang dari minimal 2 prodi berbeda** (Ideal: 3-4 prodi).
- Setiap prodi diwakili **minimal 2 mahasiswa** dalam satu tim.
- Ada aturan abu-abu di tingkat Fakultas terkait larangan "Nilai C" dan keharusan "2 Kelompok per Desa" yang sedang diklarifikasi ke PIC Dosen Prodi.

### Sistem Kerja Tim (Struktur Matrix)
- Tim ini menggunakan **Struktur Organisasi Matrix**.
- Setiap anggota WAJIB memegang 2 peran: **Peran Operasional Posko** (Ketua, Bendahara, Konsumsi, Perkap, dll) DAN **Peran Fungsional Proker** (Koor Divisi Teknologi, Divisi Lingkungan, Divisi PADP, dll).
- Agent harus membedakan mana rapat/kebutuhan operasional (hidup di posko) dan rapat/kebutuhan proker (terjun ke warga) saat memberikan saran/rencana kerja.

### Rekomendasi 2 Anggota Sisa (Slot Terakhir)
| Slot | Prodi | Peran Matrix yang Dibutuhkan |
|:----:|-------|-------|
| 9 | Ilmu Komunikasi (FISHIPOL) | Operasional: PDD / Proker: Koor Divisi Pendidikan-Sosial |
| 10 | Ilmu Komunikasi (FISHIPOL) | Operasional: Humas / Proker: Anggota Divisi Pendidikan-Sosial |

## Panduan untuk Agent: Cara Membantu

### Jika diminta panduan birokrasi & kampus:
1. Rujuk ke dokumen di folder `Panduan/`.
2. Ingatkan *user* bahwa aturan prodi (PIC PLK) selalu mengalahkan aturan universitas jika terjadi perbedaan tafsir (Hukum Tertinggi adalah persetujuan dosen prodi).
3. Untuk perhitungan jam terbang 272 jam, rujuk ke trik `Draft Simulasi 272 Jam Kerja.md` (masukkan jam di Jogja).

### Format output yang disukai:
- Gunakan tabel markdown untuk data terstruktur.
- Gunakan list/bullet yang jelas dan tidak bertele-tele (prinsip: *Dar-der-dor, cepat, tereksekusi*).
- Gunakan emoji sebagai visual indicator (🔴 kritis, 🟠 penting, 🟡 sedang, 🟢 aman).
- Wikilinks Obsidian: `[[nama file]]` untuk referensi antar note.

---

*File ini otomatis dibaca oleh AI agent saat membantu proyek ini.*
*Update file ini secara berkala jika ada perubahan komposisi tim atau pergantian fase proyek.*
