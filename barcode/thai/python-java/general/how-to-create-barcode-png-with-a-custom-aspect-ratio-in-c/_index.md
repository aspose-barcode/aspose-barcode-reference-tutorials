---
category: general
date: 2026-10-05
description: สร้าง PNG ของบาร์โค้ดด้วย C# และเรียนรู้วิธีตั้งอัตราส่วน 15 สำหรับบาร์โค้ด
  DataBar แบบซ้อนที่มีทิศทางหลายทิศทาง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: th
lastmod: 2026-10-05
og_description: สร้างไฟล์ PNG ของบาร์โค้ดด้วย C# และค้นหาวิธีตั้งอัตราส่วน 15 สำหรับบาร์โค้ด
  DataBar แบบซ้อนแนวหลายทิศทางในไม่กี่ขั้นตอน
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: สร้างบาร์โค้ด PNG ใน C# – ตั้งอัตราส่วน 15 การสอน
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: วิธีสร้าง PNG ของบาร์โค้ดด้วยอัตราส่วนที่กำหนดเองใน C#
url: /th/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ PNG ของบาร์โค้ดพร้อมอัตราส่วนภาพที่กำหนดใน C#

หากคุณต้องการ **สร้างไฟล์ PNG ของบาร์โค้ด** ด้วย C# คู่มือนี้จะแสดง **วิธีตั้งค่าอัตราส่วนภาพ** 15 สำหรับบาร์โค้ด DataBar stacked omnidirectional เราจะอธิบายแต่ละการเรียก API ทำไมอัตราส่วนภาพถึงสำคัญ และให้ตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบที่คุณสามารถนำไปใส่ในโปรเจกต์ .NET ใดก็ได้

การสร้างภาพบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง ป้ายจัดส่ง และแอปพลิเคชันจุดขายของร้านค้า เมื่อจบบทเรียนนี้คุณจะได้ไฟล์ PNG ที่ตรงตามสเปคภาพที่คู่ค้าทางธุรกิจของคุณกำหนด ไม่ต้องใช้เครื่องมือภายนอก ไม่ต้องแก้ไขภาพด้วยมือ—เพียงแค่โค้ด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมี:

* .NET 6.0 หรือใหม่กว่า (ตัวอย่างใช้ .NET 6 แต่ทำงานได้กับ .NET 5+)
* Visual Studio 2022 (หรือ IDE ใดก็ได้ที่รองรับ .NET)
* แพ็กเกจ NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* สิทธิ์การเขียนในโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ PNG

ข้อกำหนดเหล่านี้เป็นขั้นต่ำ; โค้ดเดียวกันทำงานได้ใน .NET Core, .NET Framework หรือแอปพลิเคชันคอนโซล

## สร้างไฟล์ PNG ของบาร์โค้ดด้วย Aspose.BarCode

ขั้นตอนแรกคือการสร้างอ็อบเจ็กต์ `BarcodeGenerator` ด้วยชนิดบาร์โค้ดที่ถูกต้อง ในกรณีนี้เราใช้ `EncodeTypes.DatabarStackedOmniDirectional` ซึ่งสร้าง DataBar แบบ stacked ที่สามารถอ่านได้จากทุกทิศทาง

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*ทำไมจึงสำคัญ:* ตัวสร้างรับอาร์กิวเมนต์สองค่า—**สัญลักษณ์บาร์โค้ด** และ **สตริงข้อมูล** ฟอร์แมต DataBar ต้องการตัวระบุแอปพลิเคชัน GS1 จึงทำให้ข้อมูลตัวอย่างเริ่มต้นด้วย `(01)`

## วิธีตั้งค่าอัตราส่วนภาพสำหรับ DataBar stacked

