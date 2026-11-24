---
category: general
date: 2026-11-23
description: เรียนรู้วิธีใช้ BarCodeReader ใน C# เพื่ออ่านบาร์โค้ดจากภาพ รวมถึงการถอดรหัส
  Macro PDF417 พร้อมตัวอย่างโค้ดเต็มและคำอธิบายที่ชัดเจน
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: th
lastmod: 2026-11-23
og_description: วิธีใช้ BarCodeReader ใน C# เพื่ออ่านบาร์โค้ดจากภาพ ทำตามคู่มือขั้นตอนนี้เพื่อถอดรหัส
  Macro PDF417 และรูปแบบอื่น ๆ พร้อมโค้ดที่พร้อมใช้งาน
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: วิธีใช้ BarCodeReader ใน C# – อ่านบาร์โค้ดจากภาพอย่างรวดเร็ว
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: วิธีใช้ BarCodeReader ใน C# เพื่ออ่านบาร์โค้ดจากภาพ
url: /th/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ BarCodeReader ใน C# เพื่ออ่านบาร์โค้ดจากรูปภาพ

หากคุณต้องการ **วิธีใช้ BarCodeReader** สำหรับการสแกนบาร์โค้ดอย่างรวดเร็ว คำแนะนำนี้จะแสดงให้คุณเห็นอย่างชัดเจน ไม่ว่าคุณจะกำลังสร้างระบบจุดขาย (POS) หรือทำระบบอัตโนมัติสำหรับรับเอกสาร คุณจะได้เรียนรู้วิธีอ่านบาร์โค้ดจากโครงการ C# ด้วยเพียงไม่กี่บรรทัดของโค้ด

ในบทเรียนนี้คุณจะได้เห็นตัวอย่างที่ทำงานได้เต็มรูปแบบ ซึ่งทำการถอดรหัสบาร์โค้ด Macro PDF417, ดึงคุณสมบัติเพิ่มเติม, และพิมพ์ข้อมูลที่เป็นประโยชน์ลงคอนโซล ไม่ต้องอ้างอิงเอกสารภายนอก – ทุกอย่างที่คุณต้องการอยู่ที่นี่แล้ว

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 (หรือใหม่กว่า) ติดตั้งแล้ว – โค้ดนี้ตั้งเป้าหมายที่เวอร์ชัน LTS ล่าสุด
* การอ้างอิงไปยังแพคเกจ NuGet **Aspose.BarCode** (หรือแพคเกจที่เข้ากันได้) ที่ให้ `BarCodeReader`
* ไฟล์รูปภาพที่มีบาร์โค้ด Macro PDF417 (ตัวอย่างใช้ `ExtPDF417Meta.png`)

> **เคล็ดลับ:** หากคุณใช้ Visual Studio ให้เพิ่มแพคเกจผ่านคำสั่ง `dotnet add package Aspose.BarCode` หรือผ่าน NuGet Package Manager UI

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ BarCodeReader

สิ่งแรกที่ทำเมื่อทำงานกับไลบรารีบาร์โค้ดคือสร้างอ็อบเจ็กต์รีดเดอร์ที่ชี้ไปยังรูปภาพต้นฉบับและบอก API ว่าต้องการค้นหาประเภทบาร์โค้ดใด

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*เหตุผลที่ขั้นตอนนี้สำคัญ:*  
`BarCodeReader` จะเปิดรูปภาพ, จัดสรรหน่วยความจำแบบเนทีฟ, และเตรียมอัลกอริทึมการถอดรหัสสำหรับ `DecodeType` ที่ระบุ การจำกัดประเภทเป็น `MacroPdf417` จะช่วยลดภาระการใช้ CPU และเพิ่มความแม่นยำในการตรวจจับ

## ขั้นตอนที่ 2: อ่านบาร์โค้ดทั้งหมดที่พบในรูปภาพ

รูปภาพเดียวอาจมีบาร์โค้ดหลายรายการ โดยเฉพาะเมื่อข้อมูลถูกเข้ารหัสแบบแมโคร วิธี `ReadBarCodes` จะคืนค่าเป็น enumerable ของอ็อบเจ็กต์ `BarCodeResult` ซึ่งแต่ละอ็อบเจ็กต์แทนบาร์โค้ดที่ตรวจพบหนึ่งรายการ

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*เหตุผลที่ขั้นตอนนี้สำคัญ:*  
การวนลูปผ่านคอลเลกชันทำให้คุณจับทุกกรณีได้ ซึ่งเป็นสิ่งจำเป็นสำหรับการประมวลผลแบบแบตช์หรือเมื่อเอกสารฝังบาร์โค้ดหลายรายการ

