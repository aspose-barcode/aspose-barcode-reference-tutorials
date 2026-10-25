---
category: general
date: 2026-10-24
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย Aspose.BarCode ใน C# พร้อมการตั้งค่าแบบคอมแพคท์และการควบคุม
  XDimension ของบาร์โค้ด
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: th
lastmod: 2026-10-24
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode. ทำตามคู่มือฉบับสมบูรณ์นี้เพื่อสร้างภาพ
  PDF417 แบบกะทัดรัด, ควบคุม XDimension, และกำหนดจำนวนคอลัมน์.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: สร้างบาร์โค้ด PDF417 ด้วย Aspose.BarCode – ขั้นตอน C# ทีละขั้น
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: วิธีสร้างบาร์โค้ด PDF417 ด้วย Aspose.BarCode ใน C#
url: /th/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการสร้างบาร์โค้ด PDF417 ด้วย Aspose.BarCode ใน C#

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงวิธีแก้ไขที่สมบูรณ์และพร้อมใช้งาน คุณจะได้เห็นว่า Aspose.BarCode ทำให้กระบวนการง่ายขึ้นพร้อมให้คุณควบคุม **PDF417 แบบกะทัดรัด**, **XDimension ของบาร์โค้ด**, และ **คอลัมน์ของ PDF417** อย่างละเอียด

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, แพลตฟอร์มตั๋ว, และเวิร์กโฟลว์เอกสาร เมื่อจบบทเรียนนี้คุณจะมีโปรแกรม C# ที่ทำงานได้เองซึ่งสร้างภาพ PNG ของบาร์โค้ด PDF417 ที่คมชัด พร้อมฝังใน UI ใด ๆ หรือพิมพ์บนป้ายได้

## สิ่งที่คุณต้องเตรียม

- .NET 6.0 SDK หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.6+)
- Visual Studio 2022 หรือโปรแกรมแก้ไข C# ที่คุณชอบ
- ไลเซนส์ Aspose.BarCode for .NET ที่ถูกต้อง (รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา)
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **เคล็ดลับ:** หากคุณกำลังประเมิน Aspose.BarCode ให้ดาวน์โหลดรุ่นทดลองจากเว็บไซต์อย่างเป็นทางการและเพิ่มแพคเกจ NuGet `Aspose.BarCode` ลงในโปรเจกต์ของคุณ รุ่นทดลองจะใส่ลายน้ำเล็ก ๆ ลงในภาพที่สร้างขึ้น ซึ่งจะหายไปเมื่อคุณใส่ไลเซนส์

## ขั้นตอนที่ 1: ติดตั้งแพคเกจ NuGet ของ Aspose.BarCode

เปิดเทอร์มินัลในโฟลเดอร์โซลูชันของคุณและรัน:

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะดึงเวอร์ชันล่าสุดที่เสถียร (ณ ตุลาคม 2026, เวอร์ชัน 23.12) การเพิ่มแพคเกจนี้จะทำให้คุณสามารถใช้เนมสเปซ `Aspose.BarCode.Generation` เพื่อ **สร้างภาพบาร์โค้ด PDF417** ได้

## ขั้นตอนที่ 2: สร้างโปรเจกต์คอนโซล C# เบื้องต้น

หากคุณยังไม่มีโปรเจกต์ ให้สร้างใหม่:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

เปิดไฟล์ `Program.cs` โครงสร้างพื้นฐานจะมีเมธอด `Main` อยู่แล้ว ซึ่งเราจะใส่โค้ดการสร้างบาร์โค้ดลงไป

## ขั้นตอนที่ 3: เริ่มต้นตัวสร้างบาร์โค้ด

