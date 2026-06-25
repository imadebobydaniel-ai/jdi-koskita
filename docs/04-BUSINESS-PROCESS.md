# JDI KOSKITA

> **Business Process Document**

---

## 📄 Document Information

| Item             | Description                  |
| ---------------- | ---------------------------- |
| **Product Name** | JDI KOSKITA                  |
| **Document**     | Business Process             |
| **Version**      | 1.0                          |
| **Developer**    | Jaya Digital Integrate (JDI) |
| **Status**       | Planning                     |

---

## 📑 Document Version

| Version | Date      | Author                       | Description                            |
| ------- | --------- | ---------------------------- | -------------------------------------- |
| 1.0     | June 2026 | Jaya Digital Integrate (JDI) | Initial Business Process Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan alur proses bisnis yang terjadi pada sistem **JDI KOSKITA**, mulai dari calon penghuni mencari kamar hingga proses pembayaran, pengelolaan kontrak, maintenance, dan laporan keuangan.

---

# 2. Aktor Sistem

Aktor yang terlibat dalam proses bisnis:

* Guest
* Member
* Admin
* Owner
* Staff Operasional
* Teknisi
* Cleaning Service
* Security
* Super Administrator

---

# 3. Business Process Overview

Seluruh proses bisnis terdiri dari beberapa modul utama:

1. Promosi Kos
2. Registrasi Member
3. Booking Kamar
4. Verifikasi Pembayaran
5. Check In Penghuni
6. Pengelolaan Tagihan
7. Pengaduan & Maintenance
8. Check Out
9. Laporan Keuangan
10. CMS Website

---

# 4. Proses Pencarian Kamar

### Alur

Guest

↓

Membuka Website

↓

Melihat Daftar Kos

↓

Memilih Gedung

↓

Memilih Kamar

↓

Melihat Detail

↓

Booking

---

# 5. Proses Registrasi Member

Guest

↓

Mengisi Form Registrasi

↓

Verifikasi Email

↓

Akun Aktif

↓

Login

---

# 6. Proses Booking

Member

↓

Pilih Kamar

↓

Isi Data

↓

Submit Booking

↓

Status:

Menunggu Pembayaran

↓

Upload Bukti Transfer

↓

Admin Verifikasi

↓

Booking Disetujui

↓

Kontrak Digital Dibuat

↓

Check In

---

# 7. Proses Pembayaran

Sistem

↓

Generate Tagihan

↓

Member Melakukan Pembayaran

↓

Upload Bukti Transfer

↓

Admin Verifikasi

↓

Status Lunas

↓

Riwayat Pembayaran

---

# 8. Proses Pengaduan

Member

↓

Buat Pengaduan

↓

Admin Menerima

↓

Teknisi Ditugaskan

↓

Dalam Proses

↓

Selesai

↓

Member Memberikan Rating

---

# 9. Proses Maintenance

Admin

↓

Membuat Work Order

↓

Teknisi

↓

Perbaikan

↓

Upload Foto

↓

Selesai

↓

Owner Menyetujui

---

# 10. Proses Check Out

Member

↓

Pengajuan Check Out

↓

Pemeriksaan Inventaris

↓

Perhitungan Tagihan

↓

Pelunasan

↓

Kontrak Berakhir

↓

Status Kamar Menjadi Kosong

---

# 11. Proses CMS Website

Admin

↓

Login

↓

Kelola Banner

↓

Kelola Gallery

↓

Kelola Promo

↓

Kelola Informasi Kos

↓

Publish Website

---

# 12. Proses Dashboard

Dashboard menampilkan informasi realtime mengenai:

* Total Gedung
* Total Kamar
* Kamar Kosong
* Kamar Terisi
* Booking Hari Ini
* Pendapatan Bulan Ini
* Pengaduan Aktif
* Tagihan Belum Lunas

---

# 13. Business Process Summary

| Modul       | Status   |
| ----------- | -------- |
| Registrasi  | Digital  |
| Booking     | Online   |
| Pembayaran  | Digital  |
| Kontrak     | Digital  |
| Pengaduan   | Online   |
| Maintenance | Digital  |
| CMS         | Online   |
| Dashboard   | Realtime |

---

# 14. Document Control

| Item              | Description                  |
| ----------------- | ---------------------------- |
| **Status**        | Planning                     |
| **Maintained By** | Jaya Digital Integrate (JDI) |
| **Next Document** | 05-USECASE-DIAGRAM.md        |

---
