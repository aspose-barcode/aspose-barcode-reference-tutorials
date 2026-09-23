---
category: general
date: 2026-07-27
description: สร้างภาพบาร์โค้ดแบบหลายทิศทางโดยใช้ Aspose.BarCode เรียนรู้วิธีสร้างบาร์โค้ดด้วย
  Aspose ปรับอัตราส่วนภาพ และบันทึกเป็นไฟล์ PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: th
lastmod: 2026-07-27
og_description: สร้างภาพบาร์โค้ดแบบหลายทิศทางด้วย Aspose. ทำตามคู่มือนี้เพื่อสร้างบาร์โค้ดด้วย
  Aspose, ปรับอัตราส่วนภาพ, และส่งออกเป็น PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: สร้างภาพบาร์โค้ดแบบหลายทิศทางด้วย Aspose – ทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: สร้างภาพบาร์โค้ดแบบหลายทิศทางด้วย Aspose – คู่มือเต็ม
url: /th/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดแบบหลายทิศทางด้วย Aspose – คู่มือเต็ม

เคยต้องการ **สร้างภาพบาร์โค้ดแบบหลายทิศทาง** แต่ไม่แน่ใจว่าจะเลือกไลบรารีใดใช่ไหม? คุณไม่ได้เป็นคนเดียว ในหลายโครงการโลจิสติกส์และค้าปลีก ฟอร์แมต DataBar Stacked Omnidirectional คือเคล็ดลับสำหรับการเข้ารหัสที่กะทัดรัดและความหนาแน่นสูง.  

ข่าวดีคืออะไร? ด้วย **Aspose.BarCode** คุณสามารถสร้างบาร์โค้ดนั้นได้ในไม่กี่บรรทัด ปรับอัตราส่วนภาพได้ และบันทึกไฟล์ PNG ลงดิสก์โดยตรง ด้านล่างคุณจะได้เห็นวิธี **generate barcode with Aspose** อย่างละเอียด ทำไมแต่ละการตั้งค่าถึงสำคัญ และสิ่งที่ควรระวังเมื่อเปลี่ยนอัตราส่วนภาพ.

---

## สิ่งที่บทเรียนนี้ครอบคลุม

เราจะเดินผ่านวงจรชีวิตทั้งหมด:

1. ตั้งค่าโฟลเดอร์ผลลัพธ์
2. สร้างอินสแตนซ์ของตัวสร้าง DataBar Stacked Omnidirectional
3. กำหนดขนาดพิกเซลและอัตราส่วนภาพ
4. บันทึกบาร์โค้ดเป็นไฟล์ PNG
5. ขยายตัวอย่างเพื่อรองรับรูปแบบอื่นและกรณีขอบ

เมื่อจบคุณจะมีแอปคอนโซล C# ที่พร้อมทำงานและสร้างภาพบาร์โค้ดสองแบบที่แตกต่างกัน ไม่ต้องใช้เครื่องมือภายนอก เพียงโค้ด Aspose อย่างเดียว

**ข้อกำหนดเบื้องต้น**

