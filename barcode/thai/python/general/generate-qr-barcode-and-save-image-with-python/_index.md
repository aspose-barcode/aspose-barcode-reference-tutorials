---
category: general
date: 2026-11-27
description: สร้างบาร์โค้ด QR ใน Python ด้วย Aspose.Barcode และเรียนรู้วิธีบันทึกรูปภาพบาร์โค้ดลงดิสก์อย่างรวดเร็ว
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: th
lastmod: 2026-11-27
og_description: สร้างบาร์โค้ด QR ด้วย Python และ Aspose.Barcode พร้อมบันทึกรูปภาพบาร์โค้ดทันที
  ทำตามตัวอย่างเต็มเพื่อสร้าง ปรับแต่ง และจัดเก็บ QR โค้ด
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: สร้าง QR barcode และบันทึกรูปภาพด้วย Python – คู่มือแบบขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: สร้างบาร์โค้ด QR และบันทึกรูปภาพด้วย Python
url: /th/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง QR barcode และบันทึกภาพด้วย Python

หากคุณต้องการ **สร้าง QR barcode** ในแอปพลิเคชัน Python คำแนะนำนี้จะแสดงวิธีทำโดยใช้ไลบรารี Aspose.Barcode คุณจะได้เรียนรู้วิธี **บันทึกภาพ barcode** ไปยังโฟลเดอร์ในเครื่องของคุณ วิธีดึงข้อมูลเวอร์ชันของไลบรารี และวิธีจัดการกับส่วนขยายของ codetext

การสร้าง QR code เป็นความต้องการทั่วไปสำหรับระบบตั๋ว, การชำระเงินผ่านมือถือ, และการติดตามสินค้า เมื่อจบบทเรียนนี้คุณจะมีสคริปต์พร้อมรันที่สร้างไฟล์ภาพ QR barcode และพิมพ์ข้อมูลเวอร์ชันสำหรับการดีบักหรือการปฏิบัติตามมาตรฐาน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* Python 3.8 หรือใหม่กว่า
* แพคเกจ `aspose-barcode` ติดตั้งด้วย `pip install aspose-barcode`
* สิทธิ์การเขียนในไดเรกทอรีที่ภาพ barcode จะถูกจัดเก็บ

ไม่ต้องใช้บริการภายนอกเพิ่มเติม; กระบวนการทั้งหมดทำงานบนเครื่องของคุณ

## ขั้นตอนที่ 1: สร้าง extended codetext ด้วย `ExtCodetextBuilder`

Extended codetext ช่วยให้คุณผสมข้อความธรรมดาและส่วน ECI (Extended Channel Interpretation) ไว้ใน QR code เดียว ซึ่งมีประโยชน์เมื่อจำเป็นต้องฝังอักขระจากชุดอักขระต่าง ๆ เช่น สัญลักษณ์ยูโร

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**ทำไมขั้นตอนนี้สำคัญ:**  
`ExtCodetextBuilder` ประกอบสตริงสุดท้ายที่ตัวเข้ารหัส QR จะประมวลผล หากไม่ได้สร้าง extended codetext barcode จะมีเฉพาะอักขระ ASCII ธรรมดาและไม่สามารถแสดงสัญลักษณ์เฉพาะภาษาต่าง ๆ ได้

## ขั้นตอนที่ 2: ดึงสตริง extended codetext ที่รวมกันแล้ว

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

ผลลัพธ์จะเป็นแบบนี้:

```
Extended codetext: ABC123[ECI3]€123
```

เครื่องหมาย `[ECI3]` ในวงเล็บบอกตัวเข้ารหัส QR ให้สลับไปใช้ชุดอักขระที่ระบุสำหรับอักขระต่อไป

## ขั้นตอนที่ 3: สร้าง QR barcode ด้วย extended codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**คำอธิบาย:**  
`BarcodeGenerator` รับอาร์กิวเมนต์สองค่า: ประเภท barcode (`QR`) และข้อมูลที่จะเข้ารหัส (`extended_codetext`). ตัวสร้างจะเตรียมโครงสร้างภายในทั้งหมดที่จำเป็นสำหรับการเรนเดอร์

