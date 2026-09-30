---
category: general
date: 2026-08-22
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode ตั้งขนาดบาร์โค้ด
  ปรับคอลัมน์ และเปิดใช้งานโหมดคอมแพคท์.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: th
lastmod: 2026-08-22
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode คู่มือนี้แสดงวิธีตั้งขนาดบาร์โค้ด
  ควบคุมคอลัมน์ และเปิดใช้งานโหมดบีบอัดเพื่อให้ได้ภาพที่เล็กลง
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – ตั้งขนาด, คอลัมน์, และโหมดคอมแพคท์
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: วิธีสร้างบาร์โค้ด PDF417 ใน C# และตั้งขนาดบาร์โค้ด
url: /th/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ใน C# และตั้งขนาดบาร์โค้ด

หากคุณต้องการ **generate PDF417 barcode** ในแอปพลิเคชัน .NET คู่มือนี้จะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เห็นอย่างชัดเจน **how to generate PDF417** ด้วย Aspose.BarCode, ปรับ **set barcode size**, และสร้างไฟล์ PNG แบบกะทัดรัดที่สามารถฝังในรายงานหรือแอปมือถือได้

การสร้างบาร์โค้ดไม่จำเป็นต้องใช้โปรแกรมแก้ไขกราฟิกแยกต่างหาก เมื่อจบบทเรียนนี้คุณจะมีเมธอด C# ที่ทำงานเต็มรูปแบบซึ่งสร้างภาพ PDF417 ด้วยขนาดที่คุณต้องการ พร้อมสำหรับการประมวลผลต่อไป

## สิ่งที่คุณจะได้เรียนรู้

* ติดตั้งและอ้างอิงไลบรารี Aspose.BarCode
* สร้าง PDF417 barcode generator และระบุข้อความที่ต้องเข้ารหัส
* **Set barcode size** โดยกำหนด X‑dimension และจำนวนคอลัมน์
* เปิดใช้งานโหมดคอมแพคท์ (truncated) เพื่อลดขนาดสัญลักษณ์
* บันทึกผลลัพธ์เป็นไฟล์ PNG
* แก้ไขปัญหาทั่วไป เช่น บาร์โค้ดอ่านไม่ออกหรือภาพขนาดใหญ่เกินไป

### ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (API ยังทำงานกับ .NET Framework 4.6+ ด้วย)
* ความคุ้นเคยพื้นฐานกับ C# และ Visual Studio (หรือ IDE C# ใดก็ได้)
* ไลเซนส์ Aspose.BarCode ที่ถูกต้อง (รุ่นทดลองฟรีใช้สำหรับทดสอบได้)

> **Pro tip:** หากคุณวางแผนจะสร้างบาร์โค้ดหลาย ๆ ตัวในลูป ให้ใช้ `BarcodeGenerator` ตัวเดียวและเปลี่ยนเฉพาะคุณสมบัติ `CodeText` เท่านั้น วิธีนี้จะลดการจัดสรรหน่วยความจำ

## สร้างบาร์โค้ด PDF417 ด้วย Aspose.BarCode

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` สำหรับสัญลักษณ์ PDF417 วัตถุนี้เป็นจุดเริ่มต้นสำหรับการทำงานกับบาร์โค้ดทั้งหมด

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Why this matters*: `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้มาตรฐาน PDF417 ซึ่งรองรับปริมาณข้อมูลมากและการแก้ไขข้อผิดพลาด ตัวสร้างยังรับข้อมูลที่คุณต้องการเข้ารหัสโดยตรง ทำให้ไม่ต้องกำหนด `CodeText` แยกภายหลัง

## ตั้งค่าขนาดบาร์โค้ดและจำนวนคอลัมน์

สัญลักษณ์ PDF417 ประกอบด้วยแถวและคอลัมน์ของโมดูลสี่เหลี่ยมเล็ก ๆ การควบคุมความกว้างของโมดูล (X‑dimension) และจำนวนคอลัมน์ช่วยให้คุณปรับขนาดโดยละเอียด

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explanation*:  
* **X‑dimension** (`Pixels`) กำหนดความกว้างของแต่ละโมดูล ค่าเล็กทำให้บาร์โค้ดกระชับมากขึ้น ค่าใหญ่ช่วยให้สแกนเนอร์ความละเอียดต่ำอ่านได้ง่ายขึ้น  
* **Columns** ควบคุมการจัดวางแนวนอน คอลัมน์น้อยทำให้บาร์โค้ดสูงขึ้น; คอลัมน์มากทำให้กว้างขึ้น ปรับสองค่าพร้อมกันเพื่อให้ได้ **set barcode size** ที่ต้องการอย่างแม่นยำ

## เปิดใช้งานโหมดคอมแพคท์เพื่อบาร์โค้ดที่เล็กลง

