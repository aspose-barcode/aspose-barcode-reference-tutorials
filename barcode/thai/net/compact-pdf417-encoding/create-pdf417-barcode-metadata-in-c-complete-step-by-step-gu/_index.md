---
category: general
date: 2026-09-28
description: สร้าง PDF417 Barcode Metadata ใน C# ด้วย Aspose.BarCode คู่มือนี้แสดงการตั้งค่าทั้งหมดที่คุณต้องใช้เพื่อฝัง
  file‑ID, timestamps, และอื่น ๆ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode metadata
- increase barcode resolution
- macro pdf417 c#
- aspose barcode c#
- barcode metadata fields
lastmod: 2026-09-28
og_description: เรียนรู้วิธีสร้าง PDF417 Barcode Metadata ใน C# ด้วย Aspose.BarCode
  บทเรียนนี้ครอบคลุมการตั้งค่า Macro PDF417, ฟิลด์ metadata, การส่งออกภาพ, และการสนับสนุน
  Unicode
og_image_alt: Screenshot of a generated PDF417 barcode containing metadata fields
og_title: สร้าง PDF417 Barcode Metadata ใน C# – คู่มือขั้นตอนต่อขั้น
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Create PDF417 barcode metadata in C# using Aspose.BarCode. Learn Macro
    PDF417 settings, save as PNG, and handle Unicode text.
  headline: Create PDF417 barcode metadata in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode metadata in C# using Aspose.BarCode. Learn Macro
    PDF417 settings, save as PNG, and handle Unicode text.
  name: Create PDF417 barcode metadata in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Setting up the Aspose.BarCode NuGet package.
    text: Setting up the Aspose.BarCode NuGet package.
  - name: Initializing a `BarcodeGenerator` for **Macro PDF417**.
    text: Initializing a `BarcodeGenerator` for **Macro PDF417**.
  - name: Populating every useful **barcode metadata field** (file ID, segment ID,
      checksum, etc.).
    text: Populating every useful **barcode metadata field** (file ID, segment ID,
      checksum, etc.).
  - name: Saving the barcode to disk and verifying the output.
    text: Saving the barcode to disk and verifying the output.
  type: HowTo
- questions:
  - answer: Increase `XDimension.Pixels` or switch to a higher‑resolution image format.
    question: What if the barcode looks blurry?
  - answer: No. Only the fields required by your downstream system are mandatory.
      Unused fields can stay at their defaults.
    question: Do I need to set every metadata field?
  - answer: Yes—loop over the data, increment `MacroPdf417SegmentID`, and generate
      a separate barcode for each segment. Remember to keep `MacroPdf417FileID` consistent
      across all segments.
    question: Can I generate a multi‑segment file automatically?
  - answer: Absolutely. The sample text contains `Å`, `ó`, and `©`, showing that Aspose.BarCode
      handles UTF‑8 out of the box.
    question: Is Unicode supported?
  type: FAQPage
tags:
- barcode
- csharp
- aspose
- pdf417
title: สร้าง PDF417 Barcode Metadata ใน C# – คู่มือขั้นตอนเต็ม
url: /th/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเมตาดาต้า PDF417 barcode ใน C# – คู่มือขั้นตอนเต็ม

เคยต้องการ **สร้างเมตาดาต้า PDF417 barcode** ใน C# แต่ไม่แน่ใจว่าต้องปรับคุณสมบัติใดบ้างหรือไม่? คุณไม่ได้เป็นคนเดียว—นักพัฒนามักเจออุปสรรคเมื่อสเปคต้องการอย่างเช่นไฟล์ ID, จำนวนเซกเมนต์, หรือ timestamp ที่กำหนดเอง. ข่าวดีคือ Aspose.BarCode ทำให้เรื่องนี้ง่ายเหมือนการตัดเค้ก. ในบทแนะนำนี้เราจะสร้าง `BarcodeGenerator` สำหรับ **Macro PDF417**, เติมเมตาดาต้าที่สำคัญทั้งหมด, และบันทึกผลลัพธ์เป็นภาพ PNG. เมื่อเสร็จคุณจะได้บาร์โค้ดที่เต็มคุณสมบัติพร้อมใช้ในระบบซัพพลายเชนหรือการจัดการเอกสารใด ๆ.

