---
category: general
date: 2026-08-22
description: เรียนรู้วิธีตั้งขนาดของบาร์โค้ด Mailmark ใน C# และบันทึกเป็นไฟล์ PNG
  พร้อมโค้ดเต็ม คำอธิบาย และเคล็ดลับ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: th
lastmod: 2026-08-22
og_description: วิธีตั้งขนาดสำหรับบาร์โค้ด Mailmark ใน C# และส่งออกเป็นไฟล์ PNG ทำตามตัวอย่างเต็มรูปแบบและหลีกเลี่ยงข้อผิดพลาดทั่วไป
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: วิธีตั้งขนาดสำหรับบาร์โค้ด Mailmark ใน C# – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: วิธีกำหนดมิติของบาร์โค้ด Mailmark ใน C#
url: /th/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าขนาดสำหรับบาร์โค้ด Mailmark ใน C#

หากคุณต้องการ **วิธีตั้งค่าขนาด** สำหรับบาร์โค้ด Mailmark ใน C# คู่มือนี้จะแสดงขั้นตอนที่แน่นอน คุณจะได้เห็นวิธีกำหนดค่า X‑dimension และความสูงของบาร์ แล้วบันทึกบาร์โค้ดเป็นภาพ PNG โดยไม่ต้องใช้เครื่องมือเพิ่มเติม

การสร้างบาร์โค้ดไปรษณีย์เป็นงานประจำเมื่อพัฒนาโปรแกรมป้ายส่งจดหมาย แต่ขนาดเริ่มต้นมักไม่ตรงกับเครื่องพิมพ์หรือข้อกำหนดการจัดวาง เมื่อจบบทเรียนนี้คุณจะสามารถควบคุมขนาดบาร์โค้ดได้อย่างแม่นยำและสร้างบาร์โค้ด Mailmark สองประเภทที่ถูกต้อง (C‑type และ L‑type) พร้อมพิมพ์ได้ทันที

**สิ่งที่คุณจะได้เรียนรู้**

* วิธีตั้งค่า X‑dimension (ความกว้างโมดูล) และความสูงของบาร์สำหรับ `BarcodeGenerator`
* วิธีบันทึกบาร์โค้ดที่สร้างเป็นไฟล์ PNG ด้วย `BarCodeImageFormat`
* ปัญหาที่พบบ่อย เช่น เส้นทางโฟลเดอร์ไม่ถูกต้องหรือค่าขนาดที่ไม่รองรับ
* เคล็ดลับการใช้การกำหนดค่าเดียวกันซ้ำหลายบาร์โค้ด

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.6+)
* **Aspose.BarCode for .NET** NuGet package (หรือไลบรารีที่เข้ากันได้ซึ่งให้ `BarcodeGenerator`, `EncodeTypes` และ `BarCodeImageFormat`)
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และการทำ I/O ของไฟล์

> **เคล็ดลับมืออาชีพ:** ติดตั้งแพ็กเกจด้วยคำสั่ง CLI  
> `dotnet add package Aspose.BarCode` เพื่อให้โครงการของคุณเป็นระเบียบ

## ขั้นตอนที่ 1: กำหนดโฟลเดอร์ผลลัพธ์

ก่อนสร้างบาร์โค้ดใด ๆ คุณต้องกำหนดว่าภาพ PNG จะถูกเขียนลงที่ไหน การใช้เส้นทางแบบ absolute จะช่วยหลีกเลี่ยงความประหลาดใจบนเครื่องต่าง ๆ

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*ทำไมเรื่องนี้ถึงสำคัญ*: หากโฟลเดอร์ไม่มีอยู่ `Save` จะโยน `IOException`. การเรียก `Directory.CreateDirectory` เป็นแบบ idempotent—จะไม่ทำอะไรหากโฟลเดอร์มีอยู่แล้ว

## ขั้นตอนที่ 2: สร้างบาร์โค้ด Mailmark ประเภท C‑type และ **ตั้งค่าขนาด**

Mailmark C‑type เข้ารหัสสตริงอัลฟานูเมอริก 20 ตัวอักษร หลังจากเริ่มต้น generator คุณสามารถ **ตั้งค่าขนาด** ผ่านอ็อบเจ็กต์ `Parameters.Barcode`

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### ทำไมต้องเลือกค่าต่าง ๆ เหล่านี้?

* **X‑dimension** ควบคุมความกว้างของบาร์ที่เล็กที่สุด ( “โมดูล” ) ค่า `4` พิกเซลทำให้บาร์โค้ดอ่านได้ง่ายโดยเครื่องพิมพ์เลเซอร์ส่วนใหญ่ และไฟล์มีขนาดพอเหมาะ
* **BarHeight** กำหนดขนาดแนวตั้งของบาร์ `50` พิกเซลเป็นความสูงที่ใช้บ่อยสำหรับป้ายส่งจดหมายมาตรฐาน แต่คุณสามารถเพิ่มได้สำหรับรูปแบบที่ใหญ่กว่า

> **Edge case:** เครื่องพิมพ์บางรุ่นต้องการความสูงบาร์ขั้นต่ำที่ 30 px การตั้งค่าความสูงต่ำกว่าความสามารถของเครื่องพิมพ์อาจทำให้บาร์โค้ดอ่านไม่ได้

## ขั้นตอนที่ 3: สร้างบาร์โค้ด Mailmark ประเภท L‑type และ **ตั้งค่าขนาด**

