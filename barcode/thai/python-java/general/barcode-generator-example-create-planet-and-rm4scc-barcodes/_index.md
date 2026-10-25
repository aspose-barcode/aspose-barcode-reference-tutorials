---
category: general
date: 2026-10-24
description: ตัวอย่างเครื่องสร้างบาร์โค้ดที่แสดงวิธีสร้างบาร์โค้ดแบบ Planet และวิธีตั้งความสูงของบาร์โค้ดโดยใช้
  Python. ทำตามคำแนะนำทีละขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: th
lastmod: 2026-10-24
og_description: ตัวอย่างเครื่องสร้างบาร์โค้ดที่สาธิตวิธีสร้างบาร์โค้ด Planet และวิธีตั้งความสูงของบาร์โค้ดใน
  Python รับโซลูชันที่สมบูรณ์และสามารถรันได้
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: ตัวอย่างเครื่องสร้างบาร์โค้ด – สร้างบาร์โค้ด Planet และ RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: ตัวอย่างเครื่องสร้างบาร์โค้ด – สร้างบาร์โค้ด Planet และ RM4SCC ด้วยความสูงที่กำหนดเอง
url: /th/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างตัวสร้างบาร์โค้ด – สร้างบาร์โค้ด Planet และ RM4SCC ด้วยความสูงที่กำหนดเอง

หากคุณกำลังมองหา **ตัวอย่างตัวสร้างบาร์โค้ด** คู่มือนี้จะให้โซลูชันที่พร้อมใช้งานและทำงานได้ทันที คุณจะได้เห็น **วิธีสร้างภาพบาร์โค้ด Planet** เรียนรู้ **วิธีตั้งค่าความสูงของบาร์โค้ด** และเข้าใจความแตกต่างเล็กน้อยระหว่างการกำหนดขนาดอัตโนมัติและการกำหนดขนาดด้วยตนเอง

บทแนะนำนี้จะเดินผ่านสองสถานการณ์ที่เป็นจริง: บาร์โค้ด Planet ที่ใช้ความสูงเริ่มต้น (auto) และบาร์โค้ด RM4SCC ที่บังคับให้ความสูงเป็น 100 px. เมื่อจบคุณจะสามารถสร้างไฟล์ PNG สำหรับประเภทบาร์โค้ดที่รองรับทั้งหมดด้วย API เดียวที่สม่ำเสมอ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน โปรดตรวจสอบว่าคุณมี:

* Python 3.8 หรือใหม่กว่า
* แพ็กเกจ `aspose-barcode` (หรือไลบรารีใด ๆ ที่ให้ `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`). ติดตั้งด้วย  

  ```bash
  pip install aspose-barcode
  ```
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

ไม่ต้องการการพึ่งพาระบบเพิ่มเติมใด ๆ

## ภาพรวมของโซลูชัน

แกนหลักของ **ตัวอย่างตัวสร้างบาร์โค้ด** ประกอบด้วยสามขั้นตอนที่สามารถนำกลับมาใช้ใหม่ได้:

1. **สร้างอินสแตนซ์** ของ `BarcodeGenerator` ด้วยค่า `EncodeTypes` ที่ต้องการและสตริงข้อมูล
2. **กำหนดค่า** X‑dimension (ความกว้างโมดูล) และเมื่อจำเป็น ความสูงของบาร์โค้ด
3. **บันทึก** ภาพลงดิสก์ในรูปแบบ PNG

ตัวอย่างทั้งสองใช้ขั้นตอน 1 และ 3 ร่วมกัน; เพียงขั้นตอน 2 แตกต่างกันเพราะบาร์โค้ด Planet พึ่งพาการคำนวณความสูงอัตโนมัติของไลบรารี ส่วนบาร์โค้ด RM4SCC แสดง **วิธีตั้งค่าความสูงของบาร์โค้ด** ด้วยตนเอง

ด้านล่างเป็นแผนภาพระดับสูงที่แสดงกระบวนการ:

![ตัวอย่างตัวสร้างบาร์โค้ดแสดงบาร์โค้ด Planet และ RM4SCC](barcode-example.png)

*ข้อความแทน: ตัวอย่างตัวสร้างบาร์โค้ดแสดงบาร์โค้ด Planet และ RM4SCC ที่มีความสูงต่างกัน*

## วิธีสร้างบาร์โค้ด Planet – ความสูงอัตโนมัติ

