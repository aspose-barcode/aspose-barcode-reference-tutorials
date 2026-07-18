---
category: general
date: 2026-07-18
description: ใช้ extcodetextbuilder ของ Aspose เพื่อสร้าง QR โค้ดที่รวมข้อความ ASCII
  ธรรมดาและข้อความรัสเซียในรูปแบบ UTF‑8 เรียนรู้การสร้าง QR Code ด้วย Aspose.Barcode
  ใน Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: th
lastmod: 2026-07-18
og_description: ใช้ ExtCodeTextBuilder ของ Aspose ช่วยให้คุณผสานส่วนข้อความธรรมดาและส่วนข้อความที่เข้ารหัสเป็น
  UTF‑8 ใน QR Code ได้ ตามคู่มือขั้นตอนต่อขั้นตอนสำหรับ Aspose.Barcode ใน Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: ใช้ extcodetextbuilder ของ aspose – สร้าง QR Code ด้วยข้อความ ECI ผสม
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'ใช้ extcodetextbuilder ของ aspose: สร้าง QR Code ด้วยข้อความ ECI แบบผสม'
url: /th/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – สร้าง QR Codes ด้วยข้อความ ECI แบบผสม

เคยสงสัยไหมว่า **use extcodetextbuilder aspose** จะฝังตัวอักษรภาษาอังกฤษธรรมดาและตัวอักษร Cyrillic ลงใน QR Code เดียวได้อย่างไร? คุณไม่ได้เป็นคนเดียว นักพัฒนาหลายคนเจออุปสรรคเมื่อจำเป็นต้องผสมข้อมูล ASCII และ non‑ASCII โดยเฉพาะเมื่อเครื่องสแกนเป้าหมายต้องการเครื่องหมาย ECI (Extended Channel Interpretation) ที่ถูกต้อง  

ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่แม่นยำเพื่อสร้าง QR Code ที่บรรจุ “HELLO123” **และ** คำภาษารัสเซีย “Привет” ทั้งหมดโดยใช้ Aspose.Barcode’s Python API. เมื่อจบคุณจะได้สคริปต์พร้อมรัน เข้าใจเหตุผลที่แต่ละคำสั่งสำคัญ และรู้วิธีปรับกระบวนการสำหรับภาษาอื่นหรือรูปแบบข้อมูลอื่น ๆ

## What You’ll Learn

- วิธี **initialize ExtCodetextBuilder** และเพิ่มส่วนข้อความธรรมดาพร้อมส่วนที่เข้ารหัสด้วย ECI.  
- ทำไมค่าการเข้ารหัส **ECI** `3` จึงสอดคล้องกับ UTF‑8 และผลต่อการสแกนอย่างไร.  
- ลำดับขั้นตอนที่แม่นยำในการตั้งค่า **QR Code generator** ด้วย Aspose.Barcode.  
- วิธีบันทึกภาพที่ได้และตรวจสอบเนื้อหาที่ผสมกัน  

**Prerequisites** – คุณต้องมี Python 3.8+, ติดตั้งแพคเกจ `aspose-barcode` (`pip install aspose-barcode`), และโฟลเดอร์ที่สามารถเขียนไฟล์รูปภาพได้. ไม่มีสิ่งอื่นที่จำเป็น.

---

## use extcodetextbuilder aspose to build mixed codetext

สิ่งแรกที่เราต้องการคืออินสแตนซ์ของ `ExtCodetextBuilder`. คิดว่าเป็นแพทเทิร์นแบบ builder ที่ต่อข้อความหลายส่วนเข้าด้วยกันโดยอัตโนมัติแทรกเครื่องหมาย ECI ที่เหมาะสมในเบื้องหลัง

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Why this matters:**  
- `add_plain_codetext` เก็บข้อมูลไว้ตามเดิม ซึ่งเหมาะสำหรับตัวเลขหรืออักษรอังกฤษ.  
- `add_eci_codetext` แทรกส่วน ECI (`[ECI:3]`) ก่อนสตริงที่ให้มา บอกเครื่องอ่านที่รองรับว่าบิตต่อไปเป็น UTF‑8. หากไม่มีส่วนนี้ เครื่องสแกนจะตีความบิต Cyrillic เป็นข้อมูลเสีย.

> **Pro tip:** หากต้องการชุดอักขระอื่น ให้เปลี่ยนค่า `eci_encoding` ตามตาราง ECI (เช่น `26` สำหรับ ISO‑8859‑1).  

---

## Initialise QR Code generation with Aspose.Barcode

เมื่อเรามี `extended_codetext` ที่จัดรูปแบบอย่างถูกต้องแล้ว เราสามารถส่งต่อให้ตัวสร้าง QR Code ได้. Aspose.Barcode จัดการสร้างเมทริกซ์ QR ระดับล่างให้เรา ทำให้เรามุ่งเน้นที่ข้อมูลได้

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**What’s happening here?**  
- `BarcodeGenerator()` สร้างอ็อบเจกต์ generator ใหม่พร้อมค่าตั้งต้น (ขนาด, ความละเอียด ฯลฯ).  
- `set_symbology` บอกเอนจินว่าเราต้องการ QR Code ไม่ใช่ Code128.  

