---
category: general
date: 2026-07-18
description: ตัวอย่างเครื่องสร้างบาร์โค้ดที่แสดงวิธีตั้งค่าขนาดและสร้างภาพบาร์โค้ด
  DataBar Stacked Omni‑Directional ด้วย C# เรียนรู้ประเภทการเข้ารหัสบาร์โค้ดอย่างรวดเร็ว.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: th
lastmod: 2026-07-18
og_description: ตัวอย่างเครื่องสร้างบาร์โค้ดจะอธิบายขั้นตอนการตั้งค่าขนาด, เลือกประเภทการเข้ารหัสบาร์โค้ด,
  และสร้างโครงการภาพบาร์โค้ดด้วย C# ด้วยโค้ดที่น้อยที่สุด
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: ตัวอย่างเครื่องสร้างบาร์โค้ด – การสร้างภาพ DataBar อย่างรวดเร็วใน C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: ตัวอย่างการสร้างบาร์โค้ด – สร้างภาพ DataBar ด้วย C#
url: /th/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างตัวสร้างบาร์โค้ด – สร้างภาพ DataBar ด้วย C#

เคยต้องการ **ตัวอย่างตัวสร้างบาร์โค้ด** ที่จริงจังและสร้างบาร์โค้ดจริงได้โดยไม่ต้องบิดหัวไหม? คุณไม่ได้อยู่คนเดียว นักพัฒนาส่วนใหญ่มักเจออุปสรรคเมื่อต้องกำหนด **วิธีตั้งค่าขนาด** สำหรับบาร์โค้ด DataBar Stacked Omni‑Directional โดยเฉพาะเมื่อเอกสารอธิบายซับซ้อนเกินไป

ในบทเรียนนี้เราจะเดินผ่านโปรแกรม C# ที่พร้อมรันเต็มรูปแบบ ซึ่งจะแสดง **วิธีสร้างภาพ databar** เลือก **barcode encode types** ที่ถูกต้อง และสุดท้าย **สร้างไฟล์ barcode image c#** ที่คุณสามารถนำไปใช้ในโปรเจกต์ใดก็ได้ ไม่มีส่วนเกิน—แค่โค้ดที่คัดลอก‑วางได้ พร้อมเหตุผลของแต่ละบรรทัด

## สิ่งที่คุณต้องเตรียม

- **.NET 6** (หรือเวอร์ชัน .NET ล่าสุด) – API ที่เราใช้รองรับ .NET Standard จึงทำงานได้บน .NET Framework ด้วย  
- **Aspose.BarCode for .NET** – ไลบรารีที่ให้ `BarcodeGenerator` คุณสามารถติดตั้งจาก NuGet ด้วย `Install-Package Aspose.BarCode`  
- **IDE สำหรับ C#** – Visual Studio, Rider หรือ VS Code ก็ได้  
- โฟลเดอร์บนดิสก์ที่ไฟล์ PNG จะถูกบันทึก (โค้ดจะสร้าง `DatabarAspectRatio15.png` และ `DatabarAspectRatio30.png`)

เตรียมครบหรือยัง? ดีแล้ว—มาเริ่มกันเลย

## ตัวอย่างตัวสร้างบาร์โค้ด – เริ่มต้นตัวสร้าง

ก่อนอื่นเราต้องมีอินสแตนซ์ของ `BarcodeGenerator` ที่ตั้งค่าสำหรับสัญลักษณ์ **DataBar Stacked Omni‑Directional** นี่คือ **barcode encode type** ที่เราจะทำงานด้วย

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **ทำไมเรื่องนี้สำคัญ:** `EncodeTypes.DatabarStackedOmniDirectional` บอกให้ Aspose รู้ว่าจะเรนเดอร์สัญลักษณ์ใด หากเลือกประเภทผิด ตัวสแกนเนอร์จะไม่อ่านบาร์โค้ดได้ แม้ภาพจะสวยแค่ไหนก็ตาม

## วิธีตั้งค่าขนาดสำหรับบาร์โค้ด

ความอ่านง่ายของบาร์โค้ดขึ้นกับ **X‑dimension** (ความกว้างของบาร์ที่แคบที่สุด) ส่วนใหญ่ค่า 2 พิกเซลทำงานได้ดี แต่คุณสามารถปรับให้เหมาะกับเครื่องพิมพ์หรือหน้าจอของคุณได้

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **เคล็ดลับ:** หากคุณต้องการ **วิธีตั้งค่าขนาด** สำหรับบาร์โค้ดตระกูลอื่น ๆ ให้ใช้โซ่คุณสมบัติเช่นเดียวกัน (`Parameters.Barcode.XDimension`) เพียงเปลี่ยนค่า `Pixels` เท่านั้น

## วิธีสร้าง DataBar Stacked Omni‑Directional Barcode

