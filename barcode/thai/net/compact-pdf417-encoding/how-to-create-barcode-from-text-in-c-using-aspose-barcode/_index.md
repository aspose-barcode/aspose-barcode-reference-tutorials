---
category: general
date: 2026-10-28
description: สร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode. เรียนรู้การสร้างภาพบาร์โค้ด
  PDF417, ตั้งค่าคอลัมน์, ปรับมิติ X, และเปิดใช้งานโหมดบีบอัด.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: th
lastmod: 2026-10-28
og_description: สร้างบาร์โค้ดจากข้อความใน C# โดยใช้ Aspose.BarCode บทเรียนนี้แสดงวิธีสร้างภาพบาร์โค้ด
  PDF417 ปรับขนาด จำนวนคอลัมน์ และโหมดคอมแพคท์
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: สร้างบาร์โค้ดจากข้อความใน C# – คู่มือขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: วิธีสร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode
url: /th/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode

หากคุณต้องการ **สร้างบาร์โค้ดจากข้อความ** ในแอปพลิเคชัน .NET คำแนะนำนี้จะให้โซลูชันที่พร้อมใช้งาน คุณจะได้เห็นวิธี **สร้างภาพบาร์โค้ด PDF417** ควบคุมความกว้างของโมดูล จำนวนคอลัมน์ และเปิดใช้งานโหมดคอมแพคโดยไม่ต้องออกจาก IDE ของคุณ

บทเรียนนี้ครอบคลุมทุกอย่างที่จำเป็นสำหรับการ **generate barcode C#** ตั้งแต่การติดตั้งไลบรารีจนถึงการบันทึกไฟล์ PNG สุดท้าย เมื่อเสร็จแล้วคุณสามารถฝังบาร์โค้ด PDF417 ความหนาแน่นสูงในรายงาน ตั๋ว หรือป้ายสินค้าต่าง ๆ ได้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* Visual Studio 2022 (หรือโปรแกรมแก้ไขใด ๆ ที่รองรับ .NET)  
* การเชื่อมต่ออินเทอร์เน็ตเพื่อดาวน์โหลดแพ็กเกจ NuGet Aspose.BarCode for .NET  

สิ่งเหล่านี้เพียงพอสำหรับการคอมไพล์และรันตัวอย่างบน Windows, Linux หรือ macOS

## ขั้นตอนที่ 1: ติดตั้งแพ็กเกจ NuGet Aspose.BarCode

ไลบรารีที่ทำหน้าที่สร้างบาร์โค้ดคือ **Aspose.BarCode for .NET** ติดตั้งโดยใช้ .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

แพ็กเกจนี้จะเพิ่มเนมสเปซ `Aspose.BarCode` ซึ่งประกอบด้วยคลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียนนี้

## ขั้นตอนที่ 2: สร้างโปรเจกต์คอนโซลและเพิ่มโค้ด

สร้างโปรเจกต์คอนโซลใหม่และแทนที่ไฟล์ `Program.cs` ที่สร้างขึ้นอัตโนมัติด้วยโค้ดต่อไปนี้ โปรแกรมจะแสดงวิธี **create barcode from text** และบันทึกเป็น **PDF417 barcode image**:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

* **`EncodeTypes.Pdf417`** เลือกสัญลักษณ์ PDF417 ซึ่งเหมาะสำหรับการเข้ารหัสข้อมูลจำนวนมากในรูปแบบสองมิติ  
* **`XDimension.Pixels = 2`** ลดความกว้างของโมดูล ทำให้บาร์โค้ดหนาแน่นขึ้นและเหมาะกับพื้นที่จำกัด  
* **`Pdf417.Columns = 3`** ควบคุมจำนวนคอลัมน์ข้อมูลแนวตั้ง; จำนวนที่น้อยจะทำให้บาร์โค้ดสูงแต่แคบกว่า  
* **`Pdf417.Truncate = true`** เปิดใช้งานโหมดคอมแพค เพื่อตัดคอลัมน์ที่ไม่ได้ใช้ทางด้านขวา นี่คือการตั้งค่าหลักที่ทำให้ PDF417 ปกติกลายเป็น **compact PDF417 barcode image**  

## ขั้นตอนที่ 3: คอมไพล์และรันโปรเจกต์

รันคำสั่งต่อไปนี้ในโฟลเดอร์โปรเจกต์:

```bash
dotnet build
dotnet run
```

เมื่อโปรแกรมทำงานเสร็จ คุณจะเห็นข้อความในคอนโซลยืนยันตำแหน่งไฟล์ เปิดไฟล์ `CompactPdf417.png` ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันผลลัพธ์

