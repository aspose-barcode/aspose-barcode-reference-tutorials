---
category: general
date: 2026-11-27
description: สร้างภาพบาร์โค้ดด้วย C# และบันทึกเป็นไฟล์ PNG ด้วย Aspose.BarCode – คู่มือแบบขั้นตอนต่อขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: th
lastmod: 2026-11-27
og_description: สร้างภาพบาร์โค้ดใน C# และบันทึกเป็นรูปแบบ PNG ด้วย Aspose.BarCode
  ทำตามบทแนะนำนี้เพื่อสร้างบาร์โค้ด Macro PDF417 ทีละขั้นตอน.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: สร้างภาพบาร์โค้ดและบันทึกเป็นรูปแบบ PNG ใน C# – คู่มือฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: สร้างภาพบาร์โค้ดและบันทึกเป็นรูปแบบ PNG ใน C#
url: /th/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดและบันทึกเป็นรูปแบบ PNG ใน C#

หากคุณต้องการ **สร้างภาพบาร์โค้ด** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงวิธีสร้างบาร์โค้ด Macro PDF417 และ **บันทึกภาพเป็นรูปแบบ PNG** ด้วย Aspose.BarCode คุณจะได้ตัวอย่างที่สมบูรณ์และสามารถรันได้พร้อมคำอธิบายของแต่ละการตั้งค่าเพื่อให้คุณปรับใช้โค้ดตามความต้องการของคุณเอง

การสร้างบาร์โค้ดไม่ใช่แค่การเรียกเมธอดเดียว; คุณต้องกำหนดขนาดโมดูล, พารามิเตอร์แมโคร, และรูปแบบการส่งออก ด้วยตอนจบของบทเรียนนี้คุณจะเข้าใจว่าทำไมแต่ละคุณสมบัติจึงสำคัญ, วิธีจัดการกับกรณีขอบที่พบบ่อย, และวิธีตรวจสอบว่าไฟล์ PNG ถูกเขียนอย่างถูกต้อง

