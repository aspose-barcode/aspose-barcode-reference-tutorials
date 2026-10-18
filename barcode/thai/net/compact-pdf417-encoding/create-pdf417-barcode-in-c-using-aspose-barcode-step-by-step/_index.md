---
category: general
date: 2026-10-18
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode บทเรียนนี้ครอบคลุมการสร้าง
  PDF417 แบบพื้นฐาน, แบบคอมแพค, แบบแมโครและแบบไมโคร พร้อมโค้ดเต็ม
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: th
lastmod: 2026-10-18
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode. ทำตามคู่มือนี้เพื่อสร้างบาร์โค้ด
  PDF417 พื้นฐาน, แบบกะทัดรัด, แบบแมโคร และแบบไมโคร ทีละขั้นตอน.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – บทเรียน Aspose.BarCode อย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: สร้างบาร์โค้ด PDF417 ด้วย C# โดยใช้ Aspose.BarCode – คู่มือแบบทีละขั้นตอน
url: /th/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด PDF417 ด้วย C# โดยใช้ Aspose.BarCode – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET นี้ คู่มือจะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เห็นวิธีสร้างบาร์โค้ดพื้นฐาน เปิดใช้งานโหมดคอมแพคท์ เพิ่มเมตาดาต้าแบบแมโคร และสร้างรูปแบบไมโคร — ทั้งหมดพร้อมคำอธิบายที่ชัดเจนและโค้ดที่สามารถรันได้

การสร้างบาร์โค้ด PDF417 เป็นเรื่องทั่วไปในโลจิสติกส์ การออกตั๋ว และการจัดการเอกสาร เมื่อจบคู่มือนี้คุณจะสามารถผสานการสร้างบาร์โค้ดเข้าไปในโครงการ C# ใด ๆ ได้โดยไม่ต้องใช้เครื่องมือภายนอก

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+ ได้เช่นกัน)
* Visual Studio 2022 หรือ IDE สำหรับ C# ใดก็ได้
* **Aspose.BarCode for .NET** แพคเกจ NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG ที่สร้างขึ้นจะถูกบันทึก

ไม่จำเป็นต้องกำหนดค่าพิเศษเพิ่มเติม; ไลบรารีจะจัดการรายละเอียดการเข้ารหัสระดับต่ำทั้งหมดให้

## ขั้นตอน 1: สร้างบาร์โค้ด PDF417 พื้นฐาน

ขั้นตอนแรกจะสร้างบาร์โค้ด PDF417 ปกติพร้อมขนาดและจำนวนคอลัมน์ที่กำหนดเอง

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**ทำไมการตั้งค่าเหล่านี้ถึงสำคัญ**

* `XDimension.Pixels` ควบคุมขนาดทางกายภาพของแต่ละองค์ประกอบของบาร์โค้ด ค่า 2 ทำให้ได้ภาพที่คมชัดบนหน้าจอและเครื่องพิมพ์ส่วนใหญ่
* `Pdf417.Columns` กำหนดจำนวนคอลัมน์ข้อมูลที่บาร์โค้ดมี คอลัมน์น้อยจะทำให้ความกว้างลดลง; คอลัมน์มากจะเพิ่มความจุของข้อมูล

การรันโค้ดจะสร้างไฟล์ `Pdf417Basic.png` ซึ่งมีลักษณะคล้ายสัญลักษณ์ PDF417 ปกติที่มีสามคอลัมน์ข้อมูลและคอลัมน์เมตาดาต้าครบชุดที่ด้านขวา

## ขั้นตอน 2: เปิดใช้งานโหมดคอมแพคท์ (ตัดส่วน)

โหมดคอมแพคท์จะลบคอลัมน์เมตาดาต้าด้านขวา ทำให้บาร์โค้ดแคบลง ซึ่งเป็นประโยชน์เมื่อพื้นที่จำกัดแต่ข้อมูลสามารถกู้คืนได้จากแถวที่เหลือ

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**ทำไมต้องตัดส่วน?**  
เมื่อ `Truncate` เป็น `true` ตัวสร้างจะละเว้นคอลัมน์ด้านขวาที่เป็นตัวเลือกซึ่งเก็บข้อมูลการแก้ไขข้อผิดพลาดและเมตาดาต้าระดับไฟล์ บาร์โค้ดที่ได้จะใช้คอลัมน์น้อยลงแต่ยังคงสแกนได้โดยเครื่องอ่าน PDF417 ส่วนใหญ่

## ขั้นตอน 3: สร้างบาร์โค้ด Macro PDF417 พร้อมเมตาดาต้าระดับไฟล์

Macro PDF417 ขยายรูปแบบมาตรฐานด้วยตัวระบุส่วน ทำให้เอกสารขนาดใหญ่สามารถแบ่งเป็นบาร์โค้ดหลายชุดได้ ซึ่งสะดวกสำหรับการเข้ารหัสสตริงยาวหรือไฟล์หลายหน้า

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**คำอธิบายของฟิลด์แมโคร**