PDF417 มีโหมด “compact” (หรือ truncated) ที่ลบพื้นที่ว่างที่ไม่จำเป็นและลดขนาดโดยรวม ซึ่งเหมาะอย่างยิ่งเมื่อหน้าจอมีพื้นที่จำกัด

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Why enable truncation?*  
เมื่อ `Truncate` เป็น `true` ตัวสร้างจะละเว้นรูปแบบหยุดและบางโค้ดแก้ไขข้อผิดพลาดที่ไม่จำเป็นสำหรับการสแกนส่วนใหญ่ ผลลัพธ์จะเล็กลงประมาณ 15‑20 % โดยไม่เสียความสมบูรณ์ของข้อมูลในกรณีใช้งานทั่วไป

## บันทึกบาร์โค้ดเป็นภาพ PNG

หลังจากกำหนดขนาดและโหมดแล้ว ให้เขียนบาร์โค้ดลงดิสก์ PNG เป็นรูปแบบ lossless ทำให้ขอบโมดูลคมชัด

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

ไฟล์ `CompactPdf417.png` จะมีสัญลักษณ์ PDF417 ที่คมชัดตรงกับขนาดที่คุณตั้งค่าในขั้นตอนก่อนหน้า

### ผลลัพธ์ที่คาดหวัง

การเปิด PNG ที่บันทึกไว้ควรแสดงบาร์โค้ด PDF417 แนวตั้งที่ประกอบด้วยสามคอลัมน์ โมดูลแต่ละตัวกว้าง 2 px และขนาดรวมประมาณ **120 × 240 px** (กว้าง × สูง) การสแกนภาพด้วยโปรแกรมอ่าน PDF417 ใด ๆ จะคืนข้อความต้นฉบับ “Sample text for PDF417”

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| บาร์โค้ดอ่านไม่ออก | X‑dimension เล็กเกินไปสำหรับสแกนเนอร์ | เพิ่ม `XDimension.Pixels` เป็น 3 หรือ 4 |
| ภาพกว้างเกินไปสำหรับ UI | ตั้งค่าคอลัมน์มากเกินไป | ลด `Pdf417.Columns` หรือเปิดใช้งาน `Truncate` |
| ข้อยกเว้น `ArgumentOutOfRangeException` | จำนวนคอลัมน์เป็นค่าลบหรือศูนย์ | ตรวจสอบให้ `Columns` เป็นจำนวนเต็มบวก (ขั้นต่ำ 1) |
| ไฟล์ PNG ว่างเปล่า | เส้นทางออกไม่มีหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปมีสิทธิ์เขียน |

> **Pro tip:** ใช้ `barcodeGenerator.ValidateParameters()` ก่อนเรียก `Save()` เพื่อจับข้อผิดพลาดการกำหนดค่าตั้งแต่แรก

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมคอนโซลแบบ self‑contained ที่รวมทุกขั้นตอนที่กล่าวมา คัดลอกไปยังโปรเจกต์ C# ใหม่, เรียกคืนแพคเกจ NuGet ของ Aspose.BarCode, แล้วรันเพื่อดูผลลัพธ์

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Running the program** จะสร้าง `CompactPdf417.png` ในไดเรกทอรีทำงานของไฟล์ executable สแกนภาพด้วยแอปมือถือ (เช่น “Barcode Scanner”) เพื่อยืนยันว่าข้อความที่เข้ารหัสตรงกับสตริงต้นฉบับ

## ขั้นตอนต่อไปและหัวข้อที่เกี่ยวข้อง

* **Increase error correction level** – ปรับ `Pdf417.ErrorLevel` สำหรับสภาพแวดล้อมที่สแกนมีสัญญาณรบกวน  
* **Change orientation** – ตั้งค่า `Pdf417.Rotate` เป็น `RotationAngle.Rotate90` หากต้องการจัดวางแนวนอน  
* **Embed the barcode in a PDF** – ผสาน Aspose.PDF กับ Aspose.BarCode เพื่อวางภาพลงในเอกสารโดยตรง  
* **Generate other 2‑D barcodes** – คลาส `BarcodeGenerator` เดียวกันรองรับ DataMatrix, QR, และ Aztec; เพียงเปลี่ยน `EncodeTypes.Pdf417` เป็นสัญลักษณ์ที่ต้องการ

โดยการเชี่ยวชาญเทคนิค **generate PDF417 barcode** คุณสามารถทำระบบตั๋วอัตโนมัติ, ป้ายสินค้า, และการส่งข้อมูลที่ปลอดภัยในแอปพลิเคชัน .NET หลากหลายประเภท

## สรุป

คุณได้เรียนรู้วิธี **generate PDF417 barcode** ใน C#, ตั้งค่า **set barcode size** อย่างแม่นยำ, กำหนดคอลัมน์, เปิดโหมดคอมแพคท์, และบันทึกผลเป็น PNG นำการตั้งค่าเหล่านี้ไปใช้เพื่อให้เข้ากับข้อจำกัด UI หรือความต้องการสแกนใด ๆ และขยายวิธีการไปยังรูปแบบบาร์โค้ดอื่น ๆ ตามต้องการ Happy coding!

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด PDF417 – การเข้ารหัส Compact PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [วิธีสร้างบาร์โค้ด – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}