## คำตอบอย่างรวดเร็ว
- **คลาสหลักสำหรับสร้างบาร์โค้ดคืออะไร?** คลาส `BarcodeGenerator` สร้างภาพบาร์โค้ดตามการตั้งค่าที่ให้.  
- **การตั้งค่าใดที่ควบคุมความคมของภาพ?** เพิ่มค่า `XDimension.Pixels` หรือใช้รูปแบบความละเอียดสูงกว่าเช่น PNG.  
- **ฉันต้องกรอกทุกฟิลด์เมตาดาต้าหรือไม่?** ไม่จำเป็น. เพียงฟิลด์ที่ระบบต่อไประบุเป็นจำเป็นเท่านั้น.  
- **ฉันสามารถฝังอักขระ Unicode ได้หรือไม่?** ได้—Aspose.BarCode รองรับ UTF‑8 โดยอัตโนมัติ, ตามที่แสดงในข้อความตัวอย่าง.  
- **Aspose.BarCode รองรับประเภทบาร์โค้ดกี่ประเภท?** มากกว่า 30 สัญลักษณ์, รวมถึง PDF417 ที่ยาวได้ถึง 5 000 โมดูล.

## สิ่งที่คู่มือนี้ครอบคลุม

เราจะเดินผ่าน:

1. ตั้งค่าแพ็กเกจ NuGet ของ Aspose.BarCode.  
2. เริ่มต้น `BarcodeGenerator` สำหรับ **Macro PDF417**.  
3. เติมทุก **ฟิลด์เมตาดาต้าบาร์โค้ด** ที่มีประโยชน์ (ไฟล์ ID, เซกเมนต์ ID, checksum, ฯลฯ).  
4. บันทึกบาร์โค้ดลงดิสก์และตรวจสอบผลลัพธ์.  

ไม่จำเป็นต้องมีประสบการณ์กับ Macro PDF417 มาก่อน—เพียงความรู้พื้นฐาน C# และ .NET runtime รุ่นล่าสุด. ทำไมคุณควรสนใจ? การฝังเมตาดาต้าที่สมบูรณ์ลงในบาร์โค้ดทำให้สแกนเนอร์ด้านล่างสามารถตรวจสอบการถ่ายโอนไฟล์ทั้งหมด, ตรวจจับเซกเมนต์ที่หายไป, หรือแม้กระทั่งเรียกใช้เวิร์กโฟลว์อัตโนมัติ. กล่าวคือ คุณจะได้ **ข้อมูลที่อธิบายตัวเองอย่างมั่นคง** โดยไม่ต้องอ้างอิงฐานข้อมูลแยก.

## วิธีสร้างเมตาดาต้า pdf417 barcode ใน C#?

โหลด `BarcodeGenerator` ที่กำหนดค่าเป็น `EncodeTypes.MacroPdf417`, ตั้งค่าคุณสมบัติเบื้องต้นของเมตาดาต้า, แล้วเรียก `Save` เพื่อเขียนไฟล์ PNG. กระบวนการสามขั้นตอนนี้จัดการข้อความ Unicode, กำหนดไฟล์ ID ที่ไม่ซ้ำ, และสามารถแยก payload ขนาดใหญ่เป็นหลายเซกเมนต์ได้ตามต้องการ. วิธีนี้ทำงานบน .NET 6+, .NET Framework 4.7+, และต้องการเพียงแพ็กเกจ Aspose.BarCode NuGet.

### ขั้นตอนที่ 1: ติดตั้งแพ็กเกจ Aspose.BarCode NuGet

คุณสามารถติดตั้งแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

ตอนนี้เรามีพื้นฐานแล้ว, ให้ดำดิ่งสู่การทำงานจริง.

## ขั้นตอนที่ 1: เริ่มต้น BarcodeGenerator สำหรับ Macro PDF417

คลาส `BarcodeGenerator` สร้างภาพบาร์โค้ดตามการตั้งค่าที่ให้. สิ่งแรกที่เราต้องการคืออินสแตนซ์ `BarcodeGenerator` ที่กำหนดค่าเป็น **Macro PDF417**. สิ่งนี้บอก Aspose.BarCode ว่าใช้อัลกอริทึมการเข้ารหัสใดและให้ที่สำหรับใส่ข้อความที่มนุษย์อ่านได้.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

