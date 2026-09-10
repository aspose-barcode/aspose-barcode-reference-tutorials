---
category: general
date: 2026-07-18
description: เรียนรู้วิธีสร้างภาพบาร์โค้ดด้วยเครื่องสร้างบาร์โค้ด .net และเปลี่ยนความสูงของบาร์โค้ดได้อย่างง่ายดายสำหรับสัญลักษณ์
  GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: th
lastmod: 2026-07-18
og_description: .NET barcode generator ช่วยให้คุณสร้างภาพบาร์โค้ดได้อย่างรวดเร็ว คู่มือนี้แสดงวิธีสร้างบาร์โค้ด
  ปรับความสูงของบาร์ และบันทึกเป็นไฟล์ PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: เปลี่ยนความสูงของบาร์โค้ดด้วยเครื่องสร้างบาร์โค้ด .net
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .net barcode generator – เปลี่ยนความสูงของบาร์โค้ด
url: /th/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – เปลี่ยนความสูงของบาร์โค้ด

เคยสงสัยไหมว่า **วิธีสร้างภาพบาร์โค้ด** อย่างไรโดยไม่ต้องใช้เครื่องมือของบุคคลที่สามหลายสิบเครื่อง? ในโลก .NET มีวิธีที่ค่อนข้างเรียบง่ายและสำคัญคือ **.net barcode generator**. ด้วยเพียงไม่กี่บรรทัดของ C# คุณสามารถสร้างสัญลักษณ์ GS1‑Databar Omni‑Directional ปรับความสูงของบาร์ และบันทึกผลลัพธ์เป็นไฟล์ PNG ได้.

หากคุณกำลังสร้างระบบจัดการสินค้าคงคลัง, เครื่องพิมพ์ฉลากจัดส่ง, หรือแอปใด ๆ ที่ต้องการรหัสที่สแกนได้, บทเรียนนี้จะพาคุณจากศูนย์สู่บาร์โค้ดที่ทำงานได้ในไม่กี่นาที. เราจะอธิบายโค้ดทั้งหมด, ทำไมแต่ละการตั้งค่าถึงสำคัญ, และแสดงวิธี **change barcode height** โดยไม่ทำให้สเปคเสียหาย.

## สิ่งที่คุณต้องการ

