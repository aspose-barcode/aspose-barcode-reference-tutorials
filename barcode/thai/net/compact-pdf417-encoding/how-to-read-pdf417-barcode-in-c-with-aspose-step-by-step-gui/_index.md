---
category: general
date: 2026-10-24
description: เรียนรู้วิธีอ่านบาร์โค้ด PDF417 ใน C# ด้วย Aspose.BarCode บทเรียนนี้ครอบคลุมการอ่านภาพบาร์โค้ด
  การสกัดฟิลด์ Macro PDF417 และการจัดการกับสถานการณ์ทั่วไป
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: th
lastmod: 2026-10-24
og_description: วิธีอ่านบาร์โค้ด PDF417 ใน C# ด้วย Aspose.BarCode. ตามบทแนะนำเต็มรูปแบบนี้เพื่อถอดรหัสภาพ,
  ดึงข้อมูลเมตาดาต้า Macro PDF417, และหลีกเลี่ยงข้อผิดพลาดทั่วไป.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: วิธีอ่านบาร์โค้ด PDF417 ด้วย C# และ Aspose – คู่มือเต็ม
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: วิธีอ่านบาร์โค้ด PDF417 ด้วย C# และ Aspose – คู่มือแบบขั้นตอนต่อขั้นตอน
url: /th/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านบาร์โค้ด PDF417 ใน C# ด้วย Aspose – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **วิธีอ่านบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าการอ่านบาร์โค้ด PDF417 ใน C# ด้วยไลบรารี Aspose.BarCode ทำอย่างไร ไม่ว่าคุณจะกำลังประมวลผลเอกสารที่สแกน, การจับภาพจากมือถือ, หรือภาพที่นำเข้าเป็นชุด, โค้ดด้านล่างจะถอดรหัสบาร์โค้ดและดึงคุณสมบัติ Macro PDF417 ทุกอย่างที่คุณอาจต้องการ

การอ่านภาพบาร์โค้ดใน C# อาจรู้สึกท้าทาย โดยเฉพาะเมื่อบาร์โค้ดมีเมตาดาต้าเพิ่มเติม บทเรียนนี้ขจัดความสับสนโดยให้ตัวอย่างที่ทำงานได้เต็มรูปแบบ พร้อมอธิบายแต่ละบรรทัดและครอบคลุมกรณีขอบเช่นส่วนแมโครที่หายไปหรือภาพเสียหาย เมื่อเสร็จสิ้นคุณจะสามารถผสานการถอดรหัส PDF417 เข้าไปในโปรเจกต์ C# ใด ๆ ได้อย่างมั่นใจ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)  
* ไลเซนส์หรือการทดลองใช้งานฟรีของ **Aspose.BarCode for .NET** – คุณสามารถรับคีย์ชั่วคราวจากเว็บไซต์ Aspose  
* ไฟล์ภาพที่มีบาร์โค้ด Macro PDF417 (เช่น `ExtPDF417Meta.png`)

> **เคล็ดลับ:** หากคุณต้องการทดลองเท่านั้น Aspose มีรุ่นทดลอง 30 วันที่ให้ฟังก์ชันเต็มสำหรับการอ่านบาร์โค้ด

## ขั้นตอนที่ 1: ติดตั้งแพ็กเกจ NuGet ของ Aspose.BarCode

เปิดโฟลเดอร์โปรเจกต์ของคุณในเทอร์มินัลและรัน:

```bash
dotnet add package Aspose.BarCode
```

แพ็กเกจนี้จะเพิ่มเนมสเปซ `Aspose.BarCode.ReadRecognition` ซึ่งประกอบด้วยคลาส `BarCodeReader` ที่ใช้ในการถอดรหัสภาพ

## ขั้นตอนที่ 2: สร้าง BarCodeReader สำหรับภาพ PDF417

คอนสตรัคเตอร์ของ `BarCodeReader` รับอาร์กิวเมนต์สองค่า: เส้นทางไปยังไฟล์ภาพและ `DecodeType` ที่คุณต้องการระบุ การระบุ `DecodeType.MacroPdf417` จะบอก Aspose ให้มองหา Symbol Macro PDF417 และเติมคุณสมบัติเพิ่มเติมโดยอัตโนมัติ

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### ทำไมต้องใช้ `DecodeType.MacroPdf417`?

* **Macro PDF417** เก็บฟิลด์เพิ่มเติม (ไฟล์ ID, จำนวนส่วน, เวลา, ฯลฯ) ที่ไม่ได้อยู่ใน PDF417 มาตรฐาน  
* คุณสมบัติ `Extended` ของ `BarCodeResult` จะถูกเติมค่าเฉพาะเมื่อคุณร้องขอประเภทแมโคร ช่วยลดขั้นตอนการพาร์สแยกออก

## ขั้นตอนที่ 3: วนลูปผ่านบาร์โค้ดที่ตรวจพบทั้งหมด

ภาพเดียวอาจมี Symbol PDF417 หลายตัว (เช่น เมื่อเอกสารถูกแบ่งเป็นหลายหน้า) เมธอด `ReadBarCodes()` จะคืนค่า `IEnumerable<BarCodeResult>` ที่คุณสามารถวนลูปได้

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

หากภาพไม่มีบาร์โค้ดใดเลย ลูปจะไม่ทำงานและโปรแกรมจะออกอย่างเรียบร้อย พฤติกรรมนี้ทำให้โค้ดปลอดภัยสำหรับการประมวลผลเป็นชุดที่บางไฟล์อาจไม่มีบาร์โค้ด

## ขั้นตอนที่ 4: แสดงคุณสมบัติขยายของ Macro PDF417

