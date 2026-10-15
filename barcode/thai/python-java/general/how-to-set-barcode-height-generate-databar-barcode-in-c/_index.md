---
category: general
date: 2026-10-12
description: วิธีตั้งความสูงของบาร์โค้ดและสร้างบาร์โค้ด DataBar ด้วย C# โดยใช้ Aspose.BarCode.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนพร้อมโค้ดเต็ม.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: th
lastmod: 2026-10-12
og_description: วิธีตั้งความสูงของบาร์โค้ดใน C# และสร้างบาร์โค้ด DataBar ด้วย Aspose.BarCode
  เรียนรู้โค้ดเต็ม ทำไมแต่ละขั้นตอนจึงสำคัญ และวิธีเปลี่ยนความสูงของบาร์โค้ด
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: วิธีตั้งความสูงของบาร์โค้ดและสร้างบาร์โค้ด DataBar ด้วย C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีตั้งความสูงของบาร์โค้ดและสร้างบาร์โค้ด DataBar ด้วย C#
url: /th/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งความสูงของบาร์โค้ด, สร้างบาร์โค้ด DataBar ใน C#

หากคุณต้องการ **how to set barcode** มิติโปรแกรม, คู่มือนี้จะแสดงขั้นตอนที่แน่นอน คุณจะได้เรียนรู้วิธีสร้างบาร์โค้ด DataBar Omni‑directional, ปรับความสูงของมัน, และบันทึกทั้งสองเวอร์ชันเป็นไฟล์ PNG.

การเปลี่ยนความสูงของบาร์ในบาร์โค้ดเป็นความต้องการทั่วไปเมื่อคุณรวมบาร์โค้ดเข้ากับใบเสร็จ, ป้ายสินค้า, หรือหน้าจอมือถือ ตัวอย่างด้านล่างใช้ไลบรารี Aspose.BarCode ซึ่งรองรับชุดสัญลักษณ์ GS1 DataBar ทั้งหมด.

## สิ่งที่คุณจะได้เรียนรู้

* **how to set barcode** ความสูงสำหรับบาร์โค้ด DataBar Omni‑directional  
* โค้ด **generate barcode c#** ที่สร้างภาพสองภาพด้วยความสูงที่ต่างกัน  
* ทำความเข้าใจสัญลักษณ์ **how to create databar** และเหตุผลที่ความสูงของบาร์สำคัญ  
* ใช้ตรรกะ **change barcode height** โดยไม่ต้องสร้าง generator ใหม่  

ไม่ต้องใช้เครื่องมือภายนอกใด ๆ นอกจากแพ็คเกจ Aspose.BarCode NuGet และรันไทม์ .NET 6+.

## ข้อกำหนดเบื้องต้น

