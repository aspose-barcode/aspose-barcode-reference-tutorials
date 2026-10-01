---
category: general
date: 2026-09-10
description: สร้างภาพบาร์โค้ดด้วย C# อย่างรวดเร็วโดยใช้ตัวอย่างเครื่องสร้างบาร์โค้ดใน
  C# ที่แสดงวิธีตั้งค่าขนาดและบันทึกเป็นไฟล์ PNG
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: th
lastmod: 2026-09-10
og_description: สร้างภาพบาร์โค้ดด้วย C# พร้อมตัวอย่างเครื่องสร้างบาร์โค้ดสั้น ๆ ใน
  C# เรียนรู้การกำหนดขนาด ความสูง และการส่งออกไฟล์ PNG ภายในไม่กี่นาที
og_image_alt: Screenshot of a barcode image created with C# code
og_title: สร้างภาพบาร์โค้ด C# – ตัวอย่างเครื่องสร้างแบบขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: สร้างภาพบาร์โค้ดด้วย C# พร้อมตัวอย่างเครื่องสร้างบาร์โค้ด
url: /th/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ด C# ด้วยตัวอย่างเครื่องสร้างบาร์โค้ด

หากคุณต้องการ **create barcode image C#** สำหรับการติดฉลากสินค้า, การติดตามสินค้าคงคลัง, หรือการสแกนด้วยมือถือ, คู่มือนี้จะแสดงวิธีแก้ไขแบบครบถ้วน คุณจะได้เห็น **barcode generator example C#** ที่กำหนดความกว้างของโมดูล, ความสูงของบาร์, และบันทึกไฟล์ PNG เพียงไม่กี่บรรทัดของโค้ด

บทแนะนำนี้ครอบคลุมทุกอย่างตั้งแต่การติดตั้งไลบรารีที่จำเป็นจนถึงการรันโปรแกรมคอนโซลที่พร้อมคอมไพล์ เมื่อเสร็จสิ้นคุณจะมีไฟล์ PNG ของบาร์โค้ดสองไฟล์—หนึ่งที่มีความสูงของบาร์ 30 พิกเซลและอีกหนึ่งที่มีความสูงของบาร์ 60 พิกเซล—พร้อมใช้งานในแอปพลิเคชัน .NET ใด ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว  
* สภาพแวดล้อมการพัฒนา เช่น Visual Studio 2022 หรือ VS Code  
* แพ็กเกจ NuGet **Aspose.BarCode** (โค้ดใช้ `BarcodeGenerator` จากไลบรารีนี้)  

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่ง CLI ต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์คอนโซล

สร้างโปรเจกต์คอนโซลใหม่และอ้างอิงไลบรารีบาร์โค้ด

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะสร้างไฟล์ `Program.cs` ที่คุณจะวางโค้ด **barcode generator example C#** ลงไป

## ขั้นตอนที่ 2: เขียนโปรแกรมการสร้างบาร์โค้ดเต็มรูปแบบ

แทนที่เนื้อหาใน `Program.cs` ด้วยตัวอย่างที่สมบูรณ์และสามารถทำงานได้ด้านล่าง โปรแกรมนี้จะแสดงวิธี **create barcode image C#** ด้วยขนาดที่กำหนดเองและวิธีบันทึกผลลัพธ์เป็นไฟล์ PNG

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

* **EncodeTypes.DatabarOmniDirectional** – เลือกสัญลักษณ์ DataBar Omnidirectional ซึ่งเข้ารหัสข้อมูลตัวเลขและใช้กันอย่างแพร่หลายในอุตสาหกรรมค้าปลีก  
* **XDimension.Pixels = 2** – ตั้งค่าความกว้างของโมดูล; ค่าที่เล็กลงจะทำให้บาร์โค้ดกระชับมากขึ้น  
* **BarHeight.Pixels** – ควบคุมความสูงของบาร์ในเชิงภาพ การปรับค่านี้ช่วยให้คุณสร้างบาร์โค้ดที่เหมาะกับขนาดฉลากต่าง ๆ  
* **Save method** – เขียนบาร์โค้ดลงไฟล์ PNG ซึ่งเป็นรูปแบบที่คงความคมของขอบและทำงานร่วมกับไลบรารีการประมวลผลภาพส่วนใหญ่ได้ดี

## ขั้นตอนที่ 3: สร้างและรันโปรแกรม

เรียกใช้คำสั่งต่อไปนี้จากโฟลเดอร์โปรเจกต์:

```bash
dotnet run
```

เมื่อโปรแกรมทำงานเสร็จ คุณจะเห็นไฟล์ PNG สองไฟล์ในโฟลเดอร์ย่อย `output`:

