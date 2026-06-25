# JDI KOSKITA

> **Project Folder Structure Documentation**

---

# 📄 Document Information

| Item         | Description                  |
| ------------ | ---------------------------- |
| Product Name | JDI KOSKITA                  |
| Document     | Project Folder Structure     |
| Version      | 1.0                          |
| Developer    | Jaya Digital Integrate (JDI) |
| Platform     | Website, Android & Firebase  |
| Status       | Planning                     |

---

# 📑 Document Version

| Version | Date      | Description                      |
| ------- | --------- | -------------------------------- |
| 1.0     | June 2026 | Initial Project Folder Structure |

---

# 1. Tujuan

Dokumen ini menjelaskan struktur folder standar yang digunakan pada proyek JDI KOSKITA agar pengembangan lebih terorganisir, mudah dipelihara, dan siap dikembangkan menjadi aplikasi berskala enterprise maupun SaaS.

---

# 2. Root Project Structure

```text
jdi-koskita/

├── docs/
├── website/
├── admin/
├── member/
├── android/
├── firebase/
├── assets/
├── database/
├── scripts/
├── .gitignore
├── README.md
├── LICENSE
├── firebase.json
├── firestore.rules
├── firestore.indexes.json
├── storage.rules
├── package.json
```

---

# 3. Folder Documentation

```text
docs/

00-PROJECT-ROADMAP.md
01-PROJECT-OVERVIEW.md
02-BUSINESS-REQUIREMENT.md
03-SOFTWARE-REQUIREMENT.md
04-BUSINESS-PROCESS.md
05-USECASE-DIAGRAM.md
06-ACTIVITY-DIAGRAM.md
07-CLASS-DIAGRAM.md
08-ERD-DATABASE.md
09-FIREBASE-COLLECTION.md
10-FIREBASE-SECURITY-RULES.md
11-SYSTEM-ARCHITECTURE.md
12-PROJECT-FOLDER-STRUCTURE.md
13-CODING-STANDARDS.md
14-UI-UX-GUIDELINES.md
15-API-DOCUMENTATION.md
16-DEPLOYMENT-GUIDE.md
```

---

# 4. Website Folder

```text
website/

assets/
css/
js/
images/
fonts/

components/
layouts/
pages/
auth/
booking/
gallery/
contact/
faq/
news/
profile/

index.html
```

Website Public digunakan oleh:

* Guest
* Calon Penyewa
* Member

---

# 5. Admin Portal

```text
admin/

assets/
css/
js/

components/
layouts/

dashboard/

users/
roles/

buildings/
floors/
rooms/

facilities/

bookings/

members/

contracts/

payments/

invoices/

complaints/

maintenance/

inventory/

cms/

reports/

settings/

login/

index.html
```

Portal Admin digunakan oleh:

* Super Admin
* Owner
* Manager
* Admin
* Finance

---

# 6. Member Portal

```text
member/

dashboard/

profile/

booking/

payments/

contracts/

complaints/

notifications/

settings/

index.html
```

---

# 7. Android Folder

```text
android/

app/

src/

assets/

res/

java/

activities/

fragments/

adapters/

models/

repositories/

services/

utils/

firebase/

AndroidManifest.xml
```

---

# 8. Firebase Folder

```text
firebase/

config/

functions/

firestore/

rules/

storage/

emulator/

scripts/
```

---

# 9. Assets Folder

```text
assets/

logo/

banner/

icons/

gallery/

illustrations/

documents/

videos/
```

---

# 10. Database Folder

```text
database/

erd/

collection/

sample-data/

migration/

backup/
```

---

# 11. Scripts Folder

```text
scripts/

seed/

backup/

restore/

deploy/

utilities/
```

---

# 12. Shared Components

Komponen yang digunakan bersama:

```text
navbar/

sidebar/

footer/

card/

table/

modal/

form/

alert/

badge/

pagination/

loading/

charts/
```

---

# 13. Naming Convention

Folder menggunakan huruf kecil.

Contoh:

```text
bookings/

payments/

contracts/

inventory/
```

Nama file:

```text
booking-list.js

booking-detail.js

room-form.js

dashboard.js
```

---

# 14. Environment Configuration

```text
.env

.env.local

.env.production

firebase.json
```

Seluruh konfigurasi sensitif disimpan pada file environment dan tidak boleh diunggah ke repository publik.

---

# 15. Git Branch Strategy

Branch utama:

```text
main
```

Branch pengembangan:

```text
develop
```

Branch fitur:

```text
feature/login

feature/booking

feature/cms

feature/payment
```

Branch perbaikan:

```text
hotfix/
```

---

# 16. Deployment Structure

```text
Developer

↓

GitHub Repository

↓

GitHub Actions

↓

Firebase Hosting

↓

Production
```

---

# 17. Best Practice

* Pisahkan kode berdasarkan modul.
* Gunakan reusable component.
* Hindari duplikasi kode.
* Dokumentasikan setiap modul baru.
* Gunakan struktur folder yang konsisten.
* Simpan aset sesuai kategori.
* Jangan menyimpan credential di repository.

---

# 18. Ringkasan

Dengan struktur folder ini, proyek JDI KOSKITA memiliki fondasi yang rapi, modular, dan mudah dikembangkan. Setiap modul memiliki lokasi yang jelas sehingga mempermudah proses pengembangan, pengujian, deployment, dan pemeliharaan.

---

# 📌 Document Control

| Item          | Description                  |
| ------------- | ---------------------------- |
| Status        | Planning                     |
| Maintained By | Jaya Digital Integrate (JDI) |
| Last Update   | June 2026                    |
| Next Document | 13-CODING-STANDARDS.md       |

---
