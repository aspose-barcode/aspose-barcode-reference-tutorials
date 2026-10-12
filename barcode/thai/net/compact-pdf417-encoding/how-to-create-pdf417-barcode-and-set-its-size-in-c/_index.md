---
category: general
date: 2026-09-22
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย C# ตั้งขนาดบาร์โค้ด และสร้างไฟล์ภาพบาร์โค้ดพร้อมตัวอย่างโค้ดที่ชัดเจนและเป็นขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: th
lastmod: 2026-09-22
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว บทเรียนนี้แสดงวิธีตั้งขนาดบาร์โค้ด,
  เปิดใช้งานโหมดคอมแพคท์, และส่งออกภาพ PNG สำหรับโครงการ .NET ใด ๆ
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: วิธีสร้างบาร์โค้ด PDF417 และกำหนดขนาดใน C#
url: /th/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 และกำหนดขนาดใน C#

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ด้วย C# คู่มือนี้จะแสดงวิธีสร้างบาร์โค้ด ควบคุมขนาดของมัน และบันทึกผลลัพธ์เป็นไฟล์รูปภาพ ไม่ว่าคุณจะกำลังสร้างระบบตั๋ว ระบบฉลากโลจิสติกส์ หรือข้อมูลประจำตัวที่ปลอดภัย การเข้าใจรูปแบบ PDF417 จะทำให้คุณเข้ารหัสข้อมูลจำนวนมากในรูปแบบภาพที่กะทัดรัด

ในบทเรียนนี้คุณจะได้เรียนรู้:

* **สร้างบาร์โค้ด PDF417** ด้วยไลบรารี Aspose.BarCode (หรือไลบรารีที่เข้ากันได้)  
* **กำหนดขนาดบาร์โค้ด** โดยปรับ X‑dimension และจำนวนคอลัมน์  
* สร้าง **รูปภาพบาร์โค้ดใน C#** สำหรับ PNG, JPEG หรือ BMP  

ตัวอย่างใช้รุ่น community edition ฟรีของ Aspose.BarCode สำหรับ .NET แต่แนวคิดเดียวกันสามารถใช้กับไลบรารีอื่นที่มีคุณสมบัติเช่นเดียวกันได้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นใหม่กว่า  
* IDE สำหรับ C# (Visual Studio, Visual Studio Code, Rider ฯลฯ)  
* แพ็กเกจ NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`)  

ไม่ต้องตั้งค่าพิเศษเพิ่มเติม; ไลบรารีทำงานได้บน Windows, Linux และ macOS

## ขั้นตอนที่ 1: สร้างบาร์โค้ด PDF417 พื้นฐานและกำหนดขนาด

ขั้นตอนแรกคือสร้างอ็อบเจกต์ `BarcodeGenerator` ด้วยค่า `EncodeTypes.Pdf417` และใส่ข้อความที่ต้องการเข้ารหัส จากนั้นปรับ **X‑dimension** (ความกว้างโมดูล) และจำนวน **columns** เพื่อควบคุมขนาดโดยรวม

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**ทำไมการตั้งค่าเหล่านี้ถึงสำคัญ**

* `XDimension.Pixels` กำหนดความกว้างของบาร์แคบที่สุด ค่าที่เล็กลงทำให้บาร์โค้ดกระชับขึ้น ส่วนค่าที่ใหญ่ขึ้นทำให้อ่านง่ายบนสแกนเนอร์ความละเอียดต่ำ  
* `Pdf417.Columns` มีผลต่ออัตราส่วนของบาร์โค้ด คอลัมน์น้อยทำให้บาร์โค้ดสูงขึ้น; คอลัมน์มากทำให้บาร์โค้ดแบนลง การปรับคอลัมน์เป็นวิธีหลักในการ **กำหนดขนาดบาร์โค้ด** โดยไม่ต้องเปลี่ยนข้อมูลที่เข้ารหัส  

หลังจากรันโค้ดแล้ว คุณจะพบไฟล์ `Pdf417Basic.png` ในโฟลเดอร์ที่ระบุ รูปภาพจะคล้ายกับภาพหน้าจอด้านล่าง:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## ขั้นตอนที่ 2: สร้างบาร์โค้ด PDF417 แบบกะทัดรัด (truncate mode) ด้วยขนาดเดียวกัน

บางครั้งคุณอาจต้องการบาร์โค้ดสั้นลงเพื่อใช้ในพื้นที่จำกัด PDF417 มีโหมด *truncate* (compact) ที่ลบ pattern สิ้นสุดและลดความสูงโดยรวม คุณสมบัติ `Truncate` จะสลับพฤติกรรมนี้

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**อะไรเปลี่ยนแปลงเมื่อ `Truncate = true`?**

* บาร์โค้ดจะสั้นลงประมาณ 15‑20 % ในแนวตั้ง ซึ่งเหมาะกับฉลากขนาดเล็กหรือหน้าจอมือถือ  
* ข้อมูลยังคงสามารถกู้คืนได้เต็มที่; สแกนเนอร์สมัยใหม่ส่วนใหญ่รองรับโหมด truncate โดยอัตโนมัติ  

ไฟล์ `CompactPdf417.png` ที่ได้จะเป็นเวอร์ชันบางกว่าของบาร์โค้ดพื้นฐาน

## ขั้นตอนที่ 3: สร้างบาร์โค้ด Micro PDF417 ปรับคอลัมน์และบันทึก

Micro PDF417 เป็นรูปแบบความหนาแน่นสูงที่ออกแบบมาสำหรับพื้นที่เล็กมาก (เช่น บัตรประจำตัว) รองรับคอลัมน์ 1‑4 เท่านั้น และไลบรารีให้คุณใช้คุณสมบัติ `XDimension` เดียวกันสำหรับควบคุมขนาด

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**จุดสำคัญของ Micro PDF417**

* ค่า enum `EncodeTypes.MicroPdf417` จะเลือกเวอร์ชันไมโครโดยอัตโนมัติ  
* เนื่องจากสัญลักษณ์หนาแน่นกว่า คุณอาจต้องใช้เครื่องพิมพ์ DPI สูง (300 dpi หรือมากกว่า) เพื่อให้บาร์โค้ดอ่านได้ชัดเจน  
* การปรับจำนวนคอลัมน์เป็นวิธีเดียวที่สามารถควบคุมขนาดได้; ไลบรารียังคงเคารพ `XDimension`

## วิธีกำหนดขนาดบาร์โค้ดสำหรับรูปแบบเอาต์พุตต่าง ๆ

ตัวอย่างข้างต้นใช้ PNG แต่เมธอด `Save` เดียวกันทำงานกับ JPEG, BMP หรือ TIFF หากคุณต้องการขนาดภาพเฉพาะ (เช่น 300 × 150 px) ให้ผสม `XDimension` กับ `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