**ผลลัพธ์ที่คาดหวัง** – PNG ความคอนทราสต์สูงที่แสดงบาร์โค้ด PDF417 แบบคอมแพค ซึ่งเข้ารหัสสตริง `Åspóse.Barcóde©` การสแกนภาพด้วยเครื่องอ่านบาร์โค้ดมาตรฐานจะคืนค่าข้อความเดิม ยืนยันว่า **generate pdf417 barcode** สำเร็จ

## ขั้นตอนที่ 4: ปรับแต่งบาร์โค้ดสำหรับสถานการณ์ต่าง ๆ

แม้ว่าตัวอย่างจะใช้จำนวนคอลัมน์และ X‑dimension คงที่ คุณสามารถปรับตัวสร้างบาร์โค้ดให้ตรงกับความต้องการอื่น ๆ ได้ดังนี้:

| สถานการณ์ | การปรับเปลี่ยน |
|----------|------------|
| ปริมาณข้อมูลมาก | เพิ่ม `Pdf417.Columns` หรือกำหนด `Pdf417.Rows` ด้วยตนเอง |
| ความน่าเชื่อถือในการสแกนสูง | เพิ่ม `XDimension.Pixels` เป็น 3 หรือ 4 |
| รูปแบบภาพอื่น | แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg` หรือ `Bmp` |
| พื้นหลังโปร่งใส | ตั้งค่า `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

ตัวเลือกเหล่านี้ช่วยให้คุณ **generate barcode C#** ได้ตามที่เหมาะกับแอปมือถือ รายงานเดสก์ท็อป หรือบริการเว็บ

## ขั้นตอนที่ 5: จัดการกรณีขอบและแนวปฏิบัติที่ดีที่สุด

* **รองรับ Unicode** – ตัวสร้างบาร์โค้ดจะเข้ารหัสอักขระ Unicode อัตโนมัติ แต่ต้องแน่ใจว่าข้อความต้นฉบับของคุณเป็น UTF‑8 หากอ่านจากไฟล์  
* **ข้อความยาว** – PDF417 สามารถเข้ารหัสได้สูงสุด 1,850 ตัวอักษรอัลฟานูเมอริก หากเกินขีดจำกัด ไลบรารีจะโยนข้อยกเว้น; ให้แบ่งข้อมูลเป็นหลายบาร์โค้ดหรือเปลี่ยนไปใช้สัญลักษณ์ที่มีความจุสูงกว่า  
* **การจัดการข้อผิดพลาด** – ห่อโค้ดการสร้างบาร์โค้ดในบล็อก `try/catch` เพื่อดักจับ `BarCodeException` และแสดงข้อความผิดพลาดที่เป็นมิตร  
* **ประสิทธิภาพ** – การสร้างบาร์โค้ดหลาย ๆ ตัวในลูปจะได้ประโยชน์จากการใช้อินสแตนซ์ `BarcodeGenerator` เพียงตัวเดียวและอัปเดต `CodeText` ระหว่างรอบ

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## รายการซอร์สโค้ดเต็ม

ด้านล่างเป็นโปรแกรมที่สมบูรณ์และทำงานได้โดยอิสระ ซึ่งคุณสามารถคัดลอกไปวางใน `Program.cs` ได้เลย ไม่ต้องมีไฟล์เพิ่มเติมใด ๆ

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

การรันโปรแกรมนี้จะสร้าง **pdf417 barcode image** ตามที่แสดงในภาพด้านล่าง

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="สร้างบาร์โค้ดจากข้อความโดยใช้ C# – ตัวอย่างบาร์โค้ด PDF417 แบบคอมแพค"}

*คำอธิบายภาพ: ไฟล์ PNG แสดงบาร์โค้ด PDF417 แบบคอมแพคที่เข้ารหัสสตริง “Åspóse.Barcóde©”.*  

## สรุป

ตอนนี้คุณรู้วิธี **create barcode from text** ใน C# และสร้าง **PDF417 barcode image** พร้อมกำหนดขนาดและโหมดคอมแพค ตัวอย่างนี้สาธิตขั้นตอนสำคัญในการ **generate barcode C#**, จัดการข้อมูล Unicode, และปรับพารามิเตอร์ภาพสำหรับสถานการณ์การใช้งานต่าง ๆ

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้องเช่น **generate QR code in C#**, **add barcode to PDF documents**, หรือ **embed barcodes in ASP.NET Core APIs** ทุกหัวข้ออิงจากพื้นฐาน `BarcodeGenerator` ที่อธิบายไว้ในที่นี้

ขอให้สนุกกับการเขียนโค้ดและการผสานบาร์โค้ดเข้าสู่โซลูชัน .NET ของคุณ!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่ใกล้เคียงและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดตัวอย่างทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณ

- [Generate PDF417 Barcode in C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [How to generate PDF417 barcode with Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}