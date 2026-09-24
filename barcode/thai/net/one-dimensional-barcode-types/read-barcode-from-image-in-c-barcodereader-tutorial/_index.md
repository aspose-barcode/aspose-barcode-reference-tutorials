---
category: general
date: 2026-08-15
description: อ่านบาร์โค้ดจากภาพใน C# ด้วย BarCodeReader. เรียนรู้วิธีอ่านบาร์โค้ดหลายรายการใน
  C#, อ่านบาร์โค้ด PDF417, และดูตัวอย่างเต็มของ BarCodeReader ใน C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: th
lastmod: 2026-08-15
og_description: อ่านบาร์โค้ดจากภาพใน C# ด้วยคู่มือขั้นตอนต่อขั้นตอน ค้นพบวิธีอ่านบาร์โค้ดหลายรายการใน
  C# ถอดรหัสสัญลักษณ์ PDF417 และรันตัวอย่าง BarCodeReader ของ C# อย่างครบถ้วน
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: อ่านบาร์โค้ดจากภาพใน C# – บทเรียน BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: อ่านบาร์โค้ดจากภาพใน C# – บทแนะนำ BarCodeReader
url: /th/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านบาร์โค้ดจากรูปภาพใน C# – บทแนะนำ BarCodeReader

หากคุณต้องการ **อ่านบาร์โค้ดจากรูปภาพ ** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงวิธีทำโดยใช้คลาส `BarCodeReader` อย่างละเอียด คุณยังจะได้เห็นวิธี **อ่านบาร์โค้ดหลายรายการใน C#**, การถอดรหัสสัญลักษณ์ PDF417, และตัวอย่าง **C# BarCodeReader** ที่คุณสามารถคัดลอกไปใช้ในโปรเจกต์ของคุณได้

บทแนะนำครอบคลุมทุกขั้นตอน — ตั้งแต่การเพิ่มแพ็กเกจ NuGet ที่จำเป็นจนถึงการพิมพ์ฟิลด์ PDF417 ที่ขยาย — เพื่อให้คุณได้โปรแกรมคอนโซลที่ทำงานได้ครบถ้วน ไม่ต้องอ้างอิงเอกสารภายนอก; โค้ดและคำอธิบายทั้งหมดรวมอยู่ที่นี่

## สิ่งที่คุณต้องมี

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า (โค้ดทำงานได้กับ .NET Core และ .NET Framework)
* Visual Studio 2022 หรือเครื่องมือแก้ไขที่รองรับ C#
* แพ็กเกจ NuGet `Aspose.BarCode` (หรือไลบรารีที่ให้ `BarCodeReader` เทียบเท่า)
* ไฟล์รูปภาพที่มีบาร์โค้ด Macro PDF417 (เช่น `ExtPDF417Meta.png`)

การมีสิ่งเหล่านี้จะทำให้ตัวอย่างคอมไพล์ได้โดยไม่ต้องตั้งค่าเพิ่มเติม

