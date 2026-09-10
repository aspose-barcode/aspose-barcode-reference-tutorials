---
category: general
date: 2026-07-27
description: วิธีอ่านบาร์โค้ด PDF417 ใน C# อย่างรวดเร็ว เรียนรู้การอ่านหลายบาร์โค้ด
  ถอดรหัสภาพ และรับข้อมูลเมตาดาต้า Macro PDF417 ในตัวอย่างบาร์โค้ด C# ฉบับเต็ม.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: th
lastmod: 2026-07-27
og_description: วิธีอ่านบาร์โค้ด PDF417 ด้วย C# ด้วยคู่มือขั้นตอนต่อขั้นตอนนี้ ถอดรหัสภาพ
  จัดการบาร์โค้ดหลายรายการ และดึงข้อมูลเมตาดาต้า Macro PDF417 ในตัวอย่างที่พร้อมใช้งาน.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: วิธีอ่าน PDF417 ใน C# – ตัวอย่างบาร์โค้ดเต็ม
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: วิธีอ่าน PDF417 ด้วย C# – ตัวอย่างบาร์โค้ดครบถ้วน
url: /th/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่าน PDF417 ใน C# – ตัวอย่างบาร์โค้ดเต็ม

เคยสงสัย **วิธีอ่าน PDF417** บาร์โค้ดในแอปพลิเคชัน C# โดยไม่ต้องบิดหัวของคุณไหม? คุณไม่ได้เป็นคนเดียว ไม่ว่าคุณจะกำลังสร้างสแกนเนอร์โลจิสติกส์, ตัวตรวจสอบตั๋ว, หรือแค่ต้องดึงข้อมูลจากบัตรประจำตัวที่เข้ารหัสด้วย PDF417 กระบวนการอาจดูลึกลับในตอนแรก  

ในบทแนะนำนี้เราจะพาไปผ่าน **ตัวอย่างบาร์โค้ด c#** ที่อ่านภาพ PDF417, จัดการกับ **การอ่านหลายบาร์โค้ด** หากมี, และสกัดข้อมูลเมตาดาต้า Macro PDF417 ที่เป็นประโยชน์ทั้งหมดที่คุณอาจต้องการ  

## สิ่งที่คุณจะสร้าง

เมื่อทำตามคำแนะนำนี้เสร็จแล้ว คุณจะมีโปรแกรมคอนโซลขนาดเล็กที่:

1. โหลดภาพบาร์โค้ดจากดิสก์  
2. ถอดรหัส **PDF417** (รวมถึง Macro PDF417)  
3. พิมพ์ข้อมูลพื้นฐานเช่นประเภทโค้ดและข้อความ  
4. แสดงชุดฟิลด์ Macro PDF417 ทั้งหมด (File ID, Segment ID, Checksum ฯลฯ)  

ไม่มีบริการภายนอก เพียงแพ็กเกจ NuGet เดียวและไม่กี่บรรทัดของ C#  

## ข้อกำหนดเบื้องต้น – สิ่งที่คุณต้องมีก่อนเริ่ม

- **.NET 6.0** หรือใหม่กว่า (โค้ดทำงานบน .NET Framework 4.6+ ด้วยเช่นกัน)  
- เวอร์ชันล่าสุดของไลบรารี **Aspose.BarCode for .NET** – ติดตั้งผ่าน NuGet (`Install-Package Aspose.BarCode`)  
- ไฟล์รูปภาพที่มีบาร์โค้ด PDF417 (ตัวอย่างใช้ `ExtPDF417Meta.png`)  
- ความเข้าใจพื้นฐานเกี่ยวกับแอปคอนโซล C# (หากคุณเคยเขียน “Hello World” ก็พร้อมแล้ว)  

> **เคล็ดลับ:** หากคุณไม่มีตัวอย่าง PDF417 อยู่ในมือ, ให้สร้างหนึ่งบนเว็บไซต์สาธิตของ Aspose หรือใช้แอปบนสมาร์ทโฟนที่สามารถสร้างแท็ก PDF417 ได้  

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และติดตั้งไลบรารี

ขั้นแรก, สร้างโปรเจกต์คอนโซลใหม่:  

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

นี่จะดึง dependencies ของ **ตัวอย่างบาร์โค้ด c#** ที่เราต้องการ. เปิดไฟล์ `Program.cs` และแทนที่โค้ดเริ่มต้นด้วยโครงสร้างด้านล่าง:  

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## ขั้นตอนที่ 2: เริ่มต้น BarCodeReader สำหรับ PDF417

