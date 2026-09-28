---
category: general
date: 2026-07-18
description: วิธีตั้งค่าระดับข้อผิดพลาดในบาร์โค้ด PDF417 ด้วย Aspose.BarCode. เรียนรู้การสร้างบาร์โค้ด
  PDF417 พร้อมข้อความที่กำหนดเองและปรับการแก้ไขข้อผิดพลาดในเวลาไม่กี่นาที.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: th
lastmod: 2026-07-18
og_description: วิธีตั้งระดับความผิดพลาดในบาร์โค้ด PDF417 อย่างรวดเร็ว บทเรียนนี้จะพาคุณผ่านการสร้างบาร์โค้ด
  PDF417 ด้วยข้อความที่กำหนดเองและระดับการแก้ไขข้อผิดพลาดที่แตกต่างกัน
og_image_alt: how to set error level in PDF417 barcode example
og_title: วิธีตั้งระดับข้อผิดพลาดในบาร์โค้ด PDF417 – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: วิธีตั้งระดับข้อผิดพลาดในบาร์โค้ด PDF417 – คู่มือฉบับสมบูรณ์
url: /th/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งระดับข้อผิดพลาดในบาร์โค้ด PDF417 – คู่มือฉบับสมบูรณ์

เคยสงสัย **วิธีตั้งข้อผิดพลาด** เมื่อต้องสร้างบาร์โค้ด PDF417 หรือไม่? คุณไม่ได้เป็นคนเดียว—นักพัฒนาส่วนใหญ่เจอปัญหานี้เมื่อต้องการบาร์โค้ดที่ทนทานต่อการสแกนในสภาพแวดล้อมที่รุนแรง ข่าวดีคือ? การปรับระดับการแก้ไขข้อผิดพลาดทำได้ง่ายด้วย Aspose.BarCode และคุณยังจะได้เรียนรู้ **วิธีสร้าง PDF417** ด้วยข้อความที่กำหนดเองของคุณในขณะเดียวกัน

ในบทแนะนำนี้เราจะเดินผ่านทุกขั้นตอน ตั้งแต่การสร้างตัวสร้างบาร์โค้ดด้วยอักขระพิเศษจนถึงการบันทึกไฟล์ PNG สองไฟล์ที่แสดงระดับการแก้ไขข้อผิดพลาดที่แตกต่างกัน เมื่อเสร็จคุณจะมั่นใจในการ **สร้างบาร์โค้ด PDF417**, ปรับ X‑dimension, จำนวนคอลัมน์ และที่สำคัญที่สุดคือ **การตั้งค่าข้อผิดพลาด** ให้เหมาะกับกรณีการใช้งานของคุณ

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า (โค้ดยังทำงานกับ .NET Framework ได้เช่นกัน)
- Aspose.BarCode สำหรับ .NET ติดตั้งแล้ว (`Install-Package Aspose.BarCode` ผ่าน NuGet)
- โฟลเดอร์บนดิสก์ที่สามารถเขียนรูปภาพได้ (แทนที่ `YOUR_DIRECTORY/` ในตัวอย่าง)
- ความรู้พื้นฐานของ C#—ถ้าคุณเคยเขียน `Console.WriteLine` มาก่อน คุณก็พร้อมแล้ว

> **เคล็ดลับมืออาชีพ:** หากคุณมุ่งเน้นการสแกนบนมือถือ ควรตั้งระดับข้อผิดพลาดสูงกว่า (Level 5) เพื่อทนต่อคราบสกปรก, รอยขีดข่วน หรือสภาพแสงน้อย

## ขั้นตอนที่ 1: สร้างตัวสร้างบาร์โค้ดด้วยข้อความกำหนดเอง

