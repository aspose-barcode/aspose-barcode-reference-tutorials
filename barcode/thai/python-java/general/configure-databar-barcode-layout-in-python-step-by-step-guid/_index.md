---
category: general
date: 2026-08-12
description: กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python อย่างรวดเร็ว เรียนรู้การตั้งค่าคอลัมน์
  แถว และบันทึกรูปภาพด้วยไลบรารีสร้างบาร์โค้ด
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: th
lastmod: 2026-08-12
og_description: กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python เพื่อควบคุมคอลัมน์ แถว
  และผลลัพธ์ภาพ ปฏิบัติตามคู่มือนี้เพื่อรับโซลูชันพร้อมใช้งาน
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python – บทเรียนครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python – คู่มือแบบขั้นตอนต่อขั้นตอน
url: /th/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **กำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python** คู่มือนี้จะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เห็นวิธีตั้งค่าจำนวนคอลัมน์หรือแถวสำหรับบาร์โค้ด Databar Expanded Stacked และวิธีบันทึกรูปภาพที่ได้ด้วยการเรียกเพียงครั้งเดียวจากไลบรารีสร้างบาร์โค้ด

การควบคุมเลย์เอาต์เป็นสิ่งสำคัญเมื่อคุณฝังบาร์โค้ดบนบรรจุภัณฑ์แคบ ใบเสร็จ หรือหน้าจอมือถือ ในส่วนต่อไปนี้เราจะครอบคลุมการนำเข้าไลบรารีที่จำเป็น ตัวเลือกเลย์เอาต์สองแบบ (คอลัมน์และแถว) และแนวทางปฏิบัติที่ดีที่สุดสำหรับการบันทึกรูป PNG ที่คมชัด

## สิ่งที่คุณต้องมี

* Python 3.8 หรือใหม่กว่า
* `aspose.barcode` (หรือแพคเกจสร้างบาร์โค้ดที่เข้ากันได้อื่น) ติดตั้งแล้ว  
  ```bash
  pip install aspose-barcode
  ```
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกจัดเก็บ

ไม่จำเป็นต้องใช้เครื่องมือภายนอกเพิ่มเติม—ไลบรารีจะจัดการการเรนเดอร์ การสเกล และการเข้ารหัสภาพภายใน

## วิธีกำหนดค่าเลย์เอาต์บาร์โค้ด Databar ใน Python

หัวใจของวิธีแก้คือคลาส `BarcodeGenerator` มันรับค่า `EncodeTypes` enum ที่ระบุสัญลักษณ์บาร์โค้ด—in this case `EncodeTypes.DatabarExpandedStacked`. หลังจากสร้าง generator แล้วคุณสามารถปรับเลย์เอาต์โดยตั้งค่าคุณสมบัติ `columns` หรือ `rows` บนวัตถุพารามิเตอร์ `data_bar`

### ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

การนำเข้าต่าง ๆ นี้ทำให้คุณเข้าถึง generator, enum สำหรับประเภท Databar, และค่าคงที่รูปแบบภาพ PNG

### ขั้นตอนที่ 2: สร้าง barcode generator สำหรับ Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*ทำไมต้องทำขั้นตอนนี้?*  
`EncodeTypes.DatabarExpandedStacked` บอกไลบรารีให้สร้างสัญลักษณ์ **Databar Expanded Stacked** ซึ่งรองรับสตริงตัวเลขยาวขึ้นในขณะที่ยังคงมีขนาดกะทัดรัด พารามิเตอร์ที่สองคือข้อมูลที่จะเข้ารหัส; สามารถเป็นสตริงใดก็ได้ที่ตรงตามสเปคของ Databar

### ขั้นตอนที่ 3: ตั้งค่าจำนวนคอลัมน์ (เลย์เอาต์แนวนอน)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** เป็นวลีสำคัญสำหรับการดำเนินการนี้ เมื่อคุณเพิ่มจำนวนคอลัมน์ บาร์โค้ดจะกระจายออกในแนวนอน ซึ่งอาจเป็นประโยชน์สำหรับป้ายกว้าง ไลบรารีจะคำนวณความกว้างโมดูลใหม่โดยอัตโนมัติเพื่อให้ขนาดโดยรวมคงที่

#### เคล็ดลับพิเศษ
จำนวนคอลัมน์สูงสุดสำหรับ Databar Expanded Stacked คือ 8 การตั้งค่าค่าที่สูงกว่าขีดจำกัดจะถูกจำกัดไว้ที่ค่าสูงสุด แต่ควรตรวจสอบค่าที่รับเข้าก่อน

### ขั้นตอนที่ 4: บันทึกรูปบาร์โค้ดด้วยเลย์เอาต์คอลัมน์

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** คือการกระทำที่เขียนบาร์โค้ดที่เรนเดอร์แล้วลงดิสก์ PNG เป็นรูปแบบ lossless ซึ่งรักษาขอบคมที่จำเป็นสำหรับการสแกนที่เชื่อถือได้

### ขั้นตอนที่ 5: สร้าง generator ตัวที่สองสำหรับประเภทบาร์โค้ดเดียวกัน (เลย์เอาต์แถว)

