# JDI KOSKITA

> **Firebase Security Rules Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Firebase Security Rules      |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Database     | Firebase Cloud Firestore     |
| Platform     | Website & Android            |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                                   |
| ------- | --------- | --------------------------------------------- |
| 1.0     | June 2026 | Initial Firebase Security Rules Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan standar keamanan yang digunakan pada Firebase Cloud Firestore, Firebase Authentication, Firebase Storage, dan seluruh layanan Firebase yang digunakan oleh JDI KOSKITA.

Tujuan utamanya adalah memastikan bahwa setiap pengguna hanya dapat mengakses data sesuai hak akses (Role Based Access Control / RBAC).

---

# 2. Security Principles

JDI KOSKITA menggunakan prinsip berikut:

* Authentication Required
* Role Based Access Control (RBAC)
* Least Privilege Access
* Secure by Default
* Audit Trail
* Data Isolation
* HTTPS Only
* Firebase Security Rules

---

# 3. User Roles

| Role             | Description                         |
| ---------------- | ----------------------------------- |
| Super Admin      | Mengelola seluruh sistem            |
| Owner            | Mengelola seluruh data milik kosnya |
| Manager          | Mengawasi operasional               |
| Admin            | Mengelola operasional harian        |
| Staff            | Modul tertentu sesuai tugas         |
| Finance          | Tagihan dan pembayaran              |
| Technician       | Maintenance                         |
| Cleaning Service | Kebersihan                          |
| Security         | Data tamu                           |
| Member           | Data pribadi dan kamar sendiri      |
| Guest            | Website publik                      |

---

# 4. Authentication

Seluruh pengguna wajib login menggunakan Firebase Authentication.

Metode autentikasi:

* Email & Password
* Google Sign In (Future)
* Phone Number OTP (Future)

Setiap akun memiliki:

* uid
* email
* role
* status

---

# 5. Authorization

Hak akses berdasarkan role:

| Collection   | Guest | Member | Admin | Owner | Super Admin |
| ------------ | :---: | :----: | :---: | :---: | :---------: |
| users        |   ❌   |   Own  |   ✔   |   ✔   |      ✔      |
| buildings    |  Read |  Read  |  CRUD |  CRUD |     CRUD    |
| rooms        |  Read |  Read  |  CRUD |  CRUD |     CRUD    |
| bookings     |   ❌   |   Own  |  CRUD |  Read |     CRUD    |
| contracts    |   ❌   |   Own  |  CRUD |  Read |     CRUD    |
| invoices     |   ❌   |   Own  |  CRUD |  Read |     CRUD    |
| payments     |   ❌   |   Own  |  CRUD |  Read |     CRUD    |
| complaints   |   ❌   |   Own  |  CRUD |  Read |     CRUD    |
| maintenances |   ❌   |  Read  |  CRUD |  Read |     CRUD    |
| cms          |  Read |  Read  |  CRUD |  CRUD |     CRUD    |
| settings     |   ❌   |    ❌   |   ❌   |  Read |     CRUD    |
| logs         |   ❌   |    ❌   |   ❌   |   ❌   |     CRUD    |

---

# 6. Firestore Security Strategy

Setiap request akan diperiksa berdasarkan:

* User Authentication
* User Role
* Resource Ownership
* Data Validation
* Document Reference

---

# 7. Contoh Security Rules

## Semua pengguna harus login

```javascript
match /{document=**} {
  allow read, write: if request.auth != null;
}
```

---

## User hanya boleh membaca profil sendiri

```javascript
match /users/{userId} {
  allow read, update: if request.auth.uid == userId;
}
```

---

## Admin dapat mengelola semua data

```javascript
allow read, write: if request.auth.token.role == "admin";
```

---

## Super Admin

```javascript
allow read, write: if request.auth.token.role == "super_admin";
```

---

# 8. Firebase Storage Rules

Folder utama:

```text
room-images/
profile-images/
payment-proofs/
complaints/
maintenance/
cms/
```

Aturan:

* Guest hanya dapat membaca gambar publik.
* Member hanya dapat mengunggah bukti transfer dan foto pengaduan miliknya.
* Admin dapat mengelola seluruh file.
* Super Admin memiliki akses penuh.

---

# 9. Data Validation Rules

Sebelum data disimpan:

* Email harus valid.
* Nomor telepon wajib menggunakan format internasional atau nasional yang telah ditentukan.
* Harga tidak boleh bernilai negatif.
* Diskon tidak boleh melebihi 100%.
* Tanggal check-out harus setelah check-in.
* Status harus sesuai daftar yang diizinkan.

---

# 10. Audit Trail

Semua aktivitas penting dicatat ke collection:

```text
logs/
```

Aktivitas yang dicatat:

* Login
* Logout
* Booking
* Pembayaran
* Verifikasi
* Maintenance
* Perubahan CMS
* Penghapusan Data
* Perubahan Role

---

# 11. Cloud Functions Security

Cloud Functions digunakan untuk:

* Generate Invoice
* Generate Contract
* Broadcast Notification
* Auto Cancel Booking
* Reminder Tagihan
* Backup Database
* Generate Dashboard Statistics

Cloud Functions hanya dapat dipanggil oleh pengguna yang memiliki hak akses sesuai.

---

# 12. Notification Security

Push Notification hanya dikirim kepada:

* Pemilik akun yang bersangkutan.
* Role tertentu sesuai target.
* Semua pengguna jika merupakan pengumuman umum.

---

# 13. Backup & Recovery

Strategi backup:

* Backup harian Firestore.
* Backup mingguan Storage.
* Arsip bulanan.
* Restore berdasarkan snapshot.

---

# 14. Best Practice

* Gunakan Document Reference.
* Hindari data sensitif di client.
* Selalu validasi input.
* Gunakan Firebase Emulator sebelum produksi.
* Terapkan prinsip least privilege.
* Hindari query tanpa filter yang diperlukan.

---

# 15. Future Security

Pengembangan berikutnya:

* Multi Factor Authentication (MFA)
* Single Sign-On (SSO)
* Device Management
* Session Monitoring
* Suspicious Login Detection
* Geo Location Validation
* Biometric Login
* API Rate Limiting

---

# 16. Security Checklist

Sebelum sistem dipublikasikan:

* Firebase Authentication aktif.
* Firestore Rules diuji.
* Storage Rules diuji.
* HTTPS aktif.
* Backup otomatis berjalan.
* Logging aktif.
* Audit Trail aktif.
* Cloud Functions tervalidasi.

---

# 17. Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Next Document | 11-SYSTEM-ARCHITECTURE.md    |

---
