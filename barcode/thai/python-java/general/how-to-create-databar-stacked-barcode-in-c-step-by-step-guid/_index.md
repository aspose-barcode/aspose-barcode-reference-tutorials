---
category: general
date: 2026-10-21
description: สร้างบาร์โค้ด Databar แบบซ้อนกันอย่างรวดเร็วด้วย C#. เรียนรู้การตั้งค่า
  X‑dimension ปรับอัตราส่วนภาพ และบันทึกภาพ PNG ในบทเรียนฉบับเต็มนี้.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: th
lastmod: 2026-10-21
og_description: สร้างบาร์โค้ด Databar แบบซ้อนกันใน C# ด้วย Aspose.BarCode. ทำตามคำแนะนำนี้เพื่อกำหนดค่า
  X‑dimension, เปลี่ยนอัตราส่วนภาพ, และส่งออกไฟล์ PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: สร้างบาร์โค้ด Databar แบบซ้อนใน C# – คู่มือการเขียนโปรแกรมฉบับเต็ม
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: วิธีสร้างบาร์โค้ด Databar แบบซ้อนใน C# – คู่มือแบบทีละขั้นตอน
url: /th/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง databar stacked barcode ใน C# – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **create databar stacked barcode** ในแอปพลิเคชัน .NET นี้ คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียด คุณจะได้เรียนรู้วิธีกำหนดค่า X‑dimension, เปลี่ยนอัตราส่วนภาพ, และบันทึกบาร์โค้ดเป็นไฟล์ PNG.

การสร้าง DataBar stacked barcode ไม่ต้องการ pipeline การสร้างที่ซับซ้อน คู่มือนี้ครอบคลุมทุกอย่างที่คุณต้องการ: แพ็กเกจที่จำเป็น, การอธิบายโค้ดทีละบรรทัด, และเคล็ดลับสำหรับปัญหาที่พบบ่อย เมื่อเสร็จสิ้นคุณจะสามารถสร้างภาพบาร์โค้ดหลายรูปแบบที่มีอัตราส่วนภาพต่างกันในเมธอดเดียวได้.

## สิ่งที่คุณต้องมี

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ C#)  
* **Aspose.BarCode for .NET** NuGet package – ไลบรารีที่ให้ `BarcodeGenerator` และ `EncodeTypes`  

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespaces

สร้างโปรเจกต์คอนโซลใหม่หรือเพิ่มโค้ดลงในโปรเจกต์ที่มีอยู่แล้ว นำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้จักคลาสบาร์โค้ด

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

คำสั่ง `using` เหล่านี้ทำให้เข้าถึง `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat` ที่จะใช้ในตัวอย่างต่อไป

## ขั้นตอนที่ 2: กำหนดโฟลเดอร์สำหรับผลลัพธ์

