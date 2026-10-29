# 🏆 Sports Club System (ระบบบริหารจัดการสโมสรกีฬา)

ระบบบริหารจัดการสโมสรกีฬาแบบครบวงจร สำหรับจัดการข้อมูลสมาชิก การจองสนาม/อุปกรณ์ การจัดการฐานข้อมูล SQL Server และระบบงานภายในสโมสร

## 📋 สิ่งที่ต้องเตรียมก่อนเริ่มใช้งาน (Prerequisites)

ก่อนที่จะเริ่มรันโปรเจกต์นี้ในเครื่องของคุณ กรุณาตรวจสอบและติดตั้งโปรแกรมดังต่อไปนี้ให้เรียบร้อย:

1. **Node.js** (แนะนำเวอร์ชัน LTS เช่น v18.x หรือ v20.x)
   * ดาวน์โหลดได้ที่: [nodejs.org](https://nodejs.org/)
   * ตรวจสอบการติดตั้งใน Terminal:
     ```bash
     node -v
     npm -v
     ```

2. **Microsoft SQL Server & SSMS**
   * **Microsoft SQL Server** (Developer หรือ Express Edition): [microsoft.com/sql-server](https://www.microsoft.com/th-th/sql-server/sql-server-downloads)
   * **SQL Server Management Studio (SSMS)**: [learn.microsoft.com/ssms](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms)

3. **Git**
   * ดาวน์โหลดได้ที่: [git-scm.com](https://git-scm.com/)

4. **Code Editor**
   * แนะนำ **Visual Studio Code (VS Code)**: [code.visualstudio.com](https://code.visualstudio.com/)

---

## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```text
Sports-Club-System/
├── Database/            # ไฟล์สคริปต์ SQL (.sql), Table Schemas และ Stored Procedures
├── Web/
│   └── sports-club-app/ # ซอร์สโค้ดหลักของเว็บแอปพลิเคชัน (Frontend/Backend)
├── package.json         # รายการ Dependencies หลัก
└── README.md            # เอกสารคู่มือการใช้งานโปรเจกต์
```

---

## 🚀 ขั้นตอนการติดตั้งและเปิดใช้งานอย่างละเอียด (Step-by-Step Setup)

### ขั้นตอนที่ 1: คลองโปรเจกต์ลงเครื่อง (Clone Repository)

เปิด Terminal / Command Prompt แล้วรันคำสั่ง:
```bash
git clone https://github.com/pgmdev2004-ui/Sports-Club-System.git
cd Sports-Club-System
```

---

### ขั้นตอนที่ 2: การติดตั้งและตั้งค่า SQL Server ใน SSMS (Database Setup)

1. เปิดโปรแกรม **SQL Server Management Studio (SSMS)**
2. เชื่อมต่อเข้ากับ SQL Server Instance ของคุณ (เช่น `localhost` หรือ `.\SQLEXPRESS`) ด้วย **Windows Authentication** หรือ **SQL Server Authentication**
3. สร้างฐานข้อมูลใหม่:
   * คลิกขวาที่โฟลเดอร์ **Databases** ใน Object Explorer -> เลือก **New Database...**
   * ตั้งชื่อ Database Name: `sports_club_db` แล้วกด **OK**
4. รันสคริปต์นำเข้าข้อมูล:
   * ไปที่เมนู **File** -> **Open** -> **File...** แล้วเลือกไฟล์ `.sql` จากโฟลเดอร์ `Database/`
   * ตรวจสอบตรง Dropdown เลือก Database ให้เป็น `sports_club_db`
   * กดปุ่ม **Execute** (หรือกด `F5`) เพื่อสร้าง Tables และข้อมูลเริ่มต้น

---

### ขั้นตอนที่ 3: ติดตั้ง Dependencies และตั้งค่า Environment Variables

1. ย้ายเข้าไปในโฟลเดอร์เว็บแอปพลิเคชัน:
   ```bash
   cd Web/sports-club-app
   ```

2. ติดตั้งแพ็กเกจที่จำเป็นทั้งหมดผ่าน `npm`:
   ```bash
   npm install
   ```

3. สร้างไฟล์ `.env` สำหรับเชื่อมต่อ Microsoft SQL Server:
   * สร้างไฟล์ชื่อ `.env` ไว้ในโฟลเดอร์ `Web/sports-club-app/`
   * ระบุค่าการเชื่อมต่อ MSSQL ดังนี้ (ปรับแก้ตามค่าจริงของเครื่องคุณ):

   ```env
   # Server Configuration
   PORT=5000

   # Microsoft SQL Server Connection
   DB_SERVER=localhost
   DB_NAME=sports_club_db
   DB_USER=sa
   DB_PASSWORD=your_password_here
   DB_PORT=1433

   # Windows Authentication (หากใช้ Windows Authentication ให้เปิดใช้งาน)
   # DB_DRIVER=msnodesqlv8

   # JWT Secret (Authentication)
   JWT_SECRET=your_secret_key_here
   ```

---

### ขั้นตอนที่ 4: เปิดใช้งานโปรเจกต์ (Run Project)

#### แบบพัฒนา (Development Mode):
```bash
npm run dev
```

#### แบบปกติ (Production / Standard Mode):
```bash
npm start
```

เปิดเว็บเบราว์เซอร์แล้วเข้าไปที่:
👉 `http://localhost:3000` หรือ `http://localhost:5000`

---

## 🛠️ เทคโนโลยีที่ใช้ (Tech Stack)

* **Frontend:** React.js / HTML5 / CSS3 / JavaScript
* **Backend:** Node.js / Express.js (msnodev8 / mssql)
* **Database:** Microsoft SQL Server & SSMS
* **Version Control:** Git & GitHub

---

## 🐞 การแก้ไขปัญหาเบื้องต้น (Troubleshooting)

* **เชื่อมต่อ MSSQL ไม่ได้ (Login failed for user / TCP Connection Error):**
  * เปิดโปรแกรม **SQL Server Configuration Manager**
  * ไปที่ **SQL Server Network Configuration** -> **Protocols for MSSQLSERVER** (หรือ SQLEXPRESS)
  * ตรวจสอบว่า **TCP/IP** ถูกเปลี่ยนเป็น **Enabled** เรียบร้อยแล้ว
  * Restart Service **SQL Server** ใน SSMS หรือ Services.msc
* **ปัญหา `npm install` มี Error:**
  * ลองสั่ง `npm install --legacy-peer-deps`

---

## 👤 ผู้พัฒนา (Developer)

* **GitHub:** [@pgmdev2004-ui](https://github.com/pgmdev2004-ui)