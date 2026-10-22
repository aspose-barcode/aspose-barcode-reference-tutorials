---
category: general
date: 2026-10-21
description: สร้างภาพบาร์โค้ด Databar Expanded Stacked ใน C# ด้วย BarcodeGenerator.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างภาพบาร์โค้ด ปรับแถวและคอลัมน์ตามต้องการ
  และส่งออกไฟล์ PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: th
lastmod: 2026-10-21
og_description: สร้างบาร์โค้ด Databar Expanded Stacked ใน C# ด้วยบทเรียนนี้ เรียนรู้วิธีใช้
  BarcodeGenerator ตั้งค่าแถวและคอลัมน์ และบันทึกภาพ PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: สร้างบาร์โค้ด Databar Expanded Stacked ด้วย C# – คู่มือฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างบาร์โค้ด Databar Expanded Stacked ด้วย C#
url: /th/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด databar expanded stacked ใน C#

หากคุณต้องการสร้างบาร์โค้ด **databar expanded stacked** ใน C# คู่มือนี้จะแสดงวิธีทำ สัญลักษณ์ databar expanded stacked เหมาะสำหรับการเข้ารหัสข้อมูลจำนวนมากในรูปแบบที่กะทัดรัด และคุณสามารถสร้างภาพได้ด้วยเพียงไม่กี่บรรทัดของโค้ด คุณยังจะได้เรียนรู้วิธี **generate barcode image** ในรูปแบบต่าง ๆ และปรับแถวหรือคอลัมน์ให้เหมาะกับสภาพแวดล้อมการสแกนของคุณ

บทเรียนนี้ครอบคลุมทุกสิ่งที่คุณต้องการเพื่อเริ่มผลิตบาร์โค้ด databar: การติดตั้งไลบรารีที่จำเป็น, การเตรียมโฟลเดอร์ผลลัพธ์, การสร้างบาร์โค้ดด้วยแถวหรือคอลัมน์ที่กำหนดเอง, และการบันทึกผลลัพธ์เป็นไฟล์ PNG เมื่อเสร็จสิ้นคุณจะสามารถ **create databar barcode** ภาพได้โดยอัตโนมัติและปรับโค้ดให้รองรับรูปแบบภาพอื่น ๆ หรือสถานการณ์การทำงานต่าง ๆ

## ข้อกำหนดเบื้องต้น

* .NET 6.0 SDK หรือรุ่นใหม่กว่า (โค้ดนี้ยังทำงานได้กับ .NET Core 3.1 และ .NET Framework 4.7+)
* สภาพแวดล้อมการพัฒนา เช่น Visual Studio 2022, Visual Studio Code หรือ Rider
* การเชื่อมต่ออินเทอร์เน็ตเพื่อทำการติดตั้งแพ็กเกจ NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **เคล็ดลับ:** หากคุณใช้ CI/CD pipeline ให้เพิ่มการอ้างอิงแพ็กเกจ NuGet ไปยังไฟล์โครงการของคุณเพื่อให้การสร้างเป็นแบบทำซ้ำได้

## ติดตั้งไลบรารี Barcode Generator C# 