* `DatabarBarHeight30Pixels.png` – ความสูงของบาร์ 30 พิกเซล  
* `DatabarBarHeight60Pixels.png` – ความสูงของบาร์ 60 พิกเซล  

ภาพทั้งสองมีข้อมูลที่เข้ารหัสเดียวกันแต่ความสูงของบาร์ต่างกัน แสดงให้เห็นว่า **barcode generator example C#** สามารถปรับให้เข้ากับความต้องการของฉลากที่หลากหลายได้อย่างไร

## ขั้นตอนที่ 4: ตรวจสอบบาร์โค้ดที่สร้างขึ้น

เปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใด ๆ คุณควรเห็นบาร์โค้ด DataBar ที่คมชัดและคอนทราสต์สูง เพื่อยืนยันว่าบาร์โค้ดอ่านได้ คุณสามารถใช้แอปสแกนบนมือถือ (เช่น แอปที่ใช้ ZXing) หรือไลบรารีบนเดสก์ท็อปอย่าง **Aspose.BarCode** ในโหมดถอดรหัส:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

หากผลลัพธ์ตรงกับ `(01)12345678901231` การสร้างบาร์โค้ดสำเร็จแล้ว

## การปรับเปลี่ยนทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับแต่ง | โค้ดตัวอย่าง |
|-----------|------------|--------------|
| **Different symbology** (เช่น QR, Code128) | เปลี่ยนค่า `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Custom image format** (JPEG, BMP) | ใช้ enum `BarCodeImageFormat` ตัวอื่น | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamic data** (ข้อมูลจากผู้ใช้) | แทนที่สตริงที่กำหนดไว้ล่วงหน้าด้วยตัวแปร | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Invalid data length** | ดัก `ArgumentException` ที่ถูกโยนโดย generator | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

เคล็ดลับ: ควรตรวจสอบความยาวของข้อมูลเสมอสำหรับสัญลักษณ์ที่เลือก; Aspose.BarCode จะโยนข้อยกเว้นหากข้อมูลไม่ตรงตามสเปค

## รายการตรวจสอบการแก้ไขปัญหา

* **Directory not found** – ตัวช่วย `SaveBarcode` จะสร้างโฟลเดอร์ `output` ให้อัตโนมัติ แต่ต้องแน่ใจว่าแอปพลิเคชันมีสิทธิ์เขียน  
* **Unexpected image size** – ตรวจสอบว่าได้ตั้งค่า `XDimension.Pixels` และ `BarHeight.Pixels` ก่อนเรียก `Save` แล้ว การเปลี่ยนค่าหลังจากบันทึกจะไม่ส่งผลต่อไฟล์ที่เขียนแล้ว  
* **Unreadable barcode** – ตรวจสอบให้แน่ใจว่าสตริงที่เข้ารหัสเป็นไปตามรูปแบบ GS1 เมื่อใช้สัญลักษณ์ DataBar การขาดวงเล็บหรือ Application Identifier ที่ไม่ถูกต้องจะทำให้การถอดรหัสล้มเหลว  

## สรุป

คุณได้เรียนรู้วิธี **create barcode image C#** ด้วยตัวอย่าง **barcode generator example C#** ที่ใช้งานได้จริง โปรแกรมเต็มกำหนดความกว้างของโมดูล, ปรับความสูงของบาร์, และบันทึกไฟล์ PNG ด้วยโค้ดเพียงเล็กน้อย จากนี้คุณสามารถสำรวจฟีเจอร์เพิ่มเติม เช่น การปรับสี, การส่งออก PDF หลายหน้า, หรือการสร้างแบบเรียลไทม์ใน ASP.NET Core Web API

**ขั้นตอนต่อไป**

* ทดลองใช้สัญลักษณ์อื่น (`EncodeTypes.Code128`, `EncodeTypes.QR`) เพื่อขยายตัวเลือกการสแกนของคุณ  
* ผสานเครื่องสร้างเข้ากับเว็บเซอร์วิสที่ให้บริการภาพบาร์โค้ดตามคำขอ  
* รวมบาร์โค้ดกับเมตาดาต้าผลิตภัณฑ์ในใบแจ้งหนี้ PDF ด้วย Aspose.PDF  

ขอให้เขียนโค้ดอย่างสนุกสนานและเพลิดเพลินกับความยืดหยุ่นที่ C# มอบให้สำหรับการสร้างภาพบาร์โค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณเอง

- [ตัวอย่างเครื่องสร้างบาร์โค้ดใน C# – ตั้งค่าคอลัมน์, แถว & ส่งออกภาพ](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [สร้างภาพบาร์โค้ด C# – ตัวอย่าง GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [ตัวอย่างเครื่องสร้างบาร์โค้ด – สร้างภาพ DataBar ใน C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}