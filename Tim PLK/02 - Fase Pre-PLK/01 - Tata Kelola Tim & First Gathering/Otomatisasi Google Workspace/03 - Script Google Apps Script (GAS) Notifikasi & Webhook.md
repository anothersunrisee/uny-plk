---
tags: [google-apps-script, gas, javascript, webhook, whatsapp, telegram, otomatisasi, bot]
created: 2026-10-26
status: active
author: Tim Nirantara PLK UNY 2027
---

# 🤖 SCRIPT GOOGLE APPS SCRIPT (GAS) NOTIFIKASI & WEBHOOK
## **Otomatisasi Kirim Notifikasi WhatsApp, Email, & Webhook Saat Form Diisi atau Data Berubah**

---

## 💡 Apa Itu Google Apps Script (GAS)?

Google Apps Script (GAS) adalah platform pemrograman berbasis **JavaScript** yang berjalan di server cloud Google secara **100% gratis**.

Dengan GAS, kita bisa membuat otomatisasi canggih seperti:
- Setiap kali ada anggota mengunggah nota belanja di Form, bot otomatis mengirim pesan ke grup:  
  *"🔔 PENGELUARAN BARU! PIC: Riski | Item: Beli Sapu & Pel | Nominal: Rp 80.000,-"*.
- Mengirim email notifikasi otomatis ke Bendahara atau Ketua tim.
- Mencatat tanggal dan jam secara otomatis (*Auto-Timestamp*) saat suatu sel dicentang.

---

## 📜 Script 1: Notifikasi WhatsApp Otomatis (Saat Form Nota / Oprec Di-Submit)

Script ini membaca baris baru yang masuk dari Google Form, lalu mengirim notifikasi ke WhatsApp menggunakan Webhook gateway (misalnya Fonnte / Wablas yang gratis atau bot Telegram / Discord).

### Kode Script (Google Apps Script):

```javascript
/**
 * NIRANTARA BOT — Notifikasi WhatsApp Otomatis saat Form Di-submit
 * Ditempel di: Extensions -> Apps Script pada Google Sheets Respon Form
 */

// GANTI DENGAN DATA TIM NIRANTARA:
const WA_API_TOKEN = "TOKEN_FONNTE_ATAU_GATEWAY_KAMU"; // Daftar gratis di fonnte.com
const TARGET_WHATSAPP = "08xxxxxxxxxx"; // Nomor HP Bendahara atau ID Grup WA Tim

function onFormSubmitNotification(e) {
  try {
    // Ambil data baris yang baru saja disubmit
    const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    const lastRow = sheet.getLastRow();
    
    // Asumsi Urutan Kolom:
    // Kolom A: Timestamp | B: Tanggal | C: Nama Anggota | D: Kategori | E: Uraian Barang | F: Nominal | G: Link Foto Struk
    const timestamp = sheet.getRange(lastRow, 1).getValue();
    const tglBelanja = sheet.getRange(lastRow, 2).getValue();
    const namaAnggota = sheet.getRange(lastRow, 3).getValue();
    const kategori = sheet.getRange(lastRow, 4).getValue();
    const uraian = sheet.getRange(lastRow, 5).getValue();
    const nominal = sheet.getRange(lastRow, 6).getValue();
    const linkBukti = sheet.getRange(lastRow, 7).getValue();

    // Format nominal ke Rupiah
    const nominalFormatted = "Rp " + Number(nominal).toLocaleString("id-ID");

    // Susun Pesan WhatsApp yang Rapi & Estetik
    const pesanWA = 
      "🔔 *[NOTIFIKASI PENGELUARAN KAS NIRANTARA]*\n" +
      "━━━━━━━━━━━━━━━━━━━━━━\n" +
      "📅 *Tanggal:* " + Utilities.formatDate(new Date(tglBelanja), "Asia/Jakarta", "dd MMMM yyyy") + "\n" +
      "👤 *PIC Belanja:* " + namaAnggota + "\n" +
      "🏷️ *Kategori:* " + kategori + "\n" +
      "📦 *Rincian Barang:* " + uraian + "\n" +
      "💰 *Total Biaya:* *" + nominalFormatted + "*\n" +
      "📎 *Bukti Struk/Nota:* " + linkBukti + "\n" +
      "━━━━━━━━━━━━━━━━━━━━━━\n" +
      "⚡ _Status: Menunggu verifikasi Bendahara (Faidatul/Zalfa)_";

    // Kirim ke WhatsApp Gateway (Contoh endpoint Fonnte API)
    const payload = {
      target: TARGET_WHATSAPP,
      message: pesanWA,
      countryCode: "62"
    };

    const options = {
      method: "post",
      payload: payload,
      headers: {
        Authorization: WA_API_TOKEN
      },
      muteHttpExceptions: true
    };

    const response = UrlFetchApp.fetch("https://api.fonnte.com/send", options);
    Logger.log("Respon API: " + response.getContentText());

  } catch (error) {
    Logger.log("Terjadi Error: " + error.toString());
  }
}
```

---

## ✉️ Script 2: Notifikasi Email Otomatis ke Bendahara & Ketua (Tanpa API Eksternal)

Jika belum ingin menggunakan gateway WhatsApp pihak ketiga, kamu bisa menggunakan fitur bawaan Google yang **100% bawaan tanpa daftar apa pun**: mengirim email otomatis ke `nirantara.plk.uny@gmail.com`.

