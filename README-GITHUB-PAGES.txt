PAKET GITHUB PAGES — MONITORING PRA IZIN DPMPTSP KOTA TEGAL

FILE FRONTEND
- index.html
- assets/logo-dpmptsp.png
- assets/logo-kota-tegal.png
- assets/favicon-kota-tegal.png
- assets/favicon.ico

FILE BACKEND
- code.gs (salin isinya ke editor Apps Script yang terhubung dengan Spreadsheet)

PERBAIKAN KONEKSI
Frontend GitHub Pages meminta endpoint JSONP melalui parameter action. Code.gs terbaru menangani:
- action=getData
- action=adminLogin
- action=addData
- action=updateData
- action=deleteData
- action=adminLogout

LANGKAH WAJIB
1. Buka proyek Apps Script yang terhubung ke Spreadsheet monitoring.
2. Ganti isi Code.gs dengan file code.gs dari paket ini. Pertahankan file HTML lama jika masih dipakai untuk membuka aplikasi versi Apps Script.
3. Buka Project Settings > Script Properties. Tambahkan ADMIN_PASSWORD dengan kata sandi admin yang kuat.
4. Jalankan fungsi cekKonfigurasi dari editor Apps Script dan izinkan akses jika diminta.
5. Klik Deploy > Manage deployments.
6. Edit deployment Web app yang URL-nya sama dengan API_URL di index.html, pilih New version, lalu Deploy.
7. Pastikan Execute as: Me dan akses web app disetel sesuai kebutuhan organisasi.
8. Buka URL API berikut untuk uji baca:
   https://script.google.com/macros/s/AKfycbxhx1vevp1GZiaf6PexsCrySzLAEWJfYYi63B0oJx3CPq7IAzasKV1SdlEJ9n5DLZBG/exec?action=getData
   Hasil yang diharapkan adalah JSON dengan success:true dan data:[...].
9. Buka GitHub Pages, lalu tekan Muat Ulang.

CATATAN
- Deployment lama tidak otomatis memakai kode baru sebelum dibuat versi deployment baru.
- Endpoint harus dapat diakses dari browser publik sesuai kebijakan instansi.
- Uji tambah/edit/hapus hanya dengan data uji setelah backup Spreadsheet.
- Kata sandi admin tidak boleh diletakkan di index.html.