สิ่งแรกที่คุณต้องการคืออินสแตนซ์ `BarcodeGenerator` ที่รู้ว่าต้องสร้าง **บาร์โค้ด PDF417** และบรรจุข้อความที่คุณต้องการเข้ารหัสอย่างแม่นยำ โปรดสังเกตการใช้ตัวอักษรที่มีสำเนียงและสัญลักษณ์ลิขสิทธิ์—ซึ่งแสดงให้เห็นว่าตัวสร้างสามารถจัดการ Unicode ได้โดยตรง

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*ทำไมจึงสำคัญ:* ธง `EncodeTypes.Pdf417` บอก Aspose ว่าคุณกำลังทำงานกับบาร์โค้ด 2‑D แบบซ้อนกัน, ส่วนอาร์กิวเมนต์สตริงเป็นข้อมูลที่ต้องเข้ารหัส หากข้ามขั้นตอนนี้ คุณจะได้บาร์โค้ด Code128 เริ่มต้นแทน PDF417 ที่มีความจุสูงที่ต้องการ

## ขั้นตอนที่ 2: ปรับพารามิเตอร์ภาพอย่างละเอียด

บาร์โค้ด PDF417 ไม่ได้เป็นแค่ข้อมูล; มันยังเป็นรูปแบบภาพด้วย การปรับ **X‑dimension** (ความกว้างของบาร์ที่เล็กที่สุด) และจำนวน **คอลัมน์** ช่วยให้คุณควบคุมขนาดทางกายภาพและความอ่านง่ายของบาร์โค้ด

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*ทำไมจึงสำคัญ:* X‑dimension ที่เล็กลงทำให้ภาพกระชับขึ้น แต่อาจอ่านไม่ออกบนสแกนเนอร์ความละเอียดต่ำ คอลัมน์สามคอลัมน์ให้สัดส่วนที่สมดุลสำหรับขนาดป้ายส่วนใหญ่

## ขั้นตอนที่ 3: ตั้งระดับการแก้ไขข้อผิดพลาดเป็น 2 และบันทึก

การแก้ไขข้อผิดพลาดเป็นหัวใจของ **วิธีตั้งข้อผิดพลาด** สำหรับ PDF417. enum `Pdf417ErrorLevel` มีค่าตั้งแต่ `Level0` (ไม่มีข้อมูลเพิ่มเติม) ถึง `Level5` (ความซ้ำซ้อนสูงสุด) ที่นี่เราจะเริ่มด้วย **Level 2** ซึ่งเพิ่มความทนทานต่อข้อผิดพลาดในระดับปานกลางโดยไม่ทำให้ภาพใหญ่เกินไป

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

หลังจากรันสคริปต์นี้ คุณจะพบไฟล์ `Pdf417ErrorLevel2.png` ในโฟลเดอร์ของคุณ เปิดไฟล์และคุณควรเห็นบาร์โค้ดสามคอลัมน์ที่สะอาดและยังคงมีความซ้ำซ้อนในระดับที่พอสมควร

## ขั้นตอนที่ 4: เพิ่มระดับการแก้ไขข้อผิดพลาดเป็น Level 5 และบันทึกอีกครั้ง

บางครั้งคุณต้องการให้บาร์โค้ดทนต่อความเสียหายที่รุนแรงกว่า—เช่นบนพื้นคลังสินค้าที่ป้ายถูกขีดข่วน การเปลี่ยนเป็น **Level 5** จะเพิ่มการแก้ไขข้อผิดพลาดให้สูงสุดแม้จะทำให้ภาพใหญ่ขึ้นเล็กน้อย

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์อยู่ข้างกัน: หนึ่งไฟล์มีการแก้ไขข้อผิดพลาดระดับปานกลาง อีกไฟล์หนึ่งมีระดับสูงสุด เปรียบเทียบดู; เวอร์ชัน Level 5 จะมีโมดูลสีเข้มมากกว่า ซึ่งเป็นสิ่งที่อัลกอริทึมเพิ่มเพื่อปกป้องข้อมูล

![ตัวอย่างการตั้งระดับข้อผิดพลาดในบาร์โค้ด PDF417](image.png)

*คำอธิบายภาพ (alt text): ตัวอย่างการตั้งระดับข้อผิดพลาดในบาร์โค้ด PDF417 – แสดงไฟล์ PNG สองไฟล์ที่มีระดับการแก้ไขข้อผิดพลาดต่างกัน.*

## ผลลัพธ์ที่คาดหวัง

