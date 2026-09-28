---
category: general
date: 2026-08-22
description: วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode. เรียนรู้การสร้างภาพบาร์โค้ดด้วย
  C# ทีละขั้นตอน, ปิดการใช้งานส่วนประกอบ 2‑D, และบันทึกไฟล์ PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: th
lastmod: 2026-08-22
og_description: วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode. บทแนะนำนี้จะแสดงวิธีสร้างภาพบาร์โค้ดด้วย
  C# โดยใช้ DataBar Expanded, เปิด/ปิดส่วนประกอบ 2‑D, และบันทึกไฟล์ PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: วิธีสร้างบาร์โค้ดใน C# – คู่มือครบถ้วนสำหรับสร้างภาพบาร์โค้ดด้วย C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: วิธีสร้างบาร์โค้ดใน C# – สร้างภาพบาร์โค้ดด้วย DataBar Expanded ใน C#
url: /th/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดใน C# – สร้างภาพบาร์โค้ด c# ด้วย DataBar Expanded

การสร้างบาร์โค้ดใน C# เป็นความต้องการที่พบบ่อยเมื่อคุณต้องฝังข้อมูลที่เครื่องอ่านได้ลงในแอปพลิเคชันของคุณ คู่มือนี้จะแสดงวิธีสร้างภาพบาร์โค้ด c# ด้วยไลบรารี Aspose.BarCode, ปิดการใช้งานส่วนประกอบคอมโพสิต 2‑D, และบันทึกผลลัพธ์เป็นไฟล์ PNG

คุณจะได้เห็นโปรแกรมที่ทำงานได้เต็มรูปแบบ, คำอธิบายของแต่ละตัวเลือกการกำหนดค่า, และเคล็ดลับในการปรับแต่งผลลัพธ์ ไม่จำเป็นต้องอ้างอิงเอกสารภายนอก—เพียงโค้ดด้านล่างและสภาพแวดล้อมการพัฒนา .NET

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน, ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นใหม่กว่า ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE ใดก็ได้ที่รองรับ .NET)  
* แพ็กเกจ NuGet Aspose.BarCode สำหรับ .NET (`Aspose.BarCode`)  

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

ไลบรารีนี้ให้คลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียนนี้

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespace

สร้างแอปพลิเคชันคอนโซลใหม่และนำเข้า namespace ที่จำเป็น:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Namespace `Aspose.BarCode.Generation` มีคลาสทั้งหมดที่ต้องใช้ในการกำหนดค่าและเรนเดอร์บาร์โค้ด

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้างบาร์โค้ด DataBar Expanded

บรรทัดแรกที่ทำงานสร้าง `BarcodeGenerator` สำหรับสัญลักษณ์ **DataBar Expanded** และส่งสตริงข้อมูลดิบให้ สตริงข้อมูลนี้เป็นไปตามรูปแบบ GS1 Application Identifier `(01)12345678901231`

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

การสร้างตัวสร้างจะจัดสรรแคนวาสบิตแมพภายใน, ทำให้คุณสามารถปรับขนาดและลักษณะก่อนการเรนเดอร์ได้

## ขั้นตอนที่ 3: กำหนดความกว้างโมดูล (X‑dimension)

X‑dimension ควบคุมความกว้างขององค์ประกอบบาร์โค้ดที่เล็กที่สุด การตั้งค่าเป็นพิกเซลทำให้คุณควบคุมขนาดภาพสุดท้ายได้อย่างแม่นยำ

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

ค่าที่ `2` พิกเซลทำงานได้ดีสำหรับการแสดงบนหน้าจอ; เพิ่มค่านี้สำหรับการพิมพ์ความละเอียดสูง

## ขั้นตอนที่ 4: ปิดการใช้งานส่วนประกอบคอมโพสิต 2‑D

DataBar Expanded สามารถรวมส่วนประกอบ 2‑D ที่บรรจุข้อมูลเพิ่มเติมได้ หากต้องการสร้างบาร์โค้ด **โดยไม่มี**ส่วนประกอบนี้ ให้ตั้งค่าแฟล็กเป็น `false`

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

การปิดส่วนประกอบจะลดความซับซ้อนของภาพและทำให้ไฟล์ PNG มีขนาดเล็กลง

## ขั้นตอนที่ 5: บันทึกภาพบาร์โค้ดโดยไม่มีส่วนประกอบ 2‑D

เลือกไดเรกทอรีปลายทางและเขียนภาพลงดิสก์ enum `BarCodeImageFormat.Png` รับประกันไฟล์ PNG แบบไม่มีการสูญเสียคุณภาพ

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

หลังจากเรียกนี้แล้ว `Databar2DComponentDisabled.png` จะมีบาร์โค้ด DataBar Expanded ที่สะอาด

## ขั้นตอนที่ 6: เปิดใช้งานส่วนประกอบคอมโพสิต 2‑D