เลือกโฟลเดอร์ที่ไฟล์ PNG ที่สร้างขึ้นจะถูกเขียนลงไป การใช้พาธแบบเต็มหรือแบบสัมพันธ์ทำงานเช่นเดียวกัน; ตัวอย่างใช้โฟลเดอร์สัมพันธ์ชื่อ `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

การสร้างโฟลเดอร์โดยโปรแกรมช่วยป้องกันข้อผิดพลาดขณะรันเมื่อไดเรกทอรีไม่มีอยู่

## ขั้นตอนที่ 3: เริ่มต้นตัวสร้าง **create databar stacked barcode**

สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วย `EncodeTypes.DatabarStackedOmniDirectional`. ตัวอย่างข้อมูล `(01)12345678901231` ปฏิบัติตามรูปแบบ GS1‑128 ที่ DataBar ต้องการ.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

อ็อบเจ็กต์ generator จะเก็บพารามิเตอร์ทั้งหมดที่ส่งผลต่อการแสดงผลของบาร์โค้ด

## ขั้นตอนที่ 4: ตั้งค่า X‑dimension (ความกว้างพิกเซลของบาร์ที่เล็กที่สุด)

X‑dimension ควบคุมขนาดโดยรวมของบาร์โค้ดโดยไม่เปลี่ยนแปลงข้อมูลที่เข้ารหัส ค่า `2` พิกเซลให้ภาพที่ชัดเจนและสแกนได้สำหรับความละเอียดหน้าจอส่วนใหญ่.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

ปรับค่าดังกล่าวหากต้องการบาร์โค้ดที่ใหญ่หรือเล็กกว่า; รักษาอัตราส่วนระหว่างความกว้างและความสูงให้สอดคล้องกัน

## ขั้นตอนที่ 5: กำหนดอัตราส่วนภาพและบันทึกรูปแรก

อัตราส่วนภาพกำหนดความสัมพันธ์ระหว่างความสูงและความกว้างของ DataBar stacked barcode. อัตราส่วน `15` เป็นค่าเริ่มต้นที่พบทั่วไปและให้ภาพที่กะทัดรัด.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนไฟล์ PNG ไปยังโฟลเดอร์ที่กำหนดไว้ก่อนหน้า ชื่อไฟล์บ่งบอกอัตราส่วนภาพที่ใช้อย่างชัดเจน.

### ผลลัพธ์ที่คาดหวังสำหรับอัตราส่วนภาพ 15

ไฟล์ `DatabarAspectRatio15.png` ที่สร้างขึ้นจะมีลักษณะคล้ายกับภาพด้านล่าง.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*ข้อความแทนภาพ:* `create databar stacked barcode image saved with aspect ratio 15`

## ขั้นตอนที่ 6: เปลี่ยนอัตราส่วนภาพและบันทึกรูปที่สอง

คุณสามารถใช้อินสแตนซ์ `BarcodeGenerator` เดียวกันเพื่อสร้างรูปแบบต่าง ๆ การเปลี่ยน `AspectRatio` เป็น `30` จะเพิ่มความสูงของแต่ละสแตกบาร์เป็นสองเท่า ซึ่งอาจจำเป็นสำหรับการพิมพ์ความละเอียดสูง.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### ผลลัพธ์ที่คาดหวังสำหรับอัตราส่วนภาพ 30

ภาพ `DatabarAspectRatio30.png` จะสูงขึ้น โดยคงความกว้างเดิมและเพิ่มความอ่านได้สำหรับสแกนเนอร์ที่อยู่ห่างไกล.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*ข้อความแทนภาพ:* `create databar stacked barcode image saved with aspect ratio 30`

## โค้ดต้นฉบับทั้งหมด

การรวมทุกขั้นตอนเข้าด้วยกันจะได้โปรแกรมที่ทำงานได้เองซึ่งคุณสามารถรันได้ทันที.

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
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

คอมไพล์และรันโปรแกรม หลังจากทำงานเสร็จ ไดเรกทอรี `Barcodes` จะมีไฟล์ PNG สองไฟล์ แต่ละไฟล์เป็น **create databar stacked barcode** ที่มีอัตราส่วนภาพต่างกัน.

## เคล็ดลับระดับมืออาชีพและข้อผิดพลาดทั่วไป

* **Pro tip:** รักษา X‑dimension ระหว่าง 1 px ถึง 4 px สำหรับกรณีการใช้งานบนหน้าจอส่วนใหญ่ ค่าใหญ่กว่าจะทำให้ไฟล์ใหญ่ขึ้นโดยไม่เพิ่มความน่าเชื่อถือในการสแกน.  
* **Pitfall:** การเปลี่ยนค่า `EncodeTypes` หลังจากสร้าง generator แล้วจะไม่อัปเดตการเข้ารหัสภายใน ต้องระบุ `EncodeTypes` ที่ถูกต้องในคอนสตรัคเตอร์เสมอ.  
* **Pro tip:** เมื่อต้องการอัตราส่วนภาพมากกว่าสองค่า ให้วนลูปผ่านอาร์เรย์ของจำนวนเต็มและเรียก `Save` ภายในลูป ซึ่งช่วยลดการทำซ้ำของโค้ด.  
* **Pitfall:** การบันทึกไปยังพาธที่ไม่มีสิทธิ์เขียนจะทำให้เกิด `UnauthorizedAccessException` ตรวจสอบให้แอปพลิเคชันทำงานด้วยสิทธิ์ไฟล์ระบบที่เหมาะสม.

## สรุป

ตอนนี้คุณรู้วิธี **create databar stacked barcode** ใน C# ด้วย Aspose.BarCode แล้ว คู่มือได้ครอบคลุมการตั้งค่าสภาพแวดล้อม, การกำหนด X‑dimension, การปรับอัตราส่วนภาพ, และการบันทึกไฟล์ PNG ด้วยพื้นฐานนี้คุณสามารถสร้างรูปแบบเพิ่มเติม, ผสานการสร้างบาร์โค้ดเข้ากับเว็บ API, หรือฝังภาพลงในรายงาน PDF.

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้อง เช่น แนวทางปฏิบัติที่ดีที่สุดสำหรับการสแกน **DataBar Stacked Omnidirectional**, การฝังบาร์โค้ดในการตอบสนองของ **ASP.NET Core**, หรือการสร้าง **QR codes** ด้วยไลบรารีเดียวกัน ทดลองใช้ `EncodeTypes` และรูปแบบภาพต่าง ๆ เพื่อให้ตรงกับความต้องการของแอปพลิเคชันของคุณ.

ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการดำเนินการทางเลือกในโครงการของคุณ.

- [วิธีสร้างภาพ PNG ของ databar ด้วย C# และ Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [วิธีตั้งค่าคอลัมน์สำหรับ Databar Expanded Stacked barcode – คู่มือ C# ฉบับสมบูรณ์](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode ใน C# – คู่มือฉบับสมบูรณ์](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}