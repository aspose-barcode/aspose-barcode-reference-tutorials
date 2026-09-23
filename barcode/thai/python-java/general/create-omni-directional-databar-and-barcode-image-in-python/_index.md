---
category: general
date: 2026-08-12
description: สร้าง Omni Directional Databar ด้วย Python และเรียนรู้วิธีสร้างภาพบาร์โค้ดด้วย
  Python โดยใช้ Aspose.BarCode. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนเพื่อรับโซลูชันที่ครบถ้วน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: th
lastmod: 2026-08-12
og_description: สร้างดาต้าแบร์แบบหลายทิศทางด้วย Python และสร้างภาพบาร์โค้ดด้วย Python
  ภายในไม่กี่นาที บทเรียนนี้แสดงตัวอย่างที่สมบูรณ์และสามารถรันได้
og_image_alt: example of create omni directional databar barcode image in Python
og_title: สร้างแถบข้อมูลหลายทิศทาง – คู่มือ Python ฉบับเต็ม
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: สร้างภาพแถบข้อมูลและบาร์โค้ดแบบหลายทิศทางใน Python
url: /th/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Omni‑directional DataBar และภาพบาร์โค้ดใน Python

หากคุณต้องการ **สร้าง Omni‑directional DataBar** ในโปรเจกต์ Python คำแนะนำนี้จะแสดงวิธีทำและยังสอนวิธี **สร้างภาพบาร์โค้ดด้วย Python** โดยใช้ไลบรารี Aspose.BarCode คุณจะได้สคริปต์พร้อมรันที่สร้างไฟล์ PNG สองไฟล์ที่มีอัตราส่วนภาพต่างกัน

การสร้าง DataBar ตามสเปค Omni‑directional เป็นความต้องการทั่วไปสำหรับแอปพลิเคชันด้านการค้าปลีกและโลจิสติกส์ บทเรียนนี้ครอบคลุมการติดตั้ง การกำหนดค่า X‑dimension การปรับอัตราส่วนภาพ และการบันทึกภาพขั้นสุดท้าย ไม่ต้องพึ่งบริการภายนอก; ทุกอย่างทำงานแบบออฟไลน์

## สิ่งที่คุณต้องมี

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* Python 3.8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ
* เข้าถึงเทอร์มินัลหรือ command prompt
* สิทธิ์การเขียนในโฟลเดอร์ที่ภาพบาร์โค้ดจะถูกบันทึก

ไลบรารีภายนอกที่จำเป็นเพียงอย่างเดียวคือ **Aspose.BarCode for Python via .NET** ซึ่งรองรับประเภท Omni‑directional DataBar โดยอัตโนมัติ

## ขั้นตอนที่ 1: ติดตั้ง Aspose.BarCode for Python

Aspose.BarCode มีคลาส `BarcodeGenerator` ที่ใช้ในโค้ดตัวอย่าง ติดตั้งแพคเกจด้วย `pip`:

```bash
pip install aspose-barcode
```

แพคเกจนี้รวมไบน์ดิงของ .NET runtime ที่จำเป็นไว้แล้ว คุณจึงไม่ต้องติดตั้ง .NET SDK แยกต่างหาก

## ขั้นตอนที่ 2: นำเข้าไลบรารีและสร้าง generator

บรรทัดแรกของสคริปต์สร้าง generator สำหรับ stacked Omni‑directional DataBar ค่า GTIN‑14 `(01)12345678901231` ถูกใช้เป็นข้อมูลตัวอย่าง

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*ทำไมขั้นตอนนี้สำคัญ*: ค่าคงที่ `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` บอกไลบรารีให้เข้ารหัสค่าเป็น Omni‑directional DataBar ซึ่งเป็นรูปแบบที่เครื่องสแกนจุดขายหลายเครื่องต้องการ

## ขั้นตอนที่ 3: ตั้งค่า X‑dimension (ความกว้างโมดูล)

X‑dimension กำหนดความกว้างของโมดูลบาร์ที่เล็กที่สุด ค่า `2` พิกเซลให้บาร์โค้ดที่ชัดเจนและอ่านง่ายโดยไม่ทำให้ไฟล์ใหญ่เกินไป

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*ทำไมขั้นตอนนี้สำคัญ*: การปรับ X‑dimension ช่วยให้คุณสมดุลระหว่างความอ่านง่ายและขนาดภาพ X‑dimension ที่เล็กเกินไปอาจทำให้บาร์โค้ดแสดงผลไม่ดีบนเครื่องพิมพ์ความละเอียดต่ำ

## ขั้นตอนที่ 4: กำหนดอัตราส่วนภาพและบันทึกภาพแรก

