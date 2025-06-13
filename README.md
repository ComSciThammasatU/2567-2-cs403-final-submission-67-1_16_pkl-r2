[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/w8H8oomW)
**<ins>Note</ins>: Students must update this `README.md` file to be an installation manual or a README file for their own CS403 projects.**

**รหัสโครงงาน:** 67-1_16_pkl-r2

**ชื่อโครงงาน (ไทย):** เว็บแอปพลิเคชันสำหรับการวางแผนการเดินทาง  
**Project Title (Eng):** TRIP PLANNING WEB APPLICATION

**อาจารย์ที่ปรึกษาโครงงาน:** ผศ. ดร.ปกรณ์ ลี้สุทธิพรชัย
 

**ผู้จัดทำโครงงาน:** 
1. นางสาว สิรีธร ดำกุล 6309610209  Sireethorn.dam@dome.tu.ac.th
2. นางสาว ณัฐณิชา บรรลือทรัพย์ 6309681309 Natnicha.bun@dome.tu.ac.th

   
Manual / Instructions for your projects starts here !

# การติดตั้งและตั้งค่า 

## การติดตั้ง  
1. Clone โปรเจกต์  
git clone https://github.com/ComSciThammasatU/2567-2-cs403-final-submission-67-1_16_pkl-r2.git  
cd planmytrip-main2  

2. ติดตั้ง backend  
cd server
npm install -g nodemon

3. การตั้งค่า google api key  
api key ตัวนี้มีการ restrict เพื่อความปลอดภัย สามารถสร้างใหม่ได้ด้วยที่ [Google console](https://console.cloud.google.com) สามารถสร้าง api key ได้ตามคลิปที่ได้แนบไว้ดังนี้ [How to สร้าง Google Maps APIs Key ภายในไม่กี่นาที!! | The Maps Tangerine EP. 9](https://youtu.be/MtltbXoDQ5M?si=pcal7bDrFEo4Ggr4)  
โดย api ที่ได้เปิดใช้มีทั้งหมด 8 ตัว คือ 
- Places API
- Places API (New)
- Route Optimization API
- Routes API
- Maps JavaScript API
- Geocoding API
- Distance Matrix API
- Directions API   
เมื่อทำการสร้าง key แล้ว คัดลอกแล้วนำไปวางในไฟล์ .env ที่อยู่ในโฟลเดอร์ server


4. ติดตั้ง frontend
กด split terminal
cd ../client  
npm install  

## การรัน frontend และ backend   
1. รัน Backend  
cd  server  
nodemon server.js  

2. รัน Frontend  
เปิด terminal ใหม่  
cd ../client  
npm run dev  
จากนั้นเปิดเบราว์เซอร์ที่ http://localhost:5173 


# วิธีการใช้งาน
เว็บแอปพลิเคชัน Plan My Trip จะมีหน้าการใช้งานอยู่ 3 หน้า คือ หน้าหลัก หนัาวิธีการใช้งาน และหน้าวางแผนการเดินทาง ซึ่งจะสามารถวางแผนการเดินทางได้ที่หน้าวางแผนการเดินทาง โดยต้องกรอกข้อมูลดังต่อไปนี้  
1. ประเภทการเดินทาง (รถยนต์, รถสาธารณะ, เดินเท้า)  
2. วันที่จะเดินทาง  
3. เวลาที่เริ่มเดินทางจากจุดเริ่มต้น  
4. สถานที่อย่างน้อย 2 สถานที่ หากต้องการเพิ่มสถานที่ให้กดปุ่มเพิ่มจุดแวะ  
5. กรอกระยะเวลาที่ใช้ในสถานที่ที่ต้องการจะไป  
6. กดเลือกหลีกเลี่ยงค่าผ่านทางหากผู้ใช้ต้องการ  
7. กดปุ่มวางแผนการเดินทาง  
8. เมื่อผลลัพธ์ออกมาแล้ว หากต้องการเดินทางสามารถกดปุ่มเดินทางเพื่อไปยัง Google map พร้อมกับสถานที่ที่เรียงตามลำดับ
เนื่องจากปัญหาขนาดของวิดิโอค่อนข้างใหญ่ ซึ่งหากนำลง git อาจทำให้เกิดปัญหาระหว่างการ clone ผู้จัดทำจึงได้อัปโหลดคลิปนี้ลงใน youtube พร้อมแนบลิงค์วิธีการติดตั้งโปรแกรม ที่จัดทำขึ้นเพื่อใช้ในการอธิบายโปรแกรมโดยละเอียด
[link to video]([https://console.cloud.google.com](https://www.youtube.com/watch?v=oXiJnZp3G_M&list=RDoXiJnZp3G_M&start_radio=1))


# ในกรณีที่เกิด Request Denied
ในกรณีที่เมื่อประมวลผลแล้ว เกิด Request Denied อาจเกิดได้หลายสาเหตุดังนี้  
**1. Environment Variables ไม่ถูกต้อง**  
- Google maps api key อาจไม่ได้ถูกโหลดหรืออาจจะมีค่าไม่ถูกต้อง

   
**2. character Encording Issues**  
- git อาจเปลี่ยน line endings  
- special character ใน URL อาจถูกเปลี่ยน

 
**3. API Quota / Rate Limiting**  


**4. Network Issues**  
หากเกิด Request Denied ในฟังก์ชัน **getAllPairDistances** ในไฟล์ apiRoutes.js ในโฟล์เดอร์ server/routes อาจเกิดจากกรณี **2. character Encording Issues** ให้ลองคัดลอกฟังค์ชัน getAllPairDistances แล้ววางใหม่อีกครั้ง
