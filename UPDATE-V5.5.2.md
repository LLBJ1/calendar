# V5.5.2 — Form Reset Fix
แก้ DOM named-property collision: ปุ่ม id=reset ชน HTMLFormElement.reset()
- เปลี่ยน id เป็น clearEventForm และปรับ app.js ทุกจุด
- ใช้ HTMLFormElement.prototype.reset.call(form) และเรียก reset โดยตรงหลังบันทึก
- เปลี่ยน cache version และบังคับโหลดไฟล์ใหม่ตอนติดตั้ง Service Worker

อัปเดตจาก V5.5.1: วาง index.html, app.js, sw.js ทับพร้อมกันบน GitHub; คง config.js, Code.gs และ style.css เดิม
ปิดแท็บ/PWA เดิมทั้งหมดแล้วเปิดใหม่หลัง GitHub Pages deploy
ทดสอบ Chromium 390 และ 1024 px โดย API จำลอง: เปิดแก้ไข, โหลด ID/version, ส่ง update หนึ่งครั้ง ไม่ส่ง create, คัดลอก, กลับรายการ, เพิ่มใหม่และล้างฟอร์ม ผ่าน ไม่มี pageerror
ยังไม่ได้ทดสอบ Safari/iPad จริงหรือ Google Sheets จริง