## ขั้นตอนที่ 4: บันทึกภาพ barcode ที่สร้างขึ้น

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**ทำไมควรใช้วิธีนี้:**  
การเรียก `save` โดยตรงจะเขียนภาพลงดิสก์โดยอิงจากรูปแบบไฟล์ที่ระบุในส่วนขยายของชื่อไฟล์ วิธีนี้รองรับ PNG, JPEG, BMP, และ TIFF ให้คุณมีความยืดหยุ่นสำหรับผู้ใช้ปลายทางที่แตกต่างกัน

### ตรวจสอบภาพที่บันทึกไว้

เปิดไฟล์ `output/qr_extended.png` ด้วยโปรแกรมดูภาพใดก็ได้ คุณควรเห็น QR code ที่เมื่อสแกนแล้วจะคืนสตริง `ABC123€123`. เครื่องสแกน QR สมัยใหม่ส่วนใหญ่จะจัดการส่วน ECI โดยอัตโนมัติ

## ขั้นตอนที่ 5: สอบถามข้อมูลเวอร์ชันของ Aspose.BarCode (ไม่บังคับแต่เป็นประโยชน์)

การรู้เวอร์ชันที่แน่นอนของไลบรารี Aspose.BarCode ช่วยเมื่อคุณต้องรายงานบั๊กหรือยืนยันความเข้ากันได้

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

ผลลัพธ์ทั่วไป:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## สคริปต์เต็ม – คัดลอก, วาง, แล้วรัน

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

การรันสคริปต์จะสร้างภาพ QR code และพิมพ์ทั้ง extended codetext และรายละเอียดเวอร์ชันลงคอนโซล

## ความแตกต่างทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับแนะนำ |
|-----------|------------------------|
| **ชุดอักขระที่แตกต่าง** | เปลี่ยนตัวระบุ ECI ที่ส่งให้ `add_eci_codetext`. สำหรับ UTF‑8 ใช้ `5`. |
| **การแก้ไขข้อผิดพลาดระดับสูง** | ตั้งค่า `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` ก่อนเรียก `save`. |
| **ขนาดภาพที่กำหนดเอง** | ใช้ `barcode.parameters.image_width` และ `barcode.parameters.image_height` เพื่อควบคุมขนาดพิกเซล |
| **ผลลัพธ์ที่ไม่ใช่ PNG** | เปลี่ยนส่วนขยายไฟล์ใน `output_path` เป็น `.jpg` หรือ `.bmp`. ไลบรารีจะเลือก encoder ที่เหมาะโดยอัตโนมัติ |

## เคล็ดลับระดับมืออาชีพ

* **สร้างโฟลเดอร์ผลลัพธ์** อย่างโปรแกรมเมติกหากอาจไม่มีอยู่:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **ตรวจสอบ QR code** หลังการสร้างโดยอ่านกลับด้วย `aspose.barcode.BarcodeReader`. วิธีนี้ทำให้มั่นใจว่าข้อมูลที่เข้ารหัสตรงกับที่คาดหวัง โดยเฉพาะเมื่อใช้ส่วน ECI

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **เคล็ดลับประสิทธิภาพ** – ใช้ instance ของ `BarcodeGenerator` เพียงตัวเดียวหากต้องสร้าง QR code จำนวนมากในลูป. รีเซ็ตคุณสมบัติ `code_text` แทนการสร้างอ็อบเจกต์ใหม่ในแต่ละรอบ

## สรุป

คุณได้เรียนรู้วิธี **สร้าง QR barcode** ด้วย Python และ Aspose.Barcode, วิธีสร้าง extended codetext ที่ผสมข้อความธรรมดาและส่วน ECI, และวิธี **บันทึกภาพ barcode** ไปยังดิสก์อย่างถูกต้อง สคริปต์ยังแสดงวิธีดึงข้อมูลเวอร์ชันของไลบรารีเพื่อการแก้ปัญหา

ขั้นตอนต่อไปที่คุณอาจสนใจ:

* เพิ่มโลโก้หรือสีที่กำหนดเองให้กับ QR code
* ฝัง QR barcode ลงใน PDF โดยใช้ Aspose.PDF
* ทำการสร้างเป็นชุดสำหรับข้อมูลจำนวนมากโดยอัตโนมัติ

ลองทดลองกับ payload ข้อมูลต่าง ๆ, ระดับการแก้ไขข้อผิดพลาด, และรูปแบบภาพที่แตกต่างกันได้เลย. Happy coding!

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดตัวอย่างทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}