หากต้องการระดับการแก้ไขข้อผิดพลาดที่สูงขึ้น สามารถเรียก `qr_generator.parameters.barcode.qr_error_level = ...` ก่อนกำหนด codetext ได้.

---

## Assign the extended codetext to the QR generator

เมื่อ generator พร้อมแล้ว ขั้นตอนต่อไปคือการใส่สตริงผสมที่เราสร้างไว้ก่อนหน้านี้

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Why not use `set_codetext`?**  
`set_codetext` จะถืออินพุตเป็นข้อความธรรมดาและลบเครื่องหมาย ECI ออก. `set_extended_codetext` จะเก็บบิตดิบไว้รวมถึงส่วน ECI ด้วย ทำให้เครื่องสแกนเห็นการสลับภาษาที่ถูกต้อง.

---

## Save the QR Code image and verify the result

สุดท้ายเราจะบันทึก QR Code ลงดิสก์. Aspose.Barcode รองรับ PNG, JPEG, BMP และอื่น ๆ; PNG เป็นค่าเริ่มต้นที่ปลอดภัยเพราะเก็บข้อมูลแบบ lossless

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

ตอนนี้คุณควรมีไฟล์ PNG ที่ตำแหน่งที่ระบุแล้ว. เปิดด้วยแอปสแกน QR ใดก็ได้ที่รองรับ ECI (สมาร์ทโฟนสมัยใหม่ส่วนใหญ่ทำได้). สแกนครั้งแรก – คุณจะเห็น “HELLO123”. สแกนครั้งที่สอง (หรือใช้สแกนที่แสดงข้อมูลดิบ) – คุณจะเห็น “Привет”. ทั้งสองส่วนปรากฏเป็น payload เดียวตามที่เราสร้างไว้.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: ตัวอย่าง QR code ของ use extcodetextbuilder aspose แสดงข้อความ ECI แบบผสม*

---

## Full, Ready‑to‑Run Script

รวมทุกอย่างเข้าด้วยกัน นี่คือโปรแกรมเต็มที่คุณสามารถคัดลอก‑วางลงในไฟล์ชื่อ `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Run it with:

```bash
python qr_mixed_eci.py
```

คุณจะเห็นข้อความในคอนโซลยืนยันตำแหน่งการบันทึก และไฟล์ PNG จะปรากฏตรงที่คุณกำหนดไว้.

---

## Common Questions & Edge Cases

### What if my scanner doesn’t recognize the Cyrillic part?
ตรวจสอบว่าแอปสแกนแสดงการสนับสนุน ECI. ฮาร์ดแวร์รุ่นเก่าอาจละเลยส่วน ECI และตีความบิตเป็น ISO‑8859‑1 ทำให้ตัวอักษรเสียรูป.

### Can I add more than two fragments?
แน่นอน. เรียก `add_plain_codetext` หรือ `add_eci_codetext` จำนวนเท่าที่ต้องการ. Builder จะต่อข้อความตามลำดับที่คุณเรียกเมธอด.

### How do I change the QR Code size or foreground color?
ใช้วัตถุ `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Is there a way to embed binary data (e.g., a small file) alongside text?
ได้. ใช้ `add_binary_codetext` พร้อมอาร์เรย์ไบต์, แล้วจับคู่กับ ECI ที่เหมาะสมหากไบต์นั้นเป็นชุดอักขระเฉพาะ. Builder จะจัดการสลับโหมดให้โดยอัตโนมัติ.

---

## Conclusion

คุณได้เรียนรู้ **วิธีใช้ extcodetextbuilder aspose** เพื่อสร้าง QR Codes ที่ผสานข้อความ ASCII ธรรมดาและข้อความรัสเซียที่เข้ารหัสเป็น UTF‑8 อย่างราบรื่น. ด้วยการใช้ `ExtCodetextBuilder`, ตั้งค่า **ECI encoding** ที่ถูกต้อง, แล้วส่งผลลัพธ์ให้กับ **Aspose.Barcode QR Code generator**, คุณจะได้ภาพมาตรฐานเดียวที่ทำงานบนเครื่องสแกนสมัยใหม่.  

จากนี้ลองสลับ `eci_encoding=3` เป็นตัวระบุภาษาต่าง ๆ, หรือทดลองเพิ่มส่วนข้อความธรรมดาเพื่อสร้าง payload หลายภาษ. คุณอาจสำรวจตัวเลือก `BarCodeImageFormat` เพื่อส่งออกเป็น SVG หรือ PDF หากต้องการกราฟิกแบบเวกเตอร์.  

Happy coding, and feel free to drop a comment if you hit any snags—your feedback helps make these guides even better!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}