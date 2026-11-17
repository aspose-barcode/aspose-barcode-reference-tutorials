---
category: general
date: 2026-11-17
description: สร้างภาพบาร์โค้ดใน C# ด้วยไลบรารี Barcode Generator. ทำตามคู่มือนี้เพื่อเรียนรู้วิธีสร้างโค้ด
  DataBar stacked omnidirectional อย่างเป็นขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: th
lastmod: 2026-11-17
og_description: สร้างภาพบาร์โค้ดใน C# ด้วยตัวอย่างสั้นกระชับ เรียนรู้วิธีสร้างบาร์โค้ด
  DataBar แบบซ้อนหลายแถวและหลายทิศทางโดยใช้ไลบรารี Barcode Generator
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: สร้างภาพบาร์โค้ดใน C# – คู่มือฉบับสมบูรณ์สำหรับรหัส DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างภาพบาร์โค้ดใน C# ด้วย DataBar stacked omnidirectional
url: /th/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดใน C# ด้วย DataBar stacked omnidirectional

หากคุณต้องการ **สร้างภาพบาร์โค้ด** ในแอปพลิเคชัน .NET นี้ จะเป็นการสาธิตวิธีใช้ **Barcode Generator C#** API เพื่อสร้าง DataBar stacked omnidirectional ซึ่งเป็นรูปแบบที่ครอบคลุมโดยคำค้น *how to generate databar*  

คู่มือนี้จะอธิบายขั้นตอนทั้งหมดตั้งแต่การติดตั้งไลบรารีจนถึงการปรับอัตราส่วนภาพ เพื่อให้คุณคัดลอกโค้ด รัน แล้วได้ไฟล์ PNG ทันที ไม่ต้องค้นหาข้อมูลจากเอกสารภายนอก

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า (ตัวอย่างนี้ยังทำงานกับ .NET Framework 4.7+)
* สภาพแวดล้อมการพัฒนา เช่น Visual Studio 2022 หรือ VS Code
* แพ็กเกจ **Aspose.BarCode for .NET** จาก NuGet (ไลบรารีที่ให้ `BarcodeGenerator`)

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

> **เคล็ดลับ:** ใช้พารามิเตอร์ `--version` เพื่อระบุเวอร์ชันล่าสุดที่เสถียร เช่น `dotnet add package Aspose.BarCode --version 23.9`

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespace

สร้างโปรเจกต์คอนโซลใหม่และอ้างอิง namespace ที่จำเป็น ขั้นตอนนี้เตรียมสภาพแวดล้อมสำหรับโค้ด **barcode generator c#** ที่จะตามมา

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

Namespace `Aspose.BarCode.Generation` มีคลาส `BarcodeGenerator` ซึ่งเป็นหัวใจของกระบวนการ **create barcode image**

## ขั้นตอนที่ 2: เริ่มต้น BarcodeGenerator สำหรับ DataBar stacked omnidirectional

ตัวสร้างต้องการข้อมูลสองส่วน: ประเภทบาร์โค้ดและข้อมูลที่จะเข้ารหัส ค่า enum `EncodeTypes.DatabarStackedOmniDirectional` จะเลือกเวอร์ชัน DataBar ที่ตรงกับสถานการณ์ *how to generate databar*

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*ทำไมต้องเลือกแบบนี้:* การเลือกค่า `EncodeTypes` ที่ถูกต้องทำให้ภาพที่ได้สอดคล้องกับมาตรฐานอุตสาหกรรมสำหรับการสแกนในร้านค้า

## ขั้นตอนที่ 3: กำหนดขนาดโมดูล (X‑dimension) เป็นพิกเซล

ความหนาแน่นของบาร์โค้ดถูกควบคุมด้วย X‑dimension การตั้งค่าเป็นค่าพิกเซลที่เหมาะสมจะทำให้ภาพอ่านได้ทั้งบนหน้าจอและการพิมพ์

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

หากต้องการบาร์โค้ดขนาดใหญ่สำหรับการพิมพ์ความละเอียดต่ำ ให้เพิ่มค่าพิกเซลตามต้องการ

## ขั้นตอนที่ 4: ปรับอัตราส่วน (Aspect Ratio) ของ DataBar เพื่อทำให้แถวสูงขึ้น

