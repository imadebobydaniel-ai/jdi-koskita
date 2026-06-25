# JDI KOSKITA

> **Firebase Collection Design**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Firebase Collection Design   |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Database     | Firebase Cloud Firestore     |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                        |
| ------- | --------- | ---------------------------------- |
| 1.0     | June 2026 | Initial Firebase Collection Design |

---

# 1. Tujuan

Dokumen ini mendefinisikan struktur Collection, Document, dan Subcollection yang akan digunakan pada Firebase Cloud Firestore untuk aplikasi JDI KOSKITA.

---

# 2. Standar Penamaan

## Collection

Menggunakan huruf kecil (lowercase) dan bentuk jamak.

Contoh:

```text
users
rooms
bookings
payments
```

---

## Field

Menggunakan format **camelCase**.

Contoh:

```text
fullName
roomNumber
bookingDate
paymentStatus
```

---

## Audit Field

Setiap document wajib memiliki field berikut:

| Field     | Type      |
| --------- | --------- |
| createdAt | timestamp |
| updatedAt | timestamp |
| createdBy | string    |
| updatedBy | string    |
| isDeleted | boolean   |

---

# 3. Collection : users

### Document

```text
users/{uid}
```

### Fields

| Field    | Type      |
| -------- | --------- |
| uid      | string    |
| fullName | string    |
| email    | string    |
| phone    | string    |
| roleId   | reference |
| photoUrl | string    |
| status   | string    |

### Subcollection

```text
notifications
activityLogs
```

---

# 4. Collection : buildings

```text
buildings/{buildingId}
```

### Fields

* buildingName
* address
* city
* province
* latitude
* longitude
* totalFloor
* totalRoom
* status

### Subcollection

```text
floors
```

---

# 5. Collection : floors

```text
buildings/{buildingId}/floors/{floorId}
```

### Fields

* floorName
* floorNumber

### Subcollection

```text
rooms
```

---

# 6. Collection : rooms

```text
buildings/{buildingId}/floors/{floorId}/rooms/{roomId}
```

### Fields

* roomNumber
* roomName
* roomTypeId
* price
* discount
* finalPrice
* capacity
* roomStatus
* area
* description
* coverImage
* gallery
* facilities

### Subcollection

```text
inventories
photos
```

---

# 7. Collection : bookings

```text
bookings/{bookingId}
```

### Fields

* bookingCode
* memberId
* roomId
* buildingId
* bookingDate
* checkInDate
* duration
* totalPrice
* bookingStatus

### Subcollection

```text
paymentHistory
```

---

# 8. Collection : contracts

```text
contracts/{contractId}
```

### Fields

* contractNumber
* bookingId
* roomId
* memberId
* startDate
* endDate
* status

---

# 9. Collection : invoices

```text
invoices/{invoiceId}
```

### Fields

* invoiceNumber
* contractId
* amount
* dueDate
* invoiceStatus

---

# 10. Collection : payments

```text
payments/{paymentId}
```

### Fields

* invoiceId
* paymentMethod
* paymentDate
* amount
* transferProof
* verificationStatus
* verifiedBy

---

# 11. Collection : complaints

```text
complaints/{complaintId}
```

### Fields

* memberId
* roomId
* title
* description
* photos
* priority
* complaintStatus

### Subcollection

```text
progressLogs
```

---

# 12. Collection : maintenances

```text
maintenances/{maintenanceId}
```

### Fields

* complaintId
* technicianId
* workDescription
* progress
* maintenanceStatus
* finishedDate

---

# 13. Collection : announcements

```text
announcements/{announcementId}
```

### Fields

* title
* content
* targetRole
* publishDate
* status

---

# 14. Collection : notifications

```text
notifications/{notificationId}
```

### Fields

* receiverId
* title
* message
* type
* isRead

---

# 15. Collection CMS

```text
banners
galleries
promos
articles
faqs
testimonials
```

Setiap collection memiliki struktur umum:

* title
* description
* imageUrl
* displayOrder
* isPublished

---

# 16. Collection Settings

```text
settings/general
```

Berisi konfigurasi:

* Nama Kos
* Logo
* Favicon
* WhatsApp
* Email
* Rekening
* QRIS
* Google Maps
* SEO
* Firebase Config

---

# 17. Collection Logs

```text
logs/{logId}
```

### Fields

* userId
* module
* activity
* ipAddress
* device
* createdAt

---

# 18. Struktur Firebase

```text
users
buildings
 └── floors
      └── rooms
           ├── inventories
           └── photos

bookings
contracts
payments
invoices
complaints
maintenances
announcements
notifications
settings
logs
cms
```

---

# 19. Strategi Query

Query utama yang akan digunakan:

* Cari kamar berdasarkan gedung.
* Cari kamar berdasarkan status.
* Cari booking berdasarkan member.
* Cari invoice yang belum lunas.
* Cari pengaduan berdasarkan status.
* Cari pembayaran berdasarkan tanggal.
* Cari kontrak yang akan berakhir.
* Cari notifikasi berdasarkan pengguna.

---

# 20. Best Practice Firestore

* Hindari nested document yang terlalu dalam.
* Gunakan Document Reference bila memungkinkan.
* Denormalisasi data untuk query yang sering digunakan.
* Simpan URL gambar di Firebase Storage.
* Gunakan batch write untuk update massal.
* Gunakan transaction untuk pembayaran.

---

# 21. Future Collection

Untuk pengembangan berikutnya:

* subscriptions
* coupons
* chatMessages
* supportTickets
* aiRecommendations
* smartLocks
* accessCards
* biometricLogs
* paymentGatewayLogs
* analytics

---

# 22. Document Control

| Item          | Description                   |
| ------------- | ----------------------------- |
| Status        | Planning                      |
| Maintained By | Jaya Digital Integrate (JDI)  |
| Next Document | 10-FIREBASE-SECURITY-RULES.md |

---