L‑type ใช้สตริงข้อมูลที่ยาวกว่า (สูงสุด 30 ตัวอักษร) วิธีการตั้งค่าขนาดเดียวกันใช้ได้เช่นกัน

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### การใช้การกำหนดค่าใหม่

หากคุณสร้างบาร์โค้ดหลาย ๆ ตัวที่มีขนาดเดียวกัน ควรแยกการกำหนดค่าออกเป็นเมธอดช่วยเหลือ:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

การเรียก `ApplyStandardDimensions(mailmarkC)` และ `ApplyStandardDimensions(mailmarkL)` จะลดการทำซ้ำและทำให้การเปลี่ยนแปลงในอนาคต (เช่น เปลี่ยนเป็นโมดูล 5 พิกเซล) ทำได้ด้วยการแก้ไขบรรทัดเดียว

## ขั้นตอนที่ 4: ตรวจสอบไฟล์ PNG ที่สร้างขึ้น

หลังจากรันโปรแกรม ให้เปิดไฟล์ PNG ทั้งสองไฟล์ในโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ด Mailmark สองแบบที่แตกต่างกัน แต่ละแบบมี 4 px ต่อโมดูลและสูง 50 px

*ผลลัพธ์ที่คาดหวัง*

| ชื่อไฟล์                     | มิติประมาณ (px) |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × module × N modules |
| `PostalMailmarkLType.png`     | 4 px × module × N modules |

ความกว้างที่แท้จริงขึ้นอยู่กับความยาวข้อมูลที่เข้ารหัส แต่ความสูงจะคงที่ที่ **50 px** เนื่องจากเราได้ตั้งค่า `BarHeight.Pixels`

## ปัญหาที่พบบ่อยและวิธีหลีกเลี่ยง

| ปัญหา                              | อาการ                                            | วิธีแก้ |
|-----------------------------------|--------------------------------------------------|---------|
| เส้นทางโฟลเดอร์ไม่ถูกต้อง          | `IOException: Could not find a part of the path` | ใช้ `Path.Combine` กับ `Environment.SpecialFolder` หรือยืนยันว่าเส้นทางถูกต้อง |
| X‑dimension ตั้งเป็น 0 หรือค่าติดลบ | บาร์โค้ดปรากฏเป็นบล็อกสีเดียว                     | ตรวจสอบให้ `XDimension.Pixels` เป็นจำนวนเต็มบวก (ขั้นต่ำ 1) |
| ไม่รองรับ `EncodeTypes.Mailmark`   | `ArgumentException` ที่การสร้าง generator       | ยืนยันว่าคุณใช้เวอร์ชันล่าสุดของไลบรารี Aspose.BarCode ที่รองรับ Mailmark |
| บันทึกด้วยรูปแบบภาพที่ไม่ถูกต้อง   | ไฟล์ PNG เสียหาย                                   | ใช้ `BarCodeImageFormat.Png` (หรือ `Jpeg` หากต้องการรูปแบบอื่น) |

## ขยายตัวอย่าง

* **ขนาดต่าง ๆ** – เปลี่ยน `XDimension.Pixels` เป็น 3 เพื่อให้บาร์โค้ดกระชับขึ้น หรือเพิ่ม `BarHeight.Pixels` เป็น 70 สำหรับป้ายขนาดใหญ่
* **การสร้างเป็นชุด** – วนลูปผ่านคอลเลกชันของสตริงข้อมูล โดยใช้การตั้งค่าขนาดเดียวกันในแต่ละรอบ
* **รูปแบบภาพอื่น** – แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Bmp` หาก workflow ของคุณต้องการ

## สรุป

คุณได้เรียนรู้ **วิธีตั้งค่าขนาด** สำหรับบาร์โค้ด Mailmark ใน C# และส่งออกเป็นไฟล์ PNG แล้ว โดยการกำหนด `XDimension.Pixels` และ `BarHeight.Pixels` คุณสามารถควบคุมขนาดภาพของบาร์โค้ดทั้งประเภท C‑type และ L‑type ให้ตรงตามสเปคของเครื่องพิมพ์และข้อจำกัดการจัดวาง  

จากนี้คุณสามารถทดลองปรับค่าขนาดต่าง ๆ รวมโค้ดเข้ากับระบบป้ายส่งจดหมายขนาดใหญ่ หรือสร้างบาร์โค้ดเป็นชุดสำหรับการส่งจดหมายจำนวนมากได้

---

*ขั้นตอนต่อไป*: สำรวจ **BarcodeGenerator dimensions** สำหรับ QR code หรืออ่านเอกสาร Aspose.BarCode เกี่ยวกับ **การตั้งค่า DPI** สำหรับการพิมพ์ความละเอียดสูง หากต้องการฝังบาร์โค้ดใน PDF ให้ผสานวิธีนี้กับไลบรารี **Aspose.PDF** เพื่อโซลูชันครบวงจรแบบเริ่มต้นถึงจบ

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [วิธีตั้งขอบสำหรับการปรับแต่งบาร์โค้ด ITF-14](/barcode/english/net/itf-14-barcode-customization/)
- [วิธีกำหนดค่า Patch Code Barcodes ด้วย Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [วิธีสร้าง DataMatrix Barcodes ด้วย Aspose.BarCode for .NET – คู่มือขั้นตอน](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}