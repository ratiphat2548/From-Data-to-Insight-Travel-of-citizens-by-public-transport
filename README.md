# 🚝 THackle Mini-Hackathon: Public Transport EDA (Dataset 5)

## 📖 Overview
โปรเจกต์นี้เป็นส่วนหนึ่งของการแข่งขัน **THackle Mini-Hackathon "From Data to Insight"** (Super AI Engineer) โดยมุ่งเน้นไปที่การนำ Open Data มาวิเคราะห์เชิงลึก (Exploratory Data Analysis: EDA) และทำ Data Storytelling 

ใน Repository นี้ (Dataset 5) เป็นการวิเคราะห์ **ข้อมูลสถิติปริมาณการเดินทางด้วยระบบขนส่งสาธารณะ (Public Transport)** โดยรวบรวมข้อมูลข้ามปี (พ.ศ. 2568 และต้นปี 2569) เพื่อนำมาตรวจสอบคุณภาพข้อมูล (Data Quality) จัดการค่าว่าง (Missing Values) และเตรียมโครงสร้างข้อมูลให้พร้อมสำหรับการสร้าง Data Visualization ต่อไป

## 🎯 Project Objectives
อ้างอิงจากเกณฑ์การประเมินของการแข่งขัน โปรเจกต์นี้มุ่งเน้นที่:
* **Data Preparation:** ดึงข้อมูลสาธารณะจาก Google Drive ผ่าน API โดยตรง เพื่อความสะดวกในการทำซ้ำ (Reproducibility)
* **Data Cleansing & Filtering:** แปลงชนิดข้อมูลวันที่ (Datetime) และกรองขอบเขตข้อมูลให้ตรงตามโจทย์ที่กำหนด
* **Data Quality Check:** วิเคราะห์ความสมบูรณ์ของชุดข้อมูลและหาช่องโหว่ (Missing Values) ผ่าน Heatmap/Matrix 
* **Localization:** ตั้งค่าระบบฟอนต์ภาษาไทย (Itim Font) ใน Matplotlib เพื่อให้กราฟสามารถอธิบาย Insight บริบทของประเทศไทยได้อย่างสมบูรณ์

## ⚙️ Data Processing Pipeline
ขั้นตอนการประมวลผลข้อมูลในไฟล์ `Super_AI_BTS.ipynb` ประกอบด้วย:
1. **Public Data Loading:** โหลดข้อมูลปี 2568 และ 2569 รูปแบบ CSV จากลิงก์ตรง (Direct Link)
2. **Data Manipulation & Consolidation:** นำข้อมูลทั้ง 2 ปีมาเชื่อมต่อกัน (Row-wise Concat) และตรวจสอบความสมบูรณ์ของ Data Frame เบื้องต้น (รวมข้อมูลกว่า 71,977 Records)
3. **Missing Value Visualization:** ใช้ไลบรารี `missingno` สร้าง Matrix Chart เพื่อหาพิกัดและแนวโน้มของการเกิดค่าว่าง (NaN) ในคอลัมน์สำคัญเช่น 'ปริมาณ' การเดินทาง
4. **Thai Font Configuration:** ติดตั้งและเซ็ตอัปฟอนต์สำหรับสร้างกราฟ Data Storytelling ในเฟสถัดไป

## 🛠️ Tech Stack & Libraries
* **Data Manipulation:** ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
* **Data Visualization:** ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Seaborn](https://img.shields.io/badge/Seaborn-%234185F4.svg?style=for-the-badge)
* **Data Quality Tools:** `missingno` (สำหรับการทำ Missing Values Profiling)
* **Environment:** Google Colab / Jupyter Notebook

## 🚀 How to Run
1. โคลน (Clone) Repository นี้ลงในเครื่องของคุณ
2. เปิดไฟล์ `Super_AI_BTS.ipynb` ผ่าน **Google Colab** หรือ **Jupyter Notebook**
3. รันเซลล์ (Run all) ตามลำดับ ระบบจะทำการดาวน์โหลดฟอนต์ภาษาไทย โหลด Dataset และแสดงผลกราฟคุณภาพข้อมูลให้ทันทีโดยไม่ต้องตั้งค่า Path เพิ่มเติม
