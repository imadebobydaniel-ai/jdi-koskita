# JDI KOSKITA

> **API Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | API Documentation            |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website, Android & Firebase  |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description               |
| ------- | --------- | ------------------------- |
| 1.0     | June 2026 | Initial API Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan standar komunikasi antara Frontend (Website, Admin Portal, Member Portal, Android) dengan layanan Firebase yang digunakan oleh JDI KOSKITA.

Karena menggunakan **Firebase Cloud Platform**, sebagian besar operasi dilakukan melalui Firebase SDK, Cloud Firestore, Cloud Functions, dan Firebase Authentication.

---

# 2. Arsitektur API

```text
Website
        │
Android
        │
Admin Portal
        │
Member Portal
        │
Firebase SDK
        │
────────────────────────────
Firebase Authentication
Cloud Firestore
Firebase Storage
Cloud Functions
Firebase Cloud Messaging
────────────────────────────
```

---

# 3. Authentication API

## Login

Service:

```text
Firebase Authentication
```

Input:

| Field    | Type   |
| -------- | ------ |
| email    | string |
| password | string |

Output:

```json
{
  "uid":"xxxxxxxx",
  "email":"user@email.com",
  "role":"member",
  "token":"firebase-token"
}
```

---

## Register

Input:

* Nama
* Email
* Password
* Nomor HP

Output:

* UID
* Email
* Status Aktif

---

## Logout

Menghapus session pengguna.

---

## Reset Password

Mengirim email reset password.

---

# 4. User API

Collection:

```text
users
```

Operasi:

* Create User
* Read User
* Update User
* Delete User (Soft Delete)
* Upload Photo Profile

---

# 5. Building API

Collection:

```text
buildings
```

Operasi:

* Tambah Gedung
* Edit Gedung
* Hapus Gedung
* Daftar Gedung
* Detail Gedung

---

# 6. Floor API

Collection:

```text
floors
```

Operasi:

* Tambah Lantai
* Edit Lantai
* Hapus Lantai
* Daftar Lantai

---

# 7. Room API

Collection:

```text
rooms
```

Operasi:

* Tambah Kamar
* Edit Kamar
* Upload Foto
* Update Harga
* Update Diskon
* Update Status
* Hapus Kamar

---

# 8. Booking API

Collection:

```text
bookings
```

Operasi:

* Booking Baru
* Batalkan Booking
* Konfirmasi Booking
* Riwayat Booking
* Detail Booking

---

# 9. Contract API

Collection:

```text
contracts
```

Operasi:

* Generate Kontrak
* Perpanjang Kontrak
* Berakhir
* Download PDF

---

# 10. Invoice API

Collection:

```text
invoices
```

Operasi:

* Generate Invoice
* Detail Invoice
* Riwayat Invoice
* Status Invoice

---

# 11. Payment API

Collection:

```text
payments
```

Operasi:

* Upload Bukti Transfer
* Verifikasi Pembayaran
* Riwayat Pembayaran
* Cetak Bukti

---

# 12. Complaint API

Collection:

```text
complaints
```

Operasi:

* Tambah Pengaduan
* Upload Foto
* Update Status
* Riwayat Pengaduan

---

# 13. Maintenance API

Collection:

```text
maintenances
```

Operasi:

* Jadwalkan Maintenance
* Update Progress
* Upload Dokumentasi
* Selesaikan Maintenance

---

# 14. CMS API

Collection:

```text
cms
```

Modul:

* Banner
* Slider
* Gallery
* Promo
* FAQ
* Artikel
* Testimoni

Operasi:

* Create
* Read
* Update
* Delete
* Publish
* Unpublish

---

# 15. Notification API

Menggunakan:

```text
Firebase Cloud Messaging
```

Jenis notifikasi:

* Booking
* Pembayaran
* Tagihan
* Kontrak
* Pengaduan
* Maintenance
* Pengumuman

---

# 16. File Upload API

Firebase Storage

Folder:

```text
profile-images/
room-images/
building-images/
payment-proofs/
complaints/
cms/
documents/
```

File yang didukung:

* JPG
* PNG
* WEBP
* PDF

---

# 17. Cloud Functions API

Digunakan untuk:

* Generate Invoice
* Generate Contract
* Reminder Tagihan
* Auto Cancel Booking
* Broadcast Notification
* Backup Data
* Dashboard Statistics

---

# 18. Response Standard

## Success

```json
{
  "success": true,
  "message": "Operation successful",
  "data": {}
}
```

---

## Error

```json
{
  "success": false,
  "message": "Operation failed",
  "error": "Error description"
}
```

---

# 19. HTTP Status Mapping

| Status | Arti                  |
| ------ | --------------------- |
| 200    | Success               |
| 201    | Created               |
| 400    | Bad Request           |
| 401    | Unauthorized          |
| 403    | Forbidden             |
| 404    | Not Found             |
| 500    | Internal Server Error |

Catatan: Untuk operasi Firebase SDK, status ini dipetakan dari hasil proses aplikasi dan Cloud Functions.

---

# 20. Validasi Data

Seluruh input wajib divalidasi:

* Required Field
* Format Email
* Nomor Telepon
* Harga Positif
* Diskon 0–100%
* Upload File
* Status Data

---

# 21. Versioning

Versi API mengikuti format:

```text
v1
v2
v3
```

Untuk Cloud Functions gunakan pola:

```text
functions/v1/
```

---

# 22. Best Practice

* Gunakan Firebase SDK.
* Hindari query berulang.
* Gunakan transaksi untuk pembayaran.
* Terapkan Firestore Security Rules.
* Gunakan Timestamp Server.
* Simpan file hanya di Firebase Storage.
* Selalu tangani error dan tampilkan pesan yang jelas kepada pengguna.

---

# 23. Ringkasan

Seluruh modul JDI KOSKITA menggunakan pendekatan API berbasis Firebase sehingga Website, Admin Portal, Member Portal, dan Android dapat berbagi data secara realtime, aman, dan konsisten.

---

# 📌 Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Last Update   | June 2026                    |
| Next Document | 16-DEPLOYMENT-GUIDE.md       |

---
