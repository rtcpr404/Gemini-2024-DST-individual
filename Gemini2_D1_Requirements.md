# Observatory Control System (OCS) Requirements

## Functional Requirements
1. **Observing Modes**
   - รองรับ mode สังเกตการณ์แบบ Interactive, Queue-Based, Remote Observing, และ Service Observing
2. **User Roles**
   - มีระบบกำหนดสิทธิ์ของผู้ใช้ เช่น นักดาราศาสตร์, ผู้สังเกตการณ์, ผู้ควบคุมกล้อง, และผู้ดูแลระบบ
3. **Operational Levels**
   - แบ่งการทำงานเป็น Observing, Maintenance, และ Test
4. **Remote Access**
   - รองรับการเข้าถึงระยะไกลสำหรับการสังเกตการณ์และตรวจสอบระบบ
5. **Data Management**
   - มีระบบจัดเก็บข้อมูลทางดาราศาสตร์ พร้อมระบบบันทึก Log
6. **AI-based Scheduling**
   - ระบบสามารถจัดลำดับการสังเกตการณ์โดยอัตโนมัติ
7. **Real-time Data Analysis**
   - ระบบสามารถวิเคราะห์และแสดงผลข้อมูลแบบเรียลไทม์
8. **Remote Operations**
   - ระบบสามารถควบคุมกล้องจากระยะไกลโดยไม่ต้องมีเจ้าหน้าที่ที่ไซต์งาน
9. **AI-based Error Detection**
   - ระบบสามารถแจ้งเตือนปัญหาอัตโนมัติ
10. **Integration System**
   - ระบบสามารถแสดงผลข้อมูลในหน้าจอเดียว

## Non-Functional Requirements
1. **Performance Requirements**
   - ระบบต้องตอบสนองคำสั่งควบคุมกล้องภายใน 500 ms
   - การประมวลผลข้อมูลต้องใช้เวลาไม่เกิน 5 วินาทีต่อการร้องขอ
   - รองรับผู้ใช้พร้อมกันอย่างน้อย 50 คน
   - รองรับการส่งข้อมูลภาพขนาดใหญ่ (ระดับ GB ต่อคืน) ไปยังคลังข้อมูล
2. **Security Requirements**
   - ควบคุมสิทธิ์การเข้าถึงตามบทบาทของผู้ใช้
   - ระบบสามารถรองรับการทำ Multi-Factor Authentication (MFA)
   - ใช้การเข้ารหัสข้อมูล (AES-256, TLS 1.3)
   - มีระบบป้องกันการโจมตีทางไซเบอร์ เช่น IDS, DDoS Protection, SQL Injection Prevention
   - ระบบสำรองข้อมูลอัตโนมัติทุก 24 ชั่วโมง และมีแผน Disaster Recovery
3. **Reliability & Maintainability**
   - ระบบต้องมี Availability ไม่ต่ำกว่า 99.9%
   - หากระบบล่ม ต้องสามารถกู้คืนได้ภายใน 30 นาที
   - มีระบบแจ้งเตือนและบันทึก Log File
   - รองรับการอัปเดตโดยไม่ทำให้ระบบหยุดทำงาน (Zero Downtime Deployment)
4. **Scalability**
   - สามารถรองรับผู้ใช้หรือเพิ่มเซิร์ฟเวอร์ได้โดยไม่กระทบต่อประสิทธิภาพการทำงาน

## Constraints
1. **Legacy System Compatibility**
   - ระบบใหม่ต้องสามารถทำงานร่วมกับระบบ OCS และฐานข้อมูลเดิม
   - ไม่สามารถเปลี่ยนแปลงฟังก์ชันหลักของ OCS ได้
2. **Offshore Development Constraints**
   - ทีมพัฒนาอยู่ในประเทศไทย แต่ต้องรองรับผู้ใช้ในฮาวายและชิลี
   - ต้องมีช่องทางสื่อสารและประชุมออนไลน์ที่เสถียร
3. **Hardware Constraints**
   - ต้องสามารถรันบนเซิร์ฟเวอร์ที่มีอยู่โดยไม่ต้องอัปเกรดฮาร์ดแวร์มากนัก
   - ต้องรองรับ Linux-based Server ซึ่งเป็นแพลตฟอร์มหลักของ OCS
4. **System Connectivity**
    - ระบบสามารถรองรับการเชื่อมต่อกับระบบอื่น ๆ เช่น Telescope Control System (TCS), Instrument Control System (ICS), Gemini Archive System, Weather Monitoring System, Remote Observation System, และฐานข้อมูลดาราศาสตร์ภายนอก