| คุณสมบัติ | วัตถุประสงค์ |
|----------|---------------|
| `MacroPdf417FileID` | ตัวระบุที่ไม่ซ้ำสำหรับไฟล์ทั้งหมด; ทุกส่วนจะใช้ค่าตัวนี้ร่วมกัน |
| `MacroPdf417SegmentID` | ดัชนีของส่วนปัจจุบัน (เริ่มที่ 1) |
| `MacroPdf417SegmentsCount` | จำนวนส่วนทั้งหมดที่ประกอบชุดข้อมูลสมบูรณ์ |

สแกนเนอร์ที่รองรับ Macro PDF417 สามารถประกอบข้อมูลต้นฉบับใหม่ได้โดยอ่านทุกส่วนและใช้ตัวระบุเหล่านี้

## ขั้นตอน 4: สร้างบาร์โค้ด Micro PDF417 สำหรับข้อมูลสั้น

Micro PDF417 เป็นเวอร์ชันคอมแพคท์ที่ออกแบบมาสำหรับข้อมูลขนาดเล็ก (สูงสุด 90 อักขระ) โดยจำกัดช่วงคอลัมน์ที่ 1‑4 ทำให้บาร์โค้ดเหมาะกับป้ายเล็กหรืออุปกรณ์ที่มีพื้นที่แสดงผลจำกัด

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**เมื่อใดควรใช้ Micro PDF417**  
ใช้รูปแบบนี้เมื่อข้อมูลสั้นและคุณต้องการบาร์โค้ดที่เล็กที่สุดเท่าที่เป็นไปได้ เหมาะสำหรับป้ายสินค้าคงคลัง, บัตรเข้าถึง, หรือสถานการณ์ใด ๆ ที่พื้นที่หน้าจอมีจำกัด

## ตัวอย่างการทำงานเต็มรูปแบบ

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่ทำงานอิสระซึ่งสร้างบาร์โค้ดสี่ประเภทในหนึ่งรอบ คัดลอกโค้ดไปยังโปรเจกต์ C# ใหม่, แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางโฟลเดอร์ที่มีอยู่, แล้วรันโปรแกรม

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

การรันโปรแกรมจะสร้างไฟล์ PNG สี่ไฟล์ในโฟลเดอร์ที่ระบุ:

* `Pdf417Basic.png` – บาร์โค้ดมาตรฐานที่มีสามคอลัมน์
* `CompactPdf417.png` – ข้อมูลเดียวกัน แต่คอลัมน์ด้านขวาถูกตัดส่วน
* `MacroPdf417.png` – บาร์โค้ดแมโครที่มีเมตาดาต้าส่วน
* `MicroPdf417.png` – บาร์โค้ดไมโครคอมแพคท์สำหรับสตริงสั้น

เปิดภาพใด ๆ ด้วยโปรแกรมดูภาพ; คุณจะเห็นรูปแบบ PDF417 ที่แตกต่างกัน การสแกนด้วยเครื่องอ่านบาร์โค้ดบนมือถือ (เช่น ZXing, Scandit) จะคืนค่าข้อความต้นฉบับ

## คำถามทั่วไปและเคล็ดลับ

* **ถ้าบาร์โค้ดดูเบลอ?**  
  เพิ่มค่า `XDimension.Pixels` เป็น 3 หรือ 4 ขนาดโมดูลที่ใหญ่ขึ้นจะให้ภาพความละเอียดสูงกว่า แต่ไฟล์จะใหญ่ขึ้น

* **ฉันสามารถส่งออกเป็น SVG แทน PNG ได้หรือไม่?**  
  ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Svg` ในคำสั่ง `Save`

* **จำเป็นต้องตั้งค่าระดับการแก้ไขข้อผิดพลาดด้วยตนเองหรือไม่?**  
  Aspose.BarCode จะเลือกระดับที่เหมาะสมโดยอัตโนมัติ สำหรับกรณีการใช้งานเฉพาะคุณสามารถปรับ `Pdf417.ErrorCorrectionLevel` ได้

* **จะฝังบาร์โค้ดลงในเอกสาร PDF อย่างไร?**  
  ใช้ `Aspose.Pdf` เพื่อเพิ่ม PNG หรือ SVG ที่สร้างขึ้นเป็นองค์ประกอบภาพบนหน้า PDF

* **ไลบรารีนี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?**  
  แต่ละอินสแตนซ์ของ `BarcodeGenerator` เป็นอิสระ; คุณสามารถสร้างตัวสร้างบนหลายเธรดได้โดยไม่มีสถานะที่ใช้ร่วมกัน

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด PDF417** ด้วย C# โดยใช้ Aspose.BarCode ครอบคลุมรูปแบบพื้นฐาน, คอมแพคท์, แมโคร, และไมโคร

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด pdf417 ใน C# – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยโหมดคอมแพคท์](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [วิธีสร้างบาร์โค้ด macro PDF417 ใน C# โดยใช้ Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}