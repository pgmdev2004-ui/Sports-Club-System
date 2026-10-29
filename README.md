# 🏆 Sports Club System

ระบบบริหารจัดการสโมสรกีฬา (Sports Club Management System) สำหรับจัดการข้อมูลสมาชิก การจองสนาม/อุปกรณ์ และระบบงานภายในสโมสร

---

## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```text
Sports-Club-System/
├── Database/            # ไฟล์สคริปต์ฐานข้อมูล (SQL / Schemas)
├── Web/
│   └── sports-club-app/ # โค้ดส่วนแอปพลิเคชันหลัก
├── package.json         # รายการ Dependencies หลัก
└── README.md            # เอกสารอธิบายโปรเจกต์
```

---

## 🚀 วิธีการติดตั้งและเปิดใช้งาน (Getting Started)

### 1. ติดตั้ง Dependencies
เปิด Terminal แล้วเข้าไปที่โฟลเดอร์แอปพลิเคชันหลัก:
```bash
cd Web/sports-club-app
npm install
```

### 2. ตั้งค่า Environment Variables (.env)
สร้างไฟล์ `.env` ในโฟลเดอร์ `Web/sports-club-app` แล้วระบุค่าการเชื่อมต่อฐานข้อมูล:
```env
PORT=5000
DATABASE_URL=your_database_connection_string
```

### 3. รันโปรเจกต์ (Development Mode)
```bash
npm run dev
# หรือ
npm start
```

---

## 🛠️ เทคโนโลยีที่ใช้ (Tech Stack)

* **Frontend / Web:** Node.js / React (`sports-club-app`)
* **Database:** SQL / Relational Database
* **Version Control:** Git & GitHub

---

## 👤 ผู้พัฒนา (Developer)
* **GitHub:** [@pgmdev2004-ui](https://github.com/pgmdev2004-ui)