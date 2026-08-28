---
category: general
date: 2026-07-15
description: สร้างบาร์โค้ดหลายทิศทางใน C# อย่างรวดเร็วด้วย Aspose.BarCode – เรียนรู้วิธีสร้างบาร์โค้ดใน
  C# พร้อมความสูงของบาร์และมิติ X ที่ปรับได้
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: th
lastmod: 2026-07-15
og_description: สร้างบาร์โค้ดหลายทิศทางใน C# ด้วย Aspose.BarCode. เชี่ยวชาญการสร้างบาร์โค้ด
  C# โดยปรับค่า XDimension และ BarHeight เพื่อผลลัพธ์ที่สมบูรณ์แบบ.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: สร้างบาร์โค้ดหลายทิศทางใน C# – คู่มือการเขียนโปรแกรมอย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: สร้างบาร์โค้ดหลายทิศทางใน C# – คู่มือขั้นตอนโดยละเอียด
url: /th/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด omni-directional ใน C# – คู่มือขั้นตอนต่อขั้นตอน

เคยสงสัยไหมว่าการสร้างบาร์โค้ด C# ที่สอดคล้องกับสัญลักษณ์ GS1 DataBar Omni‑Directional เป็นอย่างไร? คุณไม่ได้เป็นคนเดียว ในบทแนะนำนี้เราจะ **สร้างบาร์โค้ด omni-directional** ตั้งแต่ต้น ปรับ X‑dimension และปรับความสูงของบาร์—ทั้งหมดโดยใช้ไลบรารี Aspose.BarCode.

เราจะเดินผ่านสถานการณ์จริง: คุณต้องการบาร์โค้ดที่กะทัดรัดและความหนาแน่นสูงสำหรับป้ายค้าปลีก และคุณต้องการควบคุมขนาดภาพอย่างเต็มที่ เมื่อเสร็จสิ้นคุณจะมีไฟล์ PNG สองไฟล์—หนึ่งไฟล์ที่มีความสูงบาร์ 30 px และอีกไฟล์ที่มี 60 px—พร้อมนำไปใช้ในกระบวนการพิมพ์ใด ๆ

## ข้อกำหนดเบื้องต้น

- .NET 6 (หรือ .NET runtime ล่าสุดใด ๆ) ติดตั้งบนเครื่องของคุณ.  
- Visual Studio 2022 หรือ VS Code—IDE ที่คุณชื่นชอบก็ใช้ได้.  
- แพคเกจ NuGet ฟรี Aspose.BarCode for .NET (`Aspose.BarCode`).

ไม่มีการพึ่งพาอื่น ๆ ที่จำเป็น หากคุณไม่เคยใช้ NuGet มาก่อน เพียงเปิด Package Manager Console แล้วรัน:

```powershell
Install-Package Aspose.BarCode
```

## สร้างบาร์โค้ด omni-directional – ทำความเข้าใจพื้นฐาน

สัญลักษณ์ **GS1 DataBar Omni‑Directional** ถูกออกแบบให้สแกนได้จากทุกทิศทาง ทำให้เหมาะกับป้ายขอบชั้นวางสินค้า เมื่อคุณเรียก `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` ไลบรารีจะทำงานหนักให้: เข้ารหัสข้อมูล, ใช้กฎของสัญลักษณ์, และเตรียมภาพแรสเตอร์

> **เคล็ดลับ:** ควรห่อข้อมูลดิบในรูปแบบ Application Identifier (AI) ที่เหมาะสมเสมอ เช่น `"(01)12345678901231"` สำหรับ GTIN‑14 ซึ่งบอกสแกนเนอร์ว่าตัวเลขเหล่านั้นหมายถึงอะไร

## ขั้นตอนที่ 1 – ตั้งค่า Barcode Generator (how to generate barcode c#)

แรกเราจะสร้างอ็อบเจกต์ generator นี่คือหัวใจหลักของ **how to generate barcode c#** ด้วย Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

ค่า enum `EncodeTypes.DatabarOmniDirectional` บอกเครื่องยนต์ว่าจะใช้สัญลักษณ์ใด อาร์กิวเมนต์ที่สองคือสตริงข้อมูลดิบที่ห่อไว้ใน GTIN AI แล้ว

## ขั้นตอนที่ 2 – ปรับ X‑Dimension (barcode XDimension)

**barcode XDimension** ควบคุมความกว้างของบาร์ที่เล็กที่สุด ค่า 2 px เป็นการสมดุลที่ดีระหว่างการอ่านและความกะทัดรัดสำหรับเครื่องพิมพ์ป้ายส่วนใหญ่.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

หากต้องการลักษณะที่ละเอียดหรือหยาบกว่า เพียงเปลี่ยนตัวเลข จำไว้ว่า: X‑dimension เป็นหน่วยพื้นฐาน; ความกว้างของบาร์อื่น ๆ เป็นผลคูณของค่านี้.

## ขั้นตอนที่ 3 – สร้างภาพแรกด้วย Bar Height 30 px (barcode BarHeight)