### Kode Script (Google Apps Script):

```javascript
/**
 * Notifikasi Email Bawaan Google (Gratis & Tanpa Tool Tambahan)
 */
function sendEmailNotification(e) {
  const emailTujuan = "nirantara.plk.uny@gmail.com";
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const lastRow = sheet.getLastRow();

  const nama = sheet.getRange(lastRow, 3).getValue();
  const item = sheet.getRange(lastRow, 5).getValue();
  const nominal = sheet.getRange(lastRow, 6).getValue();
  const linkBukti = sheet.getRange(lastRow, 7).getValue();

  const subjek = "[KAS NIRANTARA] Laporan Nota Baru: " + nama + " (" + item + ")";
  const bodyHTML = `
    <div style="font-family: Arial, sans-serif; padding: 20px; border: 1px solid #1B4D3E; border-radius: 8px;">
      <h2 style="color: #1B4D3E;">Laporan Pengeluaran Kas Masuk</h2>
      <p>Halo Tim Bendahara Nirantara, ada laporan belanja baru yang perlu diverifikasi:</p>
      <table style="width: 100%; border-collapse: collapse;">
        <tr><td style="padding: 8px; font-weight: bold;">Nama PIC</td><td>: ${nama}</td></tr>
        <tr><td style="padding: 8px; font-weight: bold;">Uraian Belanja</td><td>: ${item}</td></tr>
        <tr><td style="padding: 8px; font-weight: bold;">Nominal</td><td>: <b>Rp ${Number(nominal).toLocaleString('id-ID')}</b></td></tr>
      </table>
      <p style="margin-top: 15px;">
        <a href="${linkBukti}" style="background-color: #1B4D3E; color: white; padding: 10px 15px; text-decoration: none; border-radius: 5px;">Buka Foto Bukti Struk</a>
      </p>
    </div>
  `;

  MailApp.sendEmail({
    to: emailTujuan,
    subject: subjek,
    htmlBody: bodyHTML
  });
}
```

---

## ⏱️ Script 3: Auto-Timestamp Saat Kotak Centang [x] Diklik

Script ini sangat berguna di spreadsheet `Master_Keuangan_Nirantara` atau `Master_Inventaris`. Saat bendahara mencentang kolom *Status Lunas / Terverifikasi*, kolom tanggal di sebelahnya **otomatis mencatat tanggal dan jam saat itu juga secara permanen**:

```javascript
/**
 * Auto-Timestamp Saat Checkbox Dicentang
 * Berjalan otomatis pada event onEdit
 */
function onEdit(e) {
  const sheet = e.source.getActiveSheet();
  const range = e.range;
  
  // Hanya berlaku di sheet "Rekap Iuran Kas"
  if (sheet.getName() === "Rekap Iuran Kas") {
    const col = range.getColumn();
    const row = range.getRow();

    // Jika yang diedit adalah kolom centang Lunas (misal Kolom L, baris 5 ke bawah)
    if (col === 12 && row >= 5 && range.getValue() === true) {
      const cellTanggal = sheet.getRange(row, 13); // Tulis di Kolom M (Catatan/Tanggal)
      const waktuSekarang = Utilities.formatDate(new Date(), "Asia/Jakarta", "dd/MM/yyyy HH:mm");
      cellTanggal.setValue("Diverifikasi: " + waktuSekarang);
    }
  }
}
```

---

## 🛠️ Tutorial Langkah Memasang Script di Google Spreadsheet

Hanya butuh 2 menit untuk mengaktifkan script ini:

```
[Buka Google Sheets] ──> [Menu Ekstensi] ──> [Apps Script] ──> [Paste Kode] ──> [Pasang Trigger]
```

1. Buka spreadsheet target di browser (misal file *Master Keuangan* atau file *Respon Form*).
2. Di menu atas, klik **Ekstensi (Extensions)** $\rightarrow$ pilih **Apps Script**.
3. Tab editor kode akan terbuka. Hapus kode default `function myFunction() {}`.
4. **Copy-paste** salah satu kode script di atas ke dalam editor.
5. Klik ikon **Simpan (Save / gambar disket)** di bagian atas atau tekan `Ctrl + S`. Beri nama proyek: `NirantaraAutomation`.

### Menghubungkan Trigger (Pemicu Otomatis):
Agar script berjalan otomatis saat ada respon form baru masuk:
1. Di bilah menu sebelah kiri Apps Script, klik ikon **Jam Dinding (Pemicu / Triggers)**.
2. Klik tombol biru **+ Tambahkan Pemicu (+ Add Trigger)** di kanan bawah.
3. Atur pengaturannya sebagai berikut:
   - **Pilih fungsi yang akan dijalankan**: Pilih `onFormSubmitNotification` atau `sendEmailNotification`.
   - **Pilih sumber acara**: `Dari spreadsheet (From spreadsheet)`.
   - **Pilih jenis acara**: 👉 **Saat mengirim formulir (On form submit)**.
4. Klik **Simpan (Save)**.
5. Google akan meminta izin keamanan satu kali (*Review permissions*). Klik akun Google-mu $\rightarrow$ Klik *Advanced* $\rightarrow$ Klik *Go to NirantaraAutomation (unsafe)* $\rightarrow$ Klik **Allow**.
6. **Selesai!** Sekarang setiap ada pengisian form, otomatisasi langsung berjalan di latar belakang tanpa ada yang perlu membuka laptop.
