---
category: general
date: 2026-10-15
description: วิธีอ่านรูปภาพบาร์โค้ดใน C# อย่างรวดเร็วโดยใช้ BarCodeReader. เรียนรู้การอ่านบาร์โค้ดหลายรายการและดูตัวอย่างเครื่องอ่านบาร์โค้ด
  C# ที่ทำงานร่วมกับ Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: th
lastmod: 2026-10-15
og_description: วิธีอ่านบาร์โค้ดใน C# ด้วย BarCodeReader. บทเรียนนี้แสดงตัวอย่างเครื่องอ่านบาร์โค้ด
  C# อย่างครบถ้วนที่รองรับหลายบาร์โค้ดและดึงข้อมูลเมตาดาต้า Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: วิธีอ่านบาร์โค้ดใน C# – ตัวอย่างขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีอ่านรูปภาพบาร์โค้ดใน C# – คู่มือเต็มตัวอย่าง
url: /th/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านรูปภาพบาร์โค้ดใน C# – คู่มือเต็มตัวอย่าง

หากคุณต้องการ **วิธีอ่านบาร์โค้ด** จากภาพในแอปพลิเคชัน .NET คู่มือนี้จะให้โซลูชันที่พร้อมรัน คุณจะได้เห็น **ตัวอย่างการอ่านบาร์โค้ดด้วย C#** ที่ทำงานกับสัญลักษณ์ Macro‑PDF417 และสามารถ **อ่านหลายบาร์โค้ด** จากภาพเดียวได้

การอ่านบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, การตรวจสอบตั๋ว, และการประมวลผลเอกสาร เมื่อจบบทเรียนนี้คุณจะสามารถ:

* เริ่มต้น `BarCodeReader` สำหรับรูปแบบที่รองรับทั้งหมด  
* ดึงข้อมูลพื้นฐานเช่น ประเภทโค้ดและข้อความที่ถอดรหัสได้  
* ดึงเมตาดาต้าเฉพาะของ Macro‑PDF417 (file ID, segment, checksum, …)  
* จัดการกับภาพที่มีหลายบาร์โค้ดโดยไม่ต้องเขียนโค้ดเพิ่ม

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* สภาพแวดล้อมการพัฒนา (Visual Studio 2022, VS Code, หรือ Rider)  
* แพ็กเกจ NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – ให้คลาส `BarCodeReader` ที่ใช้ในตัวอย่าง  
* ไฟล์ภาพที่มีบาร์โค้ด Macro‑PDF417 (เช่น `MacroPdf417.png`)  

คุณสามารถติดตั้งแพ็กเกจ NuGet ด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## วิธีอ่านบาร์โค้ดด้วย BarCodeReader ใน C#

แกนหลักของโซลูชันประกอบด้วยสี่ขั้นตอนสั้น ๆ แต่ครบถ้วน แต่ละขั้นตอนอยู่ในบล็อก `using` เพื่อรับประกันว่าทรัพยากรที่ไม่ได้จัดการจะถูกปล่อยออกอย่างทันท่วงที

### ขั้นตอน 1: เริ่มต้น `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**เหตุผลที่สำคัญ:**  
`BarCodeReader` รับพาธไฟล์และ `DecodeType` การระบุ `DecodeType.MacroPdf417` จะบอกไลบรารีให้มองหาเฉพาะสัญลักษณ์ Macro‑PDF417 ซึ่งช่วยเพิ่มความเร็วในการตรวจจับและลดผลบวกลบเท็จ

### ขั้นตอน 2: อ่านบาร์โค้ดทั้งหมดที่อยู่ในภาพ

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**เหตุผลที่สำคัญ:**  
เมธอด `ReadBarCodes()` คืนค่าเป็นอาเรย์ที่อาจมี `BarCodeResult` หนึ่งหรือหลายอ็อบเจกต์ นี่คือจุดที่ความสามารถ **อ่านหลายบาร์โค้ด** โดดเด่น – ไม่ต้องเขียนลูปแยกสำหรับแต่ละบาร์โค้ด

