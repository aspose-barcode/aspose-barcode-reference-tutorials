---
category: general
date: 2026-09-10
description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีสร้าง PDF417 และวิธีปรับขนาดบาร์โค้ดด้วย
  Aspose.BarCode เพียงไม่กี่บรรทัด
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: th
lastmod: 2026-09-10
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว บทเรียนนี้แสดงวิธีสร้าง
  PDF417 และวิธีปรับขนาดบาร์โค้ดโดยใช้ Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือการเขียนโปรแกรมครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: วิธีสร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือขั้นตอนโดยละเอียด
url: /th/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ใน C# – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นขั้นตอนที่แน่นอน คุณจะได้เห็นตัวอย่างสั้น ๆ ที่พร้อมรันซึ่งสร้างบาร์โค้ด PDF417 ให้คุณควบคุมขนาดของมันและบันทึกผลลัพธ์เป็นภาพ PNG

การสร้างบาร์โค้ด PDF417 เป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, บัตรโดยสาร, และการติดตามเอกสาร ในบทแนะนำนี้เรายังครอบคลุม **วิธีการเปลี่ยนขนาดบาร์โค้ด** เพื่อให้โค้ดปรับให้เข้ากับความต้องการการพิมพ์หรือการแสดงผลบนหน้าจอที่แตกต่างกัน

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.6+ ได้เช่นกัน)
* Visual Studio 2022 หรือ IDE สำหรับ C# ใด ๆ
* แพคเกจ **Aspose.BarCode for .NET** บน NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* ความคุ้นเคยพื้นฐานกับแอปพลิเคชันคอนโซล C#

## การตั้งค่าโปรเจกต์

1. สร้างโปรเจกต์คอนโซลใหม่:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. เพิ่มการอ้างอิง Aspose.BarCode (ดูข้อกำหนดเบื้องต้น).

3. เปิดไฟล์ `Program.cs` และแทนที่เนื้อหาด้วยตัวอย่างเต็มด้านล่าง

