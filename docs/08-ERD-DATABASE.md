# JDI KOSKITA

> **ERD & Firebase Database Design**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | ERD Database                 |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Database     | Firebase Cloud Firestore     |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                      |
| ------- | --------- | -------------------------------- |
| 1.0     | June 2026 | Initial Firebase Database Design |

---

# 1. Tujuan

Dokumen ini mendefinisikan struktur database **Firebase Cloud Firestore** yang digunakan pada JDI KOSKITA. Setiap Collection, Document, dan Reference dirancang agar sistem memiliki performa tinggi, mudah dikembangkan, aman, dan mendukung sinkronisasi data secara realtime.

---

# 2. Struktur Collection

```text
users
roles
buildings
floors
rooms
roomTypes
facilities
bookings
contracts
invoices
payments
complaints
maintenances
inventories
announcements
notifications
visitors
vehicles
galleries
banners
promos
articles
faqs
settings
logs
```

---

# 3. Entity Relationship

```text
Building
   │
   ├── Floor
   │      │
   │      └── Room
   │              │
   │              ├── Booking
   │              ├── Contract
   │              ├── Invoice
   │              ├── Complaint
   │              └── Inventory
   │
User
   │
   ├── Booking
   ├── Payment
   ├── Complaint
   ├── Notification
   └── Contract
```

---

# 4. Collection : users

| Field     | Type      |
| --------- | --------- |
| uid       | string    |
| fullName  | string    |
| email     | string    |
| phone     | string    |
| gender    | string    |
| address   | string    |
| photo     | string    |
| roleId    | reference |
| status    | string    |
| createdAt | timestamp |
| updatedAt | timestamp |

---

# 5. Collection : buildings

| Field        | Type    |
| ------------ | ------- |
| id           | string  |
| buildingName | string  |
| address      | string  |
| city         | string  |
| province     | string  |
| latitude     | number  |
| longitude    | number  |
| totalFloor   | number  |
| totalRoom    | number  |
| status       | boolean |

---

# 6. Collection : floors

| Field       | Type      |
| ----------- | --------- |
| id          | string    |
| buildingId  | reference |
| floorName   | string    |
| floorNumber | number    |

---

# 7. Collection : rooms

| Field       | Type      |
| ----------- | --------- |
| id          | string    |
| buildingId  | reference |
| floorId     | reference |
| roomTypeId  | reference |
| roomNumber  | string    |
| roomName    | string    |
| price       | number    |
| discount    | number    |
| finalPrice  | number    |
| status      | string    |
| capacity    | number    |
| area        | string    |
| description | string    |
| coverImage  | string    |
| gallery     | array     |
| facilities  | array     |
| isPublished | boolean   |
| createdAt   | timestamp |

---

# 8. Collection : bookings

| Field         | Type      |
| ------------- | --------- |
| bookingCode   | string    |
| memberId      | reference |
| roomId        | reference |
| bookingDate   | timestamp |
| checkInDate   | timestamp |
| duration      | number    |
| totalPrice    | number    |
| bookingStatus | string    |

---

# 9. Collection : contracts

| Field          | Type      |
| -------------- | --------- |
| contractNumber | string    |
| bookingId      | reference |
| memberId       | reference |
| roomId         | reference |
| startDate      | timestamp |
| endDate        | timestamp |
| status         | string    |

---

# 10. Collection : invoices

| Field         | Type      |
| ------------- | --------- |
| invoiceNumber | string    |
| contractId    | reference |
| memberId      | reference |
| amount        | number    |
| dueDate       | timestamp |
| status        | string    |

---

# 11. Collection : payments

| Field         | Type      |
| ------------- | --------- |
| invoiceId     | reference |
| paymentMethod | string    |
| transferProof | string    |
| paymentDate   | timestamp |
| amount        | number    |
| verifiedBy    | reference |
| status        | string    |

---

# 12. Collection : complaints

| Field       | Type      |
| ----------- | --------- |
| memberId    | reference |
| roomId      | reference |
| title       | string    |
| description | string    |
| photos      | array     |
| priority    | string    |
| status      | string    |

---

# 13. Collection : maintenances

| Field           | Type      |
| --------------- | --------- |
| complaintId     | reference |
| technicianId    | reference |
| workDescription | string    |
| progress        | number    |
| status          | string    |
| finishedDate    | timestamp |

---

# 14. Collection : inventories

| Field     | Type      |
| --------- | --------- |
| roomId    | reference |
| assetName | string    |
| category  | string    |
| quantity  | number    |
| condition | string    |

---

# 15. Collection : announcements

| Field       | Type      |
| ----------- | --------- |
| title       | string    |
| content     | string    |
| targetRole  | array     |
| publishDate | timestamp |
| status      | boolean   |

---

# 16. Collection : notifications

| Field      | Type      |
| ---------- | --------- |
| receiverId | reference |
| title      | string    |
| message    | string    |
| type       | string    |
| isRead     | boolean   |
| createdAt  | timestamp |

---

# 17. Collection : CMS

Collection CMS terdiri dari:

* galleries
* banners
* promos
* articles
* faqs

Semua menggunakan struktur dasar berikut:

| Field       | Type      |
| ----------- | --------- |
| title       | string    |
| description | string    |
| image       | string    |
| status      | boolean   |
| createdAt   | timestamp |

---

# 18. Collection : settings

Digunakan untuk konfigurasi sistem.

Contoh:

* Nama Kos
* Logo
* Favicon
* WhatsApp
* Email
* Rekening Bank
* QRIS
* Jam Operasional
* SEO Website
* Firebase Config

---

# 19. Collection : logs

Digunakan untuk Audit Trail.

| Field     | Type      |
| --------- | --------- |
| userId    | reference |
| activity  | string    |
| module    | string    |
| createdAt | timestamp |
| ipAddress | string    |

---

# 20. Strategi Relasi Firebase

Semua relasi menggunakan Document Reference atau Document ID.

Contoh:

```text
users/{uid}

rooms/{roomId}

bookings/{bookingId}

contracts/{contractId}
```

Tidak ada JOIN seperti pada database SQL. Data akan diambil menggunakan Reference dan Query Firestore.

---

# 21. Denormalisasi Data

Untuk meningkatkan performa, beberapa informasi penting akan disalin (denormalisasi), seperti:

* Nama penghuni pada Booking.
* Nomor kamar pada Invoice.
* Nama gedung pada Room.
* Nama penghuni pada Payment.
* Nama kamar pada Complaint.

Dengan cara ini jumlah pembacaan (read) Firestore dapat dikurangi.

---

# 22. Index Firestore

Index yang akan digunakan:

* roomStatus + buildingId
* bookingStatus + checkInDate
* paymentStatus + paymentDate
* memberId + createdAt
* complaintStatus + priority
* invoiceStatus + dueDate

---

# 23. Backup Strategy

* Cloud Firestore Export
* Cloud Storage Backup
* Daily Backup
* Weekly Full Backup
* Monthly Archive

---

# 24. Future Collections

Collection yang telah dipersiapkan untuk pengembangan berikutnya:

* coupons
* subscriptions
* digitalSignatures
* chatMessages
* liveChats
* cctvLogs
* accessCards
* smartLocks
* aiRecommendations
* analytics

---

# 25. Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Next Document | 09-FIREBASE-COLLECTION.md    |

---