- .NET 6.0 หรือใหม่กว่า (API ทำงานเช่นเดียวกันบน .NET Framework 4.7+)
- การอ้างอิงไปยังไลบรารีบาร์โค้ด (เช่น Aspose.BarCode for .NET – คลาสเดียวกันนี้ใช้ในคิทเชิงพาณิชย์หลายชุด)
- สภาพแวดล้อมการพัฒนา (Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#)
- โฟลเดอร์ที่คุณมีสิทธิ์เขียน – บทเรียนจะบันทึกไฟล์ PNG ลงในที่นั้น

เท่านี้เอง. ไม่ต้องมีแพ็กเกจ NuGet เพิ่มเติมนอกจากไลบรารีบาร์โค้ดเอง.

## การใช้ .net barcode generator เพื่อเปลี่ยนความสูงของบาร์โค้ด

ด้านล่างเป็น **โปรแกรมคอนโซลที่สมบูรณ์และสามารถรันได้**. คัดลอกไปยังโปรเจกต์ C# ใหม่, ปรับโฟลเดอร์ผลลัพธ์, แล้วกด F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

| บรรทัด | เหตุผล |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | สร้างอินสแตนซ์ของ **.net barcode generator** ด้วยสัญลักษณ์และข้อมูลที่ต้องการ. enum `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีให้ใช้รูปแบบ GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimension คือความกว้างของบาร์ที่บางที่สุด. การตั้งค่าเป็น *2 pixels* ให้ภาพคมชัดบนจอส่วนใหญ่และทำให้ขนาดไฟล์เล็กลง. |
| `BarHeight.Pixels = 30;` | นี่คือขั้นตอน **change barcode height** ที่กำหนดความสูงของแต่ละบาร์. ความสูง 30 pixel เป็นค่าเริ่มต้นที่ดีสำหรับป้ายขนาดเล็ก. |
| `generator.Save(...);` | บันทึกบาร์โค้ดเป็นไฟล์ PNG. PNG เป็นรูปแบบ loss‑less ซึ่งหมายความว่าตัวสแกนจะเห็นรูปแบบที่คุณสร้างอย่างแม่นยำ. |
| `BarHeight.Pixels = 60;` | ที่นี่เราจะ **change barcode height** อีกครั้ง—ครั้งนี้เป็น 60 pixels. ไลบรารีจะรีเรนเดอร์สัญลักษณ์ใหม่โดยอัตโนมัติเมื่อคุณเรียก `Save` ครั้งที่สอง. |
| `Console.WriteLine(...);` | ให้ข้อมูลตอบกลับอย่างรวดเร็วว่ากระบวนการเสร็จสิ้นโดยไม่มีข้อยกเว้น. |

> **Pro tip:** หากคุณต้องการผลลัพธ์ความละเอียดสูงสำหรับการพิมพ์, เปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Tiff` และเพิ่มค่า `Resolution` (เช่น `generator.Parameters.ImageResolution = 300;`). ความสูงของบาร์จะยังคงถูกนำไปใช้, เพียงแต่แสดงผลที่ DPI ที่ละเอียดกว่า.

## วิธีสร้างภาพบาร์โค้ดด้วยการตั้งค่าต่าง ๆ

ส่วนโค้ดข้างต้นครอบคลุมพื้นฐาน, แต่สถานการณ์จริงมักต้องการการปรับแต่งเพิ่มเติม:

### ปรับ X‑dimension สำหรับการพิมพ์ขนาดใหญ่
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
การเพิ่ม X‑dimension ทำให้บาร์โค้ดทั้งหมดใหญ่ขึ้นโดยไม่เปลี่ยนแปลงข้อมูลที่เข้ารหัส. นี้เป็นประโยชน์เมื่อคุณพิมพ์บนฉลากขนาดใหญ่.

### เปลี่ยนรูปแบบการส่งออก
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG สามารถขยายได้ไม่จำกัด, เหมาะอย่างยิ่งสำหรับสแกนเนอร์บนเว็บที่ต้องการเวกเตอร์คมชัด.

### เพิ่มข้อความที่อ่านได้โดยมนุษย์
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
การเปิดใช้งาน `CodeTextVisible` จะเพิ่มข้อมูลดิบใต้บาร์โค้ด, มีประโยชน์สำหรับการตรวจสอบระหว่างการทดสอบ.

## ข้อผิดพลาดทั่วไปเมื่อคุณ **change barcode height**

1. **Height too small** – ตัวสแกนบางรุ่นต้องการความสูงบาร์ขั้นต่ำ (มักประมาณ 10 mm ในหน่วยจริง). หากตั้งค่า `BarHeight.Pixels` ต่ำเกินไป, ภาพที่สร้างอาจอ่านไม่ได้บนสแกนเนอร์จริง. ควรทดสอบกับฮาร์ดแวร์เป้าหมายเสมอ.
2. **Mismatched X‑dimension and height** – ความสูงบาร์ที่มากเกินไปร่วมกับ X‑dimension ที่เล็กเกินไปอาจทำให้บาร์ดูยืดและอาจทำให้การถอดรหัสล้มเหลว. ควรรักษาอัตราส่วนที่สมดุล (ประมาณ 3:1 ถึง 5:1) เว้นแต่สเปคจะกำหนดอย่างอื่น.
3. **Forgetting to reset parameters** – ตัวสร้างบาร์โค้ดจะเก็บสถานะระหว่างการบันทึก. หากคุณเปลี่ยน `BarHeight` สำหรับภาพหนึ่งแล้วใช้อินสแตนซ์เดียวกันสำหรับบาร์โค้ดอื่น, ความสูงก่อนหน้าจะยังคงอยู่. ให้รีเซ็ตคุณสมบัตินั้นหรือสร้าง `BarcodeGenerator` ใหม่สำหรับแต่ละบาร์โค้ดที่แตกต่างกัน.

## ตัวอย่างเต็มขั้นตอน (รวมการติดตั้ง NuGet)

หากคุณเริ่มจากศูนย์, ทำตามขั้นตอนเหล่านี้เพื่อให้โปรเจกต์ทำงานได้:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

แทนที่ `Program.cs` ที่สร้างอัตโนมัติด้วยโค้ดบล็อกที่แสดงก่อนหน้า, **อย่าลืมแทนที่ `YOUR_DIRECTORY`** ด้วยเส้นทางเช่น `Path.Combine(Environment.CurrentDirectory, "output")`. จากนั้น:

```bash
dotnet run
```

คุณควรเห็นไฟล์ PNG สองไฟล์ในโฟลเดอร์ `output`:

- `DatabarBarHeight30Pixels.png` – บาร์โค้ดความสูง 30 pixel แบบกะทัดรัด.
- `DatabarBarHeight60Pixels.png` – เวอร์ชันความสูง 60 pixel ที่สูงกว่า.

ทั้งสองภาพจะดูคล้ายกัน, แต่ภาพที่สองจะมีบาร์ยาวกว่าอย่างชัดเจน, ทำให้สแกนเนอร์ความละเอียดต่ำอ่านได้ง่ายขึ้น.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator แสดงผลลัพธ์ที่มีความสูงของบาร์ต่างกัน"}

## สรุป & ขั้นตอนต่อไป

เราได้อธิบายวิธี **generate barcode** ด้วย **.net barcode generator**, ปรับแต่งคุณสมบัติ **change barcode height** และบันทึกผลลัพธ์เป็น PNG. สิ่งที่ควรจำคือ:

- สร้างอินสแตนซ์ของ generator ด้วย `EncodeTypes` ที่ถูกต้อง.
- ควบคุมขนาดภาพด้วย `XDimension` และ `BarHeight`.
- เรียก `Save` หลังจากแต่ละการเปลี่ยนแปลงเพื่อบันทึกภาพใหม่.
- ปรับความละเอียด, รูปแบบ,

## สิ่งที่คุณควรเรียนต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณเอง.

- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพที่กำหนดเองโดยใช้ Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [วิธีสร้าง dotcode พร้อมข้อความโค้ดขยายโดยใช้ Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}