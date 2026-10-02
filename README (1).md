# Google Apps Script Backend

Backend SISABI tetap dijalankan di Google Apps Script.

File frontend utama di repository adalah `../index.html`.

Di project Google Apps Script:
1. Buat/pertahankan file HTML bernama `index`.
2. Tempel isi `index.html` ke file HTML tersebut.
3. `Code.gs` harus menggunakan:

```javascript
function doGet() {
  return HtmlService.createHtmlOutputFromFile('index')
    .setTitle('SISABI — Sistem Assessment Rehabilitasi Lapas Kelas III Batulicin')
    .addMetaTag('viewport', 'width=device-width, initial-scale=1');
}
```

Backend dan Spreadsheet tidak disimpan di repository ini untuk menghindari credential/data operasional ikut terpublikasi.
