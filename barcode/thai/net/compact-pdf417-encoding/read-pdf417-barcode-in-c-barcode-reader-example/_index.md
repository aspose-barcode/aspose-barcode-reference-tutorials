---
category: general
date: 2026-08-03
description: อ่านบาร์โค้ด PDF417 จากภาพโดยใช้ C# BarCodeReader – ตัวอย่างการอ่านบาร์โค้ดที่ครบถ้วนซึ่งยังแสดงวิธีการอ่านบาร์โค้ดหลายรายการด้วย
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: th
lastmod: 2026-08-03
og_description: อ่านบาร์โค้ด PDF417 อย่างรวดเร็วด้วยตัวอย่าง C# BarCodeReader. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อถอดรหัส
  macro PDF417 และอ่านบาร์โค้ดหลายรายการจากภาพ.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: อ่านบาร์โค้ด PDF417 ด้วย C# – ตัวอย่างเครื่องอ่านบาร์โค้ดครบวงจร
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: อ่านบาร์โค้ด PDF417 ด้วย C# – ตัวอย่างเครื่องอ่านบาร์โค้ด
url: /th/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านบาร์โค้ด PDF417 ใน C# – ตัวอย่างเครื่องอ่านบาร์โค้ด

หากคุณต้องการอ่านข้อมูลบาร์โค้ด PDF417 จากภาพ คู่มือนี้จะแสดงวิธีทำด้วยคลาส **BarCodeReader** ใน C# คุณจะได้เรียนรู้ตัวอย่างเครื่องอ่านบาร์โค้ดที่รองรับ macro PDF417 และสามารถอ่านบาร์โค้ดหลายรายการในภาพเดียว

การทำงานกับบาร์โค้ดมักหมายถึงการจัดการกับแหล่งภาพที่หลากหลาย สภาพแสงที่แตกต่างกัน และบางครั้งข้อมูลเชิงซ้อนเช่นส่วนของ macro PDF417 บทเรียนนี้ครอบคลุมทุกอย่างที่คุณต้องการเพื่อถอดรหัสบาร์โค้ด PDF417 ดึงฟิลด์ขยายของมัน และประมวลผลบาร์โค้ดหลายรายการจากรูปเดียวกัน เมื่อเสร็จสิ้นคุณจะได้โปรแกรมคอนโซลที่สามารถรันได้ซึ่งอ่านบาร์โค้ดจากไฟล์ภาพและพิมพ์ข้อมูลรายละเอียดลงในคอนโซล

## สิ่งที่คุณต้องมี

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่าได้ติดตั้งแล้ว  
* แพคเกจ NuGet **Aspose.BarCode for .NET** รุ่นล่าสุด (หรือไลบรารีที่เข้ากันได้ซึ่งให้ `BarCodeReader` และ `DecodeType.MacroPdf417`)  
* ไฟล์ภาพที่มีบาร์โค้ด PDF417 หรือ macro PDF417 (ตัวอย่างใช้ `ExtPDF417Meta.png`)  
* โปรแกรมแก้ไขโค้ดหรือ IDE เช่น Visual Studio 2022  

ไม่จำเป็นต้องใช้บริการเพิ่มเติมหรือ API ภายนอกใด ๆ

## การตั้งค่าโครงการสำหรับการอ่านบาร์โค้ด

1. **สร้างโครงการคอนโซลใหม่**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **เพิ่มไลบรารีบาร์โค้ด**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **คัดลอกภาพบาร์โค้ด**  

   วางไฟล์ `ExtPDF417Meta.png` (หรือภาพใด ๆ ที่มีบาร์โค้ด PDF417) ลงในโฟลเดอร์โครงการ  
   สำหรับบทเรียนนี้เราจะสมมติว่าไฟล์อยู่ที่ `YOUR_DIRECTORY/ExtPDF417Meta.png`

โครงการของคุณพร้อมสำหรับการคอมไพล์และรันตัวอย่างเครื่องอ่านบาร์โค้ดแล้ว

## วิธีอ่านบาร์โค้ด PDF417 ด้วย BarCodeReader

หัวใจของวิธีแก้คือบล็อก `using` ที่สร้างอินสแตนซ์ `BarCodeReader` ระบุ `DecodeType.MacroPdf417` และวนลูปผ่านบาร์โค้ดที่ตรวจพบทั้งหมด โค้ดต่อไปนี้เป็นโปรแกรมที่สมบูรณ์และเป็นอิสระซึ่งคุณสามารถวางลงในไฟล์ `Program.cs` ได้

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**เหตุผลที่ทำงานได้**:  

