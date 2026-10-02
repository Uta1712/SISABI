# SISABI — GitHub Pages Edition

Frontend SISABI untuk GitHub Pages dengan backend tetap menggunakan Google Apps Script dan Google Spreadsheet SISABI yang sudah berjalan.

## Arsitektur

GitHub Pages → Google Apps Script Web App `/exec` → Google Spreadsheet

Frontend tidak lagi memakai `google.script.run`. Komunikasi server menggunakan endpoint HTTP `doPost(e)` Apps Script.

## Sebelum dipublikasikan

1. Buka project Apps Script produksi SISABI.
2. Tambahkan fungsi `doPost(e)` dari:
   `apps-script/GitHub_API_Patch.gs`
3. Simpan.
4. Deploy → Manage deployments → Edit → **New version** → Deploy.
5. Pastikan Web App memakai URL produksi `/exec` yang sama dengan URL di `index.html`.
6. Upload `index.html` ke repository GitHub.
7. Aktifkan GitHub Pages dari branch/folder repository tersebut.

## Backend yang digunakan

Patch memanggil fungsi backend yang sudah ada:
- `loginSISABI`
- `logoutSISABI`
- `submitAssessment`
- `getDashboardStats`
- `getAssessmentList`
- `getParticipantRecords`
- `clearAssessmentDataServer`
- `getSessionInfo`

## Keamanan

- Password tidak ditaruh di `index.html`.
- Password dikirim hanya melalui HTTPS ke endpoint Apps Script.
- Session token berasal dari backend dan disimpan sementara di `sessionStorage` untuk UI.
- Validasi hak akses tetap dilakukan server-side oleh fungsi backend existing.
- Data assessment tetap masuk ke Google Spreadsheet.
- Jangan commit credential, token, atau data peserta ke GitHub.

## Penting

GitHub Pages hanya menjadi frontend. Database dan autentikasi produksi tetap berada di Google Apps Script/Spreadsheet.