// Step 1: Create a BarcodeGenerator for Macro PDF417 with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the steps will go inside this using block.
}
```

> **ทำไมเรื่องนี้สำคัญ:** `EncodeTypes.MacroPdf417` เปิดโหมด PDF417 ขยายที่รองรับเมตาดาต้าเช่นไฟล์ ID และหมายเลขเซกเมนต์. ตัวอย่างข้อความมีอักขระ Unicode (`Å`, `ó`, `©`) เพื่อพิสูจน์ว่าตัวสร้างจัดการอินพุตที่ไม่ใช่ ASCII ได้อย่างราบรื่น.

## ขั้นตอนที่ 2: กำหนดลักษณะพื้นฐานของบาร์โค้ด

`XDimension` กำหนดความกว้างของแต่ละโมดูลบาร์โค้ดเป็นพิกเซล. ก่อนที่เราจะเริ่มเติมเมตาดาต้า, เราควรตั้งค่าพารามิเตอร์ภาพบางอย่างเพื่อให้บาร์โค้ดไม่เป็นจุดจิ๋ว. `XDimension` ควบคุมความกว้างโมดูล, ส่วน `Columns` มีผลต่อรูปทรงโดยรวม.

```csharp
// Step 2: Define basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns
```

> **เคล็ดลับ:** ความกว้างพิกเซล `2` ทำงานได้ดีสำหรับการแสดงบนหน้าจอและเครื่องพิมพ์ส่วนใหญ่. หากต้องการพิมพ์ความละเอียดสูงขึ้น, เพิ่มเป็น `3` หรือ `4`.

## ขั้นตอนที่ 3: เติมฟิลด์เมตาดาต้า macro PDF417

ตอนนี้มาถึงหัวใจของบทแนะนำ—การเพิ่ม **ฟิลด์เมตาดาต้าบาร์โค้ด**. แต่ละคุณสมบัติแมปตรงกับส่วนหนึ่งของสเปค Macro PDF417.

```csharp
// Step 3: Set Macro PDF417 metadata
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // Unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                // Current segment number
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;            // Total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";           // Logical file name
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;               // CCITT‑16 checksum
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;             // File size in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";           // Intended recipient
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";              // Sender identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### สิ่งที่แต่ละคุณสมบัติทำ

| Property | วัตถุประสงค์ | ค่าที่พบบ่อย |
|----------|----------------|----------------|
| **MacroPdf417FileID** | ตัวระบุที่ไม่ซ้ำทั่วโลกสำหรับชุดไฟล์ทั้งหมด. | `12345678` |
| **MacroPdf417SegmentID** | ดัชนีของเซกเมนต์ปัจจุบัน (เริ่มที่ `0`). | `12` |
| **MacroPdf417SegmentsCount** | จำนวนเซกเมนต์ทั้งหมดที่คาดว่าจะมีสำหรับไฟล์. | `20` |
| **MacroPdf417FileName** | ชื่อที่มนุษย์อ่านได้, มักเป็นชื่อไฟล์ต้นฉบับ. | `"file01"` |
| **MacroPdf417Checksum** | checksum CCITT 16‑บิตสำหรับตรวจจับข้อผิดพลาด. | `1234` |
| **MacroPdf417FileSize** | ขนาดของไฟล์ต้นฉบับเป็นไบต์. | `400000` |
| **MacroPdf417TimeStamp** | เวลาที่ไฟล์ถูกสร้าง. | `new DateTime(2019,11,1)` |
| **MacroPdf417Addressee** | ฟิลด์ทางเลือกที่ระบุปลายทาง. | `"street"` |
| **MacroPdf417Sender** | ฟิลด์ทางเลือกที่ระบุระบบต้นทาง. | `"aspose"` |
| **MacroPdf417Terminator** | แฟล็กที่บอกสแกนเนอร์ว่าเป็นเซกเมนต์สุดท้าย. | `Pdf417MacroTerminator.Set` |

