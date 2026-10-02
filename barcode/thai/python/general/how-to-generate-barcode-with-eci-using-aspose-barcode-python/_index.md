---
category: general
date: 2026-08-19
description: วิธีสร้างบาร์โค้ดด้วย ECI โดยใช้ Aspose.Barcode สำหรับ Python เรียนรู้วิธีเพิ่มข้อมูล
  ECI ผสมข้อความธรรมดา และบันทึกภาพในคู่มือที่ชัดเจนหนึ่งเดียว.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: th
lastmod: 2026-08-19
og_description: วิธีสร้างบาร์โค้ดด้วย ECI โดยใช้ Aspose.Barcode สำหรับ Python. ตามบทแนะนำนี้เพื่อเรียนรู้วิธีเพิ่มข้อมูล
  ECI, ปรับแต่งลักษณะ, และบันทึกผลลัพธ์.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: วิธีสร้างบาร์โค้ดด้วย ECI โดยใช้ Aspose.Barcode Python – ทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: วิธีสร้างบาร์โค้ดด้วย ECI โดยใช้ Aspose.Barcode Python
url: /th/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดด้วย ECI โดยใช้ Aspose.Barcode Python

หากคุณต้องการทราบ **วิธีสร้างบาร์โค้ด** ที่มีทั้งอักขระธรรมดาและข้อมูลที่เข้ารหัสด้วย ECI คำแนะนำนี้จะแสดงกระบวนการทั้งหมด คุณจะได้เห็น **วิธีเพิ่มส่วน eci** ปรับขนาด และบันทึกภาพลงดิสก์ด้วยสคริปต์ที่ทำงานได้ในครั้งเดียว

บทเรียนนี้ครอบคลุม:

* การดึงเวอร์ชันของไลบรารี Aspose.Barcode (ไม่บังคับแต่มีประโยชน์สำหรับการดีบัก)  
* การสร้างสตริง codetext ที่ขยายได้ซึ่งผสมอักขระธรรมดาและอักขระที่เข้ารหัสด้วย ECI  
* การสร้างตัวสร้างบาร์โค้ดสำหรับ symbology ที่รองรับ codetext ที่ขยายได้  
* การปรับขนาดบาร์โค้ดและบันทึกไฟล์ PNG สุดท้าย

ไม่จำเป็นต้องอ้างอิงเอกสารภายนอก; คัดลอกโค้ด, รันมัน, แล้วคุณจะได้ภาพบาร์โค้ดที่รวมอักขระจีนที่เข้ารหัสด้วย ECI 26 (UTF‑8)

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

* Python 3.8 หรือใหม่กว่า  
* แพ็กเกจ `aspose-barcode` ติดตั้งแล้ว (`pip install aspose-barcode`)  
* สิทธิ์การเขียนในโฟลเดอร์ที่คุณตั้งใจจะบันทึกไฟล์ PNG

หากคุณใช้ virtual environment ให้เปิดใช้งานก่อนเพื่อแยกการพึ่งพาออกจากระบบหลัก

## ขั้นตอนที่ 1: ตรวจสอบเวอร์ชันของ Aspose.Barcode (ไม่บังคับ)

การรู้เวอร์ชันที่แน่นอนของไลบรารีช่วยเมื่อคุณต้องรายงานบั๊กหรือเปรียบเทียบฟีเจอร์ระหว่างรุ่นต่าง ๆ

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*ทำไมจึงสำคัญ*: ผลลัพธ์ของเวอร์ชันยืนยันว่ารันไทม์ตรงกับเอกสารที่คุณกำลังทำตาม รุ่นที่ต่างกันอาจรองรับค่า ECI ที่แตกต่างกัน ดังนั้นนี่เป็นการตรวจสอบอย่างรวดเร็ว

## ขั้นตอนที่ 2: สร้าง extended codetext ด้วยส่วนธรรมดาและส่วนที่เข้ารหัสด้วย ECI

Aspose.Barcode มี `ExtCodetextBuilder` เพื่อเชื่อมต่อข้อมูลธรรมดาและส่วนที่เข้ารหัสด้วย ECI ในตัวอย่างนี้เราจะผสมสตริงตัวเลขกับอักขระจีน

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*คำอธิบาย*:  
* `add_plain_codetext` แทรกข้อมูลที่ symbology ของบาร์โค้ดถือเป็นอักขระธรรมดา  
* `add_eci_codetext` บอกตัวสร้างให้ใส่ตัวบ่งชี้ ECI (ที่นี่ **26** ซึ่งแมปกับ UTF‑8) ก่อนข้อความที่ให้มา นี่คือ **วิธีเพิ่ม eci** ลงในบาร์โค้ด