บาร์โค้ด Planet เป็นส่วนหนึ่งของตระกูลบาร์โค้ดไปรษณีย์ที่ใช้โดยหลายบริการไปรษณีย์แห่งชาติ ในกรณีส่วนใหญ่คุณให้ SDK กำหนดความสูงเอง ซึ่งช่วยให้สัดส่วนภาพคงที่แม้ข้อมูลจะยาวต่างกัน

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**ทำไมวิธีนี้ถึงได้ผล**

* `EncodeTypes.Planet` บอกไลบรารีให้ใช้สัญลักษณ์ Planet
* การตั้งค่า `x_dimension.pixels` เป็น 4 ทำให้แต่ละโมดูลมีความกว้าง 4 px ซึ่งเป็นค่าเริ่มต้นที่นิยมสำหรับป้ายพิมพ์
* ไม่ได้กำหนดความสูงอย่างชัดเจน; SDK จะคำนวณความสูงที่เหมาะสมตามข้อมูลและ X‑dimension ซึ่งทำให้เป็น **ตัวอย่างตัวสร้างบาร์โค้ด** ที่ง่ายที่สุดสำหรับรหัสไปรษณีย์

**ผลลัพธ์ที่คาดหวัง**

ไฟล์ PNG 2‑D ชื่อ `PostalPlanetBarHeightAuto.png` ที่มีบาร์โค้ด Planet คมชัด ความสูงประมาณ 30 px (ขึ้นอยู่กับเวอร์ชันของไลบรารี) และความกว้างเป็น 4 px × จำนวนโมดูล

## วิธีตั้งค่าความสูงของบาร์โค้ด – ตัวอย่าง RM4SCC ที่กำหนดเอง

RM4SCC เป็นบาร์โค้ดไปรษณีย์อีกประเภทหนึ่งที่มักต้องการความสูงคงที่เพื่อให้ตรงกับเทมเพลตป้าย ส่วนนี้ของบทแนะนำจะแสดง **วิธีตั้งค่าความสูงของบาร์โค้ด** ให้ตรงกับจำนวนพิกเซลที่ต้องการ

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**ทำไมวิธีนี้ถึงได้ผล**

* `EncodeTypes.RM4SCC` เลือกสัญลักษณ์ RM4SCC
* X‑dimension ยังคงเป็น 4 px เพื่อให้ขนาดโมดูลสอดคล้องกันระหว่างบาร์โค้ดทั้งสอง
* `bar_height.pixels = 100` บังคับให้บาร์โค้ดสูง 100 px อย่างแม่นยำ, แทนที่การคำนวณอัตโนมัติ นี่เป็นวิธีที่แนะนำ **วิธีตั้งค่าความสูงของบาร์โค้ด** เมื่อเลย์เอาต์ของคุณต้องการขนาดเฉพาะ

**ผลลัพธ์ที่คาดหวัง**

ไฟล์ PNG ชื่อ `PostalRM4SCCBarHeight100Pixels.png` ที่แสดงบาร์โค้ด RM4SCC สูง ความกว้างยังคงกำหนดโดย X‑dimension ส่วนความสูงคงที่ที่ 100 px ทำให้เหมาะกับเครื่องพิมพ์ป้ายความละเอียดสูง

## สคริปต์เต็ม – รวมตัวอย่างทั้งสอง

หากคุณต้องการสคริปต์เดียวที่สร้างภาพทั้งสอง ให้คัดลอกโค้ดต่อไปนี้ไปยังไฟล์ `generate_barcodes.py` แล้วรัน

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**คำอธิบายสคริปต์**

* ฟังก์ชันช่วยเหลือสองตัวทำให้โค้ดเป็น DRY (Don’t Repeat Yourself) และง่ายต่อการขยายสคริปต์สำหรับสัญลักษณ์อื่น ๆ
* คำสั่ง `if __name__ == "__main__":` ทำให้ไฟล์สามารถนำเข้าเป็นโมดูลโดยไม่ทำงานส่วนการสร้างบาร์โค้ด ซึ่งเป็นประโยชน์สำหรับการทดสอบหน่วย
* พารามิเตอร์ทั้งหมด (สตริงข้อมูล, X‑dimension, ความสูง) ถูกระบุอย่างชัดเจน ทำให้สคริปต์เป็น **ตัวอย่างตัวสร้างบาร์โค้ด** ที่อ้างอิงได้สำหรับโครงการในอนาคต

