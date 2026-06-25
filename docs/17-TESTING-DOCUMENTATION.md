# JDI KOSKITA

> **Testing Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Testing Documentation        |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website, Android & Firebase  |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                   |
| ------- | --------- | ----------------------------- |
| 1.0     | June 2026 | Initial Testing Documentation |

---

# 1. Tujuan

Dokumen ini menjadi pedoman pengujian seluruh modul JDI KOSKITA untuk memastikan sistem berjalan sesuai kebutuhan bisnis, aman, stabil, dan siap digunakan pada lingkungan produksi.

---

# 2. Ruang Lingkup Pengujian

Pengujian mencakup:

* Website Publik
* Portal Admin
* Portal Member
* Aplikasi Android
* Firebase Authentication
* Cloud Firestore
* Firebase Storage
* Cloud Functions
* Firebase Hosting
* Firebase Cloud Messaging

---

# 3. Jenis Pengujian

## Unit Testing

Menguji fungsi atau komponen secara individual.

Contoh:

* Validasi Login
* Hitung Tagihan
* Hitung Diskon
* Generate Invoice

---

## Integration Testing

Menguji komunikasi antar modul.

Contoh:

* Booking → Invoice
* Invoice → Payment
* Payment → Dashboard
* Complaint → Maintenance

---

## System Testing

Menguji keseluruhan sistem sebagai satu kesatuan.

Contoh:

* Booking hingga penghuni menempati kamar.
* Pembayaran hingga laporan keuangan.

---

## User Acceptance Testing (UAT)

Pengujian oleh pengguna akhir untuk memastikan sistem memenuhi kebutuhan operasional.

---

# 4. Modul yang Diuji

| Modul          | Status  |
| -------------- | ------- |
| Authentication | Pending |
| Dashboard      | Pending |
| Building       | Pending |
| Floor          | Pending |
| Room           | Pending |
| Booking        | Pending |
| Member         | Pending |
| Payment        | Pending |
| Invoice        | Pending |
| Contract       | Pending |
| Complaint      | Pending |
| Maintenance    | Pending |
| CMS            | Pending |
| Reports        | Pending |
| Notifications  | Pending |

---

# 5. Functional Testing

Seluruh fungsi utama diuji, antara lain:

* Login
* Logout
* Register
* Booking
* Pembayaran
* Upload Bukti Transfer
* Verifikasi Pembayaran
* Kontrak Digital
* Pengaduan
* Maintenance
* Broadcast
* CMS
* Dashboard
* Laporan

---

# 6. UI Testing

Pastikan:

* Layout konsisten.
* Responsive.
* Tidak ada tombol rusak.
* Form mudah digunakan.
* Navigasi jelas.

---

# 7. Responsive Testing

Pengujian dilakukan pada:

| Device  | Status  |
| ------- | ------- |
| Mobile  | Pending |
| Tablet  | Pending |
| Laptop  | Pending |
| Desktop | Pending |

---

# 8. Browser Compatibility

Website harus berjalan pada:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari

---

# 9. Android Compatibility

Minimal mendukung:

* Android 10
* Android 11
* Android 12
* Android 13
* Android 14

---

# 10. Firebase Testing

Pastikan:

* Authentication berhasil.
* Firestore dapat membaca dan menulis data.
* Storage dapat upload dan download file.
* Cloud Functions berjalan.
* FCM mengirim notifikasi.
* Security Rules berfungsi sesuai hak akses.

---

# 11. Security Testing

Lakukan pengujian terhadap:

* Login tanpa autentikasi.
* Hak akses pengguna.
* Upload file tidak valid.
* Validasi input.
* Akses data lintas pengguna.
* Pengujian Firebase Security Rules.

---

# 12. Performance Testing

Uji:

* Kecepatan login.
* Waktu muat dashboard.
* Kecepatan pencarian kamar.
* Upload gambar.
* Generate laporan.
* Generate invoice.

Target:

* Login < 3 detik.
* Dashboard < 2 detik.
* Query Firestore < 1 detik (rata-rata).

---

# 13. Stress Testing

Simulasikan:

* Banyak pengguna login bersamaan.
* Banyak booking dalam waktu yang sama.
* Upload file besar.
* Broadcast ke seluruh penghuni.

---

# 14. Backup & Recovery Testing

Pastikan:

* Backup database dapat dipulihkan.
* File di Storage dapat dipulihkan.
* Konfigurasi sistem dapat dikembalikan.

---

# 15. Bug Report Template

| Field     | Keterangan                     |
| --------- | ------------------------------ |
| Bug ID    | Nomor Bug                      |
| Modul     | Nama Modul                     |
| Deskripsi | Penjelasan Bug                 |
| Severity  | Low / Medium / High / Critical |
| Reporter  | Nama Penguji                   |
| Status    | Open / Fixed / Closed          |

---

# 16. Test Case Template

| Field            | Keterangan              |
| ---------------- | ----------------------- |
| Test ID          | TC-001                  |
| Modul            | Booking                 |
| Skenario         | Booking kamar tersedia  |
| Langkah Uji      | Isi data → Klik Booking |
| Hasil Diharapkan | Booking berhasil        |
| Hasil Aktual     | Diisi saat pengujian    |
| Status           | Pass / Fail             |

---

# 17. Acceptance Criteria

Sistem dinyatakan siap dipublikasikan apabila:

* Seluruh test case berstatus **Pass**.
* Tidak ada bug kategori **Critical**.
* Tidak ada bug kategori **High** yang belum diperbaiki.
* Firebase Security Rules telah diverifikasi.
* Tidak ditemukan error pada Console Browser.
* Seluruh fitur utama berjalan normal.

---

# 18. Tools Pengujian

Gunakan:

* Google Chrome DevTools
* Firebase Emulator Suite
* Firebase Console
* Android Studio Emulator
* Visual Studio Code
* GitHub Issues

---

# 19. Ringkasan

Seluruh fitur JDI KOSKITA wajib melalui proses pengujian sebelum digabungkan ke branch **main** dan dipublikasikan ke lingkungan produksi. Dokumentasi pengujian menjadi acuan kualitas agar sistem tetap stabil, aman, dan memenuhi kebutuhan pengguna.

---

# 📌 Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Last Update   | June 2026                    |
| Next Document | 18-USER-MANUAL.md            |

---
