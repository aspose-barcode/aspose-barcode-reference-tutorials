---
category: general
date: 2026-09-13
description: เรียนรู้วิธีสร้างบาร์โค้ดใน C# ปรับขนาดบาร์โค้ด และบันทึกภาพบาร์โค้ดเป็น
  PNG ด้วย Aspose.BarCode คู่มือขั้นตอนเต็มรูปแบบ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: th
lastmod: 2026-09-13
og_description: วิธีสร้างบาร์โค้ดใน C# ด้วยขนาดบาร์โค้ดที่กำหนดเองและบันทึกรูปภาพบาร์โค้ดเป็น
  PNG. ติดตามคู่มือฉบับเต็มสำหรับ Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: วิธีสร้างบาร์โค้ด ตั้งค่าขนาดกำหนดเอง และบันทึกภาพใน C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: วิธีสร้างบาร์โค้ดกำหนดขนาดเองและบันทึกรูปภาพใน C#
url: /th/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างชุดบาร์โค้ดขนาดกำหนดเองและบันทึกภาพใน C#

หากคุณต้องการ **วิธีสร้างบาร์โค้ด** ในแอปพลิเคชัน .NET นี้ จะเป็นบทแนะนำที่ให้วิธีแก้ไขแบบครบวงจร คุณจะได้เห็นวิธีปรับ **ขนาดบาร์โค้ดกำหนดเอง** และ **บันทึกภาพบาร์โค้ด** เพียงไม่กี่บรรทัดของโค้ด C# เท่านั้น

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบคลังสินค้า ป้ายจัดส่ง และแอปพลิเคชันจุดขาย (POS) เมื่ออ่านจบคู่มือนี้ คุณจะมีโปรแกรมที่สามารถรันได้ซึ่งสร้างบาร์โค้ด DataBar‑Stacked‑Omnidirectional สองแบบ แต่ละแบบมีอัตราส่วนภาพที่แตกต่างกัน และบันทึกเป็นไฟล์ PNG บนดิสก์

**Prerequisites**

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานได้กับ .NET Framework 4.7+)
- Visual Studio 2022 หรือ IDE ที่รองรับ C#
- Aspose.BarCode for .NET (รุ่นทดลองหรือแพคเกจ NuGet ที่มีลิขสิทธิ์)

---

## วิธีสร้างบาร์โค้ดด้วย Aspose.BarCode

ไลบรารี Aspose.BarCode จะทำหน้าที่ซ่อนรายละเอียดระดับต่ำของมาตรฐานบาร์โค้ด ทำให้คุณโฟกัสที่ข้อมูลที่ต้องการเข้ารหัสและลักษณะภาพที่ต้องการ

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

| ขั้นตอน | คำอธิบาย |
|------|-------------|
| **1️⃣ สร้างตัวสร้าง** | ค่าตัวแปร `EncodeTypes.DatabarStackedOmniDirectional` บอก Aspose ว่าจะใช้สัญลักษณ์บาร์โค้ดประเภทใด สตริง `"(01)12345678901231"` เป็นรูปแบบข้อมูล GS1‑128 โดย `(01)` คือ Application Identifier สำหรับ GTIN |
| **2️⃣ ตั้งค่า X‑dimension** | `XDimension.Pixels` กำหนดความกว้างของโมดูลบาร์โค้ดหนึ่งหน่วย (บาร์ที่แคบที่สุด) การเปลี่ยนค่าตัวนี้เป็นวิธีหลักในการทำ **ขนาดบาร์โค้ดกำหนดเอง** โดยไม่ต้องแก้ไขข้อมูลที่เข้ารหัส |
| **3️⃣ ตั้งค่าอัตราส่วนภาพ & บันทึก** | `DataBar.AspectRatio` ควบคุมอัตราส่วนความสูงต่อความกว้างของสัญลักษณ์ DataBar อัตราส่วน 15 จะให้บาร์โค้ดสั้นและกว้าง ส่วน 30 จะทำให้บาร์โค้ดสูงขึ้น `Save` จะเขียนภาพที่แสดงผลออกเป็นไฟล์ PNG เพื่อตอบสนองความต้องการ **บันทึกภาพบาร์โค้ด** |
| **4️⃣ เปลี่ยนอัตราส่วนภาพและบันทึกอีกครั้ง** | การใช้ตัวสร้างเดียวกันหลายครั้งทำให้คุณสร้างภาพหลายภาพที่มีลักษณะภาพต่างกันแต่ข้อมูลคงที่ |

---

## ปรับขนาดบาร์โค้ดกำหนดเองเกิน X‑dimension

แม้ว่า `XDimension.Pixels` จะกำหนดความกว้างของโมดูล แต่คุณยังสามารถปรับขนาดโดยรวมของบาร์โค้ดได้ด้วยการใช้คุณสมบัติสองอย่างร่วมกัน:

1. **`BarHeight`** – ความสูงที่ระบุเป็นพิกเซล  
2. **`BarWidth`** – ความกว้างที่ระบุเป็นพิกเซล (จะทับค่า X‑dimension)

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **เคล็ดลับ:** เมื่อต้องพิมพ์บาร์โค้ด ควรทดสอบภาพที่สร้างขึ้นในขนาดการพิมพ์จริง ความกว้างโมดูล 2 px เหมาะกับการแสดงบนหน้าจอ แต่ป้ายที่พิมพ์มักต้องการอย่างน้อย 4 px เพื่อให้สแกนได้อย่างแม่นยำ

---

## การเลือกฟอร์แมตภาพที่เหมาะสมสำหรับการบันทึกบาร์โค้ด

Aspose.BarCode รองรับ PNG, JPEG, BMP, GIF, และ TIFF PNG มีคุณสมบัติ lossless ทำให้คมชัดที่สุด จึงเป็นตัวเลือกที่ปลอดภัยที่สุดสำหรับการใช้งานส่วนใหญ่ หากต้องการไฟล์ขนาดเล็กสำหรับเว็บ JPEG ที่ตั้งค่าคุณภาพเป็น 90 ก็ทำงานได้ดี แต่ต้องระวังว่าอาร์ติฟาクトจากการบีบอัดอาจส่งผลต่อความแม่นยำในการสแกน

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นแอปพลิเคชันคอนโซลแบบครบวงจรที่คุณสามารถคัดลอก วาง แล้วรันได้ ตัวอย่างนี้แสดง **วิธีสร้างบาร์โค้ด**, ปรับ **ขนาดบาร์โค้ดกำหนดเอง**, และ **บันทึกภาพบาร์โค้ด** ในสองฟอร์แมตที่แตกต่างกัน

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**ผลลัพธ์ที่คาดว่าจะเห็นบนคอนโซล**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

ไฟล์ภาพสี่ไฟล์จะถูกสร้างในโฟลเดอร์ของโปรแกรม


## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณเอง

- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอน](/barcode/english/net/datamatrix-barcode-configuration/)
- [วิธีสร้างบาร์โค้ด PDF417 ด้วย Aspose – คู่มือฉบับสมบูรณ์](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพกำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}