หากคุณต้องการสแต็กแนวตั้ง ให้ทำงานกับแถวแทนคอลัมน์ โค้ดด้านล่างใช้ค่าเดียวกันแต่สร้างอินสแตนซ์ `BarcodeGenerator` ใหม่เพื่อหลีกเลี่ยงการผสมผสานการตั้งค่าคอลัมน์และแถว

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### ขั้นตอนที่ 6: ตั้งค่าจำนวนแถว (เลย์เอาต์แนวตั้ง)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** จัดเรียงโมดูลบาร์โค้ดในแนวตั้ง การจัดเรียงแบบสามแถวจะลดความสูงของแต่ละสแต็ก ทำให้บาร์โค้ดเหมาะกับใบเสร็จแคบหรือหน้าจอมือถือ

#### กรณีขอบ
หากคุณตั้งค่า `rows` เป็น 1 ไลบรารีจะสร้าง Databar แถวเดียว (เทียบเท่ากับ Databar มาตรฐาน) ค่าที่ต่ำกว่า 1 จะถูกละเว้นและรีเซ็ตเป็นค่าเริ่มต้น (1 แถว)

### ขั้นตอนที่ 7: บันทึกรูปบาร์โค้ดด้วยเลย์เอาต์แถว

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

อีกครั้ง เรา **save barcode image** ด้วย PNG เพื่อให้ผลลัพธ์คมชัด

## ตัวอย่างที่สามารถรันได้ทั้งหมด

การรวมส่วนต่าง ๆ เข้าด้วยกันจะให้สคริปต์ที่เป็นอิสระซึ่งคุณสามารถใส่ลงในโปรเจกต์ Python ใดก็ได้

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**ผลลัพธ์ที่คาดหวัง**

การรันสคริปต์จะสร้างไฟล์ PNG สองไฟล์:

* `output/ExpandedCols4.png` – บาร์โค้ดที่ขยายออกในสี่คอลัมน์
* `output/ExpandedRows3.png` – บาร์โค้ดที่บีบอัดเป็นสามแถว

ทั้งสองภาพสามารถเปิดด้วยโปรแกรมดูภาพใดก็ได้หรือทำการนำเข้าโดยตรงไปยังใบแจ้งหนี้ PDF, เทมเพลตป้าย, หรือหน้าเว็บ

## คำถามทั่วไปและการแก้ไขปัญหา

| Question | Answer |
|----------|--------|
| *ถ้าบาร์โค้ดดูเบลอ?* | เพิ่มความละเอียดของภาพโดยตั้งค่า `barcode_generator.parameters.image_width` และ `image_height` ก่อนเรียก `save`. |
| *ฉันสามารถใช้รูปแบบภาพอื่นได้หรือไม่?* | ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Gif` ตามต้องการ. |
| *มีขีดจำกัดความยาวของข้อมูลหรือไม่?* | Databar Expanded Stacked รองรับสูงสุด 74 ตัวอักษรตัวเลข. หากเกินขีดจำกัดจะเกิด `ArgumentException`. |
| *ฉันจะเปลี่ยนสีพื้นหน้าอย่างไร?* | ใช้ `barcode_generator.parameters.barcode.color = Color.Blue` (นำเข้า `System.Drawing.Color`). |
| *ฉันสามารถรวมคอลัมน์และแถวได้หรือไม่?* | ไม่ได้. API ถือว่าคอลัมน์และแถวเป็นโหมดเลย์เอาต์ที่ไม่สามารถใช้ร่วมกันได้. เลือกหนึ่งโหมดต่ออินสแตนซ์ของบาร์โค้ด. |

## ขั้นตอนต่อไป

ตอนนี้คุณสามารถ **กำหนดค่าเลย์เอาต์บาร์โค้ด Databar** แล้ว ลองสำรวจหัวข้อที่เกี่ยวข้องต่อไปนี้:

* **เพิ่มคำบรรยายข้อความ** – ใช้ `barcode_generator.parameters.barcode.code_text` เพื่อแสดงค่าที่เข้ารหัสใต้ภาพ
* **ฝังบาร์โค้ดใน PDF** – ผสาน PNG ที่สร้างกับ `aspose.pdf` เพื่อสร้างเอกสารที่พิมพ์ได้
* **การกำหนดขนาดแบบไดนามิก** – คำนวณจำนวนคอลัมน์หรือแถวที่เหมาะสมตามขนาดป้ายในเวลารัน
* **การประมวลผลเป็นชุด** – วนลูปผ่าน CSV ของรหัสสินค้าเพื่อสร้างไลบรารีรูปบาร์โค้ดโดยอัตโนมัติ

ทดลองใช้ค่าคอลัมน์และแถวต่าง ๆ เพื่อดูว่ามันส่งผลต่อความน่าเชื่อถือของการสแกนบนอุปกรณ์เป้าหมายอย่างไร ยิ่งคุณทดสอบมากเท่าไหร่ คุณก็จะเข้าใจการแลกเปลี่ยนระหว่างขนาดบาร์โค้ด ความอ่านง่าย และข้อจำกัดของพื้นที่ได้ดียิ่งขึ้น

---

*ขอให้เขียนโค้ดอย่างสนุก! หากคุณพบว่าคู่มือนี้เป็นประโยชน์, แชร์ให้เพื่อนร่วมทีมหรือแสดงความคิดเห็นเกี่ยวกับความท้าทายของการกำหนดเลย์เอาต์ที่คุณเจอ*

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณเอง

- [สร้างภาพบาร์โค้ด DotCode – แถวและคอลัมน์ (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [สร้างภาพบาร์โค้ด c# – กำหนดค่า Codablock F แถวและคอลัมน์](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [การปรับความสูงของบาร์โค้ด Databar มิติเดียว](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}