* `DecodeType.MacroPdf417` บอกให้ตัวอ่านมองหาส่วนขยาย macro ของ PDF417 ซึ่งบรรจุเมตาดาต้าเพิ่มเติมเช่นไฟล์ ID, จำนวนส่วน, และเวลาประทับ  
* คำสั่ง `using` รับประกันว่าทรัพยากรที่ไม่ได้จัดการ (เช่นไฟล์แฮนด์เดิล, บัฟเฟอร์การถอดรหัสแบบเนทีฟ) จะถูกปล่อยอย่างทันท่วงที  
* ลูป `foreach` จะประมวลผล **ทั้งหมด** ของบาร์โค้ดที่ภาพมีอยู่ ทำให้ตอบสนองต่อความต้องการ *อ่านบาร์โค้ดหลายรายการ*  

เมื่อคุณรันโปรแกรม (`dotnet run`) คุณควรเห็นผลลัพธ์คล้ายกับด้านล่าง:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

หากภาพมีบาร์โค้ด PDF417 มากกว่าหนึ่งรายการ ลูปจะพิมพ์บล็อกแยกต่างหากสำหรับแต่ละบาร์โค้ด ซึ่งแสดงวิธี **อ่านบาร์โค้ดหลายรายการ** จากรูปเดียว

## การอ่านบาร์โค้ดหลายรายการจากภาพเดียว

อินสแตนซ์ `BarCodeReader` เดียวกันสามารถถอดรหัสหลายประเภทบาร์โค้ดพร้อมกัน เพื่อขยายขอบเขตจาก macro PDF417 เพียงอย่างเดียวไปยัง PDF417 ใด ๆ (หรือแม้แต่ QR, Code128 ฯลฯ) ให้ปรับค่า `DecodeType` ดังนี้:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* เป็นบิตมาสก์ คุณจึงสามารถรวมรูปแบบที่สนับสนุนได้หลายแบบ ความยืดหยุ่นนี้ทำให้โค้ดส่วนนั้นเป็น **ตัวอย่างเครื่องอ่านบาร์โค้ด** ที่ทำงานได้กับกรณีการใช้งานที่หลากหลาย เช่น การสแกนฉลากสินค้า, ตั๋ว, หรือบัตรประจำตัว

## การเข้าถึงฟิลด์ macro PDF417 อย่างปลอดภัย

Macro PDF417 เพิ่มชุดคุณสมบัติเพิ่มเติมที่หลากหลาย อย่างไรก็ตาม ไม่ใช่บาร์โค้ดทุกอันจะมีฟิลด์ทั้งหมด การเข้าถึงคุณสมบัติที่ไม่มีอาจทำให้เกิด `NullReferenceException` วิธีที่ปลอดภัยที่สุดคือการตรวจสอบแต่ละคุณสมบัติก่อนพิมพ์:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*เหตุผลที่สำคัญ*: ในการใช้งานจริงคุณอาจได้รับบาร์โค้ด PDF417 ธรรมดาที่ไม่มีข้อมูล macro การตรวจสอบเชิงป้องกันทำให้แอปพลิเคชันของคุณทำงานต่อได้โดยไม่หยุดทำงาน

## ข้อผิดพลาดทั่วไปและแนวทางปฏิบัติที่ดีที่สุด

| ปัญหา | สาเหตุ | วิธีแก้แนะนำ |
|-------|--------|---------------|
| เส้นทางไฟล์ภาพไม่ถูกต้อง | `BarCodeReader` ขว้างข้อยกเว้นไฟล์ไม่พบก่อนทำการถอดรหัส | ใช้ `Path.Combine` และตรวจสอบไฟล์มีอยู่ด้วย `File.Exists` |
| ภาพความละเอียดต่ำ | ตัวถอดรหัสไม่สามารถหาขอบบาร์โค้ดได้ ส่งผลให้ตรวจจับไม่ได้ | ให้ความละเอียดขั้นต่ำที่ 300 dpi เพื่อผลลัพธ์ที่เชื่อถือได้ |
| บาร์โค้ดหมุน > 45° | ไลบรารีหลายตัวสมมติว่าบาร์โค้ดอยู่ในแนวตั้ง | เปิด `reader.RecognitionOptions.RotateImage = true` หากต้องการให้หมุนภาพ |

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณเอง

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}