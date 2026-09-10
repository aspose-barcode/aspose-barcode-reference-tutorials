---
category: general
date: 2026-07-24
description: สร้างบาร์โค้ด PDF417 ด้วย C# โดยใช้ Aspose.BarCode. เรียนรู้วิธีสร้างบาร์โค้ด
  PDF417 ด้วย C# ในโหมดคอมแพคท์ภายในไม่กี่นาที.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: th
lastmod: 2026-07-24
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็วด้วย Aspose.BarCode บทเรียนนี้จะแสดงวิธีสร้างบาร์โค้ด
  PDF417 ด้วย C# ในโหมดคอมแพคท์ รวมถึงการตั้งค่า โค้ด และการตรวจสอบ
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: สร้างบาร์โค้ด PDF417 ใน C# – คู่มือเร็ว
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: สร้างบาร์โค้ด PDF417 ด้วย C# – สร้างบาร์โค้ด PDF417 C#
url: /th/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือการเขียนโปรแกรมแบบครบถ้วน

เคยสงสัยไหมว่า **การสร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน C# อย่างไรโดยไม่ต้องค้นหาผ่านกระทู้ในฟอรั่มที่ไม่มีที่สิ้นสุด? คุณไม่ได้เป็นคนเดียว ไม่ว่าคุณจะกำลังสร้างระบบจองตั๋ว, บัตรประจำตัวที่ปลอดภัย, หรือแค่ต้องการวิธีรวดเร็วในการฝังข้อมูลในรูปแบบที่พิมพ์ได้ การเชี่ยวชาญรูปแบบ PDF417 สามารถช่วยคุณประหยัดเวลาหลายชั่วโมงจากการลองผิดลองถูก

ในคู่มือนี้เราจะเดินผ่าน **ตัวอย่างที่พร้อมรันเต็มรูปแบบ** ที่แสดงให้คุณเห็นอย่างชัดเจนว่า **สร้างบาร์โค้ด PDF417 ด้วย C#** อย่างไรโดยใช้ไลบรารี Aspose.BarCode ที่เป็นที่นิยม เราจะครอบคลุมทุกอย่างตั้งแต่การติดตั้งแพ็กเกจ NuGet จนถึงการปรับโหมดคอมแพค เพื่อให้คุณคัดลอก‑วางโค้ดและเห็นผลลัพธ์ทันที

## สิ่งที่คุณจะได้เรียนรู้

- วิธีตั้งค่าไลบรารี Aspose.BarCode ในโครงการ .NET  
- คำสั่ง C# ที่จำเป็นเพื่อ **สร้างบาร์โค้ด PDF417** พร้อมข้อความที่กำหนดเอง, ขนาดโมดูล, และจำนวนคอลัมน์  
- เหตุผลที่การเปิด/ปิดตัวเลือก *Compact* (Truncate) มีความสำคัญสำหรับข้อมูลที่หนาแน่น  
- วิธีการบันทึกบาร์โค้ดเป็น PNG และตรวจสอบผลลัพธ์  

ไม่จำเป็นต้องมีประสบการณ์บาร์โค้ดมาก่อน; เพียงแค่เข้าใจพื้นฐานของ C# และ Visual Studio (หรือ IDE ที่คุณชอบ) เท่านั้น เมื่อเสร็จสิ้นคุณจะมีเมธอดที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในโครงการใดก็ได้ที่ต้องการภาพ PDF417

## ข้อกำหนดเบื้องต้น