## ขั้นตอนที่ 1: สร้างบาร์โค้ด PDF417

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarcodeGenerator` ที่กำหนดค่าให้ใช้สัญลักษณ์ **PDF417** วัตถุนี้เป็นจุดเริ่มต้นสำหรับการทำงานกับบาร์โค้ดทั้งหมด

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*ทำไมสิ่งนี้ถึงสำคัญ* – ค่า enum `EncodeTypes.Pdf417` บอกให้ Aspose.BarCode ใช้มาตรฐาน PDF417, ส่วนอาร์กิวเมนต์ที่สองเป็นข้อมูลที่จะเข้ารหัส ตัวสร้างบาร์โค้ดจะมีอ็อบเจกต์บาร์โค้ดเต็มรูปแบบที่คุณสามารถปรับแต่งก่อนบันทึกได้

## ขั้นตอนที่ 2: วิธีเปลี่ยนขนาดบาร์โค้ด (ขนาดโมดูล)

บาร์โค้ด PDF417 ประกอบด้วยโมดูลสี่เหลี่ยมจัตุรัสขนาดเล็ก การปรับขนาดโมดูลจะเปลี่ยนมิติรวมของภาพโดยไม่กระทบต่อข้อมูลที่เข้ารหัส

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*ทำไมสิ่งนี้ถึงสำคัญ* – `XDimension` ที่ใหญ่ขึ้นจะให้บาร์โค้ดขนาดใหญ่ขึ้น เหมาะกับการพิมพ์ความละเอียดสูง; ค่าที่เล็กลงจะเหมาะกับการแสดงบนหน้าจอ ค่าเริ่มต้นมักเป็น 1 px ซึ่งอาจดูแออัดบนจอโมเดิร์น

## ขั้นตอนที่ 3: กำหนดรูปแบบ – จำนวนคอลัมน์และแถว

PDF417 อนุญาตให้คุณกำหนดจำนวนคอลัมน์และแถว ซึ่งส่งผลต่อรูปทรงของบาร์โค้ดและความสามารถในการแก้ไขข้อผิดพลาด

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*ทำไมสิ่งนี้ถึงสำคัญ* – คอลัมน์มากขึ้นทำให้บาร์โค้ดกว้างขึ้น, แถวมากขึ้นทำให้บาร์โค้ดสูงขึ้น ปรับค่าต่าง ๆ เพื่อให้พอดีกับพื้นที่ที่มีใน UI หรือป้ายพิมพ์ของคุณ

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด

สุดท้ายให้เขียนบาร์โค้ดลงไฟล์ ที่นี่เราใช้ PNG เนื่องจากรักษาความคมของขอบและรองรับความโปร่งใส

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

การรันโปรแกรมจะสร้างไฟล์ `LayoutPdf417.png` ในโฟลเดอร์เอาต์พุตของโปรเจกต์ ภาพจะมีลักษณะดังนี้:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="ตัวอย่างการสร้างบาร์โค้ด PDF417 แสดง 4 คอลัมน์และ 9 แถว"}

*เคล็ดลับ*: หากคุณต้องการรูปแบบภาพอื่น (JPEG, BMP, TIFF) ให้แทนที่ `BarCodeImageFormat.Png` ด้วยค่า enum ที่เหมาะสม

## วิธีสร้าง PDF417 – แหล่งข้อมูลทางเลือก

โค้ดด้านบนใช้สตริงที่กำหนดไว้ล่วงหน้า `"Layout test"` ในสถานการณ์จริงคุณมักดึงข้อมูลจากฐานข้อมูล, ไฟล์, หรืออินพุตของผู้ใช้

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

ขั้นตอนที่เหลือ (ขนาด, รูปแบบ, การบันทึก) ยังคงเหมือนเดิม นี่แสดงให้เห็น **วิธีสร้าง PDF417** จากแหล่งข้อมูลแบบไดนามิกโดยไม่ซับซ้อนเพิ่มเติม

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| บาร์โค้ดดูเบลอ | `XDimension` ตั้งค่าต่ำเกินไปสำหรับความละเอียดเอาต์พุต | เพิ่มค่า `XDimension.Pixels` หรือบันทึกเป็นรูปแบบเวกเตอร์เช่น SVG (`BarCodeImageFormat.Svg`) |
| ข้อความไม่พอดีกับรูปแบบที่เลือก | ตัวอักษรมากเกินไปสำหรับแถว/คอลัมน์ที่กำหนด | ลดจำนวนแถว/คอลัมน์ หรือแยกข้อมูลเป็นหลายบาร์โค้ด |
| ไม่สร้างไฟล์ภาพ | โฟลเดอร์เอาต์พุตไม่มีอยู่หรือไม่มีสิทธิ์เขียน | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่ (`Directory.CreateDirectory`) และแอปทำงานด้วยสิทธิ์ที่เหมาะสม |

## การตรวจสอบบาร์โค้ด

หลังจากสร้างภาพแล้ว คุณสามารถตรวจสอบได้โดยใช้แอปสแกน PDF417 ใด ๆ (โทรศัพท์มือถือมีสแกนเนอร์ฟรี) หรือใช้ตัวอ่าน Aspose.BarCode ที่มีในตัว:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

หากผลลัพธ์ตรงกับข้อความต้นฉบับ กระบวนการ **สร้างบาร์โค้ด PDF417** จะสำเร็จ

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอกและวางลงใน `Program.cs` ได้ รวมถึงคำสั่ง using ทั้งหมด, การจัดการข้อผิดพลาด, และคอมเมนต์

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

การรันโปรแกรมนี้จะแสดงผล:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

ตอนนี้คุณมี **โซลูชันครบวงจรและอิสระ** สำหรับการสร้างบาร์โค้ด PDF417 และการควบคุมขนาดของมัน

## สรุป

ในบทแนะนำนี้คุณได้เรียนรู้วิธี **สร้างบาร์โค้ด PDF417** ใน C# ด้วย Aspose.BarCode, วิธี **เปลี่ยนขนาดบาร์โค้ด** โดยปรับ X‑dimension, และวิธีกำหนดคอลัมน์และแถวเพื่อควบคุมรูปแบบ คุณยังได้เห็นวิธีตรวจสอบผลลัพธ์ด้วยโปรแกรมและวิธีปรับโค้ดให้ทำงานกับข้อมูลแบบไดนามิก

ต่อไปคุณอาจสำรวจ:

* **วิธีสร้าง PDF417** ด้วยการปรับระดับการแก้ไขข้อผิดพลาด (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* การส่งออกเป็น **รูปแบบเวกเตอร์** (SVG, EPS) เพื่อการขยายแบบไม่มีขีดจำกัด
* การฝังบาร์โค้ดในเอกสาร PDF ด้วย **Aspose.PDF**

ลองทดลองขนาดโมดูลและตัวเลือกรูปแบบต่าง ๆ เพื่อให้เหมาะกับ UI หรือความต้องการการพิมพ์ของคุณเอง ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด PDF417 ด้วย Aspose – คู่มือเต็ม](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [ปรับขนาดบาร์โค้ด – คู่มือ C# สำหรับสร้างบาร์โค้ด PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [วิธีบันทึกบาร์โค้ดใน C# – สร้างบาร์โค้ด PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}