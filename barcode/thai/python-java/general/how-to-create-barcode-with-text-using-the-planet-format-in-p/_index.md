---
category: general
date: 2026-11-27
description: เรียนรู้วิธีสร้างบาร์โค้ดพร้อมข้อความและสร้างบาร์โค้ดแบบ Planet ใน Python—คู่มือขั้นตอนต่อขั้นตอนสำหรับการสร้างไฟล์
  PNG ความละเอียดสูง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: th
lastmod: 2026-11-27
og_description: สร้างบาร์โค้ดพร้อมข้อความและสร้างบาร์โค้ดแบบ Planet ด้วย Python ทำตามคู่มือฉบับเต็มนี้เพื่อสร้างไฟล์
  PNG ความละเอียดสูง.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: สร้างบาร์โค้ดพร้อมข้อความใน Python – สร้างบาร์โค้ด Planet อย่างง่าย
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: วิธีสร้างบาร์โค้ดพร้อมข้อความโดยใช้รูปแบบ Planet ใน Python
url: /th/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดพร้อมข้อความโดยใช้รูปแบบ Planet ใน Python

หากคุณต้องการ **สร้างบาร์โค้ดพร้อมข้อความ** สำหรับระบบการส่งจดหมาย บทแนะนำนี้จะแสดงวิธีทำอย่างละเอียด คุณจะได้เห็นตัวอย่างสั้น ๆ ที่ทำงานตั้งแต่ต้นจนจบ ซึ่งสร้างบาร์โค้ด Planet ปรับความละเอียด และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับโลจิสติกส์, การจัดการสินค้าคงคลัง, และแอปพลิเคชันการออกตั๋ว ในคู่มือนี้คุณจะได้เรียนรู้ไม่เพียงแต่ **วิธีสร้างไฟล์บาร์โค้ด** เท่านั้น แต่ยังเข้าใจว่าทำไมแต่ละขั้นตอนการกำหนดค่าถึงสำคัญและจะหลีกเลี่ยงข้อผิดพลาดทั่วไปได้อย่างไร

## สิ่งที่คุณจะได้เรียน

* ตั้งค่าเครื่องสร้างบาร์โค้ด Planet พร้อมข้อความที่กำหนดเอง
* ปรับค่า X‑dimension เพื่อเพิ่มความคมของภาพ
* บันทึกบาร์โค้ดเป็นไฟล์ PNG ที่สามารถพิมพ์หรือแสดงบนเว็บได้
* ขยายตัวอย่างไปยังประเภทบาร์โค้ดหรือรูปแบบผลลัพธ์อื่น ๆ

**ข้อกำหนดเบื้องต้น**

* Python 3.8 หรือใหม่กว่า
* แพ็กเกจ `aspose-barcode` (หรือไลบรารีที่เข้ากันได้ซึ่งให้ `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`)
* ความคุ้นเคยพื้นฐานกับการเขียนสคริปต์ Python

คุณสามารถติดตั้งแพ็กเกจที่จำเป็นได้ด้วย:

```bash
pip install aspose-barcode
```

---

## ขั้นตอนที่ 1: สร้างบาร์โค้ดพร้อมข้อความ – เริ่มต้นเครื่องสร้าง

สิ่งแรกที่คุณต้องทำคือสร้างอินสแตนซ์ `BarcodeGenerator` ที่ระบุสัญลักษณ์ที่ใช้และข้อความที่ต้องเข้ารหัส สำหรับบาร์โค้ด Planet ค่าคงที่ `EncodeTypes.Planet` จะบอกไลบรารีให้ปฏิบัติตามสเปค USPS Planet

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**ทำไมจึงสำคัญ:**  
อ็อบเจกต์ `BarcodeGenerator` จะบรรจุการตั้งค่าทั้งหมดของบาร์โค้ด การใส่ข้อความในขั้นตอนการสร้างทำให้ค่าที่เข้ารหัสคงที่ตลอดกระบวนการ ซึ่งช่วยป้องกันความไม่ตรงกันโดยไม่ได้ตั้งใจในภายหลัง

---

## ขั้นตอนที่ 2: ปรับการตั้งค่า – วิธีสร้างบาร์โค้ดที่ความละเอียดสูงขึ้น

บาร์โค้ดที่ความละเอียดต่ำอาจดูเบลอเมื่อพิมพ์บนเครื่องพิมพ์ฉลาก X‑dimension (ความกว้างของโมดูล) ควบคุมขนาดของแต่ละบาร์ การตั้งค่าเป็น 4 พิกเซลจะให้ภาพคมชัดและความละเอียดสูง เหมาะกับเครื่องพิมพ์สมัยใหม่ส่วนใหญ่

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**คำอธิบาย:**  
* `gen.parameters.barcode.x_dimension.pixels` ตรงกับความกว้างจริงของโมดูลเดียว  
* ค่า **4** หมายความว่าบาร์แต่ละบาร์กว้างสี่พิกเซล ซึ่งประมาณ 0.127 มม. ที่ 300 dpi — อยู่ในช่วงที่แนะนำสำหรับบาร์โค้ด USPS Planet  

