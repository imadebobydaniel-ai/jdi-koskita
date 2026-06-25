# JDI KOSKITA

> **Class Diagram Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Class Diagram                |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website & Android            |
| Database     | Firebase Cloud Firestore     |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                         |
| ------- | --------- | ----------------------------------- |
| 1.0     | June 2026 | Initial Class Diagram Documentation |

---

# 1. Tujuan

Dokumen ini menjelaskan struktur class (domain model) yang digunakan dalam pengembangan JDI KOSKITA. Setiap class merepresentasikan entitas utama pada sistem dan akan menjadi dasar pembuatan model aplikasi, struktur database Firebase, serta relasi antar data.

---

# 2. Daftar Class

## Master Data

* User
* Role
* Permission
* Building
* Floor
* Room
* RoomType
* Facility
* Gallery
* Banner
* Promo
* Article
* FAQ
* Testimonial

---

## Transaksi

* Booking
* Contract
* Invoice
* Payment
* Complaint
* Maintenance
* WorkOrder
* Announcement

---

## Operasional

* Inventory
* AssetCategory
* AssetMutation
* Visitor
* Vehicle
* Notification

---

## Laporan

* RevenueReport
* ExpenseReport
* OccupancyReport
* DashboardStatistic

---

# 3. Detail Class

## User

### Attributes

* id
* fullName
* email
* phone
* gender
* address
* photo
* roleId
* status
* createdAt
* updatedAt

### Methods

* login()
* logout()
* updateProfile()
* changePassword()

---

## Building

### Attributes

* id
* buildingName
* address
* city
* province
* totalFloor
* totalRoom
* status

### Methods

* createBuilding()
* updateBuilding()
* deleteBuilding()

---

## Floor

### Attributes

* id
* buildingId
* floorNumber
* floorName

### Methods

* createFloor()
* updateFloor()
* deleteFloor()

---

## Room

### Attributes

* id
* buildingId
* floorId
* roomNumber
* roomTypeId
* price
* discount
* capacity
* status
* description

### Methods

* createRoom()
* updateRoom()
* uploadPhoto()
* updateStatus()

---

## RoomType

### Attributes

* id
* roomTypeName
* defaultPrice
* description

### Methods

* createType()
* updateType()

---

## Facility

### Attributes

* id
* facilityName
* category
* icon

### Methods

* createFacility()
* updateFacility()

---

## Booking

### Attributes

* id
* bookingCode
* memberId
* roomId
* bookingDate
* checkInDate
* duration
* totalPayment
* status

### Methods

* createBooking()
* cancelBooking()
* approveBooking()

---

## Contract

### Attributes

* id
* bookingId
* memberId
* roomId
* startDate
* endDate
* status

### Methods

* generateContract()
* extendContract()
* closeContract()

---

## Invoice

### Attributes

* id
* invoiceNumber
* memberId
* amount
* dueDate
* status

### Methods

* generateInvoice()
* markPaid()

---

## Payment

### Attributes

* id
* invoiceId
* paymentDate
* paymentMethod
* transferProof
* status

### Methods

* uploadTransfer()
* verifyPayment()

---

## Complaint

### Attributes

* id
* memberId
* roomId
* complaintTitle
* description
* photo
* status

### Methods

* createComplaint()
* updateStatus()

---

## Maintenance

### Attributes

* id
* complaintId
* technicianId
* progress
* finishedDate

### Methods

* assignTechnician()
* uploadProgress()
* finishMaintenance()

---

## Inventory

### Attributes

* id
* roomId
* assetName
* quantity
* condition

### Methods

* addInventory()
* updateInventory()

---

## Announcement

### Attributes

* id
* title
* content
* publishDate
* targetRole

### Methods

* publish()
* unpublish()

---

## Notification

### Attributes

* id
* receiverId
* title
* message
* isRead

### Methods

* send()
* markAsRead()

---

# 4. Relationship Antar Class

```text
User
 │
 ├──── Booking
 │
 ├──── Payment
 │
 ├──── Complaint
 │
 └──── Contract

Building
 │
 └──── Floor
         │
         └──── Room
                   │
                   ├──── RoomType
                   ├──── Facility
                   ├──── Inventory
                   ├──── Booking
                   ├──── Contract
                   └──── Complaint
```

---

# 5. Dependency

* Booking bergantung pada Room dan User.
* Contract dibuat dari Booking yang telah disetujui.
* Invoice dihasilkan dari Contract aktif.
* Payment mengacu pada Invoice.
* Complaint dibuat oleh Member dan terkait dengan Room.
* Maintenance dibuat berdasarkan Complaint.
* Notification dikirim ketika terjadi perubahan status pada Booking, Payment, Contract, atau Complaint.

---

# 6. Implementasi Firebase

Setiap class akan direpresentasikan sebagai collection atau subcollection di Firebase Cloud Firestore. Relasi antar class menggunakan Document ID (Reference ID) sehingga tetap fleksibel dan mudah diskalakan.

---

# 7. Catatan Pengembangan

Seluruh class akan digunakan sebagai dasar untuk:

* Model JavaScript
* Model Android (Java/Kotlin)
* Firebase Collections
* Firestore Security Rules
* Repository Layer
* Service Layer

---

# 8. Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Next Document | 08-ERD-DATABASE.md           |

---
