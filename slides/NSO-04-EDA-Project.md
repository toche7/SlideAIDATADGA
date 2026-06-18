---
marp: true
theme: mahidol-green
paginate: true
size: 16:9
footer: "Stat on Campus | Session 04"

---

<!-- _class: lead -->

<style scoped>
.logo-bar { position: absolute; top: 36px; right: 64px; display: flex; align-items: center; gap: 16px; }
.logo-bar img { width: 100px; height: 100px; object-fit: contain; }
</style>

<div class="logo-bar">
  <img src="../fig/logos/mahidol.svg" alt="Mahidol University">
  <img src="../fig/logos/nso.png" alt="NSO">
</div>

# Session 04

# Project: Data EDA and Visualization with Gemini in Colab

Stat on Campus: Data innovators 
Turning data into impact for public sector

Taweesak Samanchuen, Ph.D.
Mahidol University


---
## วัตถุประสงค์ของ Session
เมื่อจบช่วงนี้ ผู้เข้าอบรมสามารถ:
1. สร้าง EDA Pipeline ที่มี workflow ชัดเจน
2. สรุป Insight ระดับต้นเพื่อใช้ต่อใน Session ถัดไป
3. สร้างกราฟที่เหมาะสมกับข้อมูลและเป้าหมายการวิเคราะห์
4. สื่อสารผลการวิเคราะห์ด้วย Visualization ให้ผู้บริหารและผู้เกี่ยวข้องเข้าใจได้ง่าย
5. ใช้ Gemini in Colab ช่วยคิด วิเคราะห์ และเขียนโค้ดในโน้ตบุ๊กเดียว




---

## Project Instructions

1. แบ่งกลุ่มกลุ่มละ 4-5 คน
2. ให้เลือกข้อมูลจาก ที่กำหนดให้ 
3. ตรวจสอบและทำความเข้าใจข้อมูลเบื้องต้น เช่น ชนิดข้อมูล, ขนาดข้อมูล, ความสมบูรณ์ของข้อมูล
4. ทำ Data Quality Check และปรับข้อมูล
5. ทำ EDA และสรุปข้อค้นพบเบื้องต้น
6. สร้างกราฟเพื่อสื่อสารข้อมูลและผลการวิเคราะห์
7. สรุป Insight ระดับต้นเพื่อใช้ต่อใน Session ถัดไป
8. นำเสนอผลการวิเคราะห์และกราฟในชั้นเรียนเพื่อรับ feedback และปรับปรุงต่อไป กลุ่มละ 10 นาที

---
## Recommend Data Sources

| Dataset | เหมาะฝึกเรื่องอะไร | คำถามที่ใช้ทำ EDA |
|---|---|---|
| Palmer Penguins | missing values, categorical comparison, outlier check | ชนิดของ penguin แต่ละกลุ่มต่างกันอย่างไร |
| Hotel Booking Demand | duplicate check, missing values, date parsing, cancellation analysis | ลูกค้าแบบใดยกเลิกการจองบ่อยที่สุด |
| Bike Sharing Demand | time series, seasonality, outlier, feature extraction จากวันที่ | ช่วงเวลาใดมี demand สูงหรือต่ำผิดปกติ |
| Ames Housing | skewed data, missing values, categorical cleanup, correlation | ปัจจัยใดสัมพันธ์กับราคาบ้านมากที่สุด |



---
## ชุดที่แนะนำสำหรับ Project

### 1) Palmer Penguins

- คำอธิบายข้อมูล: ข้อมูลนกเพนกวิน 3 สายพันธุ์ จากหมู่เกาะ Palmer ในทวีปแอนตาร์กติกา
- เหมาะกับผู้เริ่มต้นเพราะโครงสร้างข้อมูลไม่ซับซ้อนเกินไป
- มีทั้งตัวแปรเชิงตัวเลขและเชิงหมวดหมู่ เช่น `species`, `island`, `sex`
- ฝึก missing values, group comparison, boxplot, scatter plot และ pairplot ได้ดี
- เหมาะกับการสอน univariate และ bivariate analysis ก่อนขยับไปงานที่ซับซ้อนกว่า
- Link: `https://allisonhorst.github.io/palmerpenguins/`
- CSV: `https://vincentarelbundock.github.io/Rdatasets/csv/palmerpenguins/penguins.csv`