แรกสุดให้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.BarCode.Generation;
```

จากนั้นภายใน `Main` ให้สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยสัญลักษณ์ PDF417 และข้อมูลที่คุณต้องการเข้ารหัส:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

สตริงนี้รวมอักขระ Unicode เพื่อแสดงให้เห็นว่า Aspose.BarCode จัดการกับข้อมูลที่ไม่ใช่ ASCII ได้อย่างถูกต้อง หากคุณต้องการเฉพาะ ASCII เพียงเปลี่ยนข้อความเป็นสตริงธรรมดาใดก็ได้

## ขั้นตอนที่ 4: ปรับ XDimension ของบาร์โค้ด (ขนาดโมดูล)

**XDimension ของบาร์โค้ด** กำหนดความกว้างของบาร์ที่เล็กที่สุด (โมดูล) การตั้งค่าเป็นพิกเซลทำให้คุณควบคุมขนาดภาพสุดท้ายได้อย่างแม่นยำ:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

ค่าที่ `2` พิกเซลให้ภาพที่กะทัดรัดโดยไม่เสียความน่าอ่านของการสแกน เพิ่มค่านี้เพื่อทำบาร์โค้ดใหญ่ขึ้นหรือ ลดลงสำหรับเลย์เอาต์ที่หนาแน่นมาก

## ขั้นตอนที่ 5: ตั้งค่าตัวเลือก PDF417 แบบกะทัดรัด

สองการตั้งค่าเฉพาะของ PDF417 มีผลต่อขนาดภาพอย่างมาก:

| การตั้งค่า | ความหมาย | ค่าโดยทั่วไปสำหรับผลลัพธ์แบบกะทัดรัด |
|-----------|-----------|----------------------------------------|
| `Columns` | จำนวนคอลัมน์ข้อมูล | `3` |
| `Truncate` (โหมดกะทัดรัด) | ไม่แสดง quiet zone ด้านขวาและลดจำนวนแถว | `true` |

นำไปใช้ดังนี้:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

การตั้งค่า **คอลัมน์ PDF417** เป็น `3` พร้อม `Truncate = true` จะสร้างบาร์โค้ด *PDF417 แบบกะทัดรัด* ที่พอดีกับป้ายมาตรฐานและยังอ่านได้โดยสแกนเนอร์ส่วนใหญ่

## ขั้นตอนที่ 6: บันทึกภาพบาร์โค้ด

สุดท้ายให้เขียนบาร์โค้ดลงไฟล์ ตัวอย่างนี้บันทึกเป็น PNG แต่ Aspose.BarCode ยังรองรับ BMP, JPEG, GIF, TIFF, และ SVG ด้วย:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

คอนสแตนท์ `BarCodeImageFormat.Png` บอกไลบรารีให้สร้าง PNG แบบไม่มีการสูญเสียคุณภาพ ซึ่งเหมาะสำหรับการประมวลผลต่อหรือการพิมพ์

## โค้ดเต็มที่สามารถรันได้

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

เมื่อรันโปรแกรมจะสร้างไฟล์ `CompactPdf417.png` ในโฟลเดอร์รากของโปรเจกต์ เปิดไฟล์ด้วยโปรแกรมดูรูปใดก็ได้ คุณจะเห็นบาร์โค้ด PDF417 ที่บีบอัดอย่างแน่นหนาซึ่งเข้ารหัสสตริง *Åspóse.Barcóde©*

![Screenshot of generated PDF417 barcode using Aspose.BarCode](placeholder-image.png "Generated PDF417 barcode")

*ข้อความแทนภาพ: ภาพหน้าจอของบาร์โค้ด PDF417 ที่สร้างด้วย Aspose.BarCode* – ข้อความแทนภาพนี้มีคีย์เวิร์ดหลักสำหรับการเข้าถึงและ SEO

## การตรวจสอบผลลัพธ์

1. เปิดไฟล์ PNG บาร์โค้ดควรประกอบด้วยสามคอลัมน์ข้อมูลแนวตั้งพร้อมเลย์เอาต์กะทัดรัด (ไม่มี quiet zone เพิ่มด้านขวา)
2. สแกนภาพด้วยแอปสแกนบาร์โค้ดบนสมาร์ทโฟนที่รองรับ PDF417 ข้อความที่ถอดรหัสต้องตรงกับสตริงต้นฉบับ
3. หากสแกนไม่สำเร็จ ให้ลองเพิ่มค่า `XDimension.Pixels` เป็น `3` หรือ `4` โมดูลที่ใหญ่ขึ้นช่วยให้อ่านได้ง่ายบนอุปกรณ์ความละเอียดต่ำ

## การเปลี่ยนแปลงทั่วไปและกรณีขอบ

### 1. เปลี่ยนรูปแบบภาพ

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG เป็นเวกเตอร์ ทำให้บาร์โค้ดคมชัดที่ระดับการซูมใด ๆ — เหมาะสำหรับเว็บเพจ

### 2. เข้ารหัสข้อมูลจำนวนมาก

PDF417 สามารถเก็บข้อความได้ประมาณ ~1.1 KB เมื่อข้อมูลเกินความจุของสามคอลัมน์ ไลบรารีจะเพิ่มแถวโดยอัตโนมัติ เพื่อให้บาร์โค้ดกะทัดรัด คุณสามารถ:

- ลดความยาวข้อมูล (เช่น ใช้ไอดีแทนข้อความเต็ม)
- เพิ่มจำนวน **คอลัมน์ PDF417** (เช่น `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. ใช้ไลเซนส์เพื่อเอาลายน้ำรุ่นทดลองออก

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

วางไฟล์ไลเซนส์ไว้ข้างไฟล์ executable หลังจากใส่ไลเซนส์แล้วภาพที่สร้างจะไม่มีลายน้ำ

### 4. จัดการข้อยกเว้น

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

ความล้มเหลวทั่วไปรวมถึงการไม่มีสิทธิ์เขียนไฟล์หรือรูปแบบภาพที่ไม่รองรับ

## ทำไมการตั้งค่าเหล่านี้ถึงสำคัญ

- **XDimension ของบาร์โค้ด** – ควบคุมความหนาของแต่ละบาร์ หากเล็กเกินไปบาร์โค้ดจะอ่านไม่ออก หากใหญ่เกินไปจะเสียพื้นที่
- **คอลัมน์ PDF417** – คอลัมน์น้อยทำให้บาร์โค้ดแคบลงแต่เพิ่มจำนวนแถว

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generate PDF417 barcode with compact settings in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}