คุณสมบัติ `Extended.Pdf417` จะรวมฟิลด์เฉพาะแมโครทั้งหมด แต่ละฟิลด์สอดคล้องกับสเปค PDF417 คุณจึงสามารถบันทึกลงฐานข้อมูล, เขียนบันทึก, หรือใช้สำหรับการตรวจสอบต่อไป

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### ความหมายของแต่ละคุณสมบัติ

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | ตัวระบุที่ไม่ซ้ำสำหรับเอกสารหลายส่วนทั้งหมด |
| **MacroPdf417SegmentID** | ดัชนีของส่วนปัจจุบัน (เริ่มจาก 0) |
| **MacroPdf417SegmentsCount** | จำนวนส่วนทั้งหมดที่เป็นส่วนของไฟล์ |
| **MacroPdf417FileName** | ชื่อไฟล์ที่ฝังอยู่ในบาร์โค้ด (เป็นตัวเลือก) |
| **MacroPdf417Checksum** | ค่า CRC‑16 checksum ของบล็อกข้อมูลแมโคร |
| **MacroPdf417FileSize** | ขนาดไฟล์ต้นฉบับเป็นไบต์ |
| **MacroPdf417TimeStamp** | เวลาที่บาร์โค้ดแมโครถูกสร้าง |
| **MacroPdf417Addressee** | ผู้รับเอกสารที่ตั้งใจ |
| **MacroPdf417Sender** | ผู้ส่งเอกสาร |
| **MacroPdf417Terminator** | ธง Terminator แสดงจุดสิ้นสุดของลำดับแมโคร |

ฟิลด์เหล่านี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องทำการประกอบ PDF หรือภาพขนาดใหญ่ที่ถูกแบ่งเป็น Symbol PDF417 หลายตัวเพื่อพิมพ์บนสื่อความละเอียดต่ำ

## ขั้นตอนที่ 5: จัดการกับกรณีขอบทั่วไป

### ฟิลด์แมโครหายไป

บางครั้งบาร์โค้ด PDF417 ถูกสร้างโดยไม่มีฟิลด์แมโครเลือกใช้ การเข้าถึงคุณสมบัติที่หายไปจะคืนค่า `null` หรือ `0` ตรวจสอบให้ดีหากคุณจะบันทึกค่าเหล่านี้:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### ภาพเสียหายหรือคุณภาพต่ำ

หากภาพเบลอ คุณสามารถปรับปรุงการตรวจจับได้โดยเปิดใช้งานตัวเลือกคุณภาพของ `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

การตั้งค่าเหล่านี้เป็นทางเลือก แต่สามารถเพิ่มอัตราความสำเร็จอย่างมากสำหรับเอกสารที่สแกน

### มีหลายรูปแบบบาร์โค้ดในภาพเดียว

หากคุณสงสัยว่ามีประเภทบาร์โค้ดอื่นอยู่ในภาพ ให้ใช้ `DecodeType.AllSupported` แล้วกรองผลลัพธ์:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## ตัวอย่างที่ทำงานได้เต็มรูปแบบ

คัดลอกโปรแกรมต่อไปนี้ไปยังโปรเจกต์คอนโซลใหม่ (`dotnet new console`) แล้วรัน แทนที่ตัวแปร `imagePath` ด้วยตำแหน่งของภาพ Macro PDF417 ของคุณ

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง** (ค่าจะแตกต่างตามภาพของคุณ):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

หากภาพไม่มี Symbol Macro PDF417 โปรแกรมจะไม่แสดงอะไรและออกอย่างเงียบ—เหมาะสำหรับงานแบชที่ต้องประมวลผลไฟล์จำนวนมาก

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถอ่าน PDF417 มาตรฐาน (ไม่ใช่แมโคร) ด้วยโค้ดเดียวกันได้หรือไม่?**  
ตอบ: ได้ เพียงเปลี่ยน `DecodeType.MacroPdf417` เป็น `DecodeType.Pdf417` คุณสมบัติ `Extended` จะว่างเปล่า แต่ `CodeText` และ `CodeTypeName` ยังคงใช้งานได้

**ถาม: Aspose.BarCode รองรับการอ่านจากสตรีมแทนเส้นทางไฟล์หรือไม่?**  
ตอบ: แน่นอน ใช้โอเวอร์โหลด `new BarCodeReader(Stream, DecodeType)` แล้วส่ง `FileStream` หรือ `MemoryStream` ให้กับมัน วิธีนี้มีประโยชน์เมื่อภาพมาจาก Web API

**ถาม: ฉันจะตรวจสอบ checksum ได้อย่างไร?**  
ตอบ: ฟิลด์ `MacroPdf417Checksum` มีค่า CRC‑16 ดิบ คุณสามารถคำนวณ checksum ใหม่บนไฟล์ที่ประกอบแล้วแล้วเปรียบเทียบเพื่อยืนยันความสมบูรณ์ของข้อมูล

## ขั้นตอนต่อไปและหัวข้อที่เกี่ยวข้อง

* **เขียนบาร์โค้ด PDF417** – สำรวจ `BarCodeGenerator` เพื่อสร้างบาร์โค้ดแมโครสำหรับการทดสอบ  
* **รวมหลายส่วน** – หลังจากอ่านทุกส่วนแล้ว ให้จัดเรียงตาม `MacroPdf417SegmentID` แล้วต่อ `CodeText` เพื่อสร้าง payload ดั้งเดิม  
* **ปรับประสิทธิภาพ** – สำหรับสถานการณ์ที่ต้องประมวลผลจำนวนมาก ให้ใช้อินสแตนซ์ `BarCodeReader` ตัวเดียวกันหลายภาพและ

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}