* .NET 6 SDK หรือเวอร์ชันที่ใหม่กว่า ติดตั้งแล้ว  
* Visual Studio 2022 (หรือโปรแกรมแก้ไข C# ใด ๆ)  
* Aspose.BarCode for .NET – ติดตั้งโดยใช้ `dotnet add package Aspose.BarCode`  

> **Pro tip:** ใช้ไลเซนส์ทดลองฟรีจาก Aspose หากคุณไม่มีคีย์เชิงพาณิชย์; API ทำงานเช่นเดียวกัน

## ขั้นตอนที่ 1: ติดตั้งแพ็คเกจ Aspose.BarCode

เปิดเทอร์มินัลในโฟลเดอร์โปรเจกต์ของคุณและรัน:

```bash
dotnet add package Aspose.BarCode
```

แพ็คเกจนี้จะเพิ่มเนมสเปซ `Aspose.BarCode` ซึ่งประกอบด้วยคลาส `BarcodeGenerator` ที่เราจะใช้เพื่อ **generate barcode c#** ภาพ

## ขั้นตอนที่ 2: สร้างตัวสร้างบาร์โค้ด DataBar

การกระทำที่เป็นรูปธรรมแรกสำหรับพารามิเตอร์ **how to set barcode** คือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยสัญลักษณ์และสตริงข้อมูลที่ต้องการ

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*ทำไมสิ่งนี้จึงสำคัญ:* `EncodeTypes.DatabarOmniDirectional` สร้าง DataBar แบบกะทัดรัดและหลายทิศทางที่สามารถสแกนจากทุกมุม—เหมาะสำหรับป้ายขนาดเล็ก

## ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์บาร์โค้ดทั่วไป (รวมถึงความสูงบาร์เริ่มต้น)

ตอนนี้เราตอบคำถาม **how to set barcode** X‑dimension และความสูงบาร์ก่อนบันทึกภาพแรก

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension ควบคุมความกว้างโดยรวมของแต่ละบาร์; การตั้งค่า 2‑pixel จะให้ภาพที่อ่านง่ายและคมชัดบนหน้าจอส่วนใหญ่ ขั้นตอน **change barcode height** ต่อมาจะใช้ generator เดิมซ้ำ, ประหยัดเวลาและหน่วยความจำ

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ดแรก (ความสูง 30‑pixel)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

ไฟล์ `DatabarHeight30.png` ตอนนี้มีบาร์โค้ด DataBar ที่มีความสูงบาร์ 30‑pixel

## ขั้นตอนที่ 5: เปลี่ยนความสูงบาร์เป็น 60 pixel เท่านั้น

เพื่อสาธิต **change barcode height** เราแก้ไขเฉพาะคุณสมบัติ `BarHeight` เท่านั้น การตั้งค่าอื่น ๆ ยังคงเหมือนเดิม ซึ่งเป็นวิธีที่มีประสิทธิภาพที่สุดในการสร้างหลายขนาดจาก generator ตัวเดียว

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## ขั้นตอนที่ 6: บันทึกภาพบาร์โค้ดที่สอง (ความสูง 60‑pixel)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์, แต่ละไฟล์มีความสูงบาร์ที่ต่างกันแต่ข้อมูลและ X‑dimension เหมือนกัน

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก‑วางลงในแอปพลิเคชันคอนโซลใหม่ (`dotnet new console`) และรันได้ทันที

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์สองไฟล์ในไดเรกทอรีทำงานของไฟล์ executable:

* `DatabarHeight30.png` – บาร์โค้ด DataBar ที่มีบาร์สูง 30‑pixel.  
* `DatabarHeight60.png` – บาร์โค้ดเดียวกัน, แต่บาร์แต่ละบาร์สูงเป็นสองเท่า.

ทั้งสองภาพสามารถเปิดด้วยโปรแกรมดูภาพใดก็ได้ หรือฝังโดยตรงใน PDF, หน้า HTML, หรือป้ายพิมพ์

## ทำไมการปรับความสูงบาร์จึงสำคัญ

* **Scanning reliability:** บางสแกนเนอร์มีปัญหากับบาร์ที่สั้นมากบนสื่อความละเอียดต่ำ; การเพิ่มความสูงช่วยปรับปรุงการตรวจจับ.  
* **Design constraints:** แอปมือถืออาจต้องการบาร์โค้ดกะทัดรัด (30 px) ในขณะที่ใบเสร็จพิมพ์อาจต้องการขนาดใหญ่กว่า (60 px).  
* **Regulatory compliance:** อุตสาหกรรมบางประเภทกำหนดความสูงบาร์ขั้นต่ำสำหรับสัญลักษณ์ GS1 DataBar.

โดยการใช้ instance ของ `BarcodeGenerator` เดียวกันซ้ำ, คุณหลีกเลี่ยงค่าใช้จ่ายในการวิเคราะห์สตริงข้อมูลใหม่, ซึ่งเป็นประโยชน์อย่างยิ่งในสภาพแวดล้อมที่ต้องประมวลผลจำนวนมาก

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับแต่งที่แนะนำ |
|-----------|-------------------|
| ต้องการ X‑dimension ที่แตกต่าง | เปลี่ยน `XDimension.Pixels` ก่อน `Save` ครั้งแรก. |
| ต้องการสัญลักษณ์ที่แตกต่าง (เช่น DataBar Stacked) | ใช้ `EncodeTypes.DatabarStacked` เมื่อสร้าง `BarcodeGenerator`. |
| ต้องฝังบาร์โค้ดใน PDF | ใช้ `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` และเพิ่มสตรีมไปยังไลบรารี PDF. |
| ทำงานบน .NET Framework 4.6 | โค้ดเดียวกันทำงาน; เพียงอ้างอิง assembly ของ Aspose.BarCode ที่เหมาะสม. |

## เคล็ดลับมืออาชีพสำหรับการสร้างบาร์โค้ดที่เชื่อถือได้

* **Cache the generator** เมื่อคุณสร้างบาร์โค้ดจำนวนมากด้วยข้อมูลเดียวกันแต่ขนาดต่างกัน.  
* **

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลรวมตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการใช้งานทางเลือกในโครงการของคุณ

- [วิธีสร้างและปรับความสูงบาร์โค้ดสำหรับ One-Dimensional Databar ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [วิธีสร้างภาพ PNG ของ databar ด้วย C# และ Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [วิธีสร้างบาร์โค้ดกำหนดขนาดกำหนดเองและบันทึกภาพใน C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}