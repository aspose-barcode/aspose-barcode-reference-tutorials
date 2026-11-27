---
category: general
date: 2026-11-27
description: เรียนรู้วิธีปรับความสูงของบาร์โค้ดในเครื่องสร้างบาร์โค้ด DataBar Omni‑Directional
  โค้ดทีละขั้นตอนแสดงการตั้งค่าความสูงเป็น 30 px และ 60 px
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: th
lastmod: 2026-11-27
og_description: ปรับความสูงของบาร์โค้ดในตัวสร้างบาร์โค้ด DataBar Omni‑Directional
  ด้วย Python. ทำตามคู่มือเต็มเพื่อกำหนดความสูง, มิติ X, และบันทึกภาพ PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: ปรับความสูงของบาร์โค้ดในตัวสร้าง DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: วิธีปรับความสูงของบาร์โค้ดในตัวสร้าง DataBar Omni‑Directional
url: /th/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับความสูงของบาร์โค้ดใน DataBar Omni‑Directional generator

หากคุณต้องการ **ปรับความสูงของบาร์โค้ด** สำหรับ DataBar Omni‑Directional barcode คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียด คุณจะได้เห็นตัวอย่าง Python ที่ทำงานได้เต็มรูปแบบซึ่งเปลี่ยนความสูงของบาร์จาก 30 px เป็น 60 px พร้อมคงค่า X‑dimension และรูปแบบภาพให้สอดคล้องกัน

การเปลี่ยนขนาดภาพของบาร์โค้ดเป็นความต้องการทั่วไปเมื่อบาร์โค้ดต้องพอดีกับขนาดหรือแนวทางการออกแบบของป้ายกำกับเฉพาะ นอกจากความสูงของบาร์แล้ว คุณอาจต้องการปรับ **X‑dimension** (ขนาดโมดูล) หรือเลือก **รูปแบบภาพของบาร์โค้ด** ที่แตกต่างกัน เช่น PNG หรือ JPEG

ในบทเรียนนี้คุณจะได้ทำสิ่งต่อไปนี้

* ติดตั้งไลบรารีที่จำเป็น (GroupDocs.Barcode for Python)
* สร้างตัวสร้าง DataBar Omni‑Directional barcode
* ตั้งค่าขนาดโมดูลด้วย `XDimension`
* ปรับคุณสมบัติความสูงของบาร์สองครั้ง
* บันทึกภาพที่ได้ใน **BarCodeImageFormat** ที่ต้องการ

ไม่จำเป็นต้องมีประสบการณ์กับ GroupDocs API มาก่อน—เพียงความรู้พื้นฐานของ Python

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

* Python 3.8 หรือใหม่กว่า ติดตั้งแล้ว
* แพคเกจ `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

หากคุณไม่คุ้นเคยกับ **DataBar Omni‑Directional barcode** มันจะเข้ารหัส GTIN 14 หลักและถูกใช้กันอย่างแพร่หลายในอุตสาหกรรมค้าปลีกเพื่อสแกนจากทุกทิศทาง

## ขั้นตอนที่ 1: ตั้งค่าตัวสร้าง DataBar Omni‑Directional barcode

ก่อนอื่น ให้นำเข้าคลาสที่จำเป็นและสร้างอินสแตนซ์ของตัวสร้างด้วยข้อมูล GTIN ที่คุณต้องการเข้ารหัส

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Why this matters:* ค่าคงที่ `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีให้สร้างสัญลักษณ์ Omni‑Directional ข้อความข้อมูลรวม AI `(01)` ที่ระบุค่า GTIN‑14

## ขั้นตอนที่ 2: กำหนด X‑dimension (ขนาดโมดูล)

X‑dimension ควบคุมความกว้างของบาร์ที่แคบที่สุด ค่าโดยทั่วไปสำหรับการแสดงผลบนหน้าจอคือ **2 px ต่อโมดูล**

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

การใช้ **set XDimension** อย่างสม่ำเสมอช่วยให้บาร์โค้ดปรับขนาดได้อย่างถูกต้องบนเครื่องพิมพ์และสแกนเนอร์ที่หลากหลาย

## ขั้นตอนที่ 3: ปรับความสูงของบาร์เป็น 30 px และบันทึกภาพ

ตอนนี้เราจะเปลี่ยนคุณสมบัติความสูงของบาร์ ความสูงแรกที่ใช้คือ **30 px** ซึ่งเหมาะกับป้ายกำกับขนาดเล็ก

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