## ขั้นตอนที่ 3: เข้าถึงคุณสมบัติเพิ่มเติมของ Macro PDF417

Macro PDF417 เก็บเมตาดาต้าเพิ่มเติม เช่น ตัวระบุไฟล์, หมายเลขส่วน, และจำนวนส่วนทั้งหมด ค่าต่าง ๆ นี้เปิดให้เข้าถึงผ่านคุณสมบัติ `Extended.Pdf417` ของ `BarCodeResult`

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*เหตุผลที่ขั้นตอนนี้สำคัญ:*  
ฟิลด์เพิ่มเติมช่วยให้คุณประกอบเอกสารหลายส่วนหรือยืนยันว่าทุกส่วนมาจากแหล่งเดียวกัน การข้ามขั้นตอนนี้จะทำให้คุณได้เพียงข้อความดิบโดยสูญเสียบริบทที่สำคัญ

## ขั้นตอนที่ 4: แสดงข้อมูลที่เป็นประโยชน์ที่สุด

สุดท้ายให้เขียนข้อมูลลงคอนโซล (หรือ logger ใด ๆ) เพื่อให้คุณตรวจสอบผลการอ่าน ตัวอย่างจะพิมพ์ประเภทโค้ด, ข้อความที่ถอดรหัส, และหลายฟิลด์ของแมโคร

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**ผลลัพธ์คอนโซลที่คาดหวัง**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **หมายเหตุ:** หากรูปภาพไม่มีบาร์โค้ด Macro PDF417, `ReadBarCodes()` จะคืนคอลเลกชันว่างและลูปจะไม่ทำงาน ควรตรวจสอบผลลัพธ์ที่ว่างเปล่าในโค้ดการผลิตเสมอ

## อ่านบาร์โค้ดจากรูปภาพใน C# – การจัดการสถานการณ์ทั่วไป

### 1. ถอดรหัสหลายรูปแบบบาร์โค้ด

หากต้องการตรวจจับมากกว่าหนึ่งรูปแบบ ให้ส่งค่า `DecodeType` ที่รวมหลายประเภทเข้าด้วยกัน:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. จัดการรูปภาพขนาดใหญ่

รูปภาพขนาดใหญ่สามารถทำให้ใช้หน่วยความจำสูงได้ ให้ลดขนาดรูปภาพก่อนส่งให้รีดเดอร์:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. การจัดการข้อผิดพลาด

ห่อหุ้มตรรกะการอ่านด้วยบล็อก try‑catch เพื่อให้เห็นข้อผิดพลาดการถอดรหัส:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## ตัวอย่างทำงานเต็มรูปแบบ

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก, วาง, และรันได้ รวมทุกขั้นตอน, คำสั่ง `using` ที่จำเป็น, และโครงสร้างการจัดการข้อผิดพลาดอย่างง่าย

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**การรันโปรแกรม** จะพิมพ์บาร์โค้ด Macro PDF417 ที่ตรวจพบแต่ละรายการพร้อมฟิลด์แมโครที่ขยายออกมา หรือแจ้งว่ไม่พบบาร์โค้ดใด ๆ

## สรุป

ตอนนี้คุณรู้ **วิธีใช้ BarCodeReader** เพื่ออ่านบาร์โค้ดจากแอปพลิเคชัน C# รวมถึงการดึงเมตาดาต้า Macro PDF417 แล้ว โซลูชันนี้ครอบคลุมการเริ่มต้น, การวนลูป, การเข้าถึงคุณสมบัติเพิ่มเติม, และเคล็ดลับการจัดการหลายรูปแบบ, รูปภาพขนาดใหญ่, และข้อผิดพลาด

ต่อไปคุณอาจสนใจสำรวจ:

* **การอ่าน QR code** – แทนที่ `DecodeType.MacroPdf417` ด้วย `DecodeType.QR`
* **การบันทึกข้อมูลที่ถอดรหัส** ลงฐานข้อมูลหรือไฟล์ JSON เพื่อการประมวลผลต่อไป
* **การผสานกับ ASP.NET Core** เพื่อรับรูปภาพอัปโหลดผ่าน Web API

ลองทดลองกับประเภทบาร์โค้ดและแหล่งรูปภาพต่าง ๆ ได้เลย ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}