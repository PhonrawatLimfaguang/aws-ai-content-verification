# 🛡️ AI Content Verification & Blockchain Audit Platform

แพลตฟอร์มวิเคราะห์ความถูกต้องของเนื้อหาด้วย AI (Google Gemini) พร้อมระบบจัดเก็บ Log บน Cloud และยืนยันความโปร่งใสผ่านเทคโนโลยี Blockchain

---

## 🏗️ System Architecture
<img width="974" height="711" alt="image" src="https://github.com/user-attachments/assets/3a3e5eb8-1005-4c74-8a88-c7c2b4d16552" />
<img width="884" height="423" alt="image" src="https://github.com/user-attachments/assets/736bb4f3-cd5e-4e44-9784-aa999e544232" />
<img width="884" height="524" alt="image" src="https://github.com/user-attachments/assets/f802c156-5f5b-49f5-899e-06a2f65896c1" />


---

## 🌟 Key Features
* **AI Authenticity Scoring:** ใช้โมเดล **Gemini 2.5 Flash** ในการประเมินเนื้อหาและให้ค่าความเชื่อมั่น (Confidence Score)
* **Data Cleansing Pipeline:** ระบบ Node.js API ที่ทำหน้าที่กรองข้อมูล (Input Validation) และปรับโครงสร้างข้อมูลให้อยู่ในรูปแบบ JSON ที่สมบูรณ์ก่อนบันทึก
* **Immutable Cloud Logging:** บันทึกผลการวิเคราะห์ลงใน **Amazon S3** โดยตรง เพื่อเป็น Audit Trail ที่แก้ไขไม่ได้
* **Blockchain Registry:** ใช้ **Smart Contract (Solidity)** ในการลงทะเบียนข้อมูลการตรวจสอบ (Attestation) เพื่อการยืนยันตัวตนระดับสากล
* **Operational Excellence:** ติดตั้งบน **AWS EC2 (Amazon Linux)** และควบคุมการทำงานด้วย **PM2** เพื่อความเสถียรของระบบ 24/7

---

## 🛠️ Tech Stack
| Layer | Technology Used |
|---|---|
| **Frontend** | React.js, Recharts, Tailwind CSS |
| **Backend** | Node.js (Express), ethers.js, AWS SDK |
| **AI Engine** | Google Gemini API (Generative AI) |
| **Cloud** | AWS (EC2, S3 Static Web Hosting) |
| **Blockchain** | Solidity, Hardhat/Remix, EVM Compatible Network |

---

## 📂 Project Structure

โครงสร้างของโปรเจกต์แบ่งออกเป็นส่วนของ Backend (Cloud & AI) และ Frontend (Dashboard) ดังนี้:

```text
ai-verificationAWS/
├── 📄 AIVerificationRegistryV2.sol  # Smart Contract (Solidity) สำหรับบันทึก Audit Trail บน Blockchain
├── 📄 server.js                      # Backend API (Node.js) จัดการ AI Logic และการเชื่อมต่อ AWS/Blockchain
├── 📄 abi.json                       # Contract Application Binary Interface สำหรับการเรียกใช้ฟังก์ชันใน Smart Contract
├── 📁 dashboard/                     # ระบบ Frontend (React.js)
│   ├── 📁 src/                       # Source code หลักของหน้าจอ Dashboard และ UI Components
│   └── 📁 public/                    # Static assets สำหรับการทำ Web Hosting
├── 📁 artifacts/                     # ไฟล์ที่ได้จากการ Compile Smart Contract สำหรับการ Deployment
├── 📄 attest_submit.js               # สคริปต์อัตโนมัติสำหรับการส่งผลการรับรอง (Attestation) ขึ้น Blockchain
├── 📄 fetch_all_events.mjs           # ระบบดึงข้อมูลย้อนหลังจาก Event Logs ของ Blockchain เพื่อการตรวจสอบ
├── 📄 package.json                   # รายการ Dependencies และสคริปต์การรันระบบ
├── 📄 .env.example                   # เทมเพลตสำหรับกำหนดค่า API Keys และ Environment Variables อย่างปลอดภัย
└── 📄 .gitignore                     # กำหนดไฟล์ที่ไม่ต้องนำขึ้นระบบ เช่น node_modules และความลับส่วนตัว