## สิ่งที่คุณต้องเตรียม

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.6+)
- Aspose.BarCode for .NET (สามารถติดตั้งผ่าน NuGet: `Install-Package Aspose.BarCode`)
- IDE เช่น Visual Studio 2022 หรือ Visual Studio Code
- สิทธิ์การเขียนไปยังโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้างบาร์โค้ด

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarcodeGenerator` โดยระบุสัญลักษณ์ `EncodeTypes.MacroPdf417` และข้อความที่คุณต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**ทำไมจึงสำคัญ:**  
`EncodeTypes.MacroPdf417` บอกไลบรารีให้ใช้รูปแบบ PDF417 macro ซึ่งรองรับการแบ่งไฟล์และเมตาดาต้าเพิ่มเติม ตัวสร้างยังรับข้อความที่มนุษย์สามารถอ่านได้ซึ่งจะถูกเข้ารหัสในบาร์โค้ด

## ขั้นตอนที่ 2: กำหนดขนาดโมดูล (X‑dimension)

X‑dimension ควบคุมความกว้างของโมดูลบาร์โค้ดหนึ่งหน่วย (องค์ประกอบสีดำ/ขาวที่เล็กที่สุด) ค่า `2` พิกเซลทำงานได้ดีสำหรับ PNG ที่แสดงบนหน้าจอ

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**เคล็ดลับปฏิบัติ:**  
หากคุณวางแผนพิมพ์บาร์โค้ด ให้เพิ่มค่าพิกเซล (เช่น `4` หรือ `5`) เพื่อหลีกเลี่ยงผลลัพธ์เบลอบนเครื่องพิมพ์ความละเอียดต่ำ

## ขั้นตอนที่ 3: กำหนดค่าพารามิเตอร์ Macro PDF417

Macro PDF417 เพิ่มฟิลด์เลือกหลายรายการที่ช่วยระบุไฟล์ต้นทาง, ลำดับส่วน, และการตรวจสอบความสมบูรณ์ ด้านล่างเป็นชุดพารามิเตอร์ทั่วไปทั้งหมด; คุณสามารถละเว้นฟิลด์ที่ไม่ต้องการได้

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**ทำไมฟิลด์เหล่านี้จึงมีประโยชน์:**  

| Parameter | วัตถุประสงค์ |
|-----------|----------------|
| `Columns` | ควบคุมความกว้างของบาร์โค้ด; คอลัมน์น้อยจะทำให้บาร์โค้ดสูงขึ้น. |
| `MacroPdf417FileID` | ตัวระบุที่ไม่ซ้ำกันซึ่งเชื่อมส่วนทั้งหมดเข้าด้วยกัน. |
| `MacroPdf417SegmentID` | ตำแหน่งของส่วนนี้ภายในไฟล์ทั้งหมด. |
| `MacroPdf417SegmentsCount` | จำนวนส่วนทั้งหมด; จำเป็นสำหรับการสร้างใหม่. |
| `MacroPdf417FileName` | ชื่อที่มนุษย์อ่านได้ซึ่งสามารถแสดงโดยแอปสแกน |
| `MacroPdf417Checksum` | ช่วยผู้รับตรวจสอบความสมบูรณ์ของข้อมูล (CCITT‑16). |
| `MacroPdf417FileSize` | คำแนะนำขนาดแบบเลือกสำหรับไฟล์ต้นฉบับ. |
| `MacroPdf417TimeStamp` | เวลาประทับของการสร้างไฟล์ต้นฉบับ. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | เมตาดาต้าสำหรับการกำหนดเส้นทางหรือความเป็นเจ้าของ. |
| `MacroPdf417Terminator` | ระบุว่านี่เป็นส่วนสุดท้าย (`Set`) หรือส่วนกลาง (`Unset`). |

**กรณีขอบ:** หากคุณสร้างบาร์โค้ดแบบส่วนเดียว ให้ตั้งค่า `MacroPdf417SegmentsCount` เป็น `1` และ `MacroPdf417Terminator` เป็น `Unset`. ไลบรารีจะละเว้นฟิลด์ที่เกี่ยวกับส่วนโดยอัตโนมัติหากไม่เกี่ยวข้อง.

## ขั้นตอนที่ 4: บันทึกบาร์โค้ดที่สร้างเป็นภาพ PNG

สุดท้าย ให้เรียก `Save` พร้อมเส้นทางไฟล์และค่า enum `BarCodeImageFormat.Png`. เมธอดนี้จะเขียนภาพลงดิสก์ในรูปแบบ PNG ที่ไม่มีการสูญเสีย

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**ทำไมต้อง PNG?**  
PNG รักษาค่าพิกเซลที่แน่นอน ซึ่งจำเป็นสำหรับสแกนเนอร์บาร์โค้ดที่พึ่งพาความคมชัดของคอนทราสต์ การบีบอัด JPEG อาจทำให้เกิดอาร์ติแฟคที่ทำลายรูปแบบบาร์โค้ด

### การตรวจสอบผลลัพธ์

หลังจากโปรแกรมทำงานเสร็จ คุณควรเห็นไฟล์ชื่อ `ExtPDF417Meta.png` ในโฟลเดอร์การทำงาน การเปิดด้วยโปรแกรมดูภาพใดก็จะเห็นบาร์โค้ดสี่เหลี่ยมแน่น คุณสามารถตรวจสอบความถูกต้องโดยสแกนภาพด้วยแอปอ่านบาร์โค้ดบนมือถือที่รองรับ PDF417 macro; แอปมักจะแสดงเมตาดาต้าที่ฝังอยู่ (ไฟล์ ID, หมายเลขส่วน, ฯลฯ).

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|-------|-------------------|--------|
| บาร์โค้ดดูเบลอ | X‑dimension ต่ำเกินไปสำหรับ DPI ที่เลือก | เพิ่มค่า `XDimension.Pixels` หรือเรนเดอร์ที่ DPI สูงกว่า (`generator.Parameters.ImageResolution`). |
| สแกนเนอร์รายงาน “checksum error” | ค่า `MacroPdf417Checksum` ไม่ถูกต้อง | ให้ Aspose คำนวณ checksum โดยอัตโนมัติโดยไม่ระบุ property นี้ หรือให้แน่ใจว่าค่าตรงกับอัลกอริทึม CCITT‑16. |
| ไฟล์ PNG ว่างหรือไม่ถูกสร้าง | เส้นทางออกไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ใช้ `Path.Combine` กับโฟลเดอร์ที่เขียนได้ที่รู้จัก (เช่น `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| ฟิลด์ Macro ถูกละเว้น | `EncodeTypes` ตั้งเป็น `Pdf417` ปกติแทน `MacroPdf417` | ตรวจสอบว่าใช้ `EncodeTypes.MacroPdf417` ในคอนสตรัคเตอร์. |

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอกไปใส่ในแอปพลิเคชันคอนโซลได้ มันคอมไพล์ด้วย .NET 6.0 และสร้างไฟล์ PNG ตามที่อธิบายข้างต้น

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง (คอนโซล):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

การเปิด `ExtPDF417Meta.png` แสดงบาร์โค้ด Macro PDF417 ที่ชัดเจนพร้อมสแกน

## ขั้นตอนต่อไป

- **เปลี่ยนรูปแบบภาพ** – แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg` หรือ `Bmp` หากคุณต้องการประเภทไฟล์อื่น จำไว้ว่า JPEG จะสร้างอาร์ติแฟคจากการบีบอัด ซึ่งอาจส่งผลต่อความน่าเชื่อถือของการสแกน.
- **ปรับความละเอียด** – ใช้

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญคุณลักษณะ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}