---
category: general
date: 2026-11-17
description: เรียนรู้วิธีบันทึกบาร์โค้ด, เปิดใช้งานโหมดคอมแพค, ปรับคอลัมน์, และสร้างบาร์โค้ด
  PDF417 พร้อมตัวอย่าง C# แบบครบถ้วน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: th
lastmod: 2026-11-17
og_description: วิธีบันทึกบาร์โค้ด, เปิดใช้งานโหมดคอมแพคท์, และปรับคอลัมน์ขณะสร้างบาร์โค้ด
  PDF417 ด้วย C#. ปฏิบัติตามคู่มือขั้นตอนโดยละเอียด.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: วิธีบันทึกบาร์โค้ดเป็น PNG และเปิดใช้งานโหมดคอมแพคท์ใน C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: วิธีบันทึกบาร์โค้ดเป็น PNG และเปิดใช้งานโหมดคอมแพคท์ใน C#
url: /th/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบันทึกบาร์โค้ดเป็น PNG และเปิดใช้งานโหมดคอมแพคท์ใน C#

หากคุณต้องการ **วิธีบันทึกบาร์โค้ด** ในรูปแบบที่สามารถใช้บนเว็บหรือในการพิมพ์ คู่มือนี้จะแสดงขั้นตอนที่แน่นอนให้คุณ คุณจะได้เรียนรู้วิธี **เปิดใช้งานโหมดคอมแพคท์**, **ปรับคอลัมน์**, และ **สร้างบาร์โค้ด PDF417** ด้วยไลบรารี Aspose.BarCode สำหรับ .NET

บทแนะนำนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าโปรเจกต์จนถึงไฟล์ PNG สุดท้าย เพื่อให้คุณสามารถคัดลอกโค้ดไปใส่ในโซลูชันของคุณเองได้โดยไม่ต้องค้นคว้าเพิ่มเติม ไม่จำเป็นต้องอ้างอิงเอกสารภายนอก; ตัวอย่างที่ทำงานได้เต็มรูปแบบรวมอยู่ในนี้แล้ว

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE สำหรับ C# ใดก็ได้)  
* แพ็กเกจ NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

สามรายการนี้เป็นเพียงสิ่งที่ต้องการสำหรับโค้ดต่อไปนี้

## ขั้นตอนที่ 1: สร้างตัวสร้างบาร์โค้ด PDF417

งานแรกเมื่อคุณ **สร้างบาร์โค้ด PDF417** คือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภทการเข้ารหัสที่ถูกต้องและข้อมูลที่คุณต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

