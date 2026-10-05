---
category: general
date: 2026-08-09
description: วิธีอ่าน PDF417 ใน C# ด้วย BarCodeReader. เรียนรู้การอ่านไฟล์ PNG ของบาร์โค้ด,
  จัดการบาร์โค้ดหลายรายการ, และดึงข้อมูลเมตาเพิ่มเติม.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: th
lastmod: 2026-08-09
og_description: วิธีอ่าน PDF417 ด้วย C# และ Aspose.BarCode บทเรียนนี้จะแสดงวิธีอ่านไฟล์
  PNG ของบาร์โค้ด, ประมวลผลบาร์โค้ดหลายรายการในภาพเดียว, และดึงข้อมูลเมตาดาต้า PDF417
  ที่ขยายเพิ่มเติม
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: วิธีอ่าน PDF417 ด้วย C# – บทแนะนำการอ่านบาร์โค้ด
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: วิธีอ่าน PDF417 ใน C# – คู่มือการอ่านบาร์โค้ดแบบครบถ้วน
url: /th/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่าน PDF417 ด้วย C# – คู่มือการอ่านบาร์โค้ดแบบครบถ้วน

หากคุณต้องการ **วิธีอ่าน PDF417** ในแอปพลิเคชัน .NET คู่มือนี้จะให้โซลูชันที่พร้อมใช้งาน คุณจะได้เห็นวิธีอ่านไฟล์ PNG ของบาร์โค้ด, ประมวลผลหลายบาร์โค้ดในภาพเดียวกัน, และดึงฟิลด์ PDF417 ที่ขยายซึ่งหลายสแกนเนอร์ซ่อนไว้

การอ่านบาร์โค้ด PDF417 เป็นเรื่องทั่วไปในโลจิสติกส์, การจำหน่ายตั๋ว, และการจัดการเอกสาร เมื่อจบบทเรียนนี้คุณจะสามารถถอดรหัสภาพ Macro PDF417, แสดงผลลัพธ์ทั้งหมด, และใช้ข้อมูลเพิ่มเติม (ไฟล์ ID, จำนวนเซกเมนต์, เวลา, ฯลฯ) ในตรรกะธุรกิจของคุณเอง

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+ ด้วย)
- Visual Studio 2022 หรือ IDE C# ใดก็ได้
- **Aspose.BarCode for .NET** (รุ่นทดลองฟรีหรือแพคเกจ NuGet ที่มีลิขสิทธิ์)
- ภาพ PNG ที่มีบาร์โค้ด Macro PDF417 (ไฟล์ตัวอย่างชื่อ `ExtPDF417Meta.png`)

> **เคล็ดลับมืออาชีพ:** ติดตั้งไลบรารีด้วยคอนโซล NuGet:  
> `dotnet add package Aspose.BarCode`

## วิธีอ่าน PDF417 ด้วย BarCodeReader ใน C#

หัวใจของโซลูชันคือคลาส `BarCodeReader` ซึ่งรับพาธของภาพและ enum `DecodeType` ที่บอกให้เอนจินรู้ว่าจะค้นหา symbology ใด

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
        }
    }
}
```

### ทำไมวิธีนี้ถึงได้ผล

- **`DecodeType.MacroPdf417`** บอกให้รีดเดอร์มองหาเวอร์ชัน Macro PDF417 ซึ่งเก็บฟิลด์เพิ่มเติมที่คุณเห็นในขั้นตอน 4.
- บล็อก `using` จะทำการปล่อยรีดเดอร์โดยอัตโนมัติ ปล่อยการจัดการไฟล์
- `ReadBarCodes()` คืนค่า **ทั้งหมด** ของบาร์โค้ดที่ตรงกับประเภทที่ร้องขอ ซึ่งตอบสนองความต้องการ *อ่านหลายบาร์โค้ด* แม้ภาพจะมีเพียงหนึ่งบาร์โค้ดก็ตาม

การรันโปรแกรมจะแสดงผลลัพธ์ที่คล้ายกับ:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## การใช้รีดเดอร์บาร์โค้ด C# เพื่ออ่านหลายบาร์โค้ด

หากภาพมีสัญลักษณ์ Macro PDF417 หลายตัว (เช่น หน้าสแกนที่มีชุดตั๋ว), ลูป `foreach` เดียวกันจะประมวลผลแต่ละอัน ไม่จำเป็นต้องเขียนโค้ดเพิ่มเติม; รีดเดอร์จะรวมผลลัพธ์ภายในโดยอัตโนมัติ.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### ข้อผิดพลาดทั่วไป

- **รูปแบบภาพ:** รีดเดอร์รองรับ PNG, JPEG, BMP, และ TIFF หากคุณลองใช้รูปแบบที่รีดเดอร์ไม่สามารถถอดรหัสได้ จะได้คอลเลกชันว่าง นั่นคือเหตุผลที่บทเรียนเน้น *อ่านบาร์โค้ด PNG*.
- **ความละเอียด:** ภาพความละเอียดต่ำ (< 300 dpi) อาจทำให้พลาดเซกเมนต์ ควรเพิ่มขนาดหรือขอสแกนคุณภาพสูงกว่าเมื่อทำได้.
- **แฟล็ก Macro:** หากลืมใช้ `DecodeType.MacroPdf417` จะทำให้เอนจินจำกัดเฉพาะ PDF417 ธรรมดาและละทิ้งข้อมูลที่ขยาย ควรระบุประเภท macro เสมอเมื่อคุณต้องการฟิลด์ *อ่านบาร์โค้ดที่ขยาย*.

## การอ่านไฟล์ PNG ของบาร์โค้ด – แนวทางปฏิบัติที่ดีที่สุด

การทำงานกับไฟล์ PNG เป็นเรื่องง่ายเพราะรูปแบบนี้รักษาข้อมูลพิกเซลแบบไม่สูญเสีย นี่คือเช็คลิสต์สั้น ๆ:

1. ตรวจสอบว่าไฟล์มีอยู่ก่อนสร้างรีดเดอร์.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. ใช้ `Image.FromFile` เฉพาะเมื่อคุณต้องการทำการประมวลผลล่วงหน้า (หมุน, ครอบ) เท่านั้น `BarCodeReader` สามารถเปิดไฟล์โดยตรง ซึ่งช่วยหลีกเลี่ยงการจัดสรรหน่วยความจำเพิ่มเติม.
3. หาก PNG มีความโปร่งใส รีดเดอร์ยังทำงานได้เนื่องจากบาร์โค้ดถูกแสดงบนพิกเซลทึบ.

## การเข้าถึงเมตาดาต้า PDF417 ที่ขยาย

อ็อบเจ็กต์ `Extended.Pdf417` เปิดเผยทุกฟิลด์ทางเลือกที่กำหนดโดยสเปค PDF417 คุณสามารถแมปฟิลด์เหล่านี้ไปยังโมเดลโดเมน, เก็บไว้ในฐานข้อมูล, หรือใช้สำหรับการตรวจสอบความถูกต้อง.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Populate the model:



## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลรวมตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณเอง.

- [วิธีอ่านบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [วิธีสร้างบาร์โค้ด – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [อ่านบาร์โค้ด DataMatrix C# – สร้างโหมด DataMatrix (อัตโนมัติ)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}