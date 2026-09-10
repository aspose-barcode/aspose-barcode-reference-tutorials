---
category: general
date: 2026-09-10
description: เข้ารหัสอักขระที่ไม่ใช่ ASCII ใน QR code และบันทึกภาพ QR code ด้วยตัวสร้าง
  Python อย่างง่าย ตามคู่มือขั้นตอนโดยใช้ ExtCodetextBuilder และ BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: th
lastmod: 2026-09-10
og_description: เข้ารหัสอักขระที่ไม่ใช่ ASCII ใน QR โค้ดและบันทึกรูปภาพ QR โค้ดด้วย
  Python บทเรียนนี้แสดงวิธีสร้างข้อความโค้ดที่ขยาย, สร้าง QR โค้ด, และบันทึกรูปภาพ.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: เข้ารหัสอักขระที่ไม่ใช่ ASCII ใน QR code และบันทึกภาพ QR code – คู่มือ Python
  ทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: เข้ารหัสอักขระที่ไม่ใช่ ASCII ใน QR code และบันทึกภาพ QR code
url: /th/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เข้ารหัสอักขระที่ไม่ใช่ ASCII ใน QR code และบันทึกภาพ QR code

หากคุณต้องการ **encode non ASCII characters** ใน QR code คู่มือนี้จะแสดงให้คุณทราบอย่างละเอียดว่าต้องทำอย่างไรและจากนั้น **save QR code image** ลงดิสก์ ไม่ว่าคุณจะจัดการข้อมูลภาษารัสเซีย, จีน หรืออีโมจิ, ExtCodetextBuilder จะช่วยให้คุณผสานข้อความธรรมดาและส่วนที่เข้ารหัสด้วย ECI ได้โดยไม่ต้องจัดการไบต์ด้วยตนเอง

คุณจะได้เรียนรู้วิธีสร้างสตริง extended codetext, สร้าง QR code ที่เข้าใจสตริงนั้น, และสุดท้ายเขียนภาพบาร์โค้ดลงไฟล์ คู่มือนี้สมมติว่าคุณมีความรู้พื้นฐานของ Python และได้ติดตั้ง SDK `barcode` แล้ว

## ข้อกำหนดเบื้องต้น

* ติดตั้ง Python 3.8+ แล้ว
* แพคเกจ Python `barcode` (หรือ SDK ที่เหมาะสม) ที่ให้บริการ `ExtCodetextBuilder`, `CodetextEncodingType`, และ `BarcodeGenerator`
* สิทธิ์การเขียนในไดเรกทอรีที่คุณต้องการ **save QR code image**

คุณสามารถติดตั้ง SDK ด้วย pip (แทนที่ `barcode-sdk` ด้วยชื่อแพคเกจจริง):

```bash
pip install barcode-sdk
```

## ขั้นตอนที่ 1: สร้าง extended codetext builder

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `ExtCodetextBuilder`. วัตถุนี้จะรวบรวมหลายส่วนของข้อความและสร้างสตริงเดียวที่สัญลักษณ์ QR code สามารถตีความได้

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*ทำไมสิ่งนี้ถึงสำคัญ*: QR codes support **extended codetext**, which means you can embed several encoding modes (plain, ECI, etc.) in one barcode. The builder abstracts the low‑level formatting required by the QR specification.

## ขั้นตอนที่ 2: เพิ่มส่วน plain‑text

plain text เป็นโหมดเริ่มต้นและทำงานกับอักขระ ASCII การเพิ่มมันเป็นส่วนแรกจะให้ผลลัพธ์ที่อ่านได้สำหรับสแกนเนอร์ที่ละเว้น ECI

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

หากคุณละเว้นขั้นตอนนี้ QR code จะมีเพียงส่วน ECI เท่านั้น ซึ่งอาจทำให้เครื่องอ่านรุ่นเก่าบางรุ่นไม่สามารถถอดรหัสได้อย่างถูกต้อง

## ขั้นตอนที่ 3: เพิ่มส่วนที่เข้ารหัสด้วย ECI สำหรับอักขระที่ไม่ใช่ ASCII

เพื่อรวมอักขระที่อยู่นอกช่วง ASCII เช่น Cyrillic, Chinese หรืออีโมจิ คุณต้องระบุการเข้ารหัส ECI (Extended Channel Interpretation). ที่นี่เราใช้ UTF‑8 สำหรับคำภาษารัสเซีย “Привет”

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*ทำไมวิธีนี้ถึงได้ผล*: The QR spec defines ECI values that tell the scanner which character set to apply. Without the ECI marker, the raw bytes would be interpreted as ISO‑8859‑1, resulting in garbled output.

## ขั้นตอนที่ 4: ดึงสตริง extended codetext ที่รวมกัน

