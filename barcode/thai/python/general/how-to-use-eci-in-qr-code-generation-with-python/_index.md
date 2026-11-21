---
category: general
date: 2026-11-20
description: เรียนรู้วิธีใช้ ECI, สร้าง QR จากข้อความ, ล้างตัวสร้าง, และบันทึกรูปภาพ
  QR ด้วยไลบรารีบาร์โค้ดของ Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: th
lastmod: 2026-11-20
og_description: วิธีใช้ ECI เพื่อสร้าง QR จากข้อความ, ล้างตัวสร้าง QR, และบันทึกภาพ
  QR – คู่มือขั้นตอนเต็มรูปแบบ
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: วิธีใช้ ECI ในการสร้าง QR code ด้วย Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: วิธีใช้ ECI ในการสร้าง QR code ด้วย Python
url: /th/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ ECI ในการสร้าง QR code ด้วย Python

หากคุณต้องการ **how to use eci** ขณะสร้าง QR codes คู่มือนี้จะแสดงขั้นตอนที่แน่นอน คุณจะได้เห็นวิธีสร้าง QR จากข้อความ, ล้าง builder, และบันทึกภาพ QR — ทั้งหมดด้วยไม่กี่บรรทัดของ Python

QR code ที่มีข้อมูลหลายภาษาโดยทั่วไปต้องการส่วน Extended Channel Interpretation (ECI) เพื่อให้เครื่องสแกนรู้ว่าจะใช้ชุดอักขระใด ส่วนนี้จะอธิบายวิธีสร้าง extended codetext, การล้าง builder เมื่อใช้งานซ้ำ, และการบันทึกผลลัพธ์เป็นไฟล์ PNG

## ความต้องการเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- Python 3.8+ ติดตั้งอยู่
- แพคเกจ Aspose.BarCode for Python via .NET (หรือไลบรารี `barcode` ที่รองรับ `ExtCodetextBuilder` และ `BarcodeGenerator`)
- ความคุ้นเคยพื้นฐานกับแนวคิด QR code

ติดตั้งไลบรารีด้วย pip:

```bash
pip install aspose-barcode
```

> **เคล็ดลับ:** ใช้ virtual environment เพื่อหลีกเลี่ยงปัญหาเวอร์ชันที่ขัดแย้งกัน

## ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น

คลาสหลักที่คุณจะทำงานด้วยคือ `ExtCodetextBuilder` สำหรับสร้าง extended codetext และ `BarcodeGenerator` สำหรับเรนเดอร์ QR code

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

การนำเข้าดังกล่าวทำให้คุณเข้าถึงเมธอดของ builder (`add_plain_codetext`, `add_eci_codetext` เป็นต้น) และฟังก์ชันของ generator เช่น `set_code_text`, `set_symbology`, และ `save`

## ขั้นตอนที่ 2: สร้างและกำหนดค่า ExtCodetextBuilder

การสร้างอินสแตนซ์ builder ใหม่เป็นตัวอย่างแรกของ **how to use eci** คุณสามารถล้าง builder ภายหลังได้หากต้องการใช้งานซ้ำ

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

การเรียก `clear()` ทำให้ builder เริ่มต้นด้วยสถานะที่สะอาด ซึ่งจำเป็นเมื่อสร้าง QR หลายรายการในลูป

## ขั้นตอนที่ 3: เพิ่ม plain (non‑ECI) codetext

ข้อความธรรมดาไม่ต้องการส่วน ECI ใช้ `add_plain_codetext` สำหรับสตริงที่เข้ากันได้กับ ASCII

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

ตอนนี้ builder จะมีส่วน plain `"HelloWorld"` อยู่แล้ว

## ขั้นตอนที่ 4: เพิ่มส่วนที่เข้ารหัสด้วย ECI

นี่คือหัวใจของ **how to use eci**: คุณระบุค่า ECI (26 สำหรับ UTF‑8) แล้วให้สตริง Unicode ที่ต้องการเข้ารหัส ซึ่งทำให้ QR code สามารถบรรจุข้อความภาษารัสเซีย, จีน หรือภาษาอื่น ๆ ที่ไม่ได้อยู่ในชุด ISO‑8859‑1 เริ่มต้น

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **ทำไมจึงสำคัญ:** หากไม่มีตัวบ่งชี้ ECI เครื่องสแกนจะตีความไบต์ด้วยชุดอักขระเริ่มต้นและแสดงอักขระที่ผิดรูปสำหรับข้อความที่ไม่ใช่ ASCII

