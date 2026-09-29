---
category: general
date: 2026-09-29
description: เรียนรู้วิธีสร้างบาร์โค้ด Databar แบบหลายทิศทางใน C# ด้วย Aspose.BarCode
  ปรับมิติ X ตั้งอัตราส่วนภาพ และบันทึกภาพเป็นไฟล์ PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: th
lastmod: 2026-09-29
og_description: สร้างบาร์โค้ด Databar แบบหลายทิศทางใน C# ด้วย Aspose.BarCode. เรียนรู้การตั้งค่ามิติ
  X, ปรับอัตราส่วน, และส่งออกไฟล์ PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: สร้างบาร์โค้ด Databar แบบหลายทิศทางใน C# – คู่มือขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: วิธีสร้างบาร์โค้ด Databar แบบหลายทิศทางใน C#
url: /th/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด Databar แบบหลายทิศทางใน C#

หากคุณต้องการ **สร้างบาร์โค้ด Databar แบบหลายทิศทาง** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงขั้นตอนที่แน่นอน คุณจะได้เห็นวิธีการเริ่มต้นบาร์โค้ด DataBar stacked omnidirectional ตั้งค่ามิติ X‑dimension ปรับอัตราส่วนภาพ และสร้างภาพ PNG ด้วย Aspose.BarCode.

