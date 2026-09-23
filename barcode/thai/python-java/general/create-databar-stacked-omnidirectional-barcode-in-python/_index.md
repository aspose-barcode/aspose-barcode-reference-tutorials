---
category: general
date: 2026-07-30
description: สร้างบาร์โค้ด Databar Stacked Omnidirectional ด้วย Python. ทำตามคู่มือขั้นตอนนี้เพื่อกำหนดอัตราส่วน,
  XDimension, และส่งออกเป็น PNG โดยใช้ตัวสร้างบาร์โค้ด Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: th
lastmod: 2026-07-30
og_description: สร้างบาร์โค้ด Databar Stacked Omnidirectional ด้วย Python การสอนนี้แสดงวิธีตั้งค่า
  XDimension ปรับอัตราส่วนของ DataBar และบันทึกเป็น PNG ด้วย BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: สร้างบาร์โค้ด Databar แบบซ้อนหลายทิศทาง – บทเรียน Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: สร้างบาร์โค้ด Databar แบบซ้อนกันหลายทิศทางด้วย Python
url: /th/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด Databar Stacked Omnidirectional ด้วย Python

เคยต้องการ **สร้างบาร์โค้ด databar stacked omnidirectional** ด้วย Python แต่ไม่แน่ใจว่าจะเริ่มต้นอย่างไรหรือไม่? คุณไม่ได้อยู่คนเดียว—นักพัฒนาหลายคนเจออุปสรรคนี้เมื่อต้องใช้คลาส `BarcodeGenerator` ครั้งแรก ข่าวดีคือกระบวนการทั้งหมดค่อนข้างตรงไปตรงมาทันทีที่คุณเข้าใจคุณสมบัติหลัก

ในคู่มือนี้เราจะพาคุณผ่านตัวอย่างที่ทำงานได้เต็มรูปแบบ ซึ่งใช้ **python barcode generator** เพื่อกำหนดค่า XDimension ปรับอัตราส่วน DataBar และสุดท้ายส่งออกไฟล์ PNG สองไฟล์ เมื่อจบคุณจะมีความเข้าใจที่มั่นคงเกี่ยวกับการสร้างสัญลักษณ์ stacked omnidirectional คุณภาพสูงสำหรับโครงการจัดการสินค้าคงคลังหรือโลจิสติกส์ใด ๆ

## สิ่งที่คุณจะได้เรียนรู้

- วิธีสร้าง **databar stacked omnidirectional** generator พร้อม payload แบบ GTIN‑14  
- ทำไม **ขนาดพิกเซล XDimension** ถึงสำคัญต่อความน่าเชื่อถือของการสแกน  
- ผลกระทบของ **อัตราส่วน DataBar** ต่อความกว้างและความสูงของแถว  
- วิธีบันทึกผลลัพธ์เป็นไฟล์ **BarCodeImageFormat PNG**  
- เคล็ดลับการใช้วัตถุ generator เดียวกันเพื่อสร้างหลายเวอร์ชันโดยไม่เพิ่มภาระหน่วยความจำ

### ข้อกำหนดเบื้องต้น

- Python 3.8+ (ไลบรารีที่เราใช้เป็น pure‑Python ไม่ต้องมี wheel ที่คอมไพล์)  
- แพ็กเกจ `barcode-generator` (ติดตั้งด้วย `pip install barcode-generator`)  
- โฟลเดอร์ที่คุณสามารถเขียนไฟล์ได้ – สคริปต์จะบันทึกภาพ PNG สองไฟล์ลงในนั้น  

หากคุณคุ้นเคยกับการ import โมดูลพื้นฐานของ Python และโค้ดแบบ object‑oriented คุณก็พร้อมแล้ว

## สร้างบาร์โค้ด Databar Stacked Omnidirectional – ภาพรวมขั้นตอน

ด้านล่างเราจะแบ่งเวิร์กโฟลว์ออกเป็นหกขั้นตอนสั้น ๆ แต่ละขั้นเป็นโค้ดที่สามารถคัดลอก‑วางลงใน REPL หรือไฟล์สคริปต์ได้อย่างอิสระ อย่ากลัวทดลองเปลี่ยนอัตราส่วนหรือ XDimension แล้วคุณจะเห็นสไตล์ที่ต่างออกไปทันที

---

## ขั้นตอนที่ 1: สร้าง Databar Stacked Omnidirectional Generator

สิ่งแรกที่เราทำคือ **สร้าง databar stacked omnidirectional** generator instance โดยส่งค่า `EncodeTypes` enum ที่เหมาะสมและสตริงข้อมูล

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **ทำไมเรื่องนี้สำคัญ:** ธง `EncodeTypes.DatabarStackedOmniDirectional` บอกไลบรารีให้สร้างสัญลักษณ์ stacked omnidirectional ซึ่งเป็นรูปแบบ DataBar เพียงแบบเดียวที่สามารถเข้ารหัสได้ถึง 14 หลักและยังอ่านได้จากทุกมุม

---

## ตั้งค่า XDimension พิกเซล