การเพิ่ม `ImageResolution` พร้อมกับสเกล `XDimension` จะช่วยรักษาคุณภาพภาพเมื่อต้องพิมพ์ความละเอียดสูง

## ข้อผิดพลาดทั่วไปและเคล็ดลับระดับมืออาชีพ

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| บาร์โค้ดดูเบลอบนหน้าจอ | DPI ต่ำร่วมกับ `XDimension` เล็ก | เพิ่ม `ImageResolution` และ/หรือ `XDimension.Pixels` |
| สแกนเนอร์อ่านโหมด truncate ไม่ได้ | เฟิร์มแวร์สแกนเนอร์เก่าไม่มีการสนับสนุน | ใช้โหมดเต็ม (ไม่ตัด) สำหรับฮาร์ดแวร์รุ่นเก่า |
| Micro PDF417 อ่านไม่ออก | พิมพ์ที่ < 300 dpi หรือคอนทราสต์ไม่เพียงพอ | พิมพ์บนกระดาษด้านแมตต์ที่ 300 dpi หรือสูงกว่า, ตรวจสอบสีพื้นหน้าเข้ม |
| ไฟล์เอาต์พุตเสียหาย | ไม่มีสิทธิ์เขียนในโฟลเดอร์เป้าหมาย | ตรวจสอบว่า `YOUR_DIRECTORY` มีอยู่และสามารถเขียนได้ |

**เคล็ดลับระดับมืออาชีพ:** ควรสร้างบาร์โค้ดเป็น PNG เมื่อคุณต้องการคุณภาพแบบ lossless สำหรับการประมวลผลต่อไป (เช่น ฝังลงใน PDF) PNG รักษาค่าพิกเซลที่แม่นยำ ส่วน JPEG จะเพิ่มศูนย์บีบอัดที่อาจทำให้บาร์โค้ดอ่านยากขึ้น

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นแอปพลิเคชันคอนโซลสมบูรณ์ที่สาธิตบาร์โค้ดสามประเภทในรอบเดียว คัดลอกโค้ดไปยังโปรเจกต์คอนโซล .NET ใหม่และรัน

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

เมื่อรันโปรแกรมจะสร้างไฟล์ PNG สามไฟล์ในโฟลเดอร์ `Barcodes`:

* `Pdf417Basic.png` – บาร์โค้ด PDF417 มาตรฐานที่มีสามคอลัมน์  
* `CompactPdf417.png` – ข้อมูลเดียวกันในโหมด truncate (กะทัดรัด) สูงกว่าสั้นลงเล็กน้อย  
* `MicroPdf417.png` – เวอร์ชัน Micro PDF417 ความหนาแน่นสูงที่มีสี่คอลัมน์  

เปิดไฟล์ใดไฟล์หนึ่งด้วยโปรแกรมดูรูปภาพ; คุณจะเห็นลักษณะการจัดเรียงแบบซ้อนกันของบาร์โค้ด

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดตัวอย่างทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณเอง

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}