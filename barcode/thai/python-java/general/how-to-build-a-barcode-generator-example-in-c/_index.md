---
category: general
date: 2026-09-19
description: ตัวอย่างตัวสร้างบาร์โค้ดที่แสดงวิธีการเปลี่ยนความสูง, สร้าง DataBar Omni‑Directional,
  และปรับขนาดบาร์โค้ดสำหรับการแสดงผลภาพใน C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: th
lastmod: 2026-09-19
og_description: ตัวอย่างการสร้างบาร์โค้ดที่สอนวิธีเปลี่ยนความสูง, สร้าง DataBar Omni‑Directional,
  และปรับขนาดบาร์โค้ดสำหรับภาพ PNG ด้วย C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: ตัวอย่างการสร้างบาร์โค้ดใน C# – คู่มือแบบทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างตัวอย่างเครื่องสร้างบาร์โค้ดด้วย C#
url: /th/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างตัวสร้างบาร์โค้ดด้วย C# – คู่มือการเขียนโปรแกรมเต็มรูปแบบ

หากคุณต้องการ **ตัวอย่างตัวสร้างบาร์โค้ด** สำหรับโครงการ .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่าต้องสร้าง, ตั้งค่า, และบันทึกบาร์โค้ด DataBar Omni‑Directional ด้วย C# อย่างไร คุณจะได้เรียนรู้วิธีเปลี่ยนความสูง, ปรับขนาดบาร์โค้ด, และส่งออกภาพ PNG คุณภาพสูง—all ในแอปพลิเคชันคอนโซลที่สามารถรันได้ในครั้งเดียว

ขั้นตอนต่อไปนี้ครอบคลุมทุกอย่างตั้งแต่การติดตั้ง SDK ที่จำเป็นจนถึงการปรับ X‑dimension และความสูงของบาร์ เมื่อจบบทเรียนคุณจะมีตัวสร้างบาร์โค้ดที่พร้อมใช้งานซึ่งสามารถนำไปผสานกับการออกใบแจ้งหนี้, ระบบสินค้าคงคลัง, หรือกระบวนการสแกนใด ๆ

## สิ่งที่ต้องมีล่วงหน้า

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)
* ไลเซนส์ที่ใช้งานได้สำหรับ **Aspose.BarCode for .NET** (รุ่นทดลองฟรีก็ใช้ทดสอบได้)

หากคุณใช้ไลบรารีอื่น แนวคิดการปรับขนาดและการบันทึกภาพยังคงเหมือนเดิม; เพียงเปลี่ยนการเรียก API ตามที่ต้องการ

## ขั้นตอนที่ 1: ตั้งค่าโครงการและเพิ่มแพ็กเกจ Aspose.BarCode

สร้างโปรเจกต์คอนโซลใหม่และอ้างอิงไลบรารีบาร์โค้ด

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

คำสั่ง `dotnet add package` จะดึงเวอร์ชันเสถียรล่าสุดของ Aspose.BarCode ซึ่งรองรับสัญลักษณ์ DataBar Omni‑Directional อย่างเต็มที่

## ขั้นตอนที่ 2: เขียนตัวอย่างตัวสร้างบาร์โค้ดเต็มรูปแบบ

เปิด **Program.cs** แล้วแทนที่เนื้อหาเดิมด้วยโค้ดต่อไปนี้ บล็อกนี้เป็น **ตัวอย่างตัวสร้างบาร์โค้ด** อย่างครบถ้วน ไม่มีส่วนที่ขาดหาย

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

* **Create a barcode generator** – ตัวสร้าง `BarcodeGenerator` เชื่อมประเภทการเข้ารหัส (`EncodeTypes.DatabarOmniDirectional`) กับข้อมูลที่คุณต้องการฝัง นี่คือหัวใจของขั้นตอน **how to create databar**  
* **Adjust barcode dimensions** – คุณสมบัติ `XDimension.Pixels` กำหนดความกว้างของบาร์ที่แคบที่สุด การเปลี่ยนค่านี้ส่งผลต่อขนาดโดยรวมและความแม่นยำในการสแกน  
* **How to change height** – คุณสมบัติ `BarHeight.Pixels` ควบคุมขนาดแนวตั้ง การเพิ่มความสูงช่วยให้อ่านได้ง่ายขึ้นสำหรับสแกนเนอร์พกพา ส่วนการลดความสูงจะประหยัดพื้นที่บนป้ายขนาดเล็ก  
* **Optional tweaks** – การตั้งค่าสีพื้นหน้า/พื้นหลังหรือระดับการแก้ไขข้อผิดพลาดเป็นตัวเลือก แต่แสดงให้เห็นวิธีขยายแนวคิด **adjust barcode dimensions**  
* **Create barcode image C#** – เมธอด `Save` จะเขียนบาร์โค้ดลงดิสก์ การใช้ `BarCodeImageFormat.Png` ทำให้ได้การบีบอัดแบบไม่มีการสูญเสีย ซึ่งเหมาะกับแอปพลิเคชันส่วนใหญ่  

## ขั้นตอนที่ 3: สร้างและรันตัวอย่าง

คอมไพล์และเรียกใช้โปรแกรม

```bash
dotnet run
```

คุณควรเห็นผลลัพธ์บนคอนโซล

```
Barcode saved to DatabarOmniDirectional.png
```

ไฟล์ชื่อ **DatabarOmniDirectional.png** จะปรากฏในโฟลเดอร์โปรเจกต์ การเปิดภาพจะเห็นบาร์โค้ด DataBar Omni‑Directional ที่คมชัดพร้อมสแกน

## วิธีเปลี่ยนความสูงหลังจากสร้าง