### ขั้นตอน 3: แสดงรายละเอียดพื้นฐานของบาร์โค้ด

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**เหตุผลที่สำคัญ:**  
`CodeTypeName` บอกว่าพบสัญลักษณ์ใด (เช่น “MacroPDF417”) ส่วน `CodeText` ถือข้อความที่ถอดรหัสได้ ฟิลด์สองนี้เป็นที่ใช้บ่อยที่สุดในตรรกะต่อไป

### ขั้นตอน 4: ดึงและแสดงเมตาดาต้าเฉพาะของ Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**เหตุผลที่สำคัญ:**  
Macro‑PDF417 ขยายรูปแบบ PDF417 ปกติด้วยเมตาดาต้าระดับเอกสาร การเข้าถึงคุณสมบัติ `Extended.Pdf417` จะให้ข้อมูลทั้งหมดที่จำเป็นสำหรับการสร้างไฟล์ต้นฉบับใหม่, ตรวจสอบความสมบูรณ์, หรือส่งต่อข้อมูลไปยังผู้รับที่เหมาะสม

### โปรแกรมเต็มที่สามารถรันได้

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่รวมสี่ขั้นตอนไว้ด้วยกัน คัดลอกโค้ดไปยังไฟล์ `.cs` ใหม่, ปรับ `imagePath` ให้ตรงกับไฟล์ของคุณ, แล้วรันด้วย `dotnet run`

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### ผลลัพธ์ที่คาดว่าจะได้บนคอนโซล

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

หากภาพมีสัญลักษณ์ Macro‑PDF417 มากกว่าหนึ่งตัว โปรแกรมจะพิมพ์บล็อกแยกสำหรับแต่ละบาร์โค้ด แสดงความสามารถ **อ่านหลายบาร์โค้ด** โดยไม่ต้องเขียนโค้ดเพิ่ม

## การจัดการกรณีขอบทั่วไป

| สถานการณ์ | วิธีทำ | เหตุผล |
|-----------|--------|--------|
| **ไฟล์ไม่พบ** | ห่อการสร้าง `BarCodeReader` ด้วย `try/catch (FileNotFoundException)` แล้วแสดงข้อความที่เป็นมิตร | ป้องกันแอปพลิเคชันหยุดทำงานและแจ้งผู้ใช้ว่าขาดไฟล์ |
| **ไม่พบบาร์โค้ด** | ตรวจสอบ `results.Length == 0` (ตามที่แสดงในโปรแกรมเต็ม) แล้วจัดการอย่างเหมาะสม | ให้ฟีดแบ็กชัดเจนเมื่อภาพไม่มีสัญลักษณ์ที่รองรับ |
| **ประเภทบาร์โค้ดต่างกัน** | เปลี่ยน `DecodeType.MacroPdf417` เป็น `DecodeType.AllSupportedTypes` หรือค่า enum เฉพาะอื่น | ทำให้โค้ดเดียวกันทำงานกับ QR, Code128, DataMatrix ฯลฯ พร้อมยังคงสนับสนุน **อ่านหลายบาร์โค้ด** |
| **ภาพขนาดใหญ่** | ตั้งค่า `reader.AutoSize = true` หรือย่อขนาดภาพก่อนส่งให้ reader | ปรับปรุงประสิทธิภาพและลดความกดดันของหน่วยความจำบน CLR |
| **การใช้งานแบบหลายเธรด** | สร้างอินสแตนซ์ `BarCodeReader` แยกสำหรับแต่ละเธรด; คลาสนี้ไม่ปลอดภัยต่อเธรด | ป้องกัน race condition ในสแกนเนอร์หลายเธรดหรือเว็บเซอร์วิส |

## เคล็ดลับขั้นสูงสำหรับโค้ดผลิตภัณฑ์

* **Dispose ทันที:** คำสั่ง `using` ทำให้ทรัพยากรเนทีฟ (เช่น บัฟเฟอร์ภาพ) ถูกปล่อยออกเร็ว ๆ ในบริการที่ทำงานต่อเนื่อง ควรปล่อย reader ทันทีหลังจากประมวลผลภาพเสร็จ  
* **Batch processing**

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}