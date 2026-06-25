# JDI KOSKITA

> **Coding Standards Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Coding Standards             |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website, Android & Firebase  |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                            |
| ------- | --------- | -------------------------------------- |
| 1.0     | June 2026 | Initial Coding Standards Documentation |

---

# 1. Tujuan

Dokumen ini menetapkan standar penulisan kode (Coding Standards) yang digunakan pada seluruh proyek JDI KOSKITA agar kode lebih konsisten, mudah dipahami, mudah dipelihara, dan siap dikembangkan oleh lebih dari satu developer.

---

# 2. Prinsip Pengembangan

Seluruh pengembangan mengikuti prinsip:

* Clean Code
* DRY (Don't Repeat Yourself)
* KISS (Keep It Simple, Stupid)
* SOLID Principle
* Separation of Concerns
* Modular Programming
* Reusable Components
* Secure by Design

---

# 3. Standar Penamaan

## 3.1 Folder

Gunakan huruf kecil.

Contoh:

```text
bookings/
payments/
reports/
inventory/
```

---

## 3.2 File

Gunakan **kebab-case**.

Contoh:

```text
booking-list.js
booking-detail.js
room-form.js
payment-history.js
firebase-config.js
```

---

## 3.3 Variabel

Gunakan **camelCase**.

Contoh:

```javascript
const bookingDate
const roomPrice
const memberName
const totalPayment
```

---

## 3.4 Konstanta

Gunakan **UPPER_SNAKE_CASE**.

```javascript
const MAX_ROOM = 100;
const DEFAULT_DISCOUNT = 0;
const APP_VERSION = "1.0";
```

---

## 3.5 Function

Gunakan nama yang jelas dan diawali kata kerja.

```javascript
loadRooms()
saveBooking()
calculateInvoice()
uploadTransferProof()
sendNotification()
```

---

## 3.6 Class

Gunakan **PascalCase**.

```javascript
Room
Booking
Invoice
PaymentService
FirebaseService
```

---

# 4. Struktur HTML

Setiap halaman mengikuti struktur berikut:

```html
<!DOCTYPE html>
<html>
<head></head>
<body>

<header></header>

<nav></nav>

<main></main>

<footer></footer>

<script></script>

</body>
</html>
```

---

# 5. Struktur CSS

Urutan penulisan:

* Variables
* Reset
* Typography
* Layout
* Components
* Utilities
* Responsive

---

# 6. Struktur JavaScript

Urutan file:

```text
Import

↓

Constants

↓

Variables

↓

DOM

↓

Functions

↓

Event Listener

↓

Initialization
```

---

# 7. Bootstrap Standards

Gunakan Bootstrap 5.

Komponen utama:

* Navbar
* Card
* Modal
* Toast
* Alert
* Badge
* Table
* Pagination
* Dropdown
* Accordion
* Offcanvas

---

# 8. Firebase Standards

Seluruh akses Firebase dilakukan melalui file:

```text
firebase-config.js
```

Tidak diperbolehkan menginisialisasi Firebase di banyak file.

Semua operasi Firestore menggunakan helper/service.

Contoh:

```javascript
RoomService.getRooms();
BookingService.createBooking();
PaymentService.savePayment();
```

---

# 9. Firestore Rules

* Hindari query tanpa filter.
* Gunakan Document ID yang unik.
* Gunakan Timestamp dari Firebase.
* Simpan relasi menggunakan Document Reference jika memungkinkan.
* Hindari nested document yang terlalu dalam.

---

# 10. Error Handling

Gunakan pola berikut:

```javascript
try {
    // process
} catch (error) {
    console.error(error);
}
```

Seluruh error penting dicatat ke Firebase Logging.

---

# 11. Comment Standards

Gunakan komentar seperlunya.

Contoh:

```javascript
// Load daftar kamar aktif
loadRooms();
```

Hindari komentar yang menjelaskan hal yang sudah jelas dari kode.

---

# 12. Git Commit Standards

Format commit:

```text
feat: add booking module

fix: payment calculation

docs: update firebase collection

refactor: room service

style: improve dashboard layout

test: booking validation
```

---

# 13. Branch Naming

Gunakan format:

```text
feature/booking
feature/payment
feature/cms

bugfix/login
bugfix/dashboard

hotfix/payment

release/v1.0
```

---

# 14. Security Standards

* Jangan menyimpan password di source code.
* Gunakan Environment Variables.
* Validasi seluruh input.
* Escape output bila diperlukan.
* Selalu gunakan HTTPS.
* Terapkan Firebase Security Rules.

---

# 15. Performance Standards

* Lazy Loading untuk gambar.
* Minify CSS dan JavaScript.
* Optimasi ukuran gambar.
* Hindari query Firestore berulang.
* Gunakan cache jika memungkinkan.

---

# 16. Responsive Standards

Breakpoint utama:

* Mobile
* Tablet
* Laptop
* Desktop

Seluruh halaman wajib responsive.

---

# 17. Documentation Standards

Setiap modul baru harus memiliki:

* Tujuan modul
* Struktur folder
* Penjelasan fungsi
* Dependensi
* Cara penggunaan

---

# 18. Code Review Checklist

Sebelum merge ke branch utama:

* Kode berhasil dijalankan.
* Tidak ada error pada console.
* Mengikuti naming convention.
* Tidak ada kode yang tidak digunakan.
* Sudah diuji.
* Dokumentasi diperbarui bila diperlukan.

---

# 19. Best Practices

* Hindari hardcode.
* Gunakan reusable component.
* Pisahkan logika bisnis dari tampilan.
* Gunakan helper untuk fungsi umum.
* Selalu lakukan validasi data.
* Jaga konsistensi struktur folder dan penamaan.

---

# 20. Ringkasan

Standar ini menjadi pedoman utama seluruh pengembangan JDI KOSKITA agar menghasilkan kode yang konsisten, aman, mudah dipelihara, dan siap dikembangkan menjadi platform manajemen rumah kos berskala enterprise.

---

# 📌 Document Control

| Item          | Description                   |
| ------------- | ----------------------------- |
| Status        | Planning                      |
| Maintained By | Jaya Digital Integrate (JDI)  |
| Last Update   | June 2026                     |
| Next Document | 14-UI-UX-DESIGN-GUIDELINES.md |

---
