# วิธีเผยแพร่ด้วย GitHub Pages

## โครงสร้างไฟล์ที่ต้องมี

โปรเจกต์นี้ใช้ GitHub Pages จาก branch `main` และ folder `/(root)` โดยให้ `index.html` อยู่ชั้นบนสุดของ repository

โครงสร้างไฟล์ที่ถูกต้องสำหรับเว็บปัจจุบัน:

```txt
index.html
style.css
app.js
firebase-config.js
firebase.rules.json
README.md
FIREBASE_SETUP.md
GITHUB_PAGES_DEPLOY.md
.nojekyll
```

> เวอร์ชันนี้ไม่ต้องมีโฟลเดอร์ `assets/` เพราะไฟล์เว็บปัจจุบันไม่ได้เรียกใช้โฟลเดอร์นั้นโดยตรง

## ขั้นตอนตั้งค่า GitHub Pages

1. เข้า repository `receipt-app`
2. ไปที่ `Settings` > `Pages`
3. ที่ `Build and deployment` เลือก `Deploy from a branch`
4. Branch เลือก `main`
5. Folder เลือก `/(root)`
6. กด `Save`
7. เปิดเว็บที่:

```txt
https://jindarungtiwaj31.github.io/receipt-app/
```

## ก่อนใช้งานหลายเครื่องจริง

ต้องตั้งค่า Firebase Realtime Database ให้เรียบร้อยก่อน:

1. เปิด Firebase Console
2. เข้าโปรเจกต์ `rmut-receipt-app`
3. เปิด `Realtime Database`
4. ไปที่ `Rules`
5. นำเนื้อหาในไฟล์ `firebase.rules.json` ไปวาง
6. กด `Publish`

ถ้าเชื่อมต่อสำเร็จ เว็บจะแสดงสถานะว่า `ฐานข้อมูลกลางเชื่อมต่อแล้ว`

## หมายเหตุเรื่องโลโก้

โลโก้ด้านบนของหน้าเว็บยังแสดงตามปกติ ส่วนโลโก้มหาวิทยาลัยที่อยู่ใต้ครุฑในหน้าใบเสร็จ/ตอนพิมพ์ถูกซ่อนแล้วตามที่กำหนด
