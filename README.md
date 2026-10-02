# SISABI — Sistem Assessment Rehabilitasi Lapas Kelas III Batulicin

SISABI adalah aplikasi assessment rehabilitasi untuk Lapas Kelas III Batulicin.

## Modul
- Dashboard
- Skrining P1–P8
- WHOQOL
- URICA
- Profil peserta
- Riwayat assessment
- Login/role Petugas dan Admin
- Viewer tanpa login

## Struktur repository

```text
SISABI/
├── index.html
├── README.md
└── apps-script/
    └── README.md
```

## Penting: GitHub Pages vs Google Apps Script

File `index.html` ini adalah **versi produksi SISABI yang digunakan di Google Apps Script**.

Backend SISABI menggunakan Google Apps Script melalui `google.script.run`. Karena itu:

- Repository GitHub dapat digunakan sebagai tempat menyimpan/versioning source code.
- `index.html` dapat dibuka sebagai source HTML.
- Jika `index.html` dipasang langsung sebagai GitHub Pages, fungsi yang membutuhkan backend Google Apps Script (login server, penyimpanan assessment, data server, profil peserta, dan dashboard server) **tidak akan berjalan seperti pada Web App Google Apps Script**.

Untuk penggunaan operasional SISABI saat ini, gunakan Web App Google Apps Script yang sudah berhasil diuji.

## Versi

Baseline: **SISABI v1.2 Production**

## Catatan keamanan

- Jangan menyimpan username/password produksi di repository.
- Jangan commit credential, token, atau data peserta.
- Data peserta/assessment sebaiknya tetap berada di Google Spreadsheet/Apps Script dan tidak dimasukkan ke GitHub.
