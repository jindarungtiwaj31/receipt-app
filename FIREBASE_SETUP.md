# วิธีตั้งค่าฐานข้อมูลกลาง Firebase Realtime Database

โปรเจกต์นี้เป็นเว็บ Static HTML/CSS/JavaScript ที่เชื่อม Firebase Realtime Database เพื่อให้หลายเครื่องใช้ข้อมูลเดียวกันได้

## สถานะ Firebase ของโปรเจกต์นี้

ไฟล์ `firebase-config.js` ใส่ค่า Firebase ของโปรเจกต์ `rmut-receipt-app` แล้ว และเปิดใช้งาน Firebase แล้ว

ค่าหลักที่ใช้:

```txt
projectId: rmut-receipt-app
authDomain: rmut-receipt-app.firebaseapp.com
databaseURL: https://rmut-receipt-app-default-rtdb.asia-southeast1.firebasedatabase.app
```

## 1) เปิด Realtime Database

1. เข้า Firebase Console
2. เลือกโปรเจกต์ `rmut-receipt-app`
3. ไปที่ `Build` > `Realtime Database`
4. กด `Create Database` หากยังไม่ได้เปิด
5. เลือก location ใกล้ไทย เช่น Singapore / asia-southeast1
6. ใช้ Test mode ได้เฉพาะช่วงทดสอบ

## 2) ตรวจค่า databaseURL

ตรวจว่า URL ใน Firebase Console > Realtime Database > Data ตรงกับค่าใน `firebase-config.js`

```txt
https://rmut-receipt-app-default-rtdb.asia-southeast1.firebasedatabase.app
```

ถ้า Firebase แสดง URL อื่น ให้แก้ `databaseURL` ใน `firebase-config.js` ให้ตรงกับ URL จริง

## 3) ตั้ง Rules

ไปที่ Firebase Console > Realtime Database > Rules แล้วนำเนื้อหาจากไฟล์ `firebase.rules.json` ไปวาง จากนั้นกด `Publish`

Rules ปัจจุบันเปิดอ่าน/เขียนเฉพาะ path ที่ระบบใช้:

- `receipt-app`
- `receipt_app_main`

และปิด root path อื่นไว้

> หมายเหตุ: Rules ชุดนี้เหมาะกับช่วงทดสอบ/เดโม หากใช้งานกับข้อมูลเงินจริงหรือเปิดใช้งานสาธารณะ ควรเพิ่ม backend หรือ Firebase Authentication และ Rules ที่เข้มงวดกว่าเดิม

## 4) ตั้งค่า GitHub Pages

ใน repository ให้ไปที่ `Settings` > `Pages` แล้วตั้งค่า:

```txt
Source: Deploy from a branch
Branch: main
Folder: /(root)
```

หลังบันทึกแล้ว เว็บจะอยู่ที่:

```txt
https://jindarungtiwaj31.github.io/receipt-app/
```

## 5) วิธีเริ่มใช้งานหลังเชื่อมฐานกลาง

1. เข้าเว็บ GitHub Pages
2. เลือก Admin และเข้าสู่ระบบด้วยบัญชี Admin เริ่มต้นที่ตั้งไว้ในหน้า Login
3. ไปแท็บ `ผู้ใช้งาน`
4. เพิ่ม User ด้วยรหัสตัวเลข 4 หลักเอง
5. ให้เครื่อง User เปิด URL เดียวกัน แล้วเข้าสู่ระบบด้วยรหัส 4 หลักที่ Admin สร้าง

เมื่อเชื่อมต่อสำเร็จ มุมบนของเว็บจะแสดงสถานะว่า `ฐานข้อมูลกลางเชื่อมต่อแล้ว`

## 6) กรณีมีข้อมูล local เดิมก่อนเปิด Firebase

1. ตั้งค่า Firebase ให้เรียบร้อย
2. เข้า Admin > `ฐานข้อมูลกลาง`
3. กด `ส่งข้อมูลเครื่องนี้ขึ้นฐานกลาง`
4. เปิดอีกเครื่องด้วย URL เดียวกันเพื่อตรวจว่าข้อมูล sync แล้ว

## 7) การสำรองและกู้คืนข้อมูล

เข้า Admin > `ฐานข้อมูลกลาง`

- กด `สำรองฐานข้อมูล JSON` เพื่อเก็บข้อมูลทั้งหมด
- กด `นำเข้า JSON` เพื่อกู้คืนข้อมูลจากไฟล์สำรอง

ควรสำรองก่อนลบเล่มใบเสร็จหรือก่อนแก้ไขข้อมูลสำคัญ
