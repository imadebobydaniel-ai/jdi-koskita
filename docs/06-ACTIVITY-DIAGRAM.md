# JDI KOSKITA

> **Activity Diagram Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Activity Diagram             |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website & Android            |
| Database     | Firebase Cloud Firestore     |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                            |
| ------- | --------- | -------------------------------------- |
| 1.0     | June 2026 | Initial Activity Diagram Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan alur aktivitas (Activity Flow) dari setiap proses utama pada sistem **JDI KOSKITA**. Dokumen ini menjadi acuan dalam pengembangan Website, Portal Admin, Portal Member, dan Aplikasi Android.

---

# 2. Daftar Activity Diagram

1. Registrasi Member
2. Login
3. Booking Kamar
4. Verifikasi Pembayaran
5. Check In Penghuni
6. Pembayaran Tagihan Bulanan
7. Pengaduan & Maintenance
8. Perpanjangan Kontrak
9. Check Out
10. CMS Website
11. Dashboard Admin
12. Broadcast Pengumuman

---

# 3. Activity Diagram Registrasi Member

```
Start
   │
Buka Website
   │
Klik Register
   │
Isi Form Registrasi
   │
Validasi Data
   │
Apakah Valid?
 ┌──────┴──────┐
 │             │
Tidak         Ya
 │             │
Tampilkan     Simpan Data Firebase
Error          │
 │             │
 └──────┬──────┘
        │
Kirim Verifikasi Email
        │
Aktivasi Akun
        │
Login
        │
Finish
```

---

# 4. Activity Diagram Login

```
Start
   │
Masukkan Email & Password
   │
Firebase Authentication
   │
Apakah Berhasil?
 ┌──────┴──────┐
 │             │
Tidak         Ya
 │             │
Pesan Error   Dashboard
 │             │
 └──────┬──────┘
        │
Finish
```

---

# 5. Activity Diagram Booking Kamar

```
Start
   │
Cari Kamar
   │
Lihat Detail
   │
Klik Booking
   │
Isi Data
   │
Submit Booking
   │
Generate Booking
   │
Status:
Waiting Payment
   │
Upload Bukti Transfer
   │
Verifikasi Admin
   │
Approved
   │
Generate Kontrak
   │
Check In
   │
Finish
```

---

# 6. Activity Diagram Pembayaran Bulanan

```
Start
   │
Sistem Generate Tagihan
   │
Notifikasi Member
   │
Member Transfer
   │
Upload Bukti
   │
Admin Verifikasi
   │
Update Status
   │
Lunas
   │
Riwayat Pembayaran
   │
Finish
```

---

# 7. Activity Diagram Pengaduan

```
Start
   │
Member Buat Pengaduan
   │
Admin Menerima
   │
Assign Teknisi
   │
Perbaikan
   │
Upload Dokumentasi
   │
Status Selesai
   │
Member Memberikan Rating
   │
Finish
```

---

# 8. Activity Diagram Check Out

```
Start
   │
Member Ajukan Check Out
   │
Admin Verifikasi
   │
Pemeriksaan Inventaris
   │
Hitung Tagihan Akhir
   │
Pelunasan
   │
Update Status Kamar
   │
Kamar Kosong
   │
Finish
```

---

# 9. Activity Diagram CMS Website

```
Start
   │
Admin Login
   │
Dashboard CMS
   │
Kelola Banner
Kelola Galeri
Kelola Promo
Kelola Artikel
Kelola FAQ
Kelola SEO
   │
Publish
   │
Website Update
   │
Finish
```

---

# 10. Activity Diagram Dashboard Admin

```
Start
   │
Login
   │
Dashboard
   │
Menampilkan:
• Pendapatan
• Okupansi
• Booking
• Pengaduan
• Tagihan
• Maintenance
• Grafik
   │
Realtime Firebase
   │
Finish
```

---

# 11. Activity Diagram Broadcast

```
Start
   │
Admin Membuat Pengumuman
   │
Pilih Target
   │
Publish
   │
Push Notification
   │
Member Menerima
   │
Finish
```

---

# 12. Activity Summary

| No | Activity    | Aktor          |
| -- | ----------- | -------------- |
| 1  | Registrasi  | Guest          |
| 2  | Login       | Semua User     |
| 3  | Booking     | Member         |
| 4  | Pembayaran  | Member & Admin |
| 5  | Check In    | Admin          |
| 6  | Tagihan     | Admin & Member |
| 7  | Pengaduan   | Member         |
| 8  | Maintenance | Teknisi        |
| 9  | Check Out   | Member & Admin |
| 10 | CMS         | Admin          |
| 11 | Dashboard   | Admin & Owner  |
| 12 | Broadcast   | Admin          |

---

# 13. Catatan Implementasi

Seluruh aktivitas di atas akan diimplementasikan menggunakan:

* Firebase Authentication
* Cloud Firestore
* Firebase Storage
* Firebase Cloud Messaging (FCM)
* Firebase Hosting
* Android Application
* Website Frontend
* Admin Portal

Setiap perubahan status pada proses bisnis akan disimpan secara realtime di Cloud Firestore dan langsung disinkronkan ke seluruh perangkat yang terhubung.

---

# 14. Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Next Document | 07-CLASS-DIAGRAM.md          |

---