ตอนนี้เราตั้งค่า **barcode BarHeight** เป็น 30 px และบันทึกภาพ ผลลัพธ์คือบาร์โค้ดขนาดพอเหมาะที่พอดีกับป้ายมาตรฐาน.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนไฟล์ PNG ลงดิสก์ คุณสามารถเปลี่ยนเป็น `BarCodeImageFormat.Jpeg` หากต้องการผลลัพธ์เป็น JPEG.

## ขั้นตอนที่ 4 – เพิ่ม Bar Height เป็น 60 px สำหรับป้ายขนาดใหญ่ (barcode BarHeight)

บางครั้งต้องการบาร์โค้ดขนาดใหญ่กว่า—อาจเป็นป้ายชั้นวางที่อยู่ห่างจากสแกนเนอร์มากกว่า ให้เราขยายความสูงเป็นสองเท่า.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

สังเกตว่าเรา **ไม่ต้อง** สร้าง generator ใหม่; เราเพียงปรับพารามิเตอร์และใช้วัตถุเดียวกันซ้ำ นั่นช่วยประหยัดหน่วยความจำและทำให้โค้ดเป็นระเบียบ.

## ขั้นตอนที่ 5 – บันทึกภาพที่สอง (how to generate barcode c#)

สุดท้าย เราบันทึก PNG ที่สอง ตอนนี้คุณมีไฟล์สองไฟล์ที่แตกต่างกันเพียงความสูงของบาร์.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### ผลลัพธ์ที่คาดหวัง

- `DatabarBarHeight30Pixels.png` – บาร์โค้ด omni‑directional สูง 30 px.  
- `DatabarBarHeight60Pixels.png` – ข้อมูลเดียวกัน แต่บาร์โค้ดสูง 60 px.

เปิดไฟล์ในโปรแกรมดูรูปใด ๆ คุณจะเห็นบาร์ที่คมชัดและสแกนได้ซึ่งสอดคล้องกับสเปค GS1 DataBar Omni‑Directional.

## คำถามทั่วไปและกรณีขอบ

### ถ้าต้องการ X‑dimension ที่แตกต่าง?

เพียงกำหนดค่าตัวเลขใหม่ก่อนเรียก `Save` สำหรับการพิมพ์ความหนาแน่นสูงมาก คุณอาจลดลงเป็น 1 px แต่ควรทดสอบกับสแกนเนอร์ของคุณก่อน—บางอุปกรณ์อาจทำงานได้ยากกับบาร์ที่มีความกว้างต่ำกว่า 2 px.

### สามารถเพิ่มข้อความที่อ่านได้โดยมนุษย์ใต้บาร์โค้ดได้หรือไม่?

ได้ ตั้งค่า `barcodeGenerator.Parameters.Barcode.CodeText` เป็นสตริงและอาจปรับ `barcodeGenerator.Parameters.Barcode.CodeLocation` เป็น `BarCodeTextLocation.Below` สิ่งนี้เป็นประโยชน์ในสภาพแวดล้อมค้าปลีกที่ต้องแสดง GTIN ตัวเลขให้มองเห็น.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### PNG เป็นฟอร์แมตที่ดีที่สุดสำหรับการพิมพ์หรือไม่?

PNG เป็นฟอร์แมต lossless ซึ่งรักษาขอบคมที่สแกนเนอร์บาร์โค้ดต้องการ หากระบบต่อไปของคุณต้องการฟอร์แมตอื่น (TIFF, BMP) เพียงเปลี่ยนค่า enum `BarCodeImageFormat`.

## ตัวอย่างทำงานเต็มรูปแบบ (create omni-directional barcode)

ด้านล่างเป็นโปรแกรมที่สมบูรณ์พร้อมรัน คัดลอกและวางลงในโปรเจกต์คอนโซลใหม่แล้วกด **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

รันโปรแกรม ตรวจสอบโฟลเดอร์ผลลัพธ์ แล้วคุณจะเห็นไฟล์ PNG สองไฟล์ตามที่อธิบายไว้.

## สรุป

เราได้แสดง **how to generate barcode C#** โค้ดที่สร้าง **create omni-directional barcode** ด้วย Aspose.BarCode โดยการปรับ **barcode XDimension** และ **barcode BarHeight** คุณจะได้การควบคุมขนาดภาพอย่างละเอียดโดยไม่เสียความน่าเชื่อถือในการสแกน.

## ขั้นตอนต่อไปคืออะไร?

- ทดลองใช้การตั้งค่าอื่น ๆ ของ **GS1 DataBar Omni-Directional** เช่น `Color` หรือ `Margin`.  
- รวมบาร์โค้ดหลายรายการบนแคนวาสเดียวโดยใช้ `Graphics` สำหรับการออกแบบป้ายที่ซับซ้อน.  
- ผสาน generator เข้ากับเว็บ API เพื่อให้แพลตฟอร์ม e‑commerce ของคุณสามารถสร้างบาร์โค้ดตามความต้องการ.

มีไอเดียหรือเคล็ดลับที่อยากแบ่งปันไหม? แสดงความคิดเห็นและเราจะสนทนาต่อไป ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ.

- [วิธีสร้างบาร์โค้ด – การกำหนดค่า Code 39 ด้วย Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [วิธีสร้าง Quiet Zone ของบาร์โค้ดสำหรับ ITF-14 ด้วย Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [วิธีสร้าง quiet zone ของบาร์โค้ดสำหรับ Code 16K ด้วย Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}