---

### 2) Hotel Booking Demand

- คำอธิบายข้อมูล: ข้อมูลการจองโรงแรม city hotel และ resort hotel พร้อมสถานะการยกเลิก การเข้าพัก และช่องทางการจอง
- เหมาะมากกับการฝึก clean ข้อมูลจริงที่มี missing และ duplicates
- วิเคราะห์ cancellation, lead time, market segment, ADR ได้หลากหลาย
- ทำ univariate, bivariate, time-based EDA ได้ครบ
- เหมาะกับโจทย์ธุรกิจและการสื่อสารเชิงตัดสินใจ
- Link: `https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand`
- Data description: `https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-02-11/readme.md`

---

### 3) Bike Sharing Demand

- คำอธิบายข้อมูล: ข้อมูลการเช่าจักรยานรายชั่วโมงและรายวัน พร้อมสภาพอากาศ ฤดูกาล และสถานะวันทำงาน
- เด่นเรื่อง time series และการสร้าง feature จาก datetime
- ฝึกแยก `hour`, `day`, `month`, `season`, `workingday`
- เหมาะกับ line chart, heatmap, rolling average, weekday-weekend comparison
- ช่วยให้เห็น seasonality และ anomaly ได้ชัด
- Link: `https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset`
- Download: `https://archive.ics.uci.edu/static/public/275/bike+sharing+dataset.zip`


---

### 4) Ames Housing

- คำอธิบายข้อมูล: ข้อมูลบ้านในเมือง Ames, Iowa ที่มีรายละเอียดคุณลักษณะบ้านและราคาขายจริงหลายมิติ
- เหมาะถ้าต้องการ dataset ที่ feature เยอะและ realistic มากขึ้น
- ฝึกจัดการ missing values หลายแบบ, skewness, outlier, และ categorical cleanup
- ใช้ correlation และ scatter plot matrix ได้ดี
- เหมาะกับทีมที่อยากไปไกลถึง regression เบื้องต้น
- Link: `https://www.openml.org/search?type=data&id=42165`

---
## การแข่งขันและการให้คะแนน

- การแข่งขัน: กลุ่มที่มีการวิเคราะห์และนำเสนอได้ดีที่สุดจะได้รับรางวัล
- การให้คะแนน: คะแนนจะพิจารณาจากความชัดเจนของคำถามวิเคราะห์, ความถูกต้องของการวิเคราะห์, ความเหมาะสมของกราฟ, และความสามารถในการสื่อสารข้อมูลให้เข้าใจง่าย
- รางวัล: รางวัลสำหรับกลุ่มที่ชนะจะเป็นของที่ระลึกจาก NSO และ Mahidol University รวมถึงโอกาสในการนำเสนอผลงานในงานสัมมนาเกี่ยวกับข้อมูลในอนาคต

---
<!-- _class: lead -->
# Thank you for your attention! 


---

## วิทยากร


**ผศ.ดร.ทวีศักดิ์ สมานชื่น**
*Asst. Prof. Taweesak Samanchuen, Ph.D.*

- รองผู้อำนวยการฝ่ายดิจิทัลเทคโนโลยี **MULKC**
- อาจารย์ประจำสาขา **ITM** คณะวิศวกรรมศาสตร์ มหาวิทยาลัยมหิดล
- หัวหน้าโครงการ **CBTU** 

🔗 [Profile](https://itm.eg.mahidol.ac.th/personnel/taweesak-samanchuen/)  
📧 t.samanchuen@gmail.com
☎ 081-441-4906

websit: [cbtumu.net](https://cbtumu.net) | facebook: [cbtumu](https://www.facebook.com/CBTUMU/)


---

<!-- _class: lead -->

# ขอบคุณครับ

**ผศ.ดร.ทวีศักดิ์ สมานชื่น**