- .NET 6.0 SDK หรือเวอร์ชันใหม่กว่า (โค้ดนี้ทำงานบน .NET Framework 4.7.2 ได้เช่นกัน)
- NuGet package Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`).
- โฟลเดอร์บนดิสก์ที่สามารถเขียนภาพได้

หากคุณมีทั้งหมดแล้ว ไปต่อกันเลย.

## ขั้นตอนที่ 1: เตรียมโฟลเดอร์ผลลัพธ์

สิ่งแรกที่ต้องทำ—บอกโปรแกรมว่าจะบันทึกไฟล์ PNG ที่ไหน การกำหนดค่าพาธแบบคงที่ทำได้สำหรับการสาธิต แต่ในสภาพการผลิตคุณอาจอ่านค่าจากการตั้งค่า.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*ทำไมสิ่งนี้ถึงสำคัญ:* `Directory.CreateDirectory` เป็น idempotent; จะไม่เกิดข้อผิดพลาดหากโฟลเดอร์มีอยู่แล้ว ทำให้คุณไม่ต้องใช้บล็อก try‑catch.

## ขั้นตอนที่ 2: สร้างตัวสร้าง DataBar Stacked Omnidirectional

ตอนนี้เราจะสร้างตัวสร้างด้วยประเภทการเข้ารหัสและข้อมูลตัวอย่างที่ระบุ สตริง `"(01)12345678901231"` ปฏิบัติตามไวยากรณ์ GS1 Application Identifier สำหรับ GTIN 14 หลัก.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*คำอธิบาย:* `EncodeTypes.DatabarStackedOmniDirectional` บอก Aspose ให้ใช้รูปแบบ omnidirectional ซึ่งสามารถอ่านได้จากทุกทิศทาง—เหมาะสำหรับป้ายเล็กที่อาจถูกหมุน.

## ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์บาร์โค้ดทั่วไป

ก่อนที่เราจะเรนเดอร์อะไรเลย เราจะกำหนดขนาดองค์ประกอบที่เล็กที่สุด (X‑Dimension) ค่า **2 พิกเซล** จะให้ภาพคมชัดโดยไม่ทำให้ไฟล์ใหญ่ขึ้น.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*เคล็ดลับ:* หากต้องการความละเอียดสูงขึ้นสำหรับการพิมพ์ ให้เพิ่มค่าเป็น 3 หรือ 4 จำไว้ว่า X‑Dimension ที่ใหญ่ขึ้นจะเพิ่มความกว้างและความสูงอย่างสัดส่วน.

## ขั้นตอนที่ 4: สร้างและบันทึกด้วย Aspect Ratio 15

ตระกูล DataBar ให้คุณปรับ **aspect ratio** ซึ่งควบคุมความสัมพันธ์ระหว่างความสูงและความกว้าง อัตราส่วน **15** เป็นค่าเริ่มต้นที่นิยมสำหรับบาร์โค้ดแบบหลายทิศทาง.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*สิ่งที่คุณจะเห็น:* บาร์โค้ดที่ค่อนข้างสูงแต่ยังพอดีกับป้ายขนาด 2 × 1 ซม. รูปแบบ PNG รักษาคุณภาพ lossless เหมาะสำหรับการประมวลผลหรือพิมพ์ต่อ.

## ขั้นตอนที่ 5: เปลี่ยน Aspect Ratio เป็น 30 และบันทึกอีกครั้ง

ต้องการบาร์โค้ดที่กว้างกว่าหรือสั้นลง? เพียงปรับคุณสมบัติ `AspectRatio` แล้วเรียก `Save` อีกครั้ง ไม่จำเป็นต้องสร้างตัวสร้างใหม่.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*ทำไมต้องใช้ตัวสร้างเดียวกัน?* วัตถุ Aspose มีน้ำหนักเบา; การเปลี่ยนคุณสมบัติและบันทึกใหม่เร็วกว่าการสร้างอินสแตนซ์ใหม่ และรับประกันว่าการตั้งค่าการเข้ารหัสเดียวกัน (เช่น X‑Dimension) จะคงที่.

## ตัวอย่างทำงานเต็มรูปแบบ

รวมทุกอย่างเข้าด้วยกัน นี่คือโปรแกรมที่สมบูรณ์และอิสระที่คุณสามารถคัดลอกและวางลงในโปรเจคคอนโซลใหม่ได้.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

เมื่อรันโปรแกรมจะสร้างโฟลเดอร์ย่อย `Barcodes` ที่มี:

- `DatabarAspectRatio15.png` – สูงกว่า, รูปแบบคลาสสิก
- `DatabarAspectRatio30.png` – แบนกว่า, เหมาะกับป้ายกว้าง

ภาพทั้งสองแสดงข้อมูล GTIN เดียวกัน; เพียงอัตราส่วนภาพที่แตกต่าง.

## การขยายตัวอย่าง (กรณีขอบและความหลากหลาย)

### 1. รูปแบบภาพต่าง ๆ

Aspose รองรับ BMP, JPEG, TIFF, และ SVG นอกเหนือจาก PNG ให้สลับค่า enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG เป็นแบบเวกเตอร์ หมายความว่าคุณสามารถปรับขนาดได้โดยไม่เสียความคม—สะดวกสำหรับเว็บแอปที่ตอบสนอง.

### 2. ปรับแต่งสี

คุณอาจต้องการบาร์โค้ดสีขาวบนพื้นหลังสีเข้ม ตั้งค่า `ForeColor` และ `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. การจัดการ Aspect Ratio ที่ไม่ถูกต้อง