| ชื่อไฟล์                     | ระดับข้อผิดพลาด | มิติประมาณ (px) |
|-------------------------------|------------------|-----------------|
| `Pdf417ErrorLevel2.png`       | Level 2          | 150 × 80        |
| `Pdf417ErrorLevel5.png`       | Level 5          | 180 × 95        |

ทั้งสองภาพเข้ารหัสสตริง **“Åspóse.Barcóde©”** และสามารถสแกนด้วยเครื่องอ่าน PDF417 มาตรฐานใดก็ได้ (เช่น ZXing, Scandit) ภาพ Level 5 ทนต่อความเสียหายได้ประมาณ ~30 % ในขณะที่ Level 2 ทนประมาณ ~15 %

## คำถามทั่วไปและกรณีขอบ

### ถ้าข้อความของฉันมีการขึ้นบรรทัดใหม่ล่ะ?

PDF417 จะเข้ารหัสอักขระ line‑feed (`\n`) โดยอัตโนมัติ เพียงแค่ใส่ไว้ในสตริง:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### ฉันสามารถใช้รูปแบบภาพอื่นได้ไหม?

ได้เลย. แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Svg` ตามกระบวนการทำงานต่อของคุณ

### การเปลี่ยน X‑dimension มีผลต่อการแก้ไขข้อผิดพลาดหรือไม่?

โดยอ้อมใช่. X‑dimension ที่ใหญ่ขึ้นทำให้โมดูลใหญ่กว่า ซึ่งอาจเพิ่มความน่าเชื่อถือในการสแกน แต่ **ไม่** เปลี่ยนระดับการแก้ไขข้อผิดพลาดเชิงตรรกะ ปรับทั้งสองพารามิเตอร์แยกกันเพื่อผลลัพธ์ที่ดีที่สุด

### วิธีสร้างบาร์โค้ด PDF417 ใน Web API?

ห่อหุ้มโค้ดเดียวกันในคอนโทรลเลอร์ ASP.NET Core แล้วสตรีม PNG กลับเป็น `FileResult` ตรรกะหลักยังคงเหมือนเดิม ซึ่งหมายความว่า **วิธีสร้าง PDF417** จะสอดคล้องกันทั้งในสภาพแวดล้อมเดสก์ท็อปและเว็บ

## สรุป

เราได้อธิบาย **วิธีตั้งข้อผิดพลาด** สำหรับบาร์โค้ด PDF417, แสดง **วิธีสร้าง PDF417** ด้วยข้อความ Unicode กำหนดเอง, และสาธิตการปรับตั้งค่าภาพเช่น X‑dimension และจำนวนคอลัมน์ โดยการสลับ `Pdf417ErrorLevel.Level2` กับ `Level5` คุณสามารถควบคุมการแลกเปลี่ยนระหว่างขนาดภาพและความทนทาน

## ขั้นตอนต่อไป

- ทดลองใช้ **บาร์โค้ดกับข้อความกำหนดเอง** ที่รวม URL หรือรหัสสินค้า
- ลองตั้งค่าจำนวนคอลัมน์ต่าง ๆ (`generator.Parameters.Barcode.Pdf417.Columns = 5`) เพื่อดูการเปลี่ยนแปลงของรูปทรง
- รวม PDF417 กับประเภทบาร์โค้ดอื่นในเอกสารเดียวเพื่อโซลูชันการสแกนหลายรูปแบบ
- สำรวจ [เอกสารอย่างเป็นทางการของ Aspose](https://docs.aspose.com/barcode/net/) เพื่อคุณลักษณะขั้นสูงเช่น macro PDF417 หรือโหมดคอมแพค

หากคุณเจอปัญหาใด ๆ หรืออยากแชร์ผลลัพธ์การสแกนของคุณ อย่าลังเลที่จะคอมเมนต์ไว้ ขอให้สนุกกับการสร้างบาร์โค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญคุณลักษณะ API เพิ่มเติมและสำรวจวิธีการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [วิธีสร้างบาร์โค้ด Aztec พร้อมการแก้ไขข้อผิดพลาดใน .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}