หัวใจของโซลูชันคือคลาส `BarCodeReader`. เราบอกให้มันสแกนไฟล์ใดและประเภทบาร์โค้ดที่เราต้องการ—ในกรณีนี้คือ `DecodeType.Pdf417` หรือรูปแบบแมโคร `DecodeType.MacroPdf417`. การใช้ประเภทแมโครทำให้เราจับฟิลด์ขยายได้  

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

ทำไมต้องใช้ `MacroPdf417` แทน `Pdf417` ธรรมดา? Macro PDF417 มีเมตาดาต้าเพิ่มเติม (File ID, Segment Count, Timestamps ฯลฯ) ที่หลายแอปพลิเคชันจริงพึ่งพา—เช่น รายการจัดส่งที่แบ่งเป็นหลายหน้า  

## ขั้นตอนที่ 3: อ่านบาร์โค้ดทั้งหมดที่พบในภาพ

ภาพเดียวอาจมี **การอ่านหลายบาร์โค้ด**—เช่น QR code อยู่ข้างๆ PDF417. เมธอด `ReadBarCodes()` จะคืนค่า `IEnumerable<BarCodeResult>` ที่เราสามารถวนลูปได้  

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

หากภาพมีเพียง PDF417 เดียว, ลูปก็ยังทำงานหนึ่งครั้ง, ทำให้โค้ดยืดหยุ่นสำหรับสถานการณ์ในอนาคตที่คุณอาจต้อง **อ่านหลายบาร์โค้ด** จากการสแกนเดียวกัน  

## ขั้นตอนที่ 4: แสดงข้อมูลพื้นฐานของบาร์โค้ด

ก่อนจะลงลึกในฟิลด์แมโคร, การแสดงประเภทบาร์โค้ดและข้อความที่ถอดรหัสเป็นประโยชน์. นี้ช่วยให้คุณตรวจสอบว่าตัวอ่านได้จำแนก PDF417 จริงหรือไม่, แทนสัญลักษณ์อื่น  

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` จะอ่านเป็น *MacroPdf417* (หรือ *Pdf417* หากไม่ได้ตั้งค่าแฟล็กแมโคร), ส่วน `CodeText` มีข้อมูลดิบที่เข้ารหัสในบาร์โค้ด  

## ขั้นตอนที่ 5: สกัดเมตาดาต้า Macro PDF417

พร็อพเพอร์ตี้ `Extended` ให้คุณเจาะลึกโครงสร้างเฉพาะของ PDF417. ทุกฟิลด์ที่เราพิมพ์ด้านล่างสอดคล้องโดยตรงกับสเปคแมโครของ PDF417  

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

- **FileID** – ตัวระบุที่ไม่ซ้ำสำหรับชุดเอกสารทั้งหมด  
- **SegmentID** – ส่วนของไฟล์หลายส่วนที่คุณกำลังดู  
- **SegmentsCount** – จำนวนส่วนทั้งหมดที่คาดว่าจะมี  
- **FileName**, **Checksum**, **FileSize** – มีประโยชน์สำหรับตรวจสอบความสมบูรณ์ของไฟล์ที่ถ่ายโอน  
- **TimeStamp**, **Addressee**, **Sender** – ฟิลด์ทางเลือกที่ระบบโลจิสติกส์หลายระบบฝังไว้  

หากฟิลด์ใดขาดหายจากบาร์โค้ดต้นฉบับ, ไลบรารีจะคืนค่า `null` หรือ `0`, ซึ่งคุณสามารถจัดการตามต้องการ  

## ขั้นตอนที่ 6: รันตัวอย่างเต็มรูปแบบ

รวมทุกส่วนเข้าด้วยกัน นี่คือโปรแกรมเต็มที่พร้อมรัน:  

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อคุณรันโปรแกรมกับไฟล์ `ExtPDF417Meta.png` ที่ถูกต้อง, คุณควรเห็นผลลัพธ์คล้ายกับ:  

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

หากภาพมีบาร์โค้ดมากกว่าหนึ่งรายการ,  

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณ  

- [วิธีสร้างบาร์โค้ด PDF417 – การเข้ารหัส Compact PDF417](/barcode/english/net/compact-pdf417-encoding/)  
- [วิธีสร้างบาร์โค้ด – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [วิธีอ่านบาร์โค้ด DataMatrix ด้วย Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}