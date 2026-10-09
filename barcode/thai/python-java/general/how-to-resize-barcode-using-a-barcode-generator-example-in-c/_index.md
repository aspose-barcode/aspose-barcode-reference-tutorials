---
category: general
date: 2026-10-08
description: เรียนรู้วิธีปรับขนาดภาพบาร์โค้ดด้วยตัวอย่างเครื่องสร้างบาร์โค้ด C# โดยปรับความสูงของบาร์จาก
  30 พิกเซลเป็น 60 พิกเซลเพียงไม่กี่บรรทัดของโค้ด
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: th
lastmod: 2026-10-08
og_description: วิธีปรับขนาดบาร์โค้ดอย่างรวดเร็วด้วยตัวอย่างตัวสร้างบาร์โค้ด C# ปรับความสูงของบาร์
  บันทึกไฟล์ PNG และหลีกเลี่ยงข้อผิดพลาดทั่วไป
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: วิธีปรับขนาดบาร์โค้ดใน C# – ตัวอย่างการสร้างแบบขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: วิธีปรับขนาดบาร์โค้ดโดยใช้ตัวอย่างตัวสร้างบาร์โค้ดใน C#
url: /th/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับขนาดบาร์โค้ดโดยใช้ตัวอย่างตัวสร้างบาร์โค้ดใน C#

หากคุณต้องการ **ปรับขนาดบาร์โค้ด** ภาพในโครงการ .NET คู่มือนี้จะแสดงวิธีแก้ไขแบบครบถ้วน คุณจะได้เห็น **ตัวอย่างตัวสร้างบาร์โค้ด C#** ที่เปลี่ยนความสูงของบาร์จาก 30 px เป็น 60 px และบันทึกแต่ละเวอร์ชันเป็นไฟล์ PNG

การปรับขนาดบาร์โค้ดมักจำเป็นเมื่อข้อมูลเดียวกันต้องแสดงบนใบเสร็จ, ป้าย, หรือหน้าผลิตภัณฑ์ในสเกลที่แตกต่างกัน แทนที่จะแก้ไขภาพราสเตอร์ด้วยโปรแกรมภายนอก คุณสามารถปรับขนาดบาร์โค้ดโดยโปรแกรมได้ ทำให้ความสมบูรณ์ของข้อมูลคงที่

ในบทเรียนนี้คุณจะ:

* ตั้งค่าตัวสร้างบาร์โค้ด DataBar Omni‑Directional
* ปรับพารามิเตอร์ X‑dimension และ bar height
* บันทึกสองภาพที่มีความสูงต่างกัน
* เข้าใจเหตุผลที่การเปลี่ยนความสูงของบาร์ทำงานและกรณีขอบที่ควรระวัง

> **Prerequisite** – คุณมีสภาพแวดล้อมการพัฒนา .NET (Visual Studio 2022 หรือใหม่กว่า) และไลบรารีบาร์โค้ดที่ให้ `BarcodeGenerator`, `EncodeTypes` และ `BarCodeImageFormat` โค้ดนี้ทำงานกับเวอร์ชันล่าสุดของไลบรารี ณ เดือนตุลาคม 2026

## ความต้องการเบื้องต้นสำหรับตัวอย่างตัวสร้างบาร์โค้ด C#

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