## คำถามที่พบบ่อยและกรณีขอบ

| คำถาม | คำตอบ |
|----------|--------|
| *ถ้าต้องการ X‑dimension ที่ต่างออกไปควรทำอย่างไร?* | เปลี่ยน `x_dimension.pixels` เป็นค่าความกว้างโมดูลที่ต้องการ ค่าที่ใหญ่ขึ้นจะทำให้บาร์โค้ดโดยรวมใหญ่ขึ้นตามสัดส่วน |
| *สามารถสร้างรูปแบบภาพอื่นได้หรือไม่?* | ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpg`, `Bmp` หรือ `Gif` ตามที่ enum ของไลบรารีรองรับ |
| *ถ้าสตริงข้อมูลมีอักขระที่ไม่ถูกต้องจะเกิดอะไรขึ้น?* | ตัวสร้างจะโยน `ArgumentException`. ควรตรวจสอบข้อมูลให้ตรงกับชุดอักขระของสัญลักษณ์ก่อนเรียกคอนสตรัคเตอร์ |
| *สามารถตั้งค่าความสูงขั้นต่ำพร้อมการสเกลอัตโนมัติได้หรือไม่?* | ใช้ `gen.parameters.barcode.bar_height.min_pixels = <value>` (ถ้า SDK มี property `min_pixels`). วิธีนี้จะป้องกันบาร์โค้ดไม่ให้ย่อลงต่ำกว่าขนาดที่อ่านได้ |
| *ต้องทำการ dispose ตัวสร้างหรือไม่?* | คลาส `BarcodeGenerator` มีการทำงานเป็น `IDisposable` ใน .NET; ใน Python ตัวจัดการหน่วยความจำจะทำหน้าที่นี้ให้โดยอัตโนมัติ แต่คุณสามารถเรียก `gen.dispose()` หากสร้างหลายอินสแตนซ์ในลูป |

## เคล็ดลับสำหรับการใช้งานในโปรดักชัน

* **เคล็ดลับระดับมืออาชีพ:** เก็บค่าของ X‑dimension และความสูงไว้ในไฟล์คอนฟิก เพื่อให้สามารถปรับเปลี่ยนได้โดยไม่ต้องคอมไพล์ใหม่
* **ระวัง:** อย่าใช้ความสูงที่เล็กเกินไปสำหรับสัญลักษณ์ที่เลือก; เครื่องสแกนอาจอ่านไม่ออก
* **หมายเหตุเรื่องประสิทธิภาพ:** การสร้างบาร์โค้ดจำนวนมากจะเร็วขึ้นเมื่อใช้อินสแตนซ์ `BarcodeGenerator` ตัวเดียวและเปลี่ยนเฉพาะ property `code_text` ระหว่างการบันทึก

## สรุป

**ตัวอย่างตัวสร้างบาร์โค้ด** นี้แสดงทั้ง **วิธีสร้างบาร์โค้ด Planet** ด้วยการกำหนดขนาดอัตโนมัติและ **วิธีตั้งค่าความสูงของบาร์โค้ด** ด้วยตนเองสำหรับโค้ด RM4SCC ด้วยการทำตามขั้นตอนอย่างละเอียด คุณสามารถผสานการสร้างบาร์โค้ดเข้าไปในแอปพลิเคชัน Python ใด ๆ ปรับขนาดตามต้องการ และผลิตไฟล์ PNG ที่พร้อมพิมพ์หรือแสดงผลดิจิทัล

### ขั้นตอนต่อไป

* สำรวจสัญลักษณ์เพิ่มเติมเช่น `EncodeTypes.Postnet` หรือ `EncodeTypes.Code128` – รูปแบบการทำงานเดียวกันจะใช้ได้
* ทดลอง **วิธีตั้งค่าความสูงของบาร์โค้ด** สำหรับ QR code หรือ DataMatrix; ไลบรารีส่วนใหญ่จะมี property `bar_height` คล้ายกัน
* ผสานตัวสร้างกับไลบรารี PDF เพื่อฝังบาร์โค้ดโดยตรงลงในใบแจ้งหนี้หรือป้ายจัดส่ง

อย่าลังเลที่จะแก้ไขสคริปต์ แบ่งปันผลลัพธ์ของคุณ และบอกเราว่าคุณเพิ่มประเภทบาร์โค้ดอะไรต่อไป!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณเอง

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}