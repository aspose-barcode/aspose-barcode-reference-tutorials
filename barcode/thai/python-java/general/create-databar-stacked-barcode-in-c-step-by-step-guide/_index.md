---
category: general
date: 2026-08-06
description: สร้างบาร์โค้ด DataBar แบบซ้อนใน C# อย่างรวดเร็ว เรียนรู้การตั้งค่ามิติ
  X ปรับอัตราส่วนภาพ และส่งออกไฟล์ PNG ด้วยเครื่องสร้าง DataBar Stacked Omnidirectional
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: th
lastmod: 2026-08-06
og_description: สร้างบาร์โค้ด Databar stacked ด้วย C# และ Aspose.BarCode บทเรียนนี้แสดงวิธีกำหนดมิติ
  X, ปรับอัตราส่วน, และบันทึกรูปภาพ PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: สร้างบาร์โค้ด Databar แบบซ้อนใน C# – คู่มือการเขียนโปรแกรมครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: สร้างบาร์โค้ด Databar แบบซ้อนใน C# – คู่มือขั้นตอนโดยละเอียด
url: /th/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด databar stacked ใน C# – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **สร้างบาร์โค้ด databar stacked** ใน C# คู่มือนี้จะแสดงวิธีทำโดยใช้ไลบรารี Aspose.BarCode คุณจะได้เรียนรู้การตั้งค่า X dimension, การเปลี่ยนอัตราส่วนของบาร์โค้ด, และการบันทึกผลลัพธ์เป็นไฟล์ PNG – ทั้งหมดในไม่กี่ขั้นตอนสั้น ๆ

การสร้าง DataBar Stacked barcode เป็นเรื่องทั่วไปเมื่อคุณต้องเข้ารหัสข้อมูล GS1‑128 สำหรับการสแกนในร้านค้าปลีกหรือการติดตามโลจิสติกส์ ในส่วนต่อไปนี้เราจะครอบคลุมตั้งแต่การตั้งค่าโปรเจกต์จนถึงการตรวจสอบผลลัพธ์ เพื่อให้คุณสามารถนำโซลูชันนี้ไปใช้ในแอปพลิเคชัน .NET ใด ๆ ได้โดยไม่พลาดรายละเอียดใด ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* **.NET 6.0** (หรือใหม่กว่า) ติดตั้งแล้ว – โค้ดนี้ใช้ SDK เวอร์ชันล่าสุด
* สำเนา **Aspose.BarCode for .NET** ที่มี **ลิขสิทธิ์** เวอร์ชันฟรีสำหรับการทดลองใช้จะมีลายน้ำ
* IDE เช่น **Visual Studio 2022** หรือ **VS Code** พร้อมส่วนขยาย C#
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ **C#** และแนวคิดของ GS1 Application Identifiers

> **เคล็ดลับ:** หากคุณใช้ NuGet package manager คำสั่ง `dotnet add package Aspose.BarCode` จะจัดการ dependencies ทั้งหมดให้โดยอัตโนมัติ

## ขั้นตอนที่ 1: สร้างโปรเจกต์คอนโซลใหม่

เปิดเทอร์มินัลหรือ Package Manager Console แล้วรัน:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

คำสั่ง `dotnet new console` จะสร้างไฟล์ **Program.cs** ขั้นพื้นฐาน การเพิ่มแพคเกจ **Aspose.BarCode** จะทำให้คลาส `BarcodeGenerator` พร้อมใช้งาน

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้าง DataBar Stacked Omnidirectional

เปิด **Program.cs** แล้วแทนที่เนื้อหาเริ่มต้นด้วยโค้ดต่อไปนี้ บรรทัดแรกสร้าง **BarcodeGenerator** ที่กำหนดค่าให้ใช้ symbology **DataBar Stacked Omnidirectional** และใส่ payload ของ GS1‑128

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**เหตุผลที่สำคัญ:** ค่า enum `EncodeTypes.DatabarStackedOmniDirectional` บอกไลบรารีให้สร้าง **databar stacked barcode** ซึ่งเป็นรูปแบบ stacked ของตระกูล DataBar omnidirectional symbology symbology นี้สามารถบรรจุตัวเลขได้สูงสุด 14 ตัว ทำให้เหมาะกับรหัส GTIN‑14

## ขั้นตอนที่ 3: ตั้งค่า X dimension (ความกว้างโมดูล)

X dimension ควบคุมความกว้างของบาร์ที่เล็กที่สุด (โมดูล) ค่าที่เล็กเกินไปอาจทำให้ภาพไม่คมบนเครื่องพิมพ์ความละเอียดต่ำ ส่วนค่าที่ใหญ่เกินไปอาจทำให้บาร์โค้ดเกินพื้นที่ของฉลาก

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **คำแนะนำ:** คุณสมบัติ `Pixels` สะดวกสำหรับการทดสอบบนหน้าจอ หากต้องการโฟกัสที่การพิมพ์ ให้ใช้ `generator.Parameters.Barcode.XDimension.Millimeters` แทน

## ขั้นตอนที่ 4: ปรับอัตราส่วนและบันทึกภาพแรก

