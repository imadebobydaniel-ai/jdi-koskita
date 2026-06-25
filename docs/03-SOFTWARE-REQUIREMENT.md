# JDI KOSKITA

> **Software Requirement Specification (SRS)**

---

## 📄 Document Information

| Item             | Description                        |
| ---------------- | ---------------------------------- |
| **Product Name** | JDI KOSKITA                        |
| **Document**     | Software Requirement Specification |
| **Version**      | 1.0                                |
| **Developer**    | Jaya Digital Integrate (JDI)       |
| **Platform**     | Website & Android                  |
| **Database**     | Firebase Cloud Firestore           |
| **Status**       | Planning                           |

---

## 📑 Document Version

| Version | Date      | Author                       | Description                                |
| ------- | --------- | ---------------------------- | ------------------------------------------ |
| 1.0     | June 2026 | Jaya Digital Integrate (JDI) | Initial Software Requirement Specification |

---

## 🎯 Document Objective

Dokumen ini menjelaskan kebutuhan teknis perangkat lunak yang akan dikembangkan untuk produk **JDI KOSKITA**. Dokumen ini menjadi acuan bagi tim pengembang dalam merancang database, antarmuka, backend, keamanan, integrasi, serta implementasi aplikasi Website dan Android.

---

# 1. System Overview

JDI KOSKITA merupakan sistem manajemen rumah kos berbasis cloud yang terdiri dari Website Publik, Portal Admin, Portal Member, Content Management System (CMS), dan Aplikasi Android. Seluruh data tersimpan secara realtime menggunakan Firebase Cloud Platform sehingga dapat diakses secara aman dari berbagai perangkat.

---

# 2. Software Architecture

Sistem terdiri dari beberapa komponen utama:

* Website Public
* Admin Portal
* Member Portal
* CMS
* Android Application
* Firebase Authentication
* Firebase Cloud Firestore
* Firebase Storage
* Firebase Hosting
* Firebase Cloud Messaging (FCM)
* Cloud Functions (Future Development)

---

# 3. System Modules

Modul utama yang akan dikembangkan meliputi:

## Public Website

* Landing Page
* Informasi Kos
* Gallery
* Daftar Kamar
* Detail Kamar
* Booking Online
* Hubungi Admin
* Upload Bukti Transfer
* Login
* Registrasi

## Admin Portal

* Dashboard
* Manajemen Gedung
* Manajemen Lantai
* Manajemen Kamar
* Manajemen Fasilitas
* Manajemen Penghuni
* Manajemen Booking
* Tagihan
* Pembayaran
* Kontrak Digital
* Maintenance
* Inventaris
* Broadcast
* CMS
* Laporan
* Pengaturan Sistem

## Member Portal

* Dashboard
* Profil
* Status Kontrak
* Tagihan
* Pembayaran
* Riwayat Pembayaran
* Pengaduan
* Notifikasi

## Android

* Login
* Dashboard
* Booking
* Pembayaran
* Upload Bukti Transfer
* Pengaduan
* Notifikasi
* Profil

---

# 4. Authentication

Sistem menggunakan Firebase Authentication dengan metode:

* Email & Password
* Google Sign In (Future)
* Phone Number OTP (Future)

Role pengguna:

* Super Admin
* Owner
* Admin
* Staff
* Teknisi
* Member
* Guest

---

# 5. Authorization

Setiap role memiliki hak akses berbeda.

Contoh:

| Role        | Access                    |
| ----------- | ------------------------- |
| Super Admin | Full Access               |
| Owner       | Seluruh data kos miliknya |
| Admin       | Operasional harian        |
| Staff       | Modul tertentu            |
| Teknisi     | Maintenance               |
| Member      | Data pribadi              |
| Guest       | Website Public            |

---

# 6. Functional Requirements

Sistem harus mampu:

* Login
* Logout
* Register
* Reset Password
* Booking Kamar
* Verifikasi Booking
* Upload Bukti Transfer
* Generate Tagihan
* Generate Kontrak Digital
* Kelola Inventaris
* Kelola Pengaduan
* Broadcast Pengumuman
* CMS Website
* Dashboard Statistik
* Export Laporan

---

# 7. Non Functional Requirements

Sistem harus memenuhi spesifikasi berikut:

* Responsive Design
* Mobile Friendly
* Realtime Database
* High Availability
* Secure Authentication
* Cloud Storage
* Automatic Backup
* Fast Loading
* Scalability
* Multi Device

---

# 8. Security Requirements

Sistem harus memiliki:

* Authentication
* Authorization
* Firestore Security Rules
* Storage Security Rules
* HTTPS Only
* SSL
* Audit Log
* Session Management

---

# 9. Performance Requirements

Target performa sistem:

* Login < 3 detik
* Dashboard < 3 detik
* Booking < 5 detik
* Upload Bukti Transfer < 10 detik
* Realtime Update < 2 detik

---

# 10. User Interface Requirements

Antarmuka harus:

* Modern
* Responsive
* Clean Design
* Bootstrap 5
* Mobile First
* Mudah digunakan
* Konsisten pada Website dan Android

---

# 11. Integration Requirements

Sistem dirancang agar dapat diintegrasikan dengan:

* Firebase Cloud Platform
* WhatsApp API (Future)
* Payment Gateway (Future)
* Google Maps
* Google Analytics
* QR Code
* Email Service

---

# 12. Technology Stack

| Layer          | Technology                           |
| -------------- | ------------------------------------ |
| Frontend       | HTML5, CSS3, Bootstrap 5, JavaScript |
| Backend        | Firebase                             |
| Database       | Cloud Firestore                      |
| Authentication | Firebase Auth                        |
| Storage        | Firebase Storage                     |
| Hosting        | Firebase Hosting                     |
| Android        | Android Studio (Java/Kotlin)         |

---

# 13. Future Enhancement

Pengembangan berikutnya:

* Multi Tenant
* SaaS Platform
* AI Chat Assistant
* Face Recognition
* Smart Door Lock
* IoT Monitoring
* Business Intelligence Dashboard

---

# 14. Document Control

| Item              | Description                  |
| ----------------- | ---------------------------- |
| **Status**        | Planning                     |
| **Maintained By** | Jaya Digital Integrate (JDI) |
| **Next Document** | 04-BUSINESS-PROCESS.md       |

---