## ขั้นตอนที่ 5: ดึงสตริง extended codetext ที่รวมกันแล้ว

หลังจากเพิ่มส่วนที่ต้องการทั้งหมดแล้ว ให้ดึงสตริงสุดท้ายที่ใช้ส่งให้ QR generator

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

ค่าที่พิมพ์ออกมาจะมีลักษณะประมาณนี้:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

รูปแบบที่แน่นอนขึ้นอยู่กับไลบรารี แต่ส่วนสำคัญคือเครื่องหมาย ECI (`[ECI26]`) จะมาก่อน payload แบบ UTF‑8

## ขั้นตอนที่ 6: สร้าง QR code ด้วยข้อความที่รวมกัน

ตอนนี้คุณสามารถ **generate QR from text** ได้โดยส่ง extended codetext ไปยัง `BarcodeGenerator`

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

เมื่อเปิด `qr_extended.png` จะเห็น QR code ที่เข้ารหัสทั้งสตริงภาษาอังกฤษและคำทักทายภาษารัสเซีย การสแกนด้วย QR scanner สมัยใหม่จะแสดง “HelloWorld” และ “Привет” อย่างถูกต้อง

### ทำไมต้องเรียก `clear()` ก่อนใช้งาน builder ซ้ำ

หากคุณสร้าง QR หลายรายการในลูปและลืมล้าง builder จะทำให้ส่วนเก่าถูกต่อกับส่วนใหม่ ส่งผลให้โค้ดไม่ถูกต้อง ตัวอย่างรูปแบบสั้น ๆ:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

โค้ดส่วนนั้นแสดง **how to clear builder** และ **how to generate QR from text** อย่างต่อเนื่อง

## กรณีขอบและข้อผิดพลาดทั่วไป

| สถานการณ์ | สิ่งที่ควรระวัง | วิธีจัดการ |
|-----------|-------------------|---------------|
| **ค่า ECI ที่ไม่รองรับ** | ไลบรารีจะโยน `InvalidArgumentException` | ใช้ค่า ECI ที่ระบุในสเปคเท่านั้น (เช่น 26 สำหรับ UTF‑8, 20 สำหรับ Shift‑JIS) |
| **ข้อความรวมกันยาวมาก** | เวอร์ชัน QR อาจเกินความจุสูงสุด | เพิ่มเวอร์ชัน QR อัตโนมัติ (`qr_generator.set_qr_version(QRVersion.AUTO)`) หรือแยกข้อมูลเป็นหลาย QR code |
| **ข้อผิดพลาดการอนุญาตไฟล์ระบบ** | `save` ล้มเหลวด้วย `IOError` | ตรวจสอบให้ไดเรกทอรีเป้าหมายมีอยู่และกระบวนการมีสิทธิ์เขียน |
| **การแสดงผล charset ไม่ถูกต้อง** | เครื่องสแกนแสดงอักขระผิดรูป | ยืนยันว่าค่า ECI ที่ใช้ตรงกับการเข้ารหัสจริงของสตริง |

## ตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบ

ด้านล่างเป็นสคริปต์ที่พร้อมคัดลอก, วาง, และรัน รวมการนำเข้า, การจัดการข้อผิดพลาด, และคอมเมนต์เพื่อความชัดเจน

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

เมื่อรันสคริปต์นี้จะสร้าง `output/qr_extended.png` ซึ่งเป็น QR code ที่เข้ารหัสข้อความภาษาอังกฤษและรัสเซียอย่างถูกต้อง

## สรุป

คุณได้เรียนรู้ **how to use eci** ขณะสร้าง QR code, วิธี **clear the QR builder** ก่อนใช้งานซ้ำ, วิธี **generate QR from text**, และขั้นตอนการ **save QR image** ด้วย Python ด้วยการทำตามรูปแบบข้างต้น คุณสามารถฝังสตริง Unicode ใด ๆ ลงใน QR code ได้โดยที่สถานะของ builder คาดเดาได้

### ขั้นตอนต่อไปคืออะไร?

- สำรวจค่า ECI อื่น ๆ สำหรับภาษาจีน (ECI 20) หรือ ISO‑8859‑5
- ปรับระดับ error‑correction (`qr_generator.set_error_correction_level`) เพื่อเพิ่มความน่าเชื่อถือในการสแกน
- รวมหลายส่วน ECI ใน QR code เดียวสำหรับข้อความหลายภาษา

ขอให้สนุกกับการเขียนโค้ดและสร้าง QR code แบบหลายภาษา!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}