อัตราส่วนภาพมีผลต่อความสูงรวมของ DataBar เมื่อเทียบกับความกว้าง อัตราส่วน `15` ให้สไตล์ที่กระชับ

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **เคล็ดลับ**: ใช้ `pathlib.Path` เพื่อสร้างเส้นทางเอาต์พุต ซึ่งจะสร้างโฟลเดอร์ที่ขาดหายไปโดยอัตโนมัติ

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## ขั้นตอนที่ 5: เปลี่ยนอัตราส่วนภาพเพื่อสไตล์ที่สองและบันทึกภาพอีกหนึ่งไฟล์

การสลับอัตราส่วนเป็น `30` จะได้บาร์โค้ดที่สูงขึ้น ซึ่งอาจจำเป็นสำหรับฮาร์ดแวร์สแกนเนอร์บางรุ่น

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*ทำไมขั้นตอนนี้สำคัญ*: ร้านค้าต่าง ๆ และอุปกรณ์สแกนมีข้อจำกัดขนาดที่แตกต่างกัน การให้ทั้งสองอัตราส่วนในสคริปต์เดียวทำให้คุณสร้างสไตล์ที่ต้องการโดยไม่ต้องทำซ้ำโค้ด

## สคริปต์เต็ม – สร้าง Omni‑directional DataBar และภาพบาร์โค้ดใน Python

ด้านล่างเป็นตัวอย่างที่ทำงานได้ครบถ้วนซึ่งรวมทุกขั้นตอนก่อนหน้า บันทึกเป็น `generate_databar.py` แล้วรันด้วย `python generate_databar.py`

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### ผลลัพธ์ที่คาดหวัง

การรันสคริปต์จะสร้างไฟล์ต่อไปนี้:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

ทั้งสองภาพแสดง Omni‑directional DataBar ที่ถูกต้องและสามารถสแกนได้ด้วยอุปกรณ์ค้าปลีกมาตรฐาน

![ตัวอย่างการสร้าง omni directional databar barcode image ใน Python](example_databar.png "สร้าง omni directional databar barcode image python")

*ภาพด้านบนเป็นเพียงตัวอย่างเพื่อแสดงไฟล์ PNG สองไฟล์ที่บันทึกไว้*

## การจัดการปัญหาทั่วไป

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode ยังไม่ได้ติดตั้งหรือติดตั้งในสภาพแวดล้อมอื่น | เปิดใช้งาน virtual environment ที่ถูกต้องและรัน `pip install aspose-barcode` |
| `PermissionError` ขณะบันทึก | สคริปต์ไม่มีสิทธิ์เขียนในโฟลเดอร์เป้าหมาย | เลือกไดเรกทอรีที่คุณเป็นเจ้าของหรือรันสคริปต์ด้วยสิทธิ์ที่เหมาะสม |
| บาร์โค้ดสแกนไม่ผ่าน | X‑dimension ต่ำเกินไปหรืออัตราส่วนภาพไม่เข้ากับสแกนเนอร์ | เพิ่มค่า `x_dimension.pixels` เป็น 3 หรือ 4 และลองค่า `aspect_ratio` ต่าง ๆ (เช่น 20, 25) |
| ขาด .NET runtime | Aspose.BarCode ต้องการ .NET runtime บน Windows/Linux | ติดตั้ง .NET runtime ล่าสุดจากเว็บไซต์ Microsoft; คู่มือแพคเกจมีคำแนะนำตามแพลตฟอร์ม |

## การขยายตัวอย่าง

คุณสามารถปรับสคริปต์ให้สร้าง DataBar ประเภทอื่น (เช่น `DATABAR_STACKED`, `DATABAR_EXPANDED`) โดยเปลี่ยนค่าคงที่ `EncodeTypes` ตามต้องการ:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

หากต้องการฝังบาร์โค้ดลงใน PDF, Aspose.PDF for Python สามารถนำเข้าไฟล์ PNG โดยตรง หรือใช้เมธอด `save` พร้อม `BarCodeImageFormat.Pdf`

## สรุป

บทเรียนนี้แสดงวิธี **สร้าง omni directional databar** และวิธี **สร้าง barcode image python** ด้วย Aspose.BarCode ตอนนี้คุณมีสคริปต์ที่ทำงานได้ครบถ้วนซึ่งสร้าง PNG สองไฟล์ที่มีอัตราส่วนภาพต่างกัน จัดการกับปัญหาที่พบบ่อย และสามารถขยายไปยังรูปแบบบาร์โค้ดอื่นได้

ต่อไปลองสร้าง QR code, ฝังบาร์โค้ดลงในใบแจ้งหนี้ PDF, หรือทำการประมวลผลแบบแบตช์สำหรับแคตตาล็อกสินค้าใหญ่ ทุกหัวข้อนี้ต่อยอดจากแพทเทิร์น `BarcodeGenerator` ที่แสดงในที่นี้ ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่นในโปรเจกต์ของคุณ

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}