**เคล็ดลับ:** หากต้องการ DPI ที่แตกต่าง ให้คำนวณความกว้างพิกเซลตามนั้น (เช่น 2 พิกเซลสำหรับ 150 dpi, 8 พิกเซลสำหรับ 600 dpi)

---

## ขั้นตอนที่ 3: บันทึกภาพ – สร้างบาร์โค้ด Planet เป็น PNG

เมื่อเครื่องสร้างถูกตั้งค่าแล้ว คุณสามารถเรนเดอร์บาร์โค้ดเป็นไฟล์ภาพ PNG ได้ PNG เป็นรูปแบบที่ไม่มีการสูญเสียข้อมูล ทำให้รูปแบบโมดูลคงที่

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**ผลลัพธ์:**  
การรันสคริปต์จะสร้างไฟล์ชื่อ `PostalPlanetBarHeightNone.png` ซึ่งบรรจุบาร์โค้ด Planet ที่เข้ารหัสสตริง “123456” ขนาดภาพประมาณ 200 × 100 พิกเซล ขึ้นอยู่กับค่า X‑dimension ที่คุณเลือก

---

## ตัวเลือก: ตรวจสอบบาร์โค้ดด้วยตาเปล่า

คุณสามารถเปิดไฟล์ PNG ที่สร้างขึ้นด้วยโปรแกรมดูภาพใด ๆ เพื่อยืนยันว่าบาร์โค้ดคมชัดและข้อความที่อ่านได้โดยมนุษย์ปรากฏอยู่ใต้รูปแบบ

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

หากภาพดูเบลอ ให้กลับไปที่ **ขั้นตอน 2** และเพิ่มค่า X‑dimension จนบาร์คมชัดขึ้น

---

## ความแตกต่างทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับเปลี่ยน |
|-----------|----------------|
| **ความยาวข้อความต่างกัน** | บาร์โค้ด Planet รองรับตัวเลขสูงสุด 12 ตัวอักษร หากเกินจะทำให้ไลบรารีโยนข้อยกเว้น |
| **รูปแบบผลลัพธ์อื่น** | แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Bmp` ตามกรณีใช้งาน |
| **สีพื้นหน้า/พื้นหลังที่กำหนดเอง** | ใช้ `gen.parameters.barcode.barcode_color = Color.Blue` และ `gen.parameters.barcode.back_color = Color.White` |
| **ไม่มีข้อความอ่านได้** | ตั้งค่า `gen.parameters.barcode.hide_code_text = True` เพื่อสร้างบาร์โค้ดโดยไม่มีคำบรรยายด้านล่าง |
| **การสร้างเป็นชุด** | วนลูปรายการสตริง สร้าง `BarcodeGenerator` ใหม่สำหรับแต่ละรายการ และบันทึกเป็นไฟล์ที่มีชื่อเฉพาะ |

การปรับเปลี่ยนเหล่านี้ช่วยให้คุณ **สร้างไฟล์บาร์โค้ด Planet** ที่ตอบสนองความต้องการทางธุรกิจที่หลากหลาย

---

## สคริปต์เต็ม – พร้อมรัน

ด้านล่างเป็นสคริปต์ครบชุดที่คุณสามารถคัดลอก, วาง, และรันได้ รวมการนำเข้า, การจัดการข้อผิดพลาด, และคอมเมนต์ครบถ้วน

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**คำอธิบายสคริปต์**

* ฟังก์ชัน `create_planet_barcode` รวมขั้นตอนหลักสามขั้นตอน ทำให้โค้ดนำกลับมาใช้ใหม่ได้ง่าย
* การตรวจสอบอินพุตทำให้คุณปฏิบัติตามสเปค Planet (ตัวเลขเท่านั้น, สูงสุด 12 หลัก)
* ฟังก์ชันจะสร้างโฟลเดอร์ผลลัพธ์โดยอัตโนมัติ ไม่ต้องจัดการไดเรกทอรีด้วยตนเอง
* หลังจากสร้างแล้ว สคริปต์จะเปิดภาพด้วย Pillow (`PIL`) เพื่อให้ตรวจสอบได้ทันที

---

## สรุป

คุณได้เรียนรู้วิธี **สร้างบาร์โค้ดพร้อมข้อความ** และ **สร้างไฟล์บาร์โค้ด Planet** ด้วย Python คู่มือได้ครอบคลุมการเริ่มต้น, การปรับความละเอียด, และการบันทึกไฟล์ พร้อมตัวเลือกการปรับแต่งและกรณีขอบทั่วไป

ต่อจากนี้คุณสามารถ:

* แทนที่ `EncodeTypes.Planet` ด้วยสัญลักษณ์อื่น (เช่น `EncodeTypes.Code128`) เพื่อใช้รูปแบบเดียวกัน
* ผสานฟังก์ชันนี้เข้ากับเว็บเซอร์วิสที่ให้บริการภาพบาร์โค้ดตามคำขอ
* ทดลองประมวลผลเป็นชุดเพื่อสร้างบาร์โค้ดหลายพันรายการสำหรับการส่งจดหมายจำนวนมาก

ปรับสคริปต์ให้เข้ากับโครงการของคุณและแบ่งปันผลลัพธ์ในคอมเมนต์ได้เลย ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโครงการของคุณ

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}