> **ทำไมคุณต้องการสิ่งเหล่านี้:** สแกนเนอร์ที่เข้าใจ Macro PDF417 สามารถประกอบไฟล์หลายเซกเมนต์, ตรวจสอบความสมบูรณ์ด้วย checksum, และแม้กระทั่งปฏิเสธข้อมูลที่ล้าสมัยตาม timestamp. สิ่งนี้ทำให้ไม่ต้องมีไฟล์ manifest แยกต่างหาก.

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด

`Save` เขียนภาพบาร์โค้ดที่สร้างขึ้นไปยังไฟล์ในรูปแบบที่เลือก. เมื่อพารามิเตอร์ทั้งหมดตั้งค่าแล้ว, เราเพียงเรียก `Save`. ตัวอย่างนี้เขียนไฟล์ PNG ไปยังโฟลเดอร์ที่คุณระบุ.

```csharp
// Step 4: Save the barcode image
generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

> **กรณีขอบ:** หากคุณวางแผนฝังบาร์โค้ดใน PDF ภายหลัง, อาจเลือกใช้ `BarCodeImageFormat.Jpeg` หรือ `Pdf`. PNG รักษารายละเอียดแบบ lossless ซึ่งสะดวกสำหรับการตรวจสอบ.

## ตัวอย่างการทำงานเต็ม

รวมทุกอย่างเข้าด้วยกัน, นี่คือโปรแกรมเต็มที่คุณสามารถคัดลอก‑วางลงในแอปคอนโซล:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a BarcodeGenerator for Macro PDF417 with Unicode text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Basic appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save as PNG
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode with metadata saved successfully.");
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ชื่อ **ExtPDF417Meta.png** ในโฟลเดอร์ของไฟล์ executable. เปิดด้วยโปรแกรมดูภาพใดก็ได้และคุณจะเห็น PDF417 barcode ที่หนาและคอนทราสต์สูง. หากสแกนด้วยเครื่องอ่านบาร์โค้ดที่รองรับ Macro PDF417, เครื่องสแกนจะคืนค่าเมตาดาต้าที่เราตั้งไว้—ไฟล์ ID `12345678`, เซกเมนต์ `12` ของ `20`, เป็นต้น.

## คำถามทั่วไป & ปัญหาที่พบบ่อย

- **ถ้าบาร์โค้ดดูเบลอ?** เพิ่มค่า `XDimension.Pixels` หรือเปลี่ยนเป็นรูปแบบภาพความละเอียดสูงกว่า.  
- **ฉันต้องตั้งค่าทุกฟิลด์เมตาดาต้าหรือไม่?** ไม่จำเป็น. เพียงฟิลด์ที่ระบบต่อไประบุเป็นจำเป็นเท่านั้น. ฟิลด์ที่ไม่ได้ใช้สามารถคงค่าเริ่มต้นไว้ได้.  
- **ฉันสามารถสร้างไฟล์หลายเซกเมนต์โดยอัตโนมัติได้หรือไม่?** ได้—วนลูปข้อมูล, เพิ่มค่า `MacroPdf417SegmentID`, และสร้างบาร์โค้ดแยกสำหรับแต่ละเซกเมนต์. อย่าลืมให้ค่า `MacroPdf417FileID` คงที่ในทุกเซกเมนต์.  
- **รองรับ Unicode หรือไม่?** แน่นอน. ตัวอย่างข้อความมี `Å`, `ó`, และ `©`, แสดงให้เห็นว่า Aspose.BarCode รองรับ UTF‑8 โดยอัตโนมัติ.

## คำถามที่พบบ่อย

**Q: Aspose.BarCode รองรับประเภทบาร์โค้ดกี่ประเภท?**  
A: Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดมากกว่า 30 แบบ, รวมถึง 1D, 2D, และรหัสไปรษณีย์, และสามารถสร้าง PDF417 barcode ที่ยาวได้ถึง 5 000 โมดูล.

**Q: ฉันสามารถฝังบาร์โค้ดโดยตรงลงในเอกสาร PDF ได้หรือไม่?**  
A: ได้—ใช้ไลบรารี `Aspose.Pdf` เพื่อวาง PNG หรือ JPEG ที่สร้างขึ้นลงในหน้า PDF, รักษาคุณภาพเวกเตอร์.

**Q: เวอร์ชัน .NET ใดที่เข้ากันได้?**  
A: ไลบรารีทำงานกับ .NET Framework 4.7+, .NET Core 3.1, .NET 5, .NET 6, และรุ่นต่อไป.

**Q: ฉันจะตรวจสอบเมตาดาต้าหลังการสแกนอย่างไร?**  
A: ใช้ `BarcodeReader` พร้อม `DecodeType = DecodeType.MacroPdf417` เพื่อดึงฟิลด์เมตาดาต้าแบบโปรแกรม.

**Q: มีขีดจำกัดขนาดไฟล์ที่ฉันสามารถเข้ารหัสได้หรือไม่?**  
A: Aspose.BarCode สามารถจัดการไฟล์ขนาดสูงสุด 10 MB ของข้อมูลดิบในสตรีม Macro PDF417 เดียว, โดยอัตโนมัติแยก payload ขนาดใหญ่เป็นหลายเซกเมนต์.

## ขั้นตอนต่อไป: ไปไกลกว่าพื้นฐาน

ตอนนี้คุณรู้วิธี **สร้างเมตาดาต้า PDF417 barcode** แล้ว, คุณอาจอยากสำรวจ:

- **ฝังบาร์โค้ดใน PDF** ด้วย `Aspose.Pdf` สำหรับการสร้างเอกสารแบบ end‑to‑end.  
- **อ่านเมตาดาต้ากลับ** ด้วย `BarcodeReader` เพื่อตรวจสอบการสแกนแบบโปรแกรม.  
- **ปรับแต่งสี** (พื้นหน้า/พื้นหลัง) เพื่อการสร้างแบรนด์.  
- **เชื่อมต่อกับฐานข้อมูล** เพื่อเติมฟิลด์อัตโนมัติ เช่น `FileID` หรือ `Timestamp`.

หัวข้อทั้งหมดนี้เชื่อมโยงกับคีย์เวิร์ดรองของเรา—**increase barcode resolution**, **macro pdf417**, **aspose barcode c#**, **barcode metadata fields**, และ **c# barcode generation**—ดังนั้นคุณจะพบเอกสารเพิ่มเติมเพื่อเรียนต่อ.

## สรุป

เราพึ่งได้เดินผ่านตัวอย่างที่สมบูรณ์และพร้อมใช้งานในระดับการผลิตของวิธี **สร้างเมตาดาต้า PDF417 barcode** ใน C#. ตั้งแต่การติดตั้ง Aspose.BarCode, เริ่มต้น `BarcodeGenerator`, เติมทุก **ฟิลด์เมตาดาต้าบาร์โค้ด** ที่เกี่ยวข้อง, จนถึงการบันทึก PNG ที่คมชัด, กระบวนการนี้ง่ายเมื่อคุณรู้คุณสมบัติที่ต้องใช้. ลองทำ, ปรับค่าต่าง ๆ, แล้วดูว่าตัวสแกนเนอร์ตอบสนองอย่างไร. ความยืดหยุ่นของ Macro PDF417 ทำให้คุณสามารถฝังทุกอย่างที่ระบบต่อไประบต้องการ—ทั้งหมดในภาพเดียวที่สแกนได้. ขอให้เขียนโค้ดสนุกและบาร์โค้ดของคุณปราศจากข้อผิดพลาด!

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโครงการของคุณเอง.

- [วิธีสร้าง Barcode – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [ไลบรารี barcode ของ Java – เพิ่ม barcode ลงใน PDF ด้วย Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)
- [วิธีสร้าง Barcode – PDF417 แบบกะทัดรัดด้วย Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

---

**อัปเดตล่าสุด:** 2026-09-28  
**ทดสอบด้วย:** Aspose.BarCode 24.10 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง Pdf417 Barcode ด้วย Aspose Barcode คู่มือขั้นตอนเต็ม](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [ตัวอย่าง Aspose Barcode สร้าง Macro Pdf417 ใน C](/barcode/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [วิธีสร้างภาพ Pdf417 Barcode ใน C ด้วย Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}