การสร้าง **DataBar stacked omnidirectional barcode** เป็นเรื่องทั่วไปเมื่อคุณต้องเข้ารหัสตัวระบุสินค้าเพื่อสแกนเนอร์ในร้านค้า ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ตั้งค่าอัตราส่วนของบาร์โค้ด**, ควบคุมขนาดโมดูล, และส่งออกผลลัพธ์โดยไม่ต้องออกจาก IDE.

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า
- Visual Studio 2022 (หรือ IDE ที่รองรับ C# ใด ๆ)
- แพคเกจ NuGet **Aspose.BarCode for .NET** (เวอร์ชัน 23.12 หรือใหม่กว่า)

คุณสามารถเพิ่มแพคเกจนี้ผ่าน NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: เริ่มต้นบาร์โค้ด Databar แบบหลายทิศทาง

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ที่ใช้สัญลักษณ์ **DataBar stacked omnidirectional** ตัวสร้างรับประเภทการเข้ารหัสและสตริงข้อมูล

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**ทำไมเรื่องนี้ถึงสำคัญ:** ค่าที่เป็น `EncodeTypes.DatabarStackedOmniDirectional` บอกให้ Aspose.BarCode แสดงรูปแบบ Databar แบบหลายทิศทางที่เฉพาะเจาะจง ซึ่งจำเป็นสำหรับการสแกนในทั้งสองทิศทาง.

## ขั้นตอนที่ 2: กำหนด X‑dimension (ขนาดโมดูล)

X‑dimension ควบคุมความกว้างของโมดูลบาร์โค้ดหนึ่งอันเป็นพิกเซล ค่า `2` พิกเซลทำงานได้ดีสำหรับการแสดงผลบนหน้าจอและเครื่องพิมพ์ส่วนใหญ่

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**ทำไมเรื่องนี้ถึงสำคัญ:** X‑dimension ที่สม่ำเสมอทำให้บาร์โค้ดตรงตามข้อกำหนดขนาดขั้นต่ำสำหรับสแกนเนอร์ในร้านค้า พร้อมทั้งทำให้ขนาดไฟล์ภาพอยู่ในระดับที่จัดการได้

## ขั้นตอนที่ 3: ตั้งค่าอัตราส่วนแรกและบันทึกภาพ

**อัตราส่วน** กำหนดความสัมพันธ์ระหว่างความสูงและความกว้างของ DataBar อัตราส่วน `15` ให้บาร์โค้ดที่กระชับและสูง เหมาะสำหรับพื้นที่ป้ายที่แคบ

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**ทำไมเรื่องนี้ถึงสำคัญ:** การปรับอัตราส่วนทำให้คุณสามารถใส่บาร์โค้ดลงในเลเบิลที่มีรูปแบบต่าง ๆ ได้โดยไม่เสียความอ่านได้ ภาพ PNG ที่บันทึกไว้สามารถตรวจสอบได้ในโปรแกรมดูภาพใด ๆ

## ขั้นตอนที่ 4: เปลี่ยนอัตราส่วนและสร้างภาพที่สอง

บางครั้งต้องการบาร์โค้ดที่กว้างกว่า—เช่นเมื่อป้ายมีพื้นที่แนวนอนมากกว่า การเปลี่ยนอัตราส่วนเป็น `30` จะทำให้บาร์โค้ดดูแบนขึ้น

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมเรื่องนี้ถึงสำคัญ:** ด้วยการเปิดเผยคุณสมบัติ **set barcode aspect ratio** คุณสามารถสร้างรูปแบบบาร์โค้ดหลายแบบจากโค้ดฐานเดียว ทำให้กระบวนการสร้างป้ายอัตโนมัติง่ายขึ้น

## ผลลัพธ์ที่คาดหวัง

เมื่อรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์ในโฟลเดอร์ผลลัพธ์ของแอปพลิเคชัน:

| ชื่อไฟล์                | อัตราส่วน | คำอธิบายภาพ |
|--------------------------|------------|--------------------|
| `DatabarAspectRatio15.png` | 15         | บาร์โค้ดสูงและแคบ เหมาะสำหรับป้ายแคบ |
| `DatabarAspectRatio30.png` | 30         | บาร์โค้ดกว้างที่เติมเต็มพื้นที่แนวนอนมากขึ้น |

![ตัวอย่างการสร้างบาร์โค้ด Databar แบบหลายทิศทาง](databar-example.png "ตัวอย่างการสร้างบาร์โค้ด Databar แบบหลายทิศทาง")

*ภาพหน้าจอแสดงไฟล์ PNG สองไฟล์ที่สร้างขึ้นเคียงข้างกัน.*

## คำถามทั่วไปและกรณีขอบ

### ถ้าฉันต้องการ X‑dimension ที่ต่างออกไป?

คุณสามารถกำหนดค่าเต็มจำนวนใด ๆ ให้กับ `XDimension.Pixels` ค่าใต `1` จะถูกละเว้น และค่ามากกว่า `10` อาจทำให้โมดูลใหญ่เกินกว่าขอบของเครื่องพิมพ์ ทดสอบผลลัพธ์ภาพหลังจากแต่ละการเปลี่ยนแปลง

### ฉันจะเข้ารหัสข้อมูล AI‑generated อื่น ๆ (เช่น UPC, EAN) อย่างไร?

แทนที่สตริงข้อมูลในคอนสตรัคเตอร์ของ `BarcodeGenerator` ด้วย Application Identifier (AI) ที่เหมาะสม สำหรับรหัส UPC‑A ให้ใช้ `"012345678905"` โดยไม่มีคำนำหน้า AI

### ฉันสามารถส่งออกเป็นรูปแบบอื่นนอกจาก PNG ได้หรือไม่?

ได้. เมธอด `Save` รองรับ `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, และ `BarCodeImageFormat.Bmp`. เลือกรูปแบบที่สอดคล้องกับกระบวนการทำงานต่อไปของคุณ

## เคล็ดลับมืออาชีพ: ใช้ตัวสร้างซ้ำสำหรับการประมวลผลเป็นชุด

หากคุณต้องการสร้างบาร์โค้ดหลายสิบรายการที่มีอัตราส่วนต่างกัน ให้คงอินสแตนซ์ของ `BarcodeGenerator` ไว้และแก้ไข `DataBar.AspectRatio` ก่อนแต่ละการ `Save` เท่านั้น วิธีนี้จะลดภาระการสร้างอินสแตนซ์ใหม่ของตัวสร้างสำหรับแต่ละภาพ

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด Databar แบบหลายทิศทาง** ใน C# ด้วย Aspose.BarCode แล้ว โดยการเริ่มต้น `BarcodeGenerator`, ตั้งค่า X‑dimension, ปรับ **set barcode aspect ratio**, และบันทึกไฟล์ PNG คุณสามารถผลิตภาพบาร์โค้ดที่ตอบสนองความต้องการของเลเบิลที่หลากหลาย

ต่อไปสำรวจหัวข้อที่เกี่ยวข้อง เช่น **generate barcode image** สำหรับ QR code, การตรวจสอบ **DataBar stacked omnidirectional barcode**, หรือการรวม PNG ที่สร้างขึ้นเข้าสู่ใบแจ้งหนี้ PDF ด้วย Aspose.PDF ทดลองอัตราส่วนและขนาดโมดูลต่าง ๆ เพื่อหาการตั้งค่าที่เหมาะสมกับฮาร์ดแวร์การพิมพ์ของคุณ

---

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ

- [วิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode ใน C# – คู่มือฉบับเต็ม](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [วิธีสร้างบาร์โค้ดใน C# – สร้างภาพบาร์โค้ด c# ด้วย DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}