| ความต้องการ | ทำไมจึงสำคัญ |
|-------------|----------------|
| .NET 6.0 หรือใหม่กว่า (หรือ .NET Framework 4.7+) | Aspose.BarCode รองรับทั้งสอง; runtime ที่ใหม่กว่าให้ประสิทธิภาพดียิ่งขึ้น |
| Visual Studio 2022 (หรือ VS Code พร้อมส่วนขยาย C#) | ให้ IntelliSense และการดีบักที่ง่าย |
| การเชื่อมต่ออินเทอร์เน็ต (สำหรับการกู้คืน NuGet ครั้งแรก) | ไลบรารีจะถูกดึงจาก NuGet.org |
| ความรู้พื้นฐานของ C# | จำเป็นสำหรับการเข้าใจโครงสร้างคลาสและการเรียกเมธอด |

ถ้าคุณมีทั้งหมดแล้ว เยี่ยม—มาเริ่มกันเลย

## ติดตั้งแพ็กเกจ NuGet ของ Aspose.BarCode

เปิดโฟลเดอร์โครงการของคุณในเทอร์มินัลและรัน:

```bash
dotnet add package Aspose.BarCode
```

หรือ, ภายใน Visual Studio, คลิกขวา **Dependencies → Manage NuGet Packages**, ค้นหา *Aspose.BarCode*, แล้วคลิก **Install**. บรรทัดเดียวนี้จะนำเข้าชนิดทั้งหมดที่เราจะใช้ รวมถึง `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`.

> **เคล็ดลับ:** หลังการติดตั้ง ให้ทำการ clean และ rebuild โซลูชันเพื่อให้แน่ใจว่า assembly ถูกอ้างอิงอย่างถูกต้อง.

## สร้างบาร์โค้ด PDF417 – การตั้งค่าและการพึ่งพา

ก่อนอื่นเราต้องมีบล็อก `using` ที่ดึงเนมสเปซที่เกี่ยวข้องเข้ามาในสโคป

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

เนมสเปซเหล่านี้ให้เราเข้าถึงคลาสตัวสร้างและ enumeration ของประเภทบาร์โค้ด ไม่ซับซ้อน—แค่สามบรรทัด แล้วเราก็พร้อมเริ่มสร้างบาร์โค้ด

## สร้างบาร์โค้ด PDF417 ด้วย C# – การดำเนินการแบบขั้นตอน

ด้านล่างเป็น **โปรแกรมคอนโซลที่ทำงานอิสระ** ที่สร้างบาร์โค้ด PDF417 แบบคอมแพคจากสตริง `"Åspóse.Barcóde©"` และบันทึกเป็น `CompactPdf417.png`. คุณสามารถเปลี่ยนข้อความเป็นอะไรก็ได้; ตัวสร้างจะจัดการกับอักขระ Unicode ได้โดยอัตโนมัติ

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### ทำไมแต่ละขั้นตอนจึงสำคัญ

1. **การกำหนดข้อมูล** – PDF417 สามารถเก็บได้ประมาณ ~1850 ตัวอักษร, แต่เราเก็บสั้นเพื่อการสาธิต การสนับสนุน Unicode หมายความว่าตัวอักษรที่มีเครื่องหมายสำเนียงจะไม่ทำให้เกิดข้อผิดพลาด  
2. **การสร้างตัวสร้าง** – ค่า enum `EncodeTypes.Pdf417` บอก Aspose ว่าจะใช้สัญลักษณ์ใด; การเปลี่ยนเป็น `EncodeTypes.QR` จะให้คุณได้ QR code แทน  
3. **X‑dimension** – ควบคุมความกว้างของแต่ละโมดูล (สี่เหลี่ยมเล็ก ๆ ที่ประกอบบาร์โค้ด) ค่า `2` พิกเซลให้ภาพคมชัดและยังอ่านได้เมื่อพิมพ์ที่ 300 dpi  
4. **ตัวเลือก PDF417** – `Columns` มีผลต่ออัตราส่วนของบาร์โค้ด; คอลัมน์น้อยทำให้ภาพสูงขึ้น, ซึ่งอาจเป็นประโยชน์สำหรับใบเสร็จ `Truncate` (หรือที่เรียกว่า *Compact mode*) ลบการเติมรูปแบบเริ่ม/หยุด, ลดขนาดไฟล์โดยไม่เสียความสมบูรณ์ของข้อมูล  
5. **เส้นทางการบันทึก** – การใช้ `Environment.CurrentDirectory` ทำให้ภาพถูกบันทึกอยู่ใกล้ไฟล์ executable, ง่ายต่อการค้นหาในระหว่างการพัฒนา  
6. **การบันทึก** – `BarCodeImageFormat.Png` ให้คุณภาพ lossless, เหมาะสำหรับการประมวลผลต่อหรือฝังใน PDF  

รันโปรแกรม (`dotnet run` หรือกด **F5** ใน Visual Studio). หลังจากไม่กี่วินาทีคุณควรเห็นข้อความคอนโซลยืนยันตำแหน่งไฟล์, และไฟล์ PNG จะปรากฏในโฟลเดอร์โครงการของคุณ

![ตัวอย่างการสร้างบาร์โค้ด PDF417 – ภาพ PNG ของบาร์โค้ด PDF417 แบบคอมแพคที่สร้างด้วย C#](generated-pdf417.png)

*Image alt text: ตัวอย่างการสร้างบาร์โค้ด PDF417 – ภาพ PNG ของบาร์โค้ด PDF417 แบบคอมแพคที่สร้างด้วย C#.*

## กำหนดค่า Compact Mode – ตัวเลือก pdf417 ของตัวสร้างบาร์โค้ด c#

หากคุณต้องการบาร์โค้ดขนาดใหญ่ขึ้น (อาจเพื่อสแกนจากระยะไกล), ปรับคุณสมบัติ `Columns` และ `Rows`. นี่คือตัวอย่างสั้น ๆ ที่แสดงการกำหนดค่าทางเลือกอื่น ๆ:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **คำถามทั่วไป:** *การปิดการใช้งาน Truncate จะทำให้สแกนเนอร์ที่มีอยู่เสียหายหรือไม่?*  
> ปกติไม่ใช่. สแกนเนอร์สมัยใหม่ส่วนใหญ่เข้าใจทั้ง PDF417 ขนาดเต็มและแบบคอมแพค อย่างไรก็ตาม หากคุณมุ่งเป้าไปที่ฮาร์ดแวร์เก่า ให้ตั้งค่า `Truncate` เป็น `false`.

## บันทึกและตรวจสอบ – วิธีการสร้างผลลัพธ์ pdf417 barcode

หลังจากบันทึก, คุณสามารถเปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้. เพื่อตรวจสอบว่าบาร์โค้ดเข้ารหัสข้อมูลที่ต้องการหรือไม่, ใช้ `BarCodeReader` ของ Aspose:



## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณเอง

- [วิธีสร้างบาร์โค้ด – Compact PDF417 ด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [ไลบรารีบาร์โค้ด java – เพิ่มบาร์โค้ดลงใน PDF ด้วย Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}