## อ่านบาร์โค้ดจากรูปภาพด้วย BarCodeReader

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarCodeReader` ที่ชี้ไปยังไฟล์รูปภาพและบอกไลบรารีว่าต้องการค้นหาประเภทบาร์โค้ดใด

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**ทำไมวิธีนี้ถึงได้ผล:**  
`BarCodeReader` จะเปิดรูปภาพ, สแกนหาประเภท `DecodeType` ที่ระบุ, แล้วคืนคอลเลกชันของอ็อบเจ็กต์ `BarCodeResult` แต่ละรายการจะมีข้อมูลบาร์โค้ดทั่วไป (`CodeTypeName`, `CodeText`) และสำหรับ Macro PDF417 จะมีอ็อบเจ็กต์ `Extended.Pdf417` ที่เปิดเผยฟิลด์เพิ่มเติมทั้งหมดตามมาตรฐาน

## อ่านบาร์โค้ดหลายรายการใน C# จากรูปเดียว

บางครั้งรูปภาพอาจมีบาร์โค้ดมากกว่าหนึ่งรายการ (เช่น QR code อยู่ข้างๆ PDF417) เพื่อจัดการสถานการณ์นี้ เพียงละเว้นการระบุ `DecodeType` อย่างชัดเจนหรือส่งค่า `DecodeType.AllSupported` แล้ววนลูปผลลัพธ์

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**เหตุผลที่ต้องทำเช่นนี้:**  
การระบุ `AllSupported` จะบอกเอนจินให้ลองทุกรูปแบบบาร์โค้ดที่รู้จัก, ซึ่งรับประกันว่าคุณจะจับสัญลักษณ์ทั้งหมดในภาพได้ วิธีนี้เป็นแนวทางแนะนำเมื่อคุณไม่สามารถคาดการณ์ประเภทบาร์โค้ดล่วงหน้าได้

## วิธีอ่านบาร์โค้ด PDF417 ด้วย C#

หากคุณต้องการเพียงรูปแบบ PDF417 แบบคลาสสิก (ไม่ใช่ macro) ให้เปลี่ยน `DecodeType` เป็น `Pdf417` โค้ดส่วนที่เหลือคงเดิม ยกเว้นฟิลด์ที่ขยายจะไม่ปรากฏ

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**ทำไมจึงสำคัญ:**  
PDF417 แบบคลาสสิกไม่เปิดเผยคุณสมบัติเฉพาะ macro, ดังนั้นบล็อก `Extended.Pdf417` จึงไม่จำเป็น การใช้ `DecodeType` ที่แม่นยำยังช่วยเร่งความเร็วการสแกน เพราะไลบรารีข้ามอัลกอริทึมที่ไม่รองรับ

## ตัวอย่างเต็ม C# BarCodeReader ที่คุณสามารถคัดลอกได้

ด้านล่างเป็นโปรแกรมเต็มที่รวมสามสถานการณ์ไว้ในแอปพลิเคชันคอนโซลที่ง่ายต่อการรัน แทนที่ `YOUR_DIRECTORY/ExtPDF417Meta.png` ด้วยพาธจริงของรูปภาพของคุณ

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อรูปภาพตัวอย่างมีบาร์โค้ด Macro PDF417 คอนโซลจะพิมพ์ข้อความคล้ายกับนี้:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

หากรูปภาพมีเพียง PDF417 ปกติ ส่วน “Macro PDF417” จะว่างเปล่า และส่วน “Classic PDF417” จะแสดงข้อความที่ถอดรหัสได้

## สรุป

ตอนนี้คุณรู้วิธี **อ่านบาร์โค้ดจากรูปภาพ** ใน C# ด้วย `BarCodeReader`, วิธี **อ่านบาร์โค้ดหลายรายการใน C#** จากไฟล์เดียว, และขั้นตอนที่แน่นอนในการ **อ่านบาร์โค้ด PDF417** — ทั้งแบบ macro และแบบคลาสสิก ตัวอย่าง **C# BarCodeReader** เต็มรูปแบบพร้อมคัดลอกไปใช้ในโปรเจกต์ .NET ใดก็ได้ และคุณสามารถขยายให้รองรับรูปแบบอื่นหรือรวมเข้ากับ pipeline การประมวลผลภาพที่ใหญ่ขึ้นได้

**ขั้นตอนต่อไป**

* สำรวจรูปแบบการจัดการข้อผิดพลาดเช่น `try / catch` รอบบล็อก reader  
* ทดลองใช้วัตถุ `ReaderParameters` เพื่อปรับความเร็วและความแม่นยำของการตรวจจับ  
* รวมการอ่านบาร์โค้ดกับไลบรารีการเตรียมรูปภาพ (


## คุณควรเรียนรู้อะไรต่อไป?


บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่นในโครงการของคุณ

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}