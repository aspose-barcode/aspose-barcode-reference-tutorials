---
category: general
date: 2026-08-19
description: สร้างไฟล์ PNG ของ databar ใน C# ด้วย Aspose.BarCode เรียนรู้วิธีสร้างภาพ
  databar กำหนดค่าพารามิเตอร์ของ databar และบันทึกผลลัพธ์เป็น PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: th
lastmod: 2026-08-19
og_description: สร้างไฟล์ PNG ของ databar ด้วย C# โดยใช้ Aspose.BarCode บทเรียนนี้จะพาคุณผ่านขั้นตอนการสร้างภาพ
  databar, การกำหนดค่าพารามิเตอร์ของ databar เช่น มิติ X และอัตราส่วน, และการบันทึกไฟล์
  PNG คุณภาพสูงสำหรับการพิมพ์หรือใช้บนเว็บ
og_image_alt: create databar PNG example
og_title: สร้างภาพ PNG ของแถบข้อมูลใน C# – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: วิธีสร้างภาพ PNG ของ databar ด้วย C# และ Aspose.BarCode
url: /th/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพ PNG ของ DataBar ด้วย C# และ Aspose.BarCode

หากคุณต้องการ **สร้างไฟล์ PNG ของ databar** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงให้คุณเห็นขั้นตอนอย่างละเอียด คุณจะได้เห็นตัวอย่างที่ทำงานได้เต็มรูปแบบซึ่งสร้างรหัส DataBar แบบ stacked omnidirectional กำหนดค่าพารามิเตอร์สำคัญ และบันทึกไฟล์ PNG สองไฟล์ที่มีอัตราส่วนภาพต่างกัน

การสร้างภาพ DataBar ไม่ได้เป็นเพียงการเรียกเมธอดเดียวเท่านั้น คุณยังต้อง **กำหนดค่าพารามิเตอร์ของ databar** เช่น X‑dimension (ความกว้างโมดูล) และอัตราส่วนภาพเพื่อให้ตรงตามข้อกำหนดการพิมพ์หรือการสแกน เมื่อจบบทเรียนนี้คุณจะเข้าใจ **วิธีสร้างกราฟิก databar** ที่ทำงานได้อย่างน่าเชื่อถือในสถานการณ์จริง

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+ ด้วย)
- Visual Studio 2022 หรือ IDE ที่รองรับ C# ใด ๆ
- ใบอนุญาตที่ถูกต้องสำหรับ **Aspose.BarCode for .NET** (การประเมินผลแบบฟรีสามารถใช้ทดสอบได้)
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **เคล็ดลับ:** หากคุณยังไม่มีใบอนุญาต คุณสามารถขอคีย์การประเมินผลชั่วคราวจากพอร์ทัลของ Aspose API ทำงานเช่นเดียวกัน; เพียงแต่ลายน้ำจะเปลี่ยนไป

## ขั้นตอนที่ 1: ติดตั้งแพคเกจ NuGet ของ Aspose.BarCode

เปิดโปรเจกต์ของคุณใน Visual Studio คลิกขวาที่โซลูชันและเลือก **Manage NuGet Packages** ค้นหา `Aspose.BarCode` แล้วติดตั้งเวอร์ชันเสถียรล่าสุด

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่ม assembly `Aspose.BarCode` ไปยังโปรเจกต์ของคุณและทำให้คลาส `BarcodeGenerator` พร้อมใช้งาน

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้างบาร์โค้ดสำหรับ DataBar แบบ stacked omnidirectional

คอนสตรัคเตอร์ `BarcodeGenerator` รับอาร์กิวเมนต์สองค่า: ประเภทบาร์โค้ดและสตริงข้อมูลดิบ สำหรับ DataBar แบบ stacked omnidirectional ให้ใช้ `EncodeTypes.DatabarStackedOmniDirectional`

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**ทำไมจึงสำคัญ:** ค่าคงที่ `EncodeTypes.DatabarStackedOmniDirectional` บอกไลบรารีให้สร้างบาร์โค้ดที่สามารถอ่านได้จากทุกทิศทาง ซึ่งเหมาะอย่างยิ่งสำหรับป้ายชั้นวางสินค้า

## ขั้นตอนที่ 3: กำหนดค่า X‑dimension (ความกว้างโมดูล) เป็นพิกเซล

