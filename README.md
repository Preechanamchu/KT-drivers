# 🚀 KT-drivers (GitHub Driver Repository for KT-Smart Automation)

คลังไฟล์ ChromeDriver สำหรับโปรแกรม **KT-Smart Automation** 
เมื่อ Google Chrome มีการอัปเดตเวอร์ชันใหม่ คุณสามารถนำไฟล์ Driver ตัวใหม่มาอัปโหลดไว้ที่นี่ เพื่อให้ผู้ใช้กว่า 30+ บริษัทกดปุ่ม **"อัพเดท drivers จาก GitHub"** บนหน้าโปรแกรมเพื่ออัปเดตอัตโนมัติ

---

## 📁 โครงสร้างไฟล์ใน Repository นี้

```
KT-drivers/
├── README.md              # คู่มือการใช้งานภาษาไทย
├── version.json           # ไฟล์บอกเวอร์ชัน Driver ล่าสุด (Manifest หลัก)
├── manifest.json          # ไฟล์ Manifest สำรอง
└── drivers/               # โฟลเดอร์เก็บไฟล์ Driver (.exe)
    ├── 128.0.6613.84.exe  # ตัวอย่างไฟล์ Driver ตามเลขเวอร์ชัน
    └── chromedriver.exe   # ไฟล์ Driver หลัก
```

---

## 📝 วิธีการอัปเดต Driver เมื่อ Google Chrome มีเวอร์ชันใหม่

เมื่อ Google Chrome อัปเดต ให้ทำตาม 4 ขั้นตอนง่ายๆ ดังนี้:

### ขั้นตอนที่ 1: ดาวน์โหลด ChromeDriver ใหม่
1. เข้าไปที่เว็บ [Chrome for Testing Availability](https://googlechromelabs.github.io/chrome-for-testing/)
2. ค้นหาเลขเวอร์ชันที่ตรงกับ Chrome ใหม่ (เช่น `148.0.6613.84` หรือ `149.0.xxx`)
3. ดาวน์โหลดไฟล์ `chromedriver-win32.zip` หรือ `chromedriver-win64.zip` แล้วแตกไฟล์ออกมาจะได้ `chromedriver.exe`

### ขั้นตอนที่ 2: นำไฟล์มาใส่ใน Repository นี้
1. เปลี่ยนชื่อไฟล์ `chromedriver.exe` เป็นเลขเวอร์ชัน เช่น `148.0.6613.84.exe` (หรือคงชื่อ `chromedriver.exe` ไว้)
2. นำไฟล์นั้นมาวางในโฟลเดอร์ `drivers/` ใน Repository นี้

### ขั้นตอนที่ 3: แก้ไขไฟล์ `version.json`
เปิดไฟล์ `version.json` แล้วปรับเปลี่ยนเลขเวอร์ชันให้ตรงกับไฟล์ใหม่:
```json
{
  "latestVersion": "148.0.6613.84",
  "chromeVersion": "148",
  "driverFileName": "148.0.6613.84.exe",
  "downloadUrl": "https://raw.githubusercontent.com/YOUR_GITHUB_USERNAME/KT-drivers/main/drivers/148.0.6613.84.exe",
  "updatedAt": "2026-07-02"
}
```

### ขั้นตอนที่ 4: Commit & Push ขึ้น GitHub
นำไฟล์ทั้งหมดอัปโหลดขึ้น GitHub Repository ของคุณ (ผ่านเว็บ GitHub หรือ Git CLI):
```bash
git add .
git commit -m "Update ChromeDriver for Chrome 148"
git push origin main
```

---

## 🔗 ลิงก์ URL สำหรับใส่ในโปรแกรม KT-Smart Automation

นำ URL ของ GitHub Repository นี้ไปใส่ในช่อง **⚙️ GitHub Config** ของโปรแกรม:
- รูปแบบ: `https://github.com/YOUR_GITHUB_USERNAME/KT-drivers`
- หรือ: `https://raw.githubusercontent.com/YOUR_GITHUB_USERNAME/KT-drivers/main`

เพียงเท่านี้ ลูกค้า 30+ บริษัทจะสามารถกดปุ่ม **"อัพเดท drivers จาก GitHub"** บนหน้าโปรแกรมเพื่ออัปเดตได้ทันที!