enum `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้สัญลักษณ์ PDF417 ซึ่งเป็นบาร์โค้ดเชิงเส้นแบบซ้อนกัน เหมาะสำหรับการเข้ารหัสข้อมูลจำนวนมาก สตริง `"Compact mode"` จะกลายเป็นข้อความที่อ่านได้โดยมนุษย์ใต้บาร์โค้ด

## ขั้นตอนที่ 2: ตั้งค่า X‑dimension (ความกว้างของโมดูล)

แต่ละบาร์ในบาร์โค้ดเรียกว่าโมดูล การควบคุมความกว้างของโมดูลช่วยให้คุณปรับขนาดภาพของบาร์โค้ดได้อย่างละเอียดโดยไม่ต้องเปลี่ยนแปลงข้อมูล

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑dimension ขนาด 2 พิกเซลจะสร้างภาพคอมแพคท์ที่ยังสแกนได้อย่างเชื่อถือได้บนอุปกรณ์ส่วนใหญ่

## ขั้นตอนที่ 3: **วิธีปรับคอลัมน์** สำหรับโค้ด PDF417

PDF417 อนุญาตให้คุณระบุจำนวนคอลัมน์ที่บาร์โค้ดควรใช้ คอลัมน์น้อยจะทำให้สัญลักษณ์สูงและแคบขึ้น ในขณะที่คอลัมน์มากจะทำให้สัญลักษณ์กว้างแต่สั้นลง

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

บรรทัดนี้แสดง **วิธีปรับคอลัมน์** คุณสามารถเปลี่ยนค่าเป็น 2, 4 หรือจำนวนใดก็ได้ที่ไลบรารีรองรับ ขึ้นอยู่กับพื้นที่ที่คุณมีบนสื่อเป้าหมาย

## ขั้นตอนที่ 4: **วิธีเปิดใช้งานโหมดคอมแพคท์** และตัดส่วนที่ไม่จำเป็นของสัญลักษณ์

โหมดคอมแพคท์จะลบพื้นที่ว่างที่ไม่จำเป็นและลดขนาดโดยรวมของบาร์โค้ด ไลบรารีเปิดเผยฟีเจอร์นี้ผ่านคุณสมบัติ `Truncate`

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

สังเกตว่าคำว่า **enable compact mode** ปรากฏที่นี่ และการกระทำเดียวกันจะอธิบายด้วยคำว่า **how to enable compact mode** ต่อไปในคู่มือเพื่อให้สอดคล้องกับคีย์เวิร์ดรอง

## ขั้นตอนที่ 5: **วิธีบันทึกบาร์โค้ด** เป็นภาพ PNG

การบันทึกรูปภาพที่สร้างเสร็จเป็นขั้นตอนสุดท้าย วิธี `Save` จะเขียนบาร์โค้ดลงในระบบไฟล์ในรูปแบบที่คุณระบุ

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

แทนที่ `YOUR_DIRECTORY` ด้วยพาธแบบเต็มหรือแบบสัมพันธ์ที่แอปพลิเคชันของคุณสามารถเขียนได้ หลังจากรันเสร็จคุณจะพบไฟล์ชื่อ `CompactPdf417.png` ที่บรรจุบาร์โค้ด PDF417 แบบคอมแพคท์

### ผลลัพธ์ที่คาดหวัง

การเปิดไฟล์ PNG ที่บันทึกไว้จะแสดงบาร์โค้ด PDF417 แนวตั้งแบบคอมแพคท์ที่มีสามคอลัมน์และพื้นที่ว่างที่ถูกตัด ขนาดภาพประมาณ 2 px ต่อโมดูล ทำให้เหมาะสำหรับฝังในแท็ก HTML `<img>` หรือพิมพ์บนป้ายเล็ก ๆ

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอกไปใส่ในโปรเจกต์คอนโซลใหม่ได้ รวมคำสั่ง `using` ที่จำเป็นทั้งหมดและสาธิต **วิธีบันทึกบาร์โค้ด**, **เปิดใช้งานโหมดคอมแพคท์**, **วิธีปรับคอลัมน์**, และ **สร้างบาร์โค้ด PDF417** ในขั้นตอนเดียว

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

การรันโปรแกรมนี้จะสร้างไฟล์ PNG ตามที่อธิบายไว้ก่อนหน้า คอนโซลจะแสดงตำแหน่งของไฟล์ที่บันทึก ช่วยให้คุณยืนยันว่าขั้นตอน **วิธีบันทึกบาร์โค้ด** สำเร็จ

## คำถามทั่วไปและกรณีขอบ

### ถ้าฉันต้องการรูปแบบภาพอื่น?

วิธี `Save` รองรับค่า enum `BarCodeImageFormat` ใดก็ได้ เช่น `Jpeg`, `Bmp`, หรือ `Gif` แทนที่ `BarCodeImageFormat.Png` ด้วยรูปแบบที่ต้องการ ส่วนโค้ดที่เหลือไม่ต้องเปลี่ยน

### การตัดส่วนส่งผลต่อความจุของข้อมูลอย่างไร?

การเปิด **โหมดคอมแพคท์** (การตัดส่วน) จะลดจำนวนแถว ซึ่งอาจทำให้ความจุข้อมูลสูงสุดของบาร์โค้ดลดลง หากคุณเจอข้อยกเว้น “Data too large” ให้เพิ่มจำนวนคอลัมน์หรือปิดการตัดส่วน

### ฉันสามารถใช้จำนวนคอลัมน์แบบไดนามิกได้หรือไม่?

ได้ คุณสามารถคำนวณจำนวนคอลัมน์จากความยาวของสตริงอินพุตได้:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

โค้ดส่วนนี้แสดง **วิธีปรับคอลัมน์** อย่างโปรแกรมเมติก เพื่อให้บาร์โค้ดพอดีกับเลย์เอาต์ที่กำหนด

### X‑dimension จำกัดที่พิกเซลจำนวนเต็มหรือไม่?

คุณสมบัติ `Pixels` ยอมรับจำนวนเต็มบวกใดก็ได้ สำหรับผลลัพธ์ความละเอียดสูง (เช่น การพิมพ์) คุณอาจเลือกใช้ `Points` แทน `Pixels` เพื่อให้ได้ขนาดที่ไม่ขึ้นกับอุปกรณ์

## เคล็ดลับสำหรับการใช้งานในโปรดักชัน

* **Pro tip:** ห่อการสร้างบาร์โค้ดด้วยบล็อก try‑catch เพื่อจัดการ `BarCodeException` เมื่อข้อมูลอินพุตเกินความจุของสัญลักษณ์  
* **Watch out for:** สิทธิ์การเข้าถึงไฟล์ ระบบต้องมีสิทธิ์เขียนในไดเรกทอรีเป้าหมาย ไม่เช่นนั้นขั้นตอน **วิธีบันทึกบาร์โค้ด** จะล้มเหลวด้วย `UnauthorizedAccessException`  
* **Performance note:** การสร้างบาร์โค้ดหลาย ๆ ตัวในลูปจะได้ประสิทธิภาพดีกว่าถ้าใช้อินสแตนซ์ `BarcodeGenerator` ตัวเดียวและอัปเดตเฉพาะคุณสมบัติ `CodeText` ระหว่างรอบ

## สรุป

คุณได้เรียนรู้ **วิธีบันทึกบาร์โค้ด** เป็นไฟล์ PNG, **เปิดใช้งานโหมดคอมแพคท์**, **วิธีปรับคอลัมน์**, และ **สร้างบาร์โค้ด PDF417** ด้วย Aspose.BarCode สำหรับ C# ตัวอย่างเต็มแสดงทุกขั้นตอนที่จำเป็น ตั้งแต่การเริ่มต้นตัวสร้างจนถึงการบันทึกรูปภาพสุดท้าย

จากนี้คุณสามารถสำรวจหัวข้อที่เกี่ยวข้องเพิ่มเติม เช่น การเพิ่มโลโก้ลงในบาร์โค้ด, การปรับสี, หรือการรวมตัวสร้างเข้ากับ ASP.NET Core API การขยายเหล่านี้ใช้รูปแบบเดียวกับที่แสดงในคู่มือนี้ ทำให้คุณปรับโค้ดได้อย่างมั่นใจ

อย่ากลัวที่จะทดลองเปลี่ยนจำนวนคอลัมน์, X‑dimension, และรูปแบบภาพต่าง ๆ เพื่อให้ตรงกับสเปคของโครงการของคุณ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [วิธีบันทึกบาร์โค้ดและสร้าง PDF417 ด้วย Aspose ใน C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยโหมดคอมแพคท์](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [วิธีสร้างบาร์โค้ด PDF417 และบันทึกเป็น PNG ใน C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}