คุณสามารถเรียก `add_eci_codetext` หลายครั้งเพื่อฝังบล็อกภาษาต่าง ๆ ได้ ตัวสร้างจะจัดการลำดับ escape sequence ที่จำเป็นโดยอัตโนมัติ

## ขั้นตอนที่ 3: เลือก symbology ที่รองรับ extended codetext

ไม่ใช่ทุกประเภทของบาร์โค้ดจะเก็บส่วน ECI ได้ Code 128, QR, และ Data Matrix เป็นตัวเลือกที่พบบ่อย ตัวอย่างใช้ Code 128 เพราะรองรับอย่างกว้างขวางและทำงานได้ดีกับข้อมูลอัลฟานูเมอริกผสม

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*ทำไมต้อง Code 128?*: รองรับช่วง ASCII ทั้งหมดและลำดับ escape ของ ECI ที่สร้างโดย builder ทำให้เหมาะกับสถานการณ์ “วิธีสร้างบาร์โค้ด” ที่ผสมข้อความธรรมดาและข้อความที่เข้ารหัส

## ขั้นตอนที่ 4: ปรับลักษณะของบาร์โค้ด

คุณสามารถควบคุมขนาด, ความสูง, ระยะขอบ, และลักษณะภาพอื่น ๆ ผ่านอ็อบเจ็กต์ `parameters`

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*เคล็ดลับ*: หากคุณวางแผนพิมพ์บาร์โค้ด ให้เพิ่มค่า `x_dimension` และ `bar_height` อย่างสัดส่วนเพื่อรักษาความอ่านได้ที่ DPI เป้าหมาย

## ขั้นตอนที่ 5: บันทึกภาพบาร์โค้ด

สุดท้ายให้เขียนภาพที่สร้างขึ้นลงไฟล์ Aspose.Barcode รองรับ PNG, JPEG, BMP และรูปแบบอื่น ๆ อีกหลายชนิด

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

ตรวจสอบให้แน่ใจว่าโฟลเดอร์ `output` มีอยู่หรือสร้างด้วย `os.makedirs("output", exist_ok=True)` ก่อนเรียก `save`

### ผลลัพธ์ที่คาดหวัง

เมื่อคุณเปิดไฟล์ `extended_codetext.png` คุณควรเห็นบาร์โค้ด Code 128 ที่เข้ารหัสสตริงตัวเลข `1234567890` ตามด้วยอักขระจีน “特殊字符” การสแกนบาร์โค้ดด้วยสแกนเนอร์สมัยใหม่ที่รองรับ ECI จะคืนค่าข้อความผสมเดิม

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="บาร์โค้ดที่สร้างด้วยตัวอย่างวิธีสร้างบาร์โค้ด"}

## คำถามทั่วไปและกรณีขอบ

### ถ้าต้องการชุดอักขระอื่น?

เลือกค่า ECI ที่เหมาะสมจากตาราง ISO/IEC 18004 ตัวอย่างเช่น ECI 27 แทนค่า ISO‑8859‑1 (Latin‑1) แทนที่ตัวระบุตัวเลขใน `add_eci_codetext` ตามนั้น

### สามารถฝังบล็อก ECI มากกว่าหนึ่งบล็อกได้หรือไม่?

ได้ เรียก `add_eci_codetext` หลายครั้ง Builder จะใส่โค้ดสลับ ECI ที่จำเป็นระหว่างบล็อกโดยคงลำดับที่คุณเพิ่มไว้

### ตัวสร้างรองรับ QR code ที่มี ECI หรือไม่?

แน่นอน แทนที่ `barcode.Symbology.CODE_128` ด้วย `barcode.Symbology.QR` และปรับพารามิเตอร์เฉพาะ QR (เช่นระดับการแก้ไขข้อผิดพลาด) ผ่าน `generator.parameters.qr`

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### จะจัดการกับสตริงข้อมูลยาวมากอย่างไร?

สำหรับบาร์โค้ดเชิงเส้นเช่น Code 128 ความยาวสูงสุดประมาณ 80 อักขระเมื่อใช้ extended codetext หากเกินนี้ให้พิจารณาเปลี่ยนไปใช้ symbology แบบสองมิติ เช่น QR หรือ Data Matrix ซึ่งสามารถเก็บข้อมูลได้หลายพันอักขระ

## สคริปต์เต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมสมบัติที่คุณสามารถคัดลอก‑วางลงในไฟล์ชื่อ `generate_extended_barcode.py` แล้วรันได้โดยตรง

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## สิ่งที่คุณควรเรียนต่อไป


บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการดำเนินการแบบต่าง ๆ ในโปรเจกต์ของคุณเอง

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}