---
category: general
date: 2026-09-23
description: บทแนะนำการสร้างบาร์โค้ดด้วย C# แสดงวิธีการสร้างภาพบาร์โค้ดที่มีอัตราส่วนภาพกำหนดเองโดยใช้ไลบรารี
  Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: th
lastmod: 2026-09-23
og_description: คู่มือการสร้างบาร์โค้ดด้วย C# จะพาคุณผ่านขั้นตอนการสร้างภาพบาร์โค้ด
  ปรับอัตราส่วนภาพ และส่งออกไฟล์ PNG โดยใช้ Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: สร้างบาร์โค้ดคุณภาพสูงด้วยเครื่องสร้างบาร์โค้ด C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: วิธีใช้ตัวสร้างบาร์โค้ด C# สำหรับรหัส DataBar
url: /th/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ตัวสร้างบาร์โค้ด C# สำหรับรหัส DataBar

หากคุณต้องการ **c# barcode generator** ที่สามารถสร้างสัญลักษณ์ DataBar stacked Omni‑Directional ได้ คู่มือนี้จะให้โซลูชันที่พร้อมใช้งานและทำงานได้ทันที คุณจะได้เห็นวิธีสร้างภาพบาร์โค้ด, ควบคุม X‑dimension, และเปลี่ยนอัตราส่วนภาพโดยไม่ต้องออกจาก IDE

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, ป้ายจัดส่ง, และแอปพลิเคชันจุดขาย (POS) เมื่อจบบทเรียนนี้คุณจะสามารถสร้างไฟล์ PNG ด้วยอัตราส่วนใดก็ได้ที่คุณเลือก และคุณจะเข้าใจวิธีปรับโค้ดสำหรับประเภทบาร์โค้ดอื่น ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* Visual Studio 2022 (หรือโปรแกรมแก้ไข C# ใด ๆ ที่คุณชอบ)  
* การอ้างอิง NuGet ไปยัง **Aspose.BarCode** – ไลบรารีที่ให้บริการคลาส `BarcodeGenerator`

คุณไม่จำเป็นต้องใช้ไลบรารีกราฟิกแยกต่างหาก; Aspose.BarCode จะจัดการการเข้ารหัสภาพภายในเอง

## ขั้นตอนที่ 1: ติดตั้งแพคเกจ NuGet ของ Aspose.BarCode

เปิดเทอร์มินัลในโฟลเดอร์โปรเจกต์ของคุณและรัน:

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่มเวอร์ชันล่าสุดของไลบรารีลงในไฟล์โปรเจกต์ของคุณ ทำให้คลาส `BarcodeGenerator` พร้อมใช้งาน

## ขั้นตอนที่ 2: กำหนดโฟลเดอร์สำหรับบันทึกผลลัพธ์

เลือกโฟลเดอร์ที่ไฟล์ PNG ที่สร้างขึ้นจะถูกบันทึก การใช้เส้นทางแบบ absolute หรือ relative ทำงานได้เช่นกัน แต่เส้นทางแบบ relative จะทำให้โปรเจกต์พกพาง่ายขึ้น

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

การสร้างโฟลเดอร์โดยโปรแกรมจะช่วยป้องกันข้อผิดพลาดในระหว่างรัน หากโฟลเดอร์ไม่มีอยู่

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของตัวสร้างบาร์โค้ด C# พร้อมข้อมูลตัวอย่าง

คอนสตรัคเตอร์ `BarcodeGenerator` ต้องการอาร์กิวเมนต์สองค่า: ประเภทบาร์โค้ดและสตริงข้อมูล สำหรับสัญลักษณ์ DataBar stacked Omni‑Directional ให้ใช้ `EncodeTypes.DatabarStackedOmniDirectional`

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

สตริงข้อมูลต้องเป็นไปตามรูปแบบ GS1 Application Identifier ค่าตัวแปร `EncodeTypes` มีมากกว่า 150 มาตรฐานบาร์โค้ด; คุณสามารถเปลี่ยนเป็นประเภทอื่นได้โดยเปลี่ยนค่า enum

## ขั้นตอนที่ 4: ตั้งค่า X‑dimension (ขนาดพิกเซล) ของบาร์โค้ด

X‑dimension ควบคุมความกว้างของบาร์ที่แคบที่สุด ค่า 2 พิกเซลจะให้ภาพคมชัดและความละเอียดสูง เหมาะกับหน้าจอส่วนใหญ่

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

การปรับ X‑dimension เป็นขั้นตอนเสริม แต่ช่วยให้คุณควบคุมความหนาแน่นของบาร์โค้ดได้อย่างละเอียด

## ขั้นตอนที่ 5: สร้างบาร์โค้ดด้วยอัตราส่วน 15 และบันทึกเป็น PNG

คุณสมบัติ `AspectRatio` อยู่ในอ็อบเจ็กต์ย่อย `DataBar` การเปลี่ยนค่าจะยืดหรือบีบบาร์โค้ดในแนวตั้งโดยยังคงข้อมูลที่เข้ารหัสไว้เดิม

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนบาร์โค้ดลงไฟล์ที่ระบุ `BarCodeImageFormat.Png` ทำให้บีบอัดแบบ lossless

![c# barcode generator output example](generated_barcode_example.png)

*Image: barcode generated with an aspect ratio of 15.*

## ขั้นตอนที่ 6: เปลี่ยนอัตราส่วนเป็น 30 และสร้างภาพที่สอง

การใช้อินสแตนซ์ `BarcodeGenerator` เดิมจะช่วยหลีกเลี่ยงการสร้างอ็อบเจ็กต์ใหม่ เพียงอัปเดต `AspectRatio` แล้วเรียก `Save` อีกครั้ง

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณจะมีไฟล์ PNG สองไฟล์ที่แตกต่างกันเฉพาะการสเกลในแนวตั้ง เทคนิคนี้มีประโยชน์เมื่อคุณต้องการใช้ข้อมูลเดียวกันสำหรับป้ายขนาดต่าง ๆ

## ความแปรผันทั่วไปและกรณีขอบ

### สลับไปใช้ประเภทบาร์โค้ดอื่น

หากต้องการ QR code, Code 128 หรือ PDF417 ให้เปลี่ยนค่า enum ในคอนสตรัคเตอร์:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

ขั้นตอนการตั้งค่าอื่น ๆ (X‑dimension, การบันทึก) ยังคงเหมือนเดิม

### จัดการกับอักขระที่ไม่รองรับ

`BarcodeGenerator` จะตรวจสอบสตริงอินพุตตามสัญลักษณ์ที่เลือก หากมีอักขระผิดกฎหมายจะเกิด `ArgumentException` ให้ใส่โค้ดในบล็อก try‑catch เพื่อแสดงข้อความข้อผิดพลาดที่เป็นมิตร:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### ส่งออกเป็นรูปแบบภาพอื่น

Aspose.BarCode รองรับ BMP, JPEG, TIFF, และ SVG ให้เปลี่ยนอาร์กิวเมนต์ที่สองของ `Save` ตามต้องการ:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### ผลลัพธ์ความละเอียดสูงสำหรับการพิมพ์

เมื่อพิมพ์บนเครื่องพิมพ์ DPI สูง ให้เพิ่ม X‑dimension และอาจตั้งค่า `Resolution` เพิ่มเติม:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

การตั้งค่านี้จะทำให้ไฟล์ใหญ่ขึ้นแต่คงความคมชัดบนสื่อฟิสิคัล

## ผลลัพธ์ที่คาดหวัง

เมื่อรันโปรแกรมเต็มรูปแบบ จะสร้างไฟล์ต่อไปนี้ในโฟลเดอร์ `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – รหัส DataBar ความสูงมาตรฐาน  
* `DatabarAspectRatio30.png` – เวอร์ชันที่ยืดในแนวตั้ง  

ทั้งสองภาพมีข้อมูล GS1 เดียวกัน และคุณสามารถตรวจสอบได้ด้วยแอปสแกนบาร์โค้ดใดก็ได้

## โค้ดเต็ม

คัดลอกโค้ดด้านล่างไปยังโปรเจกต์คอนโซลใหม่ (`dotnet new console`) แล้วรัน โปรแกรมจะพิมพ์ข้อความสถานะบนคอนโซลและบันทึกไฟล์ PNG ลงดิสก์

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

การรันโปรแกรมจะให้ผลลัพธ์บนคอนโซลคล้ายกับ:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## สรุป

ตอนนี้คุณมี **c# barcode generator** ที่สามารถสร้างสัญลักษณ์ DataBar stacked Omni‑Directional, ปรับ X‑dimension, และส่งออกไฟล์ PNG ด้วยอัตราส่วนที่กำหนดเอง รูปแบบเดียวกันนี้ทำงานได้กับสัญลักษณ์บาร์โค้ดอื่น ๆ ที่ Aspose.BarCode รองรับ ทำให้การรวมการสร้างบาร์โค้ดเข้าไปในระบบสินค้าคงคลัง, การจัดส่ง, หรือ POS เป็นเรื่องง่าย

หากต้องการสำรวจต่อไป ลองทำ:

* สร้าง QR code หรือสัญลักษณ์ PDF417 (`how to generate barcode` สำหรับแอปมือถือ)  
* ส่งออกเป็น SVG เพื่อกราฟิกเว็บที่ปรับขนาดได้  
* ฝังภาพที่สร้างลงในใบแจ้งหนี้ PDF โดยใช้ Aspose.PDF  

ทดลองเปลี่ยนค่า `AspectRatio`, ขนาด X‑dimension, และรูปแบบผลลัพธ์เพื่อให้ตรงกับความต้องการของคุณอย่างแม่นยำ


## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณเอง

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}