X‑dimension ควบคุมขนาดของบาร์ที่เล็กที่สุด การตั้งค่าเป็นพิกเซลทำให้คุณควบคุมขนาดภาพสุดท้ายได้อย่างแม่นยำ

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

ค่าที่ **2 พิกเซล** เป็นสมดุลที่ดีระหว่างความอ่านง่ายและความกระชับสำหรับเครื่องพิมพ์ป้ายส่วนใหญ่ ปรับค่านี้หากต้องการโมดูลที่ใหญ่หรือเล็กกว่านี้

## ขั้นตอนที่ 4: ตั้งค่าอัตราส่วนภาพแรกและบันทึกเป็น PNG

อัตราส่วนภาพมีผลต่อความสูงของ DataBar แบบ stacked อัตราส่วนภาพ **15** จะให้บาร์โค้ดที่ค่อนข้างสั้น ในขณะที่ **30** จะทำให้บาร์โค้ดสูงขึ้น

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนบาร์โค้ดที่สร้างขึ้นลงในไฟล์ PNG PNG เป็นรูปแบบ lossless ซึ่งรักษาขอบคมที่จำเป็นสำหรับสแกนเนอร์บาร์โค้ด

## ขั้นตอนที่ 5: เปลี่ยนอัตราส่วนภาพและบันทึก PNG ที่สอง

คุณสามารถใช้ตัวอย่าง `BarcodeGenerator` เดียวกันเพื่อสร้างรูปแบบที่แตกต่างได้โดยเพียงเปลี่ยนอัตราส่วนภาพ

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์—`DatabarAspectRatio15.png` และ `DatabarAspectRatio30.png`—แต่ละไฟล์มีความหนาแน่นภาพที่ต่างกัน

## ขั้นตอนที่ 6: ตรวจสอบผลลัพธ์

เปิดไฟล์ PNG ที่สร้างขึ้นในโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ด DataBar ที่คมชัดและคอนทราสต์สูง การสแกนภาพด้วยแอปสแกนบาร์โค้ดบนสมาร์ทโฟนจะยืนยันว่าอัตราส่วนภาพทั้งสองถอดรหัสได้ค่า GTIN ดั้งเดิม `12345678901231`

![ตัวอย่างการสร้าง databar PNG](databar_example.png)

*ภาพด้านบนแสดงไฟล์ PNG สองไฟล์เคียงข้างกัน ภาพซ้ายใช้อัตราส่วนภาพ 15, ภาพขวาใช้อัตราส่วนภาพ 30.*

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | สิ่งที่ต้องเปลี่ยน | เหตุผล |
|----------|----------------|--------|
| **ข้อมูลต่าง ๆ** | แทนที่สตริง `(01)12345678901231` ด้วย GS1 Application Identifier และข้อมูลที่ถูกต้องใด ๆ | ทำให้คุณสามารถเข้ารหัสรหัสสินค้า, หมายเลขซีเรียล ฯลฯ |
| **ความละเอียดสูงขึ้น** | เพิ่มค่า `XDimension.Pixels` เป็น 3 หรือ 4 | จำเป็นเมื่อบาร์โค้ดจะพิมพ์ขนาดใหญ่หรือสแกนจากระยะไกล |
| **ประเภท DataBar อื่น** | ใช้ `EncodeTypes.DatabarStacked` หรือ `EncodeTypes.DatabarExpanded` | เลือกประเภทที่เหมาะกับการจัดวางป้ายของคุณที่สุด |
| **พื้นหลังโปร่งแสง** | ส่ง `BarCodeImageFormat.Png` พร้อมกับ `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | มีประโยชน์สำหรับการวางบาร์โค้ดบนป้ายสี |

> **ระวัง:** การตั้งค่า X‑dimension ที่เล็กเกินไป (< 1 pixel) อาจทำให้บาร์โค้ดดูเบลอหลังจาก

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้ทางเลือกในโปรเจกต์ของคุณเอง

- [วิธีสร้างและปรับความสูงของบาร์โค้ด One-Dimensional Databar ด้วย Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [สร้าง One-Dimensional Databar การเข้ารหัส GS1 ด้วย Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [สร้างบาร์โค้ด Databar ของ Aspose.BarCode ด้วย .NET API – การกำหนดค่าแถวและคอลัมน์](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}