**ขนาดพิกเซล XDimension** ควบคุมโมดูลที่เล็กที่สุด (บาร์สีดำที่บางที่สุด) ค่า `2` พิกเซลทำงานได้ดีในสถานการณ์แสดงผลบนหน้าจอส่วนใหญ่

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **เคล็ดลับมือโปร:** หากคุณวางแผนพิมพ์บาร์โค้ดที่ความละเอียด DPI สูง ให้เพิ่มค่านี้เป็น 3 หรือ 4 เพื่อหลีกเลี่ยงขอบที่เบลอ

---

## ปรับอัตราส่วน DataBar (15)

**อัตราส่วน DataBar** กำหนดความกว้างของแต่ละแถวเทียบกับความสูงของมัน อัตราส่วน `15` ทำให้แถวกว้างขึ้น ซึ่งหลายสแกนเนอร์ชอบเพราะจับภาพได้เร็ว

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **ทำไมต้องเป็น 15?** สเปค GS1 อย่างเป็นทางการแนะนำอัตราส่วนระหว่าง 10 ถึง 20 สำหรับสัญลักษณ์ stacked omnidirectional เราเลือก `15` เป็นค่าเริ่มต้นที่สมดุล

---

## ส่งออกบาร์โค้ดเป็น PNG ด้วย BarCodeImageFormat

เมื่อ generator ถูกตั้งค่าแล้ว เราจะบันทึกภาพ `BarCodeImageFormat.Png` enum ทำให้ได้ผลลัพธ์แบบ lossless เหมาะสำหรับการประมวลผลต่อไป

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **สิ่งที่คุณจะเห็น:** เปิดไฟล์ PNG ที่สร้างขึ้น คุณควรเห็นบาร์โค้ดที่คมชัด มีคอนทราสต์สูงและแถวค่อนข้างกว้าง

---

## เปลี่ยนอัตราส่วน DataBar เป็น 30

บางครั้งคุณอาจต้องการแถวที่สูงกว่าแถวกว้าง – เช่น เพื่อให้พอดีกับป้ายแคบ การเปลี่ยน **อัตราส่วน DataBar** เป็น `30` จะทำให้แต่ละแถวสูงขึ้น

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **กรณีขอบ:** อัตราส่วนที่สูงมาก (เช่น >40) อาจทำให้บาร์โค้ดสูงเกินความสูงป้ายมาตรฐาน จึงควรทดสอบบนเครื่องพิมพ์จริงก่อนใช้งานจริง

---

## ส่งออกบาร์โค้ดอีกครั้งด้วยอัตราส่วนใหม่

สุดท้าย เราใช้วัตถุ `barcode_generator` เดิมเพื่อเขียน PNG ที่สอง ไม่ต้องสร้าง generator ใหม่ – เพียงเปลี่ยนคุณสมบัติและเรียก `Save` อีกครั้ง

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **ผลลัพธ์:** ตอนนี้คุณมีไฟล์ PNG สองไฟล์ – หนึ่งไฟล์ที่มีแถวกว้าง (`AR15`) อีกไฟล์ที่มีแถวสูง (`AR30`) เปรียบเทียบกันข้าง ๆ เพื่อเลือกว่าตัวไหนทำงานดีที่สุดกับสแกนเนอร์ของคุณ

---

## ตัวอย่างทำงานเต็มรูปแบบ

รวมทุกขั้นตอนเข้าด้วยกัน นี่คือสคริปต์สมบูรณ์ที่คุณสามารถรันได้ทันที แทนที่ `YOUR_DIRECTORY` ด้วยพาธเต็มบนเครื่องของคุณ

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**ผลลัพธ์ที่คาดหวัง** (ในคอนโซลของคุณ):

```
✅ Two PNG files created – AR15 and AR30
```

และไฟล์ภาพสองไฟล์จะปรากฏในโฟลเดอร์เป้าหมาย พร้อมสำหรับการทดสอบสแกน

---

## สรุป

เราได้ **สร้างบาร์โค้ด databar stacked omnidirectional** ด้วย Python ปรับ **ขนาดพิกเซล XDimension** ทดลองกับการตั้งค่า **อัตราส่วน DataBar** สองค่า แล้วส่งออกผลลัพธ์เป็นไฟล์ **BarCodeImageFormat PNG** ทั้งหมดทำได้ในไม่กี่บรรทัด แต่ให้คุณควบคุมลักษณะภาพที่สำคัญต่อสแกนเนอร์ได้อย่างเต็มที่

ต่อไปคุณอาจลองเปลี่ยน payload เป็น GTIN อื่น ๆ เล่นสีโดยแปลง PNG เป็นภาพแบบ palette‑based หรือสร้างรายงาน PDF ที่ฝัง PNG ทั้งสองข้างกัน `BarcodeGenerator` class มีความยืดหยุ่นพอที่จะรองรับทุกกรณีเหล่านี้ ดังนั้นอย่ากลัวทดลอง

มีคำถามเกี่ยวกับการใช้งานเฉพาะหรือเจอข้อผิดพลาด? แสดงความคิดเห็นด้านล่าง แล้วผมจะช่วยคุณอย่างเต็มที่ ขอให้เขียนโค้ดสนุกนะ!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}