# JDI KOSKITA

> **System Architecture Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | System Architecture          |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website, Android & Firebase  |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                               |
| ------- | --------- | ----------------------------------------- |
| 1.0     | June 2026 | Initial System Architecture Documentation |

---

# 1. Pendahuluan

Dokumen ini menjelaskan arsitektur teknis JDI KOSKITA yang dibangun menggunakan Firebase Cloud Platform sebagai Backend-as-a-Service (BaaS).

Arsitektur dirancang agar:

* Realtime
* Cloud Native
* Modular
* Mudah dikembangkan
* Aman
* Multi Platform

Sistem akan melayani Website Publik, Portal Admin, Portal Member, dan Aplikasi Android dalam satu ekosistem yang saling terintegrasi.

---

# 2. Arsitektur Sistem

```
                        INTERNET
                            │
        ┌───────────────────┴───────────────────┐
        │                                       │
 Website Public                          Android App
        │                                       │
        └───────────────┬───────────────────────┘
                        │
                 Firebase Hosting
                        │
      ┌─────────────────┼──────────────────┐
      │                 │                  │
Authentication     Cloud Firestore    Storage
      │                 │                  │
      ├────────────┬────┼───────┬──────────┤
      │            │            │
Cloud Functions    FCM      Analytics
      │
      ▼
 Portal Admin & Portal Member
```

---

# 3. Komponen Sistem

JDI KOSKITA terdiri dari empat komponen utama.

## 3.1 Website Public

Digunakan oleh masyarakat umum untuk melihat informasi rumah kos.

Fitur:

* Landing Page
* Informasi Kos
* Daftar Gedung
* Daftar Kamar
* Galeri
* Booking Online
* Registrasi
* Login
* Upload Bukti Transfer
* Hubungi Admin
* FAQ
* Promo

---

## 3.2 Portal Member

Digunakan oleh penghuni.

Fitur:

* Dashboard
* Profil
* Tagihan
* Pembayaran
* Kontrak
* Riwayat Pembayaran
* Pengaduan
* Maintenance
* Notifikasi

---

## 3.3 Portal Admin

Digunakan oleh Admin dan Owner.

Modul:

* Dashboard
* Gedung
* Lantai
* Kamar
* Fasilitas
* Booking
* Penghuni
* Tagihan
* Pembayaran
* Inventaris
* Maintenance
* CMS
* Broadcast
* Laporan
* Pengaturan

---

## 3.4 Android App

Digunakan oleh penghuni.

Fitur:

* Login
* Booking
* Pembayaran
* Upload Bukti
* Pengaduan
* Chat Admin
* Notifikasi
* Profil

---

# 4. Teknologi yang Digunakan

## Frontend

* HTML5
* CSS3
* Bootstrap 5
* JavaScript ES6

## Android

* Kotlin
* Android Studio

## Backend

* Firebase Authentication
* Cloud Firestore
* Firebase Storage
* Firebase Hosting
* Cloud Functions
* Firebase Cloud Messaging
* Firebase Analytics

---

# 5. Firebase Architecture

## Firebase Authentication

Digunakan untuk:

* Login
* Register
* Reset Password
* Session Login

---

## Cloud Firestore

Menyimpan seluruh data:

* User
* Gedung
* Kamar
* Booking
* Pembayaran
* Pengaduan
* CMS
* Inventaris

---

## Firebase Storage

Digunakan untuk:

* Foto Gedung
* Foto Kamar
* Bukti Transfer
* Foto Pengaduan
* Banner
* Slider
* Gallery

---

## Firebase Hosting

Digunakan untuk hosting:

* Website Public
* Admin Portal
* Member Portal

---

## Cloud Functions

Digunakan untuk:

* Generate Invoice
* Reminder Tagihan
* Broadcast Notification
* Auto Cancel Booking
* Generate Laporan
* Backup

---

## Firebase Cloud Messaging

Mengirim:

* Reminder Tagihan
* Booking Berhasil
* Pembayaran Diterima
* Pengaduan Diproses
* Pengumuman

---

# 6. Authentication Flow

```
User

↓

Login

↓

Firebase Authentication

↓

UID

↓

Firestore Users Collection

↓

Role

↓

Dashboard
```

---

# 7. Role Access

| Role        | Website | Admin | Android |
| ----------- | ------- | ----- | ------- |
| Guest       | ✔       | ❌     | ❌       |
| Member      | ✔       | ❌     | ✔       |
| Admin       | ✔       | ✔     | ✔       |
| Owner       | ✔       | ✔     | ✔       |
| Super Admin | ✔       | ✔     | ✔       |

---

# 8. Data Flow

```
Website

↓

Firebase Authentication

↓

Cloud Firestore

↓

Cloud Functions

↓

Storage

↓

Android
```

---

# 9. Notification Flow

```
Booking Baru

↓

Cloud Function

↓

FCM

↓

Android

↓

Member
```

---

# 10. Keamanan Sistem

Sistem menggunakan:

* Firebase Authentication
* Firestore Security Rules
* Storage Rules
* HTTPS
* SSL
* Role Based Access Control (RBAC)
* Audit Log
* Session Validation

---

# 11. Scalability

Arsitektur mendukung:

* Multi Gedung
* Multi Owner
* Multi Cabang
* Multi Kota
* Multi Tenant (SaaS)

Tanpa perubahan besar pada struktur aplikasi.

---

# 12. Integrasi Masa Depan

Rencana integrasi:

* Payment Gateway
* QRIS
* Midtrans
* Xendit
* WhatsApp API
* Google Maps
* Google Calendar
* Smart Door Lock
* Face Recognition
* AI Chat Assistant

---

# 13. Struktur Deploy

```
Developer

↓

GitHub Repository

↓

GitHub Actions (Future)

↓

Firebase Hosting

↓

Production
```

---

# 14. Prinsip Pengembangan

JDI KOSKITA dikembangkan dengan prinsip:

* Modular Architecture
* Mobile First
* Responsive Design
* Cloud Native
* Realtime Data
* Clean Code
* Separation of Concerns
* Security First
* High Availability
* Maintainability

---

# 15. Ringkasan Arsitektur

Dengan menggunakan Firebase sebagai Backend-as-a-Service, JDI KOSKITA mampu menyediakan platform manajemen rumah kos yang cepat, aman, realtime, dan mudah dikembangkan.

Arsitektur ini mendukung Website Publik, Portal Admin, Portal Member, serta Aplikasi Android dalam satu ekosistem cloud yang terintegrasi.

---

# 📌 Document Control

| Item          | Description                    |
| ------------- | ------------------------------ |
| Status        | Planning                       |
| Maintained By | Jaya Digital Integrate (JDI)   |
| Last Update   | June 2026                      |
| Next Document | 12-PROJECT-FOLDER-STRUCTURE.md |

---