ค่าคงที่ `BarCodeImageFormat.Png` เลือกรูปแบบภาพ **barcode image format** เป็น PNG ซึ่งรักษาคุณภาพแบบ lossless

### ผลลัพธ์ที่คาดหวัง

ไฟล์ `DatabarBarHeight30Pixels.png` มี DataBar Omni‑Directional barcode ที่บาร์สูง 30 px ด้านล่างเป็นตัวอย่างภาพตัวอย่าง

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tip:** หากคุณเปิดไฟล์ PNG ในโปรแกรมแก้ไขภาพ คุณจะเห็นความสูงของบาร์ที่แน่นอน บาร์แคบมีความกว้าง 2 px ตามที่กำหนดไว้ก่อนหน้า

## ขั้นตอนที่ 4: เปลี่ยนความสูงของบาร์เป็น 60 px สำหรับบาร์โค้ดที่สูงขึ้น

สำหรับการใช้งานที่ต้องการพื้นที่ภาพใหญ่ขึ้น—เช่นป้ายกำกับสินค้าขนส่ง—คุณสามารถเพิ่มความสูงของบาร์เป็น **60 px** ได้

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

มีเพียงคุณสมบัติ `BarHeight` ที่เปลี่ยนแปลง; X‑dimension และการเข้ารหัสยังคงเหมือนเดิม ทำให้บาร์โค้ดยังคงสแกนได้

## ขั้นตอนที่ 5: บันทึกภาพบาร์โค้ดที่อัปเดต

สุดท้าย ให้บันทึกบาร์โค้ดที่สูงขึ้นเป็นไฟล์ PNG ที่สอง

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### ผลลัพธ์ที่คาดหวัง

ไฟล์ `DatabarBarHeight60Pixels.png` แสดงข้อมูลเดียวกันที่เข้ารหัสไว้ แต่บาร์แต่ละบาร์มีความสูง 60 px ความแตกต่างด้านภาพแสดงด้านล่าง

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## ตัวอย่างเต็มที่สามารถทำงานได้

รวมทุกอย่างเข้าด้วยกัน นี่คือสคริปต์สมบัติที่คุณสามารถคัดลอก‑วางลงในไฟล์ชื่อ `adjust_barcode_height.py` แล้วรันได้โดยตรง

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Run the script:

```bash
python adjust_barcode_height.py
```

คุณควรเห็นไฟล์ PNG สองไฟล์ในโฟลเดอร์ `output` แต่ละไฟล์จะแสดงความสูงของบาร์ตามที่คุณตั้งค่าไว้

## คำถามทั่วไปและกรณีขอบ

| Question | Answer |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is lossy, so prefer PNG for precise scanning. |
| **What if I need a bar height that isn’t a multiple of 10?** | The `BarHeight.Pixels` property accepts any integer value. Just assign the desired pixel count (e.g., `45`). |
| **Does changing the bar height affect the encoded data?** | No. Only the visual representation changes; the underlying data string remains identical. |
| **How do I change the X‑dimension after saving the first image?** | You can modify `gen.parameters.barcode.x_dimension.pixels` at any time before calling `save()`. The change will apply to subsequent images. |
| **Is the generator thread‑safe?** | The `BarcodeGenerator` instance is not guaranteed to be thread‑safe. Create a separate instance per thread if you generate barcodes concurrently. |

## สรุป

คุณได้เรียนรู้วิธี **ปรับความสูงของบาร์โค้ด** ใน DataBar Omni‑Directional barcode generator ด้วย Python แล้ว บทเรียนนี้ครอบคลุมการสร้างตัวสร้าง, การตั้งค่า **X‑dimension**, การแก้ไขคุณสมบัติ **barcode bar height**, และการบันทึกรูปภาพใน **barcode image format** ที่ต้องการ

จากนี้คุณสามารถทดลองกับความสูงอื่น ๆ, ขนาดโมดูลที่แตกต่างกัน, หรือสลับไปใช้รูปแบบภาพอื่น ๆ เช่น JPEG หรือ BMP คุณอาจสำรวจฟีเจอร์เพิ่มเติมของ **barcode generator python** เช่น การเพิ่มข้อความที่อ่านได้โดยมนุษย์หรือการเปลี่ยนโทนสี

Happy coding, and keep your barcodes crisp and perfectly sized!

## สิ่งที่คุณควรเรียนต่อ

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [วิธีตั้งความกว้างและปรับความสูงสำหรับ GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [สร้าง omni directional databar และภาพบาร์โค้ดใน Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}