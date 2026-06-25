# JDI KOSKITA

> **Use Case Diagram Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Use Case Diagram             |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website & Android            |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                    |
| ------- | --------- | ------------------------------ |
| 1.0     | June 2026 | Initial Use Case Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan seluruh **Use Case** yang terdapat pada sistem **JDI KOSKITA** sebagai dasar pengembangan Website, Admin Portal, Member Portal, Android Application, Firebase Database, dan Dashboard.

---

# 2. Aktor Sistem

| No | Aktor                 |
| -- | --------------------- |
| 1  | Super Administrator   |
| 2  | Owner Kos             |
| 3  | Manager Operasional   |
| 4  | Admin Kos             |
| 5  | Staff Keuangan        |
| 6  | Teknisi               |
| 7  | Cleaning Service      |
| 8  | Security              |
| 9  | Penghuni (Member)     |
| 10 | Guest (Calon Penyewa) |

---

# 3. Modul Website Publik

### Guest

* Melihat Beranda
* Melihat Informasi Kos
* Melihat Galeri
* Melihat Daftar Gedung
* Melihat Daftar Kamar
* Filter Kamar
* Melihat Detail Kamar
* Melihat Harga
* Melihat Promo
* Melihat Fasilitas
* Melihat Lokasi Google Maps
* Menghubungi Admin
* Registrasi Member
* Login
* Booking Kamar

---

# 4. Modul Portal Member

### Member

* Login
* Dashboard
* Edit Profil
* Upload Foto Profil
* Booking Kamar
* Upload Bukti Transfer
* Melihat Status Booking
* Melihat Status Pembayaran
* Melihat Tagihan
* Download Invoice
* Download Kontrak
* Mengajukan Pengaduan
* Upload Foto Pengaduan
* Tracking Maintenance
* Melihat Pengumuman
* Chat Admin
* Mengajukan Check Out
* Melihat Riwayat Pembayaran
* Mengubah Password
* Logout

---

# 5. Modul Portal Admin

### Admin Kos

## Dashboard

* Dashboard
* Statistik Pendapatan
* Statistik Kamar
* Statistik Penghuni

## Gedung

* Tambah Gedung
* Edit Gedung
* Hapus Gedung

## Lantai

* Tambah Lantai
* Edit Lantai
* Hapus Lantai

## Kamar

* Tambah Kamar
* Edit Kamar
* Hapus Kamar
* Upload Foto
* Menentukan Harga
* Menentukan Diskon
* Menentukan Status
* Menentukan Fasilitas

## Booking

* Melihat Booking
* Verifikasi Booking
* Menolak Booking
* Approve Booking

## Penghuni

* Tambah Penghuni
* Edit Penghuni
* Perpanjang Kontrak
* Check Out

## Pembayaran

* Generate Tagihan
* Verifikasi Transfer
* Cetak Invoice
* Riwayat Pembayaran

## Pengaduan

* Melihat Pengaduan
* Assign Teknisi
* Update Status
* Menutup Pengaduan

## Inventaris

* Tambah Inventaris
* Edit Inventaris
* Penghapusan Inventaris

## CMS

* Kelola Banner
* Kelola Slider
* Kelola Galeri
* Kelola Promo
* Kelola FAQ
* Kelola Artikel
* Kelola Testimoni
* Kelola Kontak
* Kelola WhatsApp
* Kelola SEO Website

---

# 6. Modul Staff Keuangan

* Dashboard Keuangan
* Laporan Pendapatan
* Laporan Pengeluaran
* Laporan Profit
* Export PDF
* Export Excel

---

# 7. Modul Teknisi

* Login
* Daftar Work Order
* Detail Maintenance
* Upload Foto
* Update Progress
* Selesai Maintenance

---

# 8. Modul Cleaning Service

* Login
* Daftar Tugas
* Update Status
* Upload Dokumentasi

---

# 9. Modul Security

* Login
* Pendataan Tamu
* Pendataan Kendaraan
* Check In Tamu
* Check Out Tamu

---

# 10. Modul Owner

* Dashboard Executive
* Pendapatan
* Okupansi
* Laporan Keuangan
* Laporan Maintenance
* Laporan Penghuni
* Grafik Pendapatan
* Grafik Pengeluaran
* Grafik Profit
* Grafik Okupansi

---

# 11. Modul Super Administrator

* Kelola User
* Kelola Role
* Kelola Permission
* Kelola Tenant
* Kelola Paket Berlangganan
* Kelola Konfigurasi Sistem
* Monitoring Aktivitas
* Backup Database
* Restore Database
* Audit Log

---

# 12. Ringkasan Use Case

| Modul               | Jumlah Use Case |
| ------------------- | --------------: |
| Website Publik      |              14 |
| Portal Member       |              18 |
| Portal Admin        |              39 |
| Staff Keuangan      |               6 |
| Teknisi             |               6 |
| Cleaning Service    |               4 |
| Security            |               5 |
| Owner               |               9 |
| Super Administrator |              10 |

**Total Use Case : ±111 Use Case**

---

# 13. Catatan Pengembangan

Seluruh use case di atas akan digunakan sebagai acuan dalam penyusunan:

* Activity Diagram
* Class Diagram
* Entity Relationship Diagram (ERD)
* Firebase Collections
* Firebase Security Rules
* Website Frontend
* Admin Portal
* Android Application
* REST API / Firebase Service
* Dashboard Analytics

---

# 14. Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Next Document | 06-ACTIVITY-DIAGRAM.md       |

---
