---
category: general
date: 2026-11-23
description: สร้างบาร์โค้ด Planet ไปรษณีย์ใน C# ด้วย Aspose.BarCode. เรียนรู้วิธีสร้างบาร์โค้ด
  Planet, ตั้งค่า X‑dimension, และบันทึกบาร์ที่เต็มหรือว่าง.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: th
lastmod: 2026-11-23
og_description: สร้างบาร์โค้ด Planet แบบไปรษณีย์ใน C# และเรียนรู้วิธีสร้างบาร์โค้ด
  Planet ด้วย Aspose.BarCode ทำตามตัวอย่างครบถ้วนเพื่อสร้างบาร์ที่เต็มและว่าง
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: วิธีสร้างบาร์โค้ด Postal Planet ด้วย C# – คู่มือทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: วิธีสร้างบาร์โค้ด Postal Planet ด้วย C#
url: /th/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างรหัสบาร์โค้ด Planet ไปรษณีย์ใน C#

หากคุณต้องการ **สร้างรหัสบาร์โค้ด Planet ไปรษณีย์** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจน **วิธีสร้างรหัสบาร์โค้ด Planet** โดยใช้ไลบรารี Aspose.BarCode คุณจะได้เห็นวิธีกำหนดค่า X‑dimension, สลับระหว่างบาร์ที่เต็มและบาร์ที่ว่าง, และบันทึกภาพเป็นรูปแบบ PNG  