Aspose ตรวจสอบช่วงค่า (โดยทั่วไป 5‑50) หากส่งค่าที่อยู่นอกช่วง จะเกิด `ArgumentException` ให้ห่อการเรียก `Save` ด้วย try‑catch เพื่อแสดงข้อความที่เป็นมิตร:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. การสร้างเป็นชุด

เมื่อคุณมีรายการ GTIN ให้วนลูปแต่ละรายการ ปรับ `CodeText` และบันทึกไฟล์แต่ละไฟล์ด้วยชื่อที่ไม่ซ้ำกัน วัตถุตัวสร้างสามารถใช้ซ้ำได้ ทำให้การใช้หน่วยความจำต่ำ.

## ข้อผิดพลาดทั่วไปและเคล็ดลับระดับมืออาชีพ

- **ห้ามลืมตั้งค่า `XDimension`** ก่อนบันทึก; ค่าเริ่มต้น (0.33 mm) อาจทำให้ภาพเบลอบนจอแสดงผลความละเอียดต่ำ
- **Aspect ratio คือ ความสูงต่อความกว้าง**, ไม่ใช่กลับกัน ค่าใหญ่ทำให้บาร์โค้ด *สั้นลง* แนวตั้ง
- **พาธไฟล์:** ใช้ `Path.Combine` เพื่อหลีกเลี่ยงปัญหาตัวคั่นที่แตกต่างตามแพลตฟอร์ม—โดยเฉพาะหากโค้ดทำงานบนคอนเทนเนอร์ Linux
- **การให้ลิขสิทธิ์:** Aspose.BarCode เป็นผลิตภัณฑ์เชิงพาณิชย์ ในโหมดทดลองจะมีลายน้ำบนภาพ ลงทะเบียนลิขสิทธิ์ตั้งแต่ต้นเพื่อหลีกเลี่ยงความประหลาดใจในสภาพการผลิต

## สรุป

ตอนนี้คุณรู้วิธี **สร้างภาพบาร์โค้ดแบบหลายทิศทาง** ด้วย Aspose ปรับอัตราส่วนภาพ และส่งออกไฟล์ PNG—ทั้งหมดในน้อยกว่า 30 บรรทัดของ C# บทเรียนนี้แสดงขั้นตอนอย่างละเอียด อธิบายว่าทำไมแต่ละการตั้งค่าถึงสำคัญ และครอบคลุมการขยายเช่นรูปแบบต่าง ๆ สี และการประมวลผลเป็นชุด

พร้อมสำหรับความท้าทายต่อไปหรือยัง? ลองสร้าง QR code, ฝังบาร์โค้ดใน PDF, หรือรวมผลลัพธ์เข้ากับ ASP.NET Core API หลักการ **generate barcode with Aspose** เดียวกันใช้ได้กับบาร์โค้ดทุกประเภท ดังนั้นคุณสามารถใช้สิ่งที่เรียนรู้วันนี้ซ้ำได้

มีคำถามหรืออยากแชร์การปรับแต่งของคุณ? แสดงความคิดเห็นด้านล่าง—ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้ทางเลือกในโครงการของคุณ.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}