หากต้องการสร้างบาร์โค้ดที่มีความสูงต่างกัน ให้ห่อการกำหนดความสูงไว้ในเมธอด

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

เรียก `SetBarHeight(generator, 45);` ก่อน `Save` วิธีนี้ทำให้คุณ **how to change height** ได้แบบไดนามิกตามอินพุตของผู้ใช้หรือไฟล์กำหนดค่า

## วิธีสร้างบาร์โค้ด DataBar Omni‑Directional ด้วยข้อมูลที่แตกต่าง

สัญลักษณ์ DataBar Omni‑Directional รองรับ GTIN‑14, GTIN‑13 และตัวระบุเชิงตัวเลขอื่น ๆ เพื่อเข้ารหัสค่าที่ต่างออกไป เพียงเปลี่ยนสตริงในคอนสตรัคเตอร์

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

อย่าลืมให้ข้อมูลเป็นตัวเลขและอยู่ในรูปแบบที่ถูกต้อง; ไม่เช่นนั้นตัวสร้างจะโยน `BarcodeException`

## ปรับขนาดบาร์โค้ดสำหรับสถานการณ์การพิมพ์ที่แตกต่าง

เครื่องพิมพ์และขนาดป้ายที่ต่างกันต้องการ X‑dimension และความสูงที่ต่างกัน ใช้ตารางต่อไปนี้เป็นอ้างอิงอย่างรวดเร็ว

| สถานการณ์ | X‑Dimension (pixels) | ความสูงของบาร์ (pixels) |
|------------------------------|----------------------|---------------------|
| ป้ายขนาดเล็ก (25 mm × 15 mm) | 1 | 20 |
| ป้ายขนาดกลาง (50 mm × 30 mm) | 2 | 30 |
| ป้ายขนาดใหญ่ (100 mm × 50 mm) | 3 | 45 |

กำหนดค่าเหล่านี้โดยตั้ง `generator.Parameters.Barcode.XDimension.Pixels` และ `BarHeight.Pixels` ตามที่ต้องการ

## เคล็ดลับระดับมืออาชีพ: ตรวจสอบบาร์โค้ดที่สร้างขึ้น

ก่อนส่งป้าย คุณสามารถตรวจสอบความสามารถในการอ่านได้โดยโปรแกรม

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

สคริปต์นี้แสดงการตรวจสอบ **adjust barcode dimensions** อย่างรวดเร็ว เพื่อให้แน่ใจว่าบาร์โค้ดตรงตามข้อกำหนดการสแกน

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | สาเหตุ | วิธีแก้ |
|--------------------------------------|---------------------------------------------|---------------------------------------------------------------------|
| ใช้ข้อมูลที่ไม่เป็นตัวเลขกับ DataBar | DataBar ต้องการรูปแบบ GTIN ตัวเลข | ตรวจสอบให้สตริงตรงกับรูปแบบ `(01)XXXXXXXXXXXXX` |
| ตั้งค่า X‑dimension เป็น 0 หรือค่าติดลบ | ไลบรารีโยน `ArgumentOutOfRangeException` | ใช้ค่าต่ำสุด 1 pixel; ทดสอบบนเครื่องพิมพ์เป้าหมายก่อน |
| บันทึกลงโฟลเดอร์ที่อ่าน‑อย่าง‑ได้อย่างเดียว | `UnauthorizedAccessException` ขณะ `Save` | เลือกไดเรกทอรีที่เขียนได้หรือรันแอปด้วยสิทธิ์ที่เหมาะสม |
| ลืมทำ `Dispose` กับ `BarCodeReader` | การรั่วไหลของหน่วยความจำในบริการที่ทำงานต่อเนื่อง | ห่อ `reader` ด้วยบล็อก `using` หรือเรียก `Dispose()` ด้วยตนเอง |

การจัดการปัญหาเหล่านี้ตั้งแต่เนิ่น ๆ จะช่วยลดเวลา Debug และเพิ่มความเสถียรของระบบในสภาพการผลิต

## สรุปโค้ดทั้งหมด

ด้านล่างเป็นโปรแกรมเต็มรูปแบบที่พร้อมคัดลอก ซึ่งทำงานเป็น **barcode generator example** ตั้งแต่ต้นจนจบ

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

การรันโปรแกรมนี้จะสร้างไฟล์ PNG ที่มีลักษณะดังนี้ (เพื่อเป็นตัวอย่าง)

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*ข้อความแทนภาพ*: **DataBar Omni‑Directional barcode generated in C#** (ตรงกับ `og_image_alt`)

## สรุป

คุณได้มี **ตัวอย่างตัวสร้างบาร์โค้ด** ที่แสดงวิธีเปลี่ยนความสูง, วิธีสร้างสัญลักษณ์ DataBar Omni‑Directional, และวิธี **adjust barcode dimensions** เพื่อให้สแกนได้อย่างเหมาะสม โค้ด C# เต็มรูปแบบบันทึกเป็นไฟล์ PNG, ตรวจสอบความถูกต้อง, และสามารถขยายเพื่อสร้างเป็นชุดจำนวนมากหรือผสานกับเว็บเซอร์วิสได้

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้อง เช่น **การสร้าง QR code ด้วย Aspose.BarCode**, **การประมวลผลหลายค่าบาร์โค้ดเป็นชุด**, หรือ **การฝังบาร์โค้ดลงในเอกสาร PDF** ทุกหัวข้อเหล่านี้ต่อยอดจากพื้นฐานเดียวกันที่อธิบายในคู่มือนี้

ขอให้เขียนโค้ดอย่างสนุกและบาร์โค้ดของคุณสแกนได้เสมอ!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}