ความกว้างของ DataBar ถูกควบคุมโดยคุณสมบัติ **aspect ratio** อัตราส่วนที่สูงกว่าจะทำให้บาร์กว้างขึ้น ซึ่งช่วยเพิ่มความน่าเชื่อถือในการสแกนบนเครื่องพิมพ์ความละเอียดต่ำ

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` กำหนดขนาดของโมดูลเดียว (บาร์หรือช่องว่างที่เล็กที่สุด) การตั้งค่าเป็น 2 px จะให้ภาพคมชัดและความหนาแน่นสูง เหมาะกับเครื่องพิมพ์ป้ายส่วนใหญ่

## ตั้งค่าอัตราส่วนภาพ 15 – การอธิบายโค้ด

ต่อไปเราจะนำ **การตั้งค่าอัตราส่วนภาพ 15** ไปใช้ นี่คือหัวใจของบทเรียนและแสดงการเรียก API ที่ต้องทำอย่างแม่นยำ

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*ทำไมต้องเป็น 15?* ค่าอัตราส่วนเริ่มต้นของ DataBar stacked คือ 12 การเพิ่มเป็น 15 จะขยายความกว้างของแต่ละบาร์ประมาณ 25 % ซึ่งมักตรงกับสเปคของผู้ให้บริการโลจิสติกส์ที่ต้องการบาร์โค้ดกว้างเพื่อการสแกนที่เร็วขึ้น

## บันทึกบาร์โค้ดเป็น PNG

เมื่อกำหนดค่าตัวสร้างแล้ว ขั้นตอนสุดท้ายคือการบันทึกภาพลงดิสก์ วิธี `Save` รับพาธไฟล์และรูปแบบภาพเป็น enum

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

รูปแบบ PNG รักษาคุณภาพแบบ lossless ทำให้บาร์โค้ดแสดงผลตรงตามที่ออกแบบบนหน้าจอหรือเครื่องพิมพ์ใดก็ได้

## ตัวอย่างเต็มและผลลัพธ์ที่คาดหวัง

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอกไปวางในเมธอด `Main` ของแอปคอนโซล รวมขั้นตอนทั้งหมดที่อธิบายไว้ข้างต้น พร้อมข้อความยืนยันสั้น ๆ

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

เมื่อรันโปรแกรมจะสร้างไฟล์ชื่อ `DatabarAspectRatio15.png` ที่มีบาร์โค้ด DataBar stacked ชัดเจนและกว้าง เมื่อเปิดไฟล์ PNG คุณจะเห็นบาร์โค้ดที่ยืดแนวนอนแต่ยังคงสอดคล้องกับสเปค GS1 DataBar

![สร้างไฟล์ PNG ของบาร์โค้ดที่แสดง DataBar stacked พร้อมอัตราส่วนภาพ 15](barcode-aspect15.png)

*ข้อความแทนภาพ:* **สร้างไฟล์ PNG ของบาร์โค้ดที่แสดง DataBar stacked พร้อมอัตราส่วนภาพ 15**

### เคล็ดลับและข้อผิดพลาดทั่วไป

| สถานการณ์ | คำแนะนำ |
|-----------|----------|
| **ภาพดูเบลอ** | เพิ่ม `XDimension.Pixels` เป็น 3 px หรือมากกว่า แต่ให้ขนาดภาพรวมไม่เกิน 500 px เพื่อหลีกเลี่ยงไฟล์ขนาดใหญ่ |
| **สแกนเนอร์อ่านไม่ออก** | ตรวจสอบว่าสตริงข้อมูลเป็นไปตามรูปแบบ GS1 (`(01)` prefix) และตรวจสอบว่าเครื่องพิมพ์มีความละเอียดอย่างน้อย 300 dpi |
| **ต้องการรูปแบบไฟล์อื่น** | แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Gif` — API รองรับรูปแบบเรสเตอร์หลักทั้งหมด |
| **ใช้งานในเว็บแอป** | ใช้ `generator.Save(Stream, BarCodeImageFormat.Png)` เพื่อเขียนโดยตรงไปยัง HTTP response โดยไม่ต้องบันทึกไฟล์ |

### การขยายตัวอย่าง

* **หลายบาร์โค้ดในหนึ่งภาพ:** สร้างอ็อบเจ็กต์ `BarcodeGenerator` เพิ่มเติมและวาดลงบน `Bitmap` เดียวโดยใช้ `Graphics` |
* **เพิ่มข้อความที่อ่านได้โดยมนุษย์:** ตั้งค่า `generator.Parameters.Caption.Visible = true` และปรับฟอนต์ผ่าน `generator.Parameters.Caption.Font` |
* **อัตราส่วนภาพแบบไดนามิก:** ดึงค่าตัวแปรอัตราส่วนจากไฟล์คอนฟิกหรือฐานข้อมูลเพื่อสร้างบาร์โค้ดที่มีความกว้างต่างกันตามต้องการ |

## สรุป

ในบทเรียนนี้คุณได้เรียนรู้วิธี **สร้างไฟล์ PNG ของบาร์โค้ด** ด้วย C# และตั้งค่า **อัตราส่วนภาพ** 15 อย่างแม่นยำสำหรับบาร์โค้ด DataBar stacked omnidirectional โค้ดที่ทำงานได้เต็มรูปแบบแสดงการเรียก API ทุกขั้นตอน อธิบายเหตุผลของแต่ละการตั้งค่า และให้เคล็ดลับการใช้งานจริงสำหรับการนำไปใช้ในสภาพแวดล้อมจริง  

ต่อไปคุณอาจสำรวจ **วิธีตั้งค่าอัตราส่วนภาพ** สำหรับประเภทบาร์โค้ดอื่น ๆ (เช่น QR Code หรือ Code 128) หรือรวมตัวสร้างเข้ากับบริการ ASP .NET Core ที่ส่งภาพบาร์โค้ดตามคำขอได้ตามต้องการ ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}