DataBar stacked omnidirectional มีสองแถว การปรับ `AspectRatio` จะช่วยควบคุมความสูงของแต่ละแถว ซึ่งเป็นประโยชน์เมื่อขนาดเริ่มต้นดูแออัด

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

อัตราส่วน `15` เป็นค่าที่นิยมใช้สำหรับป้ายสินค้าในร้านค้า; คุณสามารถทดลองค่าระหว่าง `10` ถึง `20` เพื่อให้ตรงกับความต้องการของการจัดวาง

## ขั้นตอนที่ 5: บันทึกบาร์โค้ดที่สร้างเป็นไฟล์ PNG

สุดท้ายให้เขียนภาพลงดิสก์ PNG เป็นรูปแบบที่ไม่มีการสูญเสียข้อมูล เหมาะสำหรับการประมวลผลต่อหรือฝังใน PDF

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

เมื่อรันโปรแกรม จะได้ไฟล์ชื่อ **DatabarAspectRatio15.png** อยู่ในโฟลเดอร์ output ของโปรเจกต์ การเปิดไฟล์จะแสดงบาร์โค้ดที่คมชัดพร้อมสแกน

### ผลลัพธ์ที่คาดหวัง

ภาพที่บันทึกจะคล้ายกับภาพตัวอย่างด้านล่าง (ภาพจริงไม่ได้แสดงเพื่อความกระชับ)

*ข้อความแทนภาพตัวอย่าง:* **create barcode image** – ไฟล์ PNG ที่แสดง DataBar stacked omnidirectional ด้วยอัตราส่วน 15

## ความแตกต่างทั่วไปและกรณีขอบ

| Situation | Adjustment |
|-----------|------------|
| **Different payload length** | Replace the GTIN string with any valid DataBar content (e.g., `(01)01234567890123`). |
| **Higher resolution for large prints** | Increase `XDimension.Pixels` to 4 or 5 and optionally set `Resolution` in `Parameters.Image`. |
| **Other DataBar formats** | Use `EncodeTypes.DatabarStacked` for a two‑row stacked variant without omnidirectional capability. |
| **Saving as JPEG** | Change `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` and optionally set `Quality`. |

ความแตกต่างเหล่านี้ตอบคำถาม *how to generate databar* อย่างกว้างขวางโดยแสดงให้เห็นว่าเครื่องสร้างเดียวกันสามารถปรับแต่งให้รองรับหลายรูปแบบของ DataBar ได้

## สรุปโค้ดทั้งหมด

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

คัดลอกโค้ดไปยัง `Program.cs` ทำการ restore NuGet packages แล้วรัน `dotnet run` คอนโซลจะแจ้งตำแหน่งไฟล์ภาพ และคุณสามารถเปิด PNG เพื่อตรวจสอบผลลัพธ์ของ **create barcode image** ได้

## สรุป

ตอนนี้คุณรู้วิธี **create barcode image** ใน C# ด้วยไลบรารี Barcode Generator และวิธี **generate DataBar** ด้วยการควบคุมขนาดและอัตราส่วนอย่างแม่นยำ ตัวอย่างเต็มแสดงการตั้งค่าตั้งแต่การเริ่มต้น `BarcodeGenerator` จนถึงการส่งออกเป็นไฟล์ PNG เพื่อให้คุณสามารถผสานการสร้างบาร์โค้ดเข้าไปในแอปพลิเคชัน .NET ใด ๆ ได้โดยไม่ต้องค้นคว้าเพิ่มเติม

### ขั้นตอนต่อไปคืออะไร?

* สำรวจ symbology บาร์โค้ดอื่น ๆ ด้วย `EncodeTypes` (เช่น QR, Code128) – เป็นการต่อยอดจาก workflow ของ **barcode generator c#**
* ผสานภาพที่สร้างกับรายงาน PDF หรือ Excel ด้วย Aspose.PDF หรือ Aspose.Cells
* ปรับสี, เพิ่มขอบ, หรือฝังบาร์โค้ดใน Web API เพื่อสร้างตามคำขอแบบเรียลไทม์

ลองปรับพารามิเตอร์ต่าง ๆ ดูได้เลย และให้โค้ดนี้เป็นพื้นฐานที่เชื่อถือได้สำหรับทุกโครงการที่เกี่ยวกับบาร์โค้ดของคุณ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}