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
**Status Tim**: Sedang membentuk tim 10 orang

## Komposisi Tim Saat Ini

- **4 orang fix**: Pendidikan Teknik Informatika (PTI), Fakultas Teknik (FT)
- **6 orang open**: Masih dicari
- **Tujuan proyek**: Campuran development + komunikasi + riset
- **Skill yang dimiliki sisa tim (6 orang)**: UI/UX desain, komunikasi/konten, IT tambahan

## Struktur Vault Ini

```
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
├── Tim PLK/                 ← Folder untuk catatan tim
│   └── (tambah note anggota, rapat, dll)
│
└── _templates/              ← Template untuk note baru
    ├── Template Anggota.md
    └── Template Rapat.md
```

## File Kunci dan Isinya

| File | Isi | Penting untuk |
|------|-----|---------------|
| `Riset/analisa oprec.md` | Analisa 36 posting oprec, ranking prodi dicari/ada | Rekrutmen anggota |
| `Riset/Daftar Fakultas dan Prodi S1 UNY.md` | 60 prodi S1 + animo + akreditasi | Referensi data UNY |
| `Panduan/Panduan PLK 2025 UNY.md` | Aturan resmi PLK, persyaratan, jadwal | Compliance PLK |
| `Panduan/WIP - Panduan Dashboard PLK.md` | Cara daftar PLK via dashboard online | Teknis pendaftaran |
| `Panduan/UNY Mengabdi - Panduan Lengkap.md` | Ringkasan lengkap semua panduan | Quick reference |

## Fakta Penting yang Harus Diketahui Agent

### Tentang PLK UNY
- PLK = setara KKN, konversi 10-20 SKS
- Dilaksanakan semester 6 (sekitar Februari–Juli 2027)
- Tim harus terdiri dari **minimal 10 orang dari minimal 2 prodi berbeda** per 2 mahasiswa
- Setiap prodi diwakili **minimal 2 mahasiswa** dalam satu tim
- Ada kategori: UNY Mengabdi (pengabdian masyarakat), UNY Riset, UNY MBKM, dll.
- Tim kita targetkan: **UNY Mengabdi**

### Tentang Analisa Oprec
- Data dari 36 posting open recruitment di grup angkatan 2024
- **Temuan terpenting**: Mahasiswa laki-laki FT = paling langka dan paling dicari
- Tim PTI (FT, laki-laki) = bargaining power tertinggi dalam merger tim
- Prodi over-supply: Pend. IPA, Fisika, Akuntansi, Matematika
- Prodi under-supply tapi dibutuhkan: Ilmu Komunikasi, Pend. Seni Rupa, TI

### Rekomendasi 6 Anggota Sisa
| Slot | Prodi | Peran |
|:----:|-------|-------|
| 5 | Biologi / Statistika (FMIPA) | Data Analis / Pemberdayaan |
| 6 | Biologi / Statistika (FMIPA) | Surveyor / Lingkungan |
| 7 | Ilmu Komunikasi (FISHIPOL) | Konten/PR |
| 8 | Ilmu Komunikasi (FISHIPOL) | Humas/Sosialisasi |
| 9 | Manajemen / PADP (FEB) | Project Coordinator / Arsip |
| 10 | Manajemen / PADP (FEB) | Bendahara / Keuangan |

## Panduan untuk Agent: Cara Membantu

### Jika ditanya tentang rekrutmen anggota:
1. Baca `Riset/analisa oprec.md` untuk konteks supply/demand prodi
2. Cross-reference dengan `Riset/Daftar Fakultas dan Prodi S1 UNY.md` untuk data animo
3. Prioritaskan slot yang belum terisi (5–10)

### Jika ditanya tentang teknis PLK:
1. Baca `Panduan/Panduan PLK 2025 UNY.md` untuk aturan resmi
2. Baca `Panduan/WIP - Panduan Dashboard PLK.md` untuk teknis pendaftaran
3. Refer ke `Panduan/UNY Mengabdi - Panduan Lengkap.md` untuk quick answer

### Jika diminta analisa data baru (posting oprec, dll):
1. Parse posting menjadi tabel: existing team | yang dicari | CP
2. Update `Riset/analisa oprec.md` — tambah ke bagian "Data Mentah"
3. Update ranking frekuensi jika ada perubahan signifikan

### Format output yang disukai:
- Gunakan tabel markdown untuk data terstruktur
- Gunakan emoji sebagai visual indicator (🔴 kritis, 🟠 penting, 🟡 sedang, 🟢 aman)
- Wikilinks Obsidian: `[[nama file]]` untuk referensi antar note
- Frontmatter YAML di setiap note baru

## Konvensi Vault

### Frontmatter YAML (wajib di setiap note baru)
```yaml
---
tags: [plk, uny, mengabdi]
created: YYYY-MM-DD
status: draft | active | selesai
---
```

### Tag yang digunakan
- `#plk` — semua yang berkaitan PLK
- `#uny` — data/info UNY resmi
- `#tim` — catatan tentang anggota tim
- `#oprec` — data open recruitment
- `#panduan` — panduan/prosedur resmi
- `#riset` — analisa dan temuan riset

### Wikilinks penting
- `[[Home]]` — kembali ke dashboard
- `[[analisa oprec]]` — analisa recruitment
- `[[Panduan PLK 2025 UNY]]` — panduan resmi
- `[[Daftar Fakultas dan Prodi S1 UNY]]` — referensi prodi

---

*File ini otomatis dibaca oleh AI agent saat membantu proyek ini.*
*Update file ini jika ada perubahan komposisi tim atau tujuan proyek.*
