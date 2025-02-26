# 📌 GForm to Telegram  
Google Apps Script for sending Google Form notifications to Telegram  

########################################  Create By AIN  ########################################
### 📌 promptpay: `0612566xxx`

## 🚀 ขั้นตอนการทำงาน  

### 1️⃣ สร้าง Google Form  
✅ เข้าไปที่ **[Google Forms](https://forms.google.com)**  
✅ สร้างแบบฟอร์มใหม่ และกำหนด **คำถาม** เช่น:  
   - เลขที่ห้องพัก  
   - ประเภทของปัญหา  
   - รายละเอียดปัญหา  
   - วันที่และเวลาที่สะดวก  
✅ เชื่อมโยง Google Form กับ Google Sheet (**Responses > Create Spreadsheet**)  

### 2️⃣ สร้าง Google Sheet  
✅ Google Form จะสร้างชีต `Responses` อัตโนมัติ  
✅ สร้างชีต **ห้อง, ประเภท, เวลา** เพื่อใช้เป็นข้อมูลอ้างอิงในฟอร์ม  
✅ สร้างชีต **Setting** เพื่อเก็บค่า **(Bot Token, Chat ID, ค่าต่างๆ)**  

### 3️⃣ สร้าง Google Apps Script สำหรับอัปเดตข้อมูลไปยัง Google Form  
✅ ไปที่ **Extensions > Apps Script**  
✅ คัดลอกโค้ดและสร้างไฟล์ **`updateFormWithSheetData.gs`**  
✅ ตั้งค่า **Trigger** เพื่ออัปเดตข้อมูลอัตโนมัติ  

### 4️⃣ สร้าง Google Apps Script สำหรับรับข้อมูลจากฟอร์ม  
✅ ไปที่ **Extensions > Apps Script**  
✅ คัดลอกโค้ดและสร้างไฟล์ **`GformToTelegram.gs`**  
✅ ตั้งค่า **Trigger** เป็น `onFormSubmit`  

### 5️⃣ สร้าง Google Apps Script สำหรับสรุปข้อมูลประจำวัน  
✅ ไปที่ **Extensions > Apps Script**  
✅ คัดลอกโค้ดและสร้างไฟล์ **`jobremind.gs`**  
✅ ตั้งค่า **Trigger** เป็น `TimeDaily`  

### 6️⃣ สร้าง Google Apps Script ส่งข้อมูลไปยัง Telegram  
✅ ไปที่ **Extensions > Apps Script**  
✅ คัดลอกโค้ดและสร้างไฟล์ **`sendTelegramNotify.gs`**  
✅ ตั้งค่า **Trigger** ให้รันเมื่อมีข้อมูลใหม่  

---

## 📌 **Flow การทำงาน**  

### 🔹 **แจ้งเตือนรายการใหม่**  
1️⃣ ผู้ใช้กรอก **Google Form**  
2️⃣ ข้อมูลบันทึกลง **Google Sheet (`FormResponses`)**  
3️⃣ Script **แจ้งเตือนผ่าน Telegram**  
4️⃣ Trigger ทำงาน **อัตโนมัติเมื่อมีการส่งฟอร์ม**  

### 🔹 **แจ้งเตือนงานประจำวัน**  
1️⃣ Trigger ทำงาน **อัตโนมัติทุกวัน**  
2️⃣ Script ตรวจสอบงานที่ตรงกับวันที่ปัจจุบัน  
3️⃣ Script **แจ้งเตือนผ่าน Telegram**  

### 🔹 **อัปเดตตัวเลือกในฟอร์ม**  
1️⃣ อัปเดตข้อมูลในชีต **ห้อง, ประเภท, เวลา**  
2️⃣ กดปุ่ม **อัพเดทข้อมูลไป Google Form**  
3️⃣ ข้อมูลใหม่จะอัปเดตบน **Google Form อัตโนมัติ**  

---
promptpay: 


🙏 ขอบคุณสำหรับการสนับสนุน! โปรเจกต์นี้เป็นโอเพ่นซอร์ส และทุกการช่วยเหลือจะช่วยให้สามารถพัฒนาต่อไปได้ 🚀