ตัวอย่างนี้ใช้ไลบรารี Aspose.BarCode ซึ่งให้คลาส `BarcodeGenerator` และ enumeration `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่มเวอร์ชันที่เสถียรล่าสุดลงในโครงการของคุณ หลังการติดตั้งคุณสามารถนำเข้า namespace ในไฟล์ C# ของคุณได้:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## เตรียมโฟลเดอร์ผลลัพธ์

เส้นทางไฟล์ที่เชื่อถือได้ช่วยป้องกันข้อผิดพลาดขณะรันไทม์เมื่อไลบรารีพยายามเขียนภาพ โค้ดต่อไปนี้จะสร้างไดเรกทอรีหากยังไม่มี:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **เหตุผลที่สำคัญ:** การพยายามบันทึกไปยังไดเรกทอรีที่ไม่มีอยู่จะทำให้เกิด `IOException` การสร้างโฟลเดอร์ล่วงหน้าช่วยให้โค้ดมีความทนทานทั้งในสภาพแวดล้อมการพัฒนาท้องถิ่นและการผลิต

## การสร้างภาพบาร์โค้ด databar expanded stacked

### การสร้างบาร์โค้ดพื้นฐาน

วิธีที่ง่ายที่สุดในการสร้างภาพ **databar expanded stacked** คือการสร้างอินสแตนซ์ของ `BarcodeGenerator` พร้อมค่าของ `EncodeTypes` ที่ต้องการและข้อมูลแบบข้อความธรรมดา.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

การรันโค้ดส่วนนี้จะสร้างไฟล์ `DatabarBasic.png` ในโฟลเดอร์ *Barcodes* ภาพนี้มีสัญลักษณ์ databar expanded stacked มาตรฐานพร้อมการจัดวางค่าเริ่มต้น (4 คอลัมน์ × 4 แถว)

### ปรับแต่งคอลัมน์ – สร้างบาร์โค้ด databar ด้วย 4 คอลัมน์

คุณสามารถควบคุมจำนวนคอลัมน์ได้โดยใช้ property `Parameters.Barcode.DataBar.Columns` ตัวอย่างต่อไปนี้สร้างบาร์โค้ดที่มี **4 คอลัมน์** พร้อมจำนวนแถวค่าเริ่มต้น

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

ไฟล์ที่ได้, **DatabarCols4.png**, มีลักษณะดังนี้:

![บาร์โค้ด Databar expanded stacked พร้อม 4 คอลัมน์](databar_cols4.png "บาร์โค้ด Databar expanded stacked พร้อม 4 คอลัมน์ – สร้างด้วย C#")

*ข้อความแทนภาพ (og_image_alt):* **ตัวอย่างภาพบาร์โค้ด databar expanded stacked ที่สร้างด้วย C#** – นี้เป็นการตอบสนองต่อข้อกำหนด SEO สำหรับข้อความแทนภาพ

### ปรับแต่งแถว – สร้างบาร์โค้ด databar ด้วย 3 แถว

เช่นเดียวกัน คุณสามารถปรับจำนวนแถวได้ผ่าน `Parameters.Barcode.DataBar.Rows` โค้ดด้านล่างจะสร้างบาร์โค้ดที่มี **3 แถว** และจำนวนคอลัมน์ค่าเริ่มต้น (4)

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

ไฟล์ **DatabarRows3.png** มีสัญลักษณ์ databar expanded stacked ที่สั้นลงในแนวตั้งเล็กน้อย ซึ่งอาจเป็นประโยชน์สำหรับป้ายที่มีพื้นที่จำกัด

### การส่งออกเป็นรูปแบบอื่น

หากคุณต้องการประเภทภาพอื่น (เช่น JPEG, BMP หรือ SVG) ให้แทนที่ `BarCodeImageFormat.Png` ด้วยค่า enum ที่เหมาะสม:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

ไลบรารีนี้ยังรองรับรูปแบบเวกเตอร์เช่น SVG ซึ่งเหมาะสำหรับการพิมพ์ความละเอียดสูง

## สถานการณ์ขั้นสูง

### การบันทึกลง MemoryStream

บางครั้งคุณอาจต้องการฝังบาร์โค้ดโดยตรงลงในการตอบสนองเว็บหรือ PDF โดยไม่ต้องเขียนไฟล์ลงระบบไฟล์ ใช้ `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### การจัดการอินพุตที่ไม่ถูกต้อง

`BarcodeGenerator` จะตรวจสอบความถูกต้องของข้อมูลตามสัญลักษณ์ที่เลือก หากข้อมูลมีอักขระที่ห้ามใช้ จะเกิด `ArgumentException` ให้ห่อโค้ดการสร้างด้วยบล็อก try‑catch เพื่อให้ข้อความแสดงข้อผิดพลาดที่เป็นมิตร:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### การปรับขนาดภาพบาร์โค้ด

คุณสามารถเปลี่ยนขนาดภาพโดยไม่ต้องแก้ไขข้อมูลที่เข้ารหัสโดยตั้งค่า `Parameters.Image.Width` และ `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

การปรับขนาดมีประโยชน์เมื่อบาร์โค้ดต้องตรงตามความต้องการ DPI เฉพาะสำหรับสแกนเนอร์

## ตัวอย่างทำงานเต็มรูปแบบ

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่สมบูรณ์พร้อมรันที่แสดงขั้นตอนทั้งหมดที่ได้อธิบายไว้:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ

- [วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked – คู่มือ C# ฉบับสมบูรณ์](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [วิธีสร้างตัวอย่างโปรแกรมสร้างบาร์โค้ดใน C# ด้วย DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [คู่มือบาร์โค้ด databar expanded stacked – วิธีสร้างและกำหนดขนาดใน C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}