เมื่อเครื่องสร้างพร้อมแล้ว เราจะเล่นกับคุณสมบัติ **aspect ratio** ซึ่งควบคุมความสัมพันธ์ความสูงต่อความกว้างของ DataBar ทำให้คุณสร้างสัญลักษณ์ที่สั้นและเป็นสี่เหลี่ยมจัตุรัส หรือสูงและแคบได้ตามต้องการ

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **กำลังเกิดอะไรขึ้น?** `AspectRatio = 15` บอกให้เอนจินทำบาร์ให้สูงกว่าความกว้าง 15 เท่า PNG ที่ได้จะถูกบันทึกไว้ข้างไฟล์ executable ของคุณ

## สร้าง Barcode Image C# – เปลี่ยน Aspect Ratio

มาทดสอบความยืดหยุ่นโดยสลับอัตราส่วนเป็น 30 แล้วบันทึกไฟล์ที่สอง

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

เมื่อรันโปรแกรม คุณจะได้ไฟล์ PNG สองไฟล์:

| ไฟล์ | อัตราส่วน | ขนาดโดยประมาณ |
|------|------------|----------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

เปิดไฟล์ด้วยโปรแกรมดูภาพใดก็ได้—you should see clean, scannable DataBar symbols.

## ภาพรวมของ Barcode Encode Types (ตัวเลือกแต่เป็นประโยชน์)

หากคุณสนใจ **barcode encode types** อื่น ๆ ที่ Aspose รองรับ นี่คือชีตสรุปสั้น ๆ:

| EncodeTypes Enum | คำอธิบาย |
|------------------|-----------|
| `EncodeTypes.Code128` | ตัวอักษรและตัวเลขความหนาแน่นสูง |
| `EncodeTypes.QR` | รหัสเมทริกซ์ 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar สำหรับการค้าปลีก |
| `EncodeTypes.DatabarStackedOmniDirectional` | **โฟกัสของเรา** – กะทัดรัด, omnidirectional |

การรู้ enum ที่ถูกต้องจะช่วยลดการลองผิดลองถูกเมื่อต้องสลับโปรเจกต์

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

- **ขาดแพ็กเกจ NuGet** – โค้ดจะไม่คอมไพล์หากไม่มี `Aspose.BarCode` รัน `dotnet add package Aspose.BarCode` ก่อน  
- **เส้นทางไฟล์ผิด** – หากใช้เส้นทางแบบ absolute ตรวจสอบเครื่องหมาย backslash (`\\`) บน Windows เส้นทางแบบ relative (ตามตัวอย่าง) จะทำให้พกพาง่ายกว่า  
- **อัตราส่วนสูงเกินไป** – อัตราส่วนเหนือ 50 ทำให้บาร์โค้ดสูงเกินกว่าสแกนเนอร์ทั่วไป ควรอยู่ในช่วง 15‑30 สำหรับการใช้งานส่วนใหญ่

## โค้ดเต็ม (พร้อมคัดลอก‑วาง)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

รันโปรแกรม (`dotnet run` หรือกด **F5** ใน Visual Studio) แล้วคุณจะเห็นข้อความในคอนโซลยืนยันว่าไฟล์ถูกสร้างบนดิสก์แล้ว

![ตัวอย่างผลลัพธ์ของตัวสร้างบาร์โค้ด แสดง DataBar barcode ด้วยอัตราส่วน 15](placeholder/path/to/image.png){: .align-center alt="ตัวอย่างผลลัพธ์ของตัวสร้างบาร์โค้ด แสดง DataBar barcode ด้วยอัตราส่วน 15"}

## สรุป

เราได้สร้าง **ตัวอย่างตัวสร้างบาร์โค้ด** ที่สาธิต **วิธีตั้งค่าขนาด**, เลือก **barcode encode types** ที่ถูกต้อง, และสุดท้าย **สร้างไฟล์ barcode image c#** ที่คุณสามารถฝังลงในโปรเจกต์ใดก็ได้ โค้ดสั้น กระชับ แนวคิดชัดเจน และคุณมีพื้นฐานที่มั่นคงสำหรับต่อยอด—เช่น เพิ่มคำบรรยาย, หมุนภาพ, หรือเปลี่ยนสัญลักษณ์เป็นแบบอื่น

### ขั้นตอนต่อไปคืออะไร?

- ทดลองกับ **X‑dimension** ต่าง ๆ เพื่อดูว่าความทนทานของสแกนเนอร์เปลี่ยนแปลงอย่างไร  
- ลอง **EncodeTypes** อื่น ๆ เช่น `Code128` หรือ `QR` เพื่อขยายเครื่องมือของคุณ  
- ทำการสร้างแบบแบตช์อัตโนมัติ: วนลูปไฟล์ CSV ของรหัสสินค้าและสร้าง PNG สำหรับแต่ละรายการ

หากเจอปัญหาใด ๆ คอมเมนต์ด้านล่างหรือดูเอกสาร Aspose.BarCode – มีตัวอย่างเพิ่มเติมที่สอดคล้องกับสิ่งที่เราอธิบายไว้ที่นี่

ขอให้เขียนโค้ดสนุกและบาร์โค้ดของคุณสแกนได้สำเร็จตั้งแต่ครั้งแรก!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่อธิบายในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอน‑ขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}