การสร้างรหัสบาร์โค้ด Planet เป็นเรื่องปกติสำหรับบริการไปรษณีย์ที่ต้องการสัญลักษณ์ความหนาแน่นสูงและเครื่องอ่านได้ โดยตอนท้ายของบทแนะนำนี้คุณจะมีไฟล์ PNG สองไฟล์—หนึ่งไฟล์ที่มีบาร์เต็มและอีกไฟล์ที่มีบาร์ว่าง—พร้อมสำหรับการผสานรวมในกระบวนการส่งจดหมายใด ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว
* Visual Studio 2022 (หรือโปรแกรมแก้ไข C# ใด ๆ) ตั้งค่าเพื่อพัฒนา .NET
* ไลเซนส์ NuGet ที่ใช้งานได้สำหรับ **Aspose.BarCode for .NET**. ติดตั้งแพคเกจด้วย:

```bash
dotnet add package Aspose.BarCode
```

ไม่ต้องใช้บริการภายนอกเพิ่มเติม; ไลบรารีทำการเข้ารหัสทั้งหมดในเครื่อง

## ขั้นตอนที่ 1 – สร้างรหัสบาร์โค้ด Planet ไปรษณีย์

การดำเนินการแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` สำหรับสัญลักษณ์ **Planet** และให้ข้อมูลที่ต้องเข้ารหัส ข้อมูลต้องเป็นตัวเลขและมีความยาวไม่เกิน 12 หลักตามข้อกำหนดของไปรษณีย์

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

การสร้างตัวสร้างจะจัดสรรโครงสร้างภายในทั้งหมดที่จำเป็นสำหรับการเรนเดอร์ ค่า enum `EncodeTypes.Planet` จะเลือกอัลกอริทึมการเข้ารหัสที่ถูกต้องสำหรับรูปแบบไปรษณีย์

## ขั้นตอนที่ 2 – ตั้งค่า X‑dimension เพื่อความชัดเจนที่ดีขึ้น

X‑dimension กำหนดความกว้างของโมดูลเดียว (ส่วนที่เล็กที่สุดของบาร์) ค่า 4 พิกเซลให้การแสดงผลที่ชัดเจนโดยไม่ทำให้ภาพโดยรวมขยายใหญ่ขึ้น

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

การปรับ X‑dimension มีความสำคัญเมื่อรหัสบาร์โค้ดจะพิมพ์บนสื่อความละเอียดต่ำ การตั้งค่าเดียวกันนี้จะถูกใช้ซ้ำสำหรับเวอร์ชันบาร์ว่างเพื่อให้ภาพทั้งสองสอดคล้องกัน

## ขั้นตอนที่ 3 – บันทึกรหัสบาร์โค้ดด้วยบาร์เต็ม

โดยค่าเริ่มต้นตัวสร้างจะเรนเดอร์ **บาร์เต็ม** (โมดูลสีดำทึบ) การบันทึกภาพทำได้ด้วยการเรียกเมธอดเดียวที่เขียนไฟล์ PNG ลงดิสก์

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางจริงที่คุณต้องการให้ไฟล์ผลลัพธ์อยู่ `BarCodeImageFormat.Png` เป็นค่าที่รับประกันการบีบอัดแบบไม่มีการสูญเสีย ซึ่งเหมาะกับการประมวลผลต่อไป

## ขั้นตอนที่ 4 – สร้างตัวสร้างรหัสบาร์โค้ด Planet อีกอันสำหรับบาร์ว่าง

เพื่อสร้างเวอร์ชันที่ใช้ **บาร์ว่าง** (โมดูลสีขาวบนพื้นหลังสีดำ) คุณต้องมีอินสแตนซ์ `BarcodeGenerator` ตัวที่สอง การใช้ข้อมูลเดียวกันทำให้ภาพทั้งสองแสดงรหัสไปรษณีย์เดียวกัน

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

การสร้างตัวสร้างแยกกันทำให้คุณสามารถแยกคุณสมบัติ `FilledBars` ออกมาได้ เพื่อสลับสไตล์การแสดงผลโดยไม่กระทบต่อภาพแรก

## ขั้นตอนที่ 5 – ตั้งค่าตัวสร้างให้เรนเดอร์บาร์ว่าง

แฟล็ก `FilledBars` จะสลับโหมดการเรนเดอร์ การตั้งค่าเป็น `false` จะบอกไลบรารีให้วาดบาร์เป็นแบบว่าง (โปร่งใส) ในขณะที่พื้นหลังยังคงเป็นสีทึบ

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

การคง X‑dimension ให้เหมือนกับเวอร์ชันบาร์เต็มรับประกันว่าทั้งสองไฟล์ PNG จะมีขนาดเท่ากัน ซึ่งทำให้การคำนวณเลย์เอาต์ในเทมเพลตการพิมพ์ง่ายขึ้น

## ขั้นตอนที่ 6 – บันทึกรหัสบาร์โค้ดที่เรนเดอร์บาร์ว่าง

สุดท้ายให้เขียนภาพบาร์ว่างลงดิสก์ ใช้รูปแบบ PNG เดียวกัน แต่คุณสามารถสลับเป็น JPEG หรือ BMP ได้โดยเปลี่ยนค่าของ `BarCodeImageFormat`

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณจะมีไฟล์สองไฟล์:

* `PostalPlanetFilledBars.png` – บาร์สีดำทึบ
* `PostalPlanetEmptyBars.png` – บาร์ว่างบนพื้นหลังสีดำ

ทั้งสองไฟล์สอดคล้องกับข้อกำหนดของสัญลักษณ์ Planet

## โค้ดต้นฉบับทั้งหมด

การรวมขั้นตอนทั้งหมดเข้าด้วยกันจะได้แอปพลิเคชันคอนโซลขนาดกะทัดรัดที่คุณสามารถรันได้โดยตรง

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

คอมไพล์และรันโปรแกรม:

```bash
dotnet run
```

คอนโซลจะแสดงข้อความ *Barcodes generated successfully.* และไฟล์ PNG สองไฟล์จะปรากฏในโฟลเดอร์โปรเจกต์

## ผลลัพธ์ที่คาดหวัง

ด้านล่างเป็นภาพแสดงตัวอย่างของภาพบาร์เต็ม ส่วนภาพบาร์ว่างจะดูเหมือนกันยกเว้นบาร์เป็นแบบโปร่งใส

![ตัวอย่างของรหัสบาร์โค้ด Planet ไปรษณีย์ที่สร้างขึ้นด้วยบาร์เต็ม](postal-planet-filled.png)

*ข้อความแทนภาพ:* **ตัวอย่างของรหัสบาร์โค้ด Planet ไปรษณีย์ที่สร้างขึ้นด้วยบาร์เต็ม** (contains the primary keyword)

โดยค่าเริ่มต้นภาพทั้งสองมีขนาด 150 × 150 พิกเซล แต่คุณสามารถควบคุมขนาดโดยรวมด้วยพารามิเตอร์ `ImageWidth` และ `ImageHeight` หากต้องการความละเอียดที่ต่างออกไป

## ตัวแปรเลือกใช้

### การเปลี่ยนรูปแบบภาพ

หากระบบต่อไปของคุณต้องการ JPEG ให้แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` JPEG จะทำให้เกิดอาร์ติแฟกต์จากการบีบอัด ดังนั้นควรใช้เฉพาะเมื่อขนาดไฟล์เป็นข้อจำกัดสำคัญ

### การปรับขนาดรหัสบาร์โค้ด

คุณสามารถขยายรหัสบาร์โค้ดโดยคงความกว้างของโมดูลไว้โดยปรับคุณสมบัติ `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

ค่ DPI ที่สูงขึ้นช่วยปรับคุณภาพการพิมพ์บนเครื่องพิมพ์เลเซอร์

### การใช้สีพื้นหลังแบบกำหนดเอง

สามารถตั้งค่าสีพื้นหลังได้ด้วย:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

วิธีนี้เหมาะสำหรับการทดสอบภาพ แต่ควรหลีกเลี่ยงในฉลากไปรษณีย์จริงที่ต้องใช้พื้นหลังสีขาว

## คำถามที่พบบ่อย

**ทำงานได้กับ .NET Core หรือไม่?**  
ใช่ ไลบรารี Aspose.BarCode รองรับ .NET Standard 2.0 ซึ่งเข้ากันได้กับ .NET 5, .NET 6 และ .NET Core 3.1  

**ถ้าข้อมูลเป็นสตริงที่มีอักขระไม่ใช่ตัวเลขจะเกิดอะไรขึ้น?**  
รหัสบาร์โค้ด Planet ยอมรับเฉพาะข้อมูลตัวเลขเท่านั้น การใส่ตัวอักษรหรือสัญลักษณ์จะทำให้เกิด `BarcodeException` ควรตรวจสอบข้อมูลก่อนสร้างตัวสร้าง  

**สามารถสร้างรหัสบาร์โค้ดในหน่วยความจำโดยไม่บันทึกลงดิสก์ได้หรือไม่?**  
ใช้เมธอด `GenerateBarCodeImage` เพื่อรับอ็อบเจกต์ `System.Drawing.Image` แล้วสตรีมออกโดยตรงไปยังการตอบสนองหรือฐานข้อมูล

## สรุป

ตอนนี้คุณรู้วิธี **สร้างรหัสบาร์โค้ด Planet ไปรษณีย์** ใน C# และเข้าใจ **วิธีสร้างรหัสบาร์โค้ด Planet** ทั้งแบบบาร์เต็มและบาร์ว่าง บทแนะนำได้ครอบคลุมขั้นตอนทั้งหมด—from การเริ่มต้นตัวสร้าง, การตั้งค่า X‑dimension, การสลับแฟล็ก `FilledBars`, จนถึงการบันทึกไฟล์ PNG ทดลองเปลี่ยนรูปแบบภาพ, การตั้งค่า DPI, และสีพื้นหลังเพื่อปรับให้รหัสบาร์โค้ดเข้ากับระบบส่งจดหมายของคุณ  

ขั้นตอนต่อไปให้สำรวจสัญลักษณ์ไปรษณีย์อื่น ๆ เช่น **POSTNET** หรือ **Intelligent Mail** โดยใช้ API ของ Aspose.BarCode เดียวกัน การปรับพารามิเตอร์เช่น `EncodeTypes.Postnet` ทำตามรูปแบบเดียวกับที่แสดงในที่นี้ ช่วยให้คุณสร้างชุดการสร้างรหัสบาร์โค้ดที่ครบวงจรในโค้ดเบสเดียว

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดตัวอย่างทำงานครบถ้วนพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [สร้างรหัสบาร์โค้ด Planet ว่าง, สร้างรหัสบาร์โค้ดไปรษณีย์ใน C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [วิธีตั้งความกว้างและสร้างรหัสบาร์โค้ด Planet ใน C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [สร้างรหัสบาร์โค้ดไปรษณีย์ใน C# – คู่มือฉบับสมบูรณ์กับรหัสบาร์โค้ด Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}