| รายการ | เหตุผล |
|------|--------|
| .NET 6.0 SDK หรือใหม่กว่า | ให้ runtime และฟีเจอร์ภาษา ที่ใช้ในตัวอย่าง |
| ไลบรารีบาร์โค้ด (เช่น Aspose.BarCode, Dynamsoft, หรือไลบรารีใด ๆ ที่มี `BarcodeGenerator`) | ให้ `EncodeTypes.DatabarOmniDirectional` enum และเมธอดส่งออกภาพ |
| โฟลเดอร์ที่สามารถเขียนไฟล์ได้ (เช่น `C:\Temp\Barcodes\`) | ตัวอย่างจะบันทึกไฟล์ PNG ไปยังตำแหน่งนี้ |
| ความรู้พื้นฐานของ C# | บทเรียนสมมติว่าคุณคุ้นเคยกับคลาส, คุณสมบัติ, และ string interpolation |

ติดตั้งไลบรารีผ่าน NuGet หากยังไม่ได้ทำ:

```bash
dotnet add package Aspose.BarCode
```

เปลี่ยนชื่อแพคเกจให้ตรงกับที่คุณใช้; API ที่แสดงด้านล่างเป็นรูปแบบทั่วไปของหลาย ๆ barcode SDK

## วิธีปรับขนาดบาร์โค้ด – ขั้นตอนที่ 1: สร้างตัวสร้าง

ขั้นตอนแรกคือสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยสัญลักษณ์และข้อมูลที่ต้องการ ในตัวอย่างนี้เราจะสร้างบาร์โค้ด **DataBar Omni‑Directional** ที่เข้ารหัสค่า GTIN‑14

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**ทำไมส่วนนี้สำคัญ:** enum `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีว่าจะใช้มาตรฐานบาร์โค้ดประเภทใด สตริงข้อมูลตาม GS1 Application Identifier `(01)` สำหรับ GTIN 14 หลัก ทำให้บาร์โค้ดสอดคล้องกับมาตรฐานการค้าระดับโลก

## วิธีปรับขนาดบาร์โค้ด – ขั้นตอนที่ 2: กำหนดความกว้างโมดูลและความสูงบาร์เริ่มต้น

ขนาดภาพของบาร์โค้ดขึ้นกับสองพารามิเตอร์:

* **X‑dimension** – ความกว้างของบาร์ที่เล็กที่สุด (โมดูล) วัดเป็นพิกเซลหรือมิลลิเมตร
* **Bar height** – ความยาวแนวตั้งของบาร์

การตั้งค่าพารามิเตอร์เหล่านี้ก่อนบันทึกจะทำให้ภาพที่เราสร้างตรงกับขนาดที่ต้องการ

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**คำอธิบาย:** X‑dimension 2 px ให้บาร์โค้ดกระชับแต่ยังสแกนได้อย่างน่าเชื่อถือ ความสูง 30 px เป็นค่าเริ่มต้นทั่วไปสำหรับป้ายขนาดเล็ก คุณสามารถปรับ X‑dimension แยกจากความสูงได้หากต้องการลวดลายที่หนาแน่นหรือกระจายมากขึ้น

## วิธีปรับขนาดบาร์โค้ด – ขั้นตอนที่ 3: บันทึกภาพแรก (ความสูง 30 px)

ตอนนี้ให้ส่งออกบาร์โค้ดเป็นไฟล์ PNG เมธอด `Save` รับพาธไฟล์และ enum รูปแบบภาพ

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**ผลลัพธ์:** `DatabarBarHeight30Pixels.png` มีบาร์โค้ดความสูง 30 px คุณสามารถเปิดไฟล์ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันขนาด

## วิธีปรับขนาดบาร์โค้ด – ขั้นตอนที่ 4: เปลี่ยนความสูงบาร์เป็น 60 px

เพื่อสร้างเวอร์ชันที่ใหญ่ขึ้น เพียงปรับคุณสมบัติ `BarHeight` ตัวสร้างจะใช้ข้อมูลและ X‑dimension เดิม ทำให้ลวดลายบาร์โค้ดคงเดิม—เพียงขนาดภาพเปลี่ยน

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**ทำไมวิธีนี้ได้ผล:** เครื่องเรนเดอร์บาร์โค้ดคำนวณเรขาคณิตของบาร์แต่ละบาร์ตามความต้องการ การอัปเดตคุณสมบัติความสูงก่อนเรียก `Save` ครั้งถัดไปจะทำให้เกิดการเรนเดอร์ใหม่ด้วยขนาดที่ปรับแล้ว

## วิธีปรับขนาดบาร์โค้ด – ขั้นตอนที่ 5: บันทึกภาพที่สอง (ความสูง 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์ หนึ่งไฟล์ขนาดเล็ก (30 px) และหนึ่งไฟล์ขนาดใหญ่ (60 px) พร้อมใช้งานบนป้ายขนาดต่าง ๆ

## โค้ดเต็มสำหรับตัวอย่างตัวสร้างบาร์โค้ด C#

ด้านล่างเป็นโปรแกรมที่สมบูรณ์และสามารถรันได้ คัดลอกไปยังโปรเจกต์คอนโซลใหม่เพื่อทดสอบทันที

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**ผลลัพธ์ที่คาดว่าจะเห็นในคอนโซล:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

หลังจากรันแล้ว ให้เปิดไฟล์ PNG ทั้งสองเพื่อดูความแตกต่างของภาพ ทั้งสองบาร์โค้ดเข้ารหัสค่า GTIN‑14 เดียวกันและสแกนได้เท่าเดิมไม่ว่าความสูงจะต่างกันแค่ไหน

## ทำไมการปรับความสูงบาร์จึงปลอดภัยต่อการสแกน

เครื่องสแกนบาร์โค้ดอ่านลำดับของโมดูลสีเข้มและสีอ่อน ไม่ได้อ้างอิงจำนวนพิกเซลโดยตรง ตราบใดที่ **X‑dimension** อยู่ในช่วง tolerances ของเครื่องสแกน (โดยทั่วไป 0.5 mm ถึง 2 mm) การเปลี่ยนความสูงจะไม่กระทบต่อความสามารถในการอ่าน ไลบรารีจะสเกลโมดูลอัตโนมัติ พร้อมรักษา quiet zone และรูปแบบการจัดตำแหน่งที่จำเป็น

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | วิธีแก้ |
|---------|------------|
| **โฟลเดอร์ปลายทางไม่มีอยู่** | เรียก `Directory.CreateDirectory(outputPath)` ก่อนบันทึก |
| **X‑dimension ไม่เหมาะทำให้สแกนเบลอ** | รักษา `XDimension.Pixels` ระหว่าง 1 px ถึง 4 px สำหรับเครื่องพิมพ์ส่วนใหญ่; ทดสอบกับเครื่องสแกนจริง |
| **ใช้รูปแบบราสเตอร์สำหรับบาร์โค้ดขนาดใหญ่มาก** | เปลี่ยนเป็น `BarCodeImageFormat.Svg` เพื่อความยืดหยุ่นไม่จำกัดโดยไม่มีการสูญเสียคุณภาพ |
| **ลืมรีเซ็ต `BarHeight` ก่อนบันทึกครั้งที่สอง** | ตรวจสอบว่าได้กำหนดความสูงใหม่ **ก่อน** เรียก `Save` อีกครั้ง |

## เคล็ดลับระดับมืออาชีพ: สร้างหลายขนาดในลูป

หากต้องการความสูงหลายระดับ (เช่น 30 px, 45 px, 60 px) ลูป `foreach` ง่าย ๆ จะช่วยลดการทำซ้ำโค้ด

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

รูปแบบนี้เหมาะกับการประมวลผลเป็นชุดสำหรับแคตตาล็อกสินค้า

## กรณีขอบ: รูปแบบภาพต่าง ๆ และการตั้งค่า DPI

* **SVG output** – ใช้ `BarCodeImageFormat.Svg` เพื่อสร้างไฟล์เวกเตอร์ที่สามารถปรับขนาดได้โดยไม่เสียคุณภาพ
* **PNG ความละเอียดสูง** – ตั้งค่า `generator.Parameters.Image.DpiX` และ `DpiY` เป็น 300 หรือ 600 สำหรับภาพพร้อมพิมพ์; ความสูงบาร์ยังคงวัดเป็นพิกเซล จึงต้องเพิ่มตามสัดส่วน
* **Symbology ที่ไม่เป็นมาตรฐาน** – บางประเภทบาร์โค้ด (เช่น QR Code) มีคุณสมบัติ `Size` แทน `BarHeight` ตรวจสอบเอกสารไลบรารีสำหรับกรณีนั้น

## การทดสอบบาร์โค้ดที่ปรับขนาดแล้ว

1. เปิด PNG แต่ละไฟล์ในโปรแกรมดูภาพและตรวจสอบขนาดพิกเซล (เช่น 150 × 30 px vs. 150 × 60 px)  
2. พิมพ์ภาพที่อัตรา 100 %  
3. สแกนด้วยเครื่องสแกนบาร์โค้ดแบบพกพาหรือแอปมือถือ ข้อมูลที่ถอดรหัสควรตรงกัน

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้เกี่ยวข้องโดยตรงและต่อยอดเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [ตัวอย่างตัวสร้างบาร์โค้ดใน C# – ตั้งค่าความกว้างและความสูง](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [วิธีปรับขนาดบาร์โค้ดใน C# ด้วย Aspose.BarCode – คู่มือขั้นตอนโดยละเอียด](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [วิธีบันทึกภาพบาร์โค้ดด้วย Barcode Generator C# – คู่มือขั้นตอนโดยละเอียด](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}