หากต้องการชั้นข้อมูลเพิ่มเติม, เปิดใช้งานแฟล็กอีกครั้ง ตัวสร้างเดียวกันสามารถใช้ซ้ำได้, ซึ่งช่วยหลีกเลี่ยงการสร้างออบเจกต์ใหม่

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## ขั้นตอนที่ 7: บันทึกภาพบาร์โค้ดพร้อมส่วนประกอบ 2‑D ที่เปิดใช้งาน

เรนเดอร์ภาพที่สองโดยใช้การตั้งค่าเดียวกัน, ยกเว้นแฟล็ก 2‑D

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

ตอนนี้ `Databar2DComponentEnabled.png` แสดงบาร์โค้ดพร้อมลวดลาย 2‑D เพิ่มเติม

## โค้ดต้นฉบับเต็ม

คัดลอกโค้ดทั้งหมดด้านล่างไปยัง `Program.cs` แล้วรันโปรเจกต์ โปรแกรมจะสร้างไฟล์ PNG ทั้งสองในโฟลเดอร์ที่คุณระบุ

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะพิมพ์:

```
Barcode images generated successfully.
```

และสร้างไฟล์สองไฟล์:

* `Databar2DComponentDisabled.png` – บาร์โค้ดโดยไม่มีส่วนประกอบ 2‑D  
* `Databar2DComponentEnabled.png` – บาร์โค้ดพร้อมส่วนประกอบ 2‑D  

เปิดไฟล์ PNG ใดก็ได้ในโปรแกรมดูรูปภาพเพื่อยืนยันความแตกต่างของภาพ

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับแต่ง |
|-----------|------------|
| **สัญลักษณ์ที่ต่างกัน** | แทนที่ `EncodeTypes.DatabarExpanded` ด้วยค่าที่อื่น เช่น `EncodeTypes.Code128`. |
| **ความละเอียดสูงขึ้น** | เพิ่มค่า `XDimension.Pixels` เป็น 4 หรือ 5 หรือกำหนด `Resolution` ใน `barcodeGenerator.Parameters.Image`. |
| **รูปแบบภาพอื่น** | ใช้ `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, หรือ `BarCodeImageFormat.Svg`. |
| **ทำงานในเว็บแอป** | สตรีมไบต์ของภาพโดยตรงไปยังการตอบสนอง HTTP แทนการบันทึกลงดิสก์. |
| **การจัดการหน่วยความจำ** | ห่อหุ้มตัวสร้างในบล็อก `using` หากคุณใช้ .NET Framework เพื่อให้แน่ใจว่าทรัพยากรที่ไม่ได้จัดการจะถูกปล่อย. |

## เคล็ดลับระดับมืออาชีพ

* **ใช้ตัวสร้างซ้ำ** – การเปลี่ยนแค่แฟล็ก 2‑D จะหลีกเลี่ยงการสร้างออบเจกต์ใหม่ ซึ่งช่วยประหยัดวงจร CPU.  
* **ตรวจสอบข้อมูล** – ข้อมูล GS1 ต้องเป็นไปตามความยาวและกฎตรวจสอบผลรวมที่แน่นอน; อินพุตที่ไม่ถูกต้องจะทำให้เกิด `ArgumentException`.  
* **การประมวลผลแบบชุด** – วนลูปผ่านคอลเลกชันของสตริงข้อมูล, สลับแฟล็ก 2‑D ตามต้องการ, และบันทึกแต่ละภาพด้วยชื่อไฟล์ที่ไม่ซ้ำกัน.  

## สรุป

คุณได้เรียนรู้วิธีสร้างบาร์โค้ดใน C# และสร้างภาพบาร์โค้ด c# พร้อมการควบคุมส่วนประกอบคอมโพสิต 2‑D อย่างเต็มที่ ตัวอย่างนี้แสดงการเริ่มต้นตัวสร้าง, กำหนดค่า X‑dimension, สลับส่วนประกอบ, และบันทึกไฟล์ PNG จากนี้คุณสามารถสำรวจสัญลักษณ์อื่น ๆ, ฝังภาพลงใน PDF, หรือรวมการสร้างบาร์โค้ดเข้าในบริการ ASP.NET Core ได้

--- 

*ขั้นตอนต่อไป*: ลองสร้าง QR code, ทดลองกับความละเอียดภาพที่ต่างกัน, หรือฝัง PNG ที่สร้างขึ้นลงใน PDF ด้วย Aspose.PDF. ส่วนขยายเหล่านี้สร้างบน API `BarcodeGenerator` เดียวกันและทำให้กระบวนการทำงานของคุณสอดคล้องกัน

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/datamatrix-barcode-configuration/)
- [วิธีสร้างและปรับความสูงของบาร์โค้ด One-Dimensional Databar ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}