หลังจากเพิ่มส่วนที่ต้องการทั้งหมดแล้ว ให้เรียก `get_extended_codetext()` เพื่อรับสตริงสุดท้ายที่ตัวสร้างบาร์โค้ดคาดหวัง

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

ค่าที่พิมพ์ออกมาจะดูเหมือนชุดของอักขระควบคุมตามด้วยข้อความจริง แต่คุณไม่จำเป็นต้องแยกวิเคราะห์ด้วยตนเอง

## ขั้นตอนที่ 5: สร้าง QR code ด้วย extended codetext

ตอนนี้สร้าง `BarcodeGenerator`, ตั้งสัญลักษณ์เป็น QR (สัญลักษณ์ 2‑D ที่ทั่วไปและรองรับ extended codetext) แล้วป้อนสตริงที่รวมกัน

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*เคล็ดลับ*: หากคุณลองทำขั้นตอนเดียวกันกับ Code‑128 หรือ DataMatrix SDK จะโยนข้อยกเว้นเนื่องจากรูปแบบเหล่านั้นไม่สามารถตีความเครื่องหมาย ECI ได้

## ขั้นตอนที่ 6: บันทึกภาพ QR code

สุดท้าย เขียนบาร์โค้ดลงไฟล์ PNG นี่คือจุดที่คุณ **save QR code image** เพื่อใช้งานต่อไป

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

ตรวจสอบให้แน่ใจว่าโฟลเดอร์ `output` มีอยู่หรือสร้างด้วย `os.makedirs('output', exist_ok=True)` ก่อนเรียก `save`

### ตัวอย่างที่สามารถรันได้เต็มรูปแบบ

การรวมทุกขั้นตอนเข้าด้วยกันจะให้สคริปต์ที่ทำงานอิสระซึ่งคุณสามารถรันได้ทันที:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**ผลลัพธ์ที่คาดหวัง** (คอนโซล):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

การเปิด `qr_extended.png` ด้วยสแกนเนอร์ QR ใดก็จะแสดง `HelloWorldПривет`. สแกนเนอร์ที่เข้าใจ ECI จะเรนเดอร์อักขระ Cyrillic อย่างถูกต้อง; ส่วนที่ไม่เข้าใจจะแสดงเฉพาะส่วน ASCII

## คำถามทั่วไป & กรณีขอบ

| Question | Answer |
|----------|--------|
| *ฉันสามารถใช้การเข้ารหัสอื่นเช่น Shift‑JIS ได้หรือไม่?* | ได้. แทนที่ `CodetextEncodingType.UTF_8` ด้วย `CodetextEncodingType.SHIFT_JIS` และให้ข้อความที่เหมาะสม |
| *ถ้าข้อมูลที่รวมกันเกินความจุของ QR จะทำอย่างไร?* | QR codes have version limits (up to 177 × 177 modules). If the builder throws a size exception, either increase the error‑correction level or split data across multiple QR codes. |
| *ฉันต้องตั้งค่าเวอร์ชัน QR เฉพาะหรือไม่?* | The SDK automatically selects the smallest version that fits the data. You can force a version with `qr_generator.set_qr_version(10)` if required. |
| *ภาพจะเป็นแบบโปร่งใสหรือไม่?* | By default the SDK writes a PNG with a white background. Use `qr_generator.set_background_color(Color.Transparent)` before `save` if you need transparency. |

## สรุป

ในบทเรียนนี้คุณได้เรียนรู้วิธี **encode non ASCII characters** ใน QR code ด้วย `ExtCodetextBuilder` แล้ว **save QR code image** ด้วย `BarcodeGenerator`. กระบวนการประกอบด้วยการสร้างสตริง extended codetext, เพิ่มส่วน plain และส่วนที่เข้ารหัสด้วย ECI, สร้างสัญลักษณ์ QR, และสุดท้ายเขียนไฟล์ภาพ

จากนี้คุณสามารถสำรวจต่อได้:

* เพิ่มส่วน ECI เพิ่มเติม (หลายภาษา หรืออีโมจิ)
* ปรับระดับการแก้ไขข้อผิดพลาดของ QR เพื่อความเชื่อถือสูงขึ้น
* ฝัง PNG ที่สร้างขึ้นลงใน PDF หรือหน้าเว็บ

ขอให้สนุกกับการเขียนโค้ดและเพลิดเพลินกับการสร้าง QR code หลายภาษา!

## สิ่งที่คุณควรเรียนต่อไปคืออะไร?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้ทางเลือกในโปรเจคของคุณ

- [วิธีสร้างภาพ QR Code ใน Python ด้วย Aspose.Barcode – คู่มือเต็ม](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [สร้างบาร์โค้ด Code128 ด้วย Aspose.Barcode Python – คู่มือเต็ม](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [แสดงชื่อสินค้าโดยใช้ไลบรารีบาร์โค้ด Python – คู่มือขั้นตอนต่อขั้นตอน](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}