**อัตราส่วน** มีผลต่อความสัมพันธ์ระหว่างความสูงและความกว้างของบาร์โค้ด stacked ประเภท DataBar Stacked Omnidirectional รองรับอัตราส่วนตั้งแต่ 10 ถึง 30 เราจะสร้างสองภาพเพื่อแสดงผลของการเปลี่ยนแปลง

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

การเรียก `generator.Save` จะเขียนไฟล์ **PNG** ไปยังไดเรกทอรีทำงานปัจจุบัน `BarCodeImageFormat.Png` ให้การบีบอัดแบบ lossless ซึ่งเหมาะสำหรับการประมวลผลต่อหรือฝังใน PDF

## ขั้นตอนที่ 5: เปลี่ยนอัตราส่วนเป็น 30 และบันทึกภาพที่สอง

ตอนนี้เราจะเพิ่มความสูงของบาร์ stacked โดยตั้งอัตราส่วนเป็น **30** ทำให้บาร์โค้ดสูงขึ้นโดยไม่ต้องเปลี่ยน X dimension

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

เมื่อรันโปรแกรมแล้วจะได้ไฟล์ PNG สองไฟล์:

* **DatabarAspectRatio15.png** – บาร์โค้ดขนาดกะทัดรัด เหมาะกับฉลากขนาดเล็ก
* **DatabarAspectRatio30.png** – บาร์โค้ดสูงขึ้น ช่วยเพิ่มความน่าเชื่อถือในการสแกนบนพื้นผิวที่มีคอนทราสต์ต่ำ

คุณสามารถเปิดภาพเหล่านี้ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันว่าบาร์ถูกจัดเรียงเป็น stacked อย่างถูกต้องและข้อมูลที่เข้ารหัสตรงกับสตริง GS1 ดั้งเดิม

## ขั้นตอนที่ 6: ตรวจสอบค่าที่เข้ารหัส (ไม่บังคับ)

หากต้องการยืนยันว่าบาร์โค้ดแท้จริงแสดงสตริงอินพุตที่ใส่เข้าไป คุณสามารถถอดรหัสด้วยไลบรารีเดียวกัน:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

ตัวถอดรหัสควรแสดงผล `(01)12345678901231` ซึ่งพิสูจน์ว่ากระบวนการ **create databar stacked barcode** รักษาข้อมูลไว้ครบถ้วน

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| บาร์โค้ดดูเบลอ | X dimension ตั้งค่าต่ำเกินความละเอียดของเอาต์พุต | เพิ่มค่า `XDimension.Pixels` หรือใช้ `Millimeters` สำหรับการพิมพ์ |
| สแกนเนอร์แจ้ง “symbol not found” | อัตราส่วนอยู่นอกช่วงที่รองรับ 10‑30 | รักษาอัตราส่วนให้อยู่ระหว่าง 10‑30; ค่า 15 และ 30 เป็นค่าเริ่มต้นที่ปลอดภัย |
| PNG มีลายน้ำ | ใช้ไลเซนส์ทดลองฟรีของ Aspose.BarCode | ซื้อไลเซนส์เต็มหรือใช้รุ่นทดลองเฉพาะการทดสอบ |
| การถอดรหัสล้มเหลวในภาพที่สอง | ตัวถอดรหัสตั้งค่า symbology ผิด | ใช้ `DecodeType.DatabarStackedOmniDirectional` เมื่อต้องอ่านบาร์โค้ด stacked |

## ขั้นตอนต่อไป

เมื่อคุณสามารถ **create databar stacked barcode** ได้แล้ว คุณอาจต้องการ:

* **ฝัง PNG ลงในใบแจ้งหนี้ PDF** ด้วยไลบรารี PDF เช่น **Aspose.PDF**
* **สร้างบาร์โค้ดแบบเรียลไทม์ใน Web API** – ส่งคืนไบต์ PNG โดยตรงจากคอนโทรลเลอร์ ASP.NET Core
* **ทดลองใช้ DataBar รุ่นอื่น** (เช่น `DatabarExpanded`, `DatabarLimited`) โดยเปลี่ยนค่า enum `EncodeTypes`
* **ปรับสี** ด้วยการตั้งค่า `generator.Parameters.Barcode.ForeColor` และ `BackColor` เพื่อให้สอดคล้องกับแบรนด์

หัวข้อเหล่านี้ทั้งหมดต่อยอดจากแนวคิดหลักที่อธิบายไว้ในบทนี้: การเริ่มต้น `BarcodeGenerator`, การกำหนดพารามิเตอร์การแสดงผล, และการบันทึกผลลัพธ์ด้วย `BarCodeImageFormat`

---

### สรุป

บทแนะนำนี้ได้สาธิตวิธี **create databar stacked barcode** ใน C# ด้วย Aspose.BarCode คุณได้เรียนรู้การตั้งค่า **X dimension**, การปรับ **อัตราส่วนของบาร์โค้ด**, และการส่งออกเป็นไฟล์ **PNG** ด้วย `BarcodeGenerator` หากเพิ่มขั้นตอนการถอดรหัส คุณยังสามารถตรวจสอบความถูกต้องของข้อมูล GS1 ได้อีกด้วย นำรูปแบบเหล่านี้ไปใช้ในระบบสินค้าคงคลัง, การจัดส่ง, หรือจุดขายของคุณและสำรวจตัวเลือกการปรับแต่งต่าง ๆ ที่ไลบรารีนี้มีให้ ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}