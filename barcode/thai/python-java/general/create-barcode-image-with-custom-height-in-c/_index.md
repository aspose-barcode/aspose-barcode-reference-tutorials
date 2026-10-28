---
category: general
date: 2026-10-28
description: สร้างภาพบาร์โค้ดใน C# และเรียนรู้วิธีปรับความสูงโดยใช้ BarcodeGenerator
  API คู่มือแบบขั้นตอนต่อขั้นตอนสำหรับการกำหนดความสูงบาร์โค้ดแบบกำหนดเองและการเปลี่ยนความสูงของบาร์.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: th
lastmod: 2026-10-28
og_description: สร้างภาพบาร์โค้ดใน C# และดูวิธีปรับความสูงได้ทันที ตามตัวอย่างเต็มนี้เพื่อกำหนดความสูงบาร์โค้ดแบบกำหนดเองด้วย
  BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: สร้างภาพบาร์โค้ดด้วยความสูงที่กำหนดเองใน C# – คู่มือเต็ม
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: สร้างภาพบาร์โค้ดด้วยความสูงที่กำหนดเองใน C#
url: /th/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดด้วยความสูงที่กำหนดเองใน C#

หากคุณต้องการ **สร้างภาพบาร์โค้ด** และควบคุมขนาดของมัน คู่มือนี้จะแสดงวิธีทำอย่างละเอียด ด้วยไลบรารี Aspose.BarCode .NET คุณสามารถสร้างบาร์โค้ด GS1‑Databar Omni‑Directional แล้ว **ปรับความสูง** ให้ตรงกับความต้องการของการจัดวางใด ๆ

คุณจะได้ทำตามโปรแกรมที่ทำงานได้เต็มรูปแบบ ซึ่งแสดง **c# barcode generator** อธิบายแต่ละคุณสมบัติที่ตั้งค่าไว้ และแสดงผลลัพธ์สองแบบ — หนึ่งที่มีความสูงของบาร์ 30 พิกเซล และอีกหนึ่งที่มีความสูงของบาร์ 60 พิกเซล สุดท้ายคุณจะสามารถ **เปลี่ยนความสูงของบาร์โค้ด** ผ่านโปรแกรมได้สำหรับบาร์โค้ดประเภทใดก็ได้ที่ไลบรารีรองรับ

## ข้อกำหนดเบื้องต้น

- .NET 6.0 SDK หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.6+)
- Visual Studio 2022 หรือเครื่องมือแก้ไขใด ๆ ที่สามารถสร้างโปรเจกต์ C# ได้
- Aspose.BarCode for .NET NuGet package (`Install-Package Aspose.BarCode`)
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **เคล็ดลับ:** หากคุณใช้ CI pipeline ให้เพิ่มแพ็กเกจ NuGet ลงในไฟล์ `csproj` ของคุณเพื่อให้การสร้างโครงการเรียกคืนแพ็กเกจโดยอัตโนมัติ

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespace

สร้างโปรเจกต์คอนโซลใหม่และเพิ่มคำสั่ง `using` ที่จำเป็น namespace จะให้คุณเข้าถึง `BarcodeGenerator`, `EncodeTypes` และตัวช่วยจัดการรูปภาพ

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **ทำไมจึงสำคัญ:** การนำเข้า namespace ที่ถูกต้องช่วยป้องกันข้อผิดพลาดระหว่างการคอมไพล์และทำให้ API ปรากฏใน IntelliSense

## ขั้นตอนที่ 2: เริ่มต้น **c# barcode generator** สำหรับโค้ด GS1‑Databar Omni‑Directional

คอนสตรัคเตอร์รับอาร์กิวเมนต์สองค่า: ประเภทบาร์โค้ด (`EncodeTypes.DatabarOmniDirectional`) และสตริงข้อมูล สตริงข้อมูลต้องเป็นไปตามรูปแบบ GS1 Application Identifier เช่น `(01)12345678901231`

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **คำอธิบาย:** อ็อบเจกต์ `BarcodeGenerator` คือจุดเริ่มต้นสำหรับการตั้งค่าที่เกี่ยวกับบาร์โค้ดทั้งหมด เมื่อคุณมีอินสแตนซ์นี้แล้ว คุณสามารถปรับมิติ สี และรูปแบบการส่งออกได้ตามต้องการ

## ขั้นตอนที่ 3: กำหนด X‑dimension (ความกว้างพิกเซลของบาร์ที่แคบที่สุด) ร่วมกัน

X‑dimension ขนาด 2 พิกเซลเป็นจุดเริ่มต้นที่ดีสำหรับสถานการณ์การแสดงผลบนหน้าจอส่วนใหญ่

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **ทำไมต้องตั้งค่า X‑dimension?** มันควบคุมความกว้างโดยรวมของบาร์โค้ด การคงค่าให้สม่ำเสมอทำให้การเปลี่ยนความสูงของบาร์ไม่ทำให้ภาพเสียสมดุล

## ขั้นตอนที่ 4: **สร้างภาพบาร์โค้ด** ด้วยความสูงบาร์ 30 พิกเซล

ตอนนี้เราจะกำหนดความสูงของบาร์ บันทึกภาพแรก แล้วเปลี่ยนความสูงสำหรับภาพที่สอง

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **ผลลัพธ์:** คุณจะได้ไฟล์ PNG ที่บาร์แนวตั้งแต่ละบาร์มีความสูง 30 พิกเซล X‑dimension ยังคงเป็น 2 พิกเซล ดังนั้นความกว้างโดยรวมไม่เปลี่ยนแปลง

## ขั้นตอนที่ 5: **วิธีปรับความสูง** – เปลี่ยนความสูงบาร์เป็น 60 พิกเซล

เพื่อสาธิต **custom barcode height** เพียงกำหนดค่าตัวแปรเดียวกันใหม่แล้วบันทึกอีกครั้ง

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **ข้อสังเกตสำคัญ:** คุณสมบัติ `BarHeight` สามารถเปลี่ยนค่าได้; คุณไม่จำเป็นต้องสร้างอินสแตนซ์ `BarcodeGenerator` ใหม่ ซึ่งทำให้การสร้างหลายขนาดในลูปหรือกระบวนการแบตช์เป็นเรื่องง่ายและประหยัดทรัพยากร

## ขั้นตอนที่ 6: ตรวจสอบผลลัพธ์

รันโปรแกรมคอนโซล (`dotnet run`) หลังจากทำงานเสร็จคุณควรเห็นไฟล์ PNG สองไฟล์ในโฟลเดอร์เอาต์พุตของโปรเจกต์:

- `DatabarBarHeight30Pixels.png` – บาร์สั้น (30 px)
- `DatabarBarHeight60Pixels.png` – บาร์สูง (60 px)

ทั้งสองภาพมีข้อมูลที่เข้ารหัสเดียวกัน แต่ความสูงของภาพแตกต่างกัน ซึ่งมีประโยชน์เมื่อนำบาร์โค้ดไปใส่ในแบบฟอร์ม ป้ายสินค้า หรือคอมโพเนนต์ UI ที่มีข้อจำกัดพื้นที่ต่างกัน

![สร้างภาพบาร์โค้ดด้วยความสูงที่กำหนดเอง](barcode-example.png){.align-center width="600" alt="สร้างภาพบาร์โค้ดด้วยความสูงที่กำหนดเอง"}

> **เคล็ดลับ:** เปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใด ๆ บาร์โค้ดที่สูงกว่าจะเป็นสองเท่าของบาร์ที่สั้นในแนวตั้ง ในขณะที่ช่องว่างแนวนอนยังคงเท่าเดิม

## ขั้นตอนที่ 7: ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การตั้งค่าที่แนะนำ |
|-----------|---------------------|
| **พิมพ์บนเครื่องพิมพ์ฉลากความละเอียดสูง** | ใช้ X‑dimension ที่ใหญ่ขึ้น (เช่น 4 px) และเพิ่ม `BarHeight` อย่างสัดส่วน |
| **แสดงบนหน้าจอ DPI ต่ำ** | คง `XDimension` ที่ 1 px และตั้ง `BarHeight` ระหว่าง 20‑40 px เพื่อความอ่านง่าย |
| **สร้าง QR code หรือบาร์โค้ด 2‑D** | คุณสมบัติ `BarHeight` จะถูกละเว้น; ใช้ `EncodeTypes.QR` และปรับ `ImageHeight` แทน |
| **สร้างหลายความสูงเป็นชุด** | วนลูปผ่านอาเรย์ของความสูงและเรียก `Save` ภายในลูป; ไม่ต้องสร้าง generator ใหม่ในแต่ละรอบ |

### การจัดการความสูงที่ไม่ถูกต้อง

ไลบรารีจะโยน `ArgumentOutOfRangeException` หากคุณตั้งค่า `BarHeight` เป็นค่าที่ไม่เป็นบวก ตรวจสอบด้วยเงื่อนไขง่าย ๆ:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## โค้ดเต็ม (พร้อมคัดลอก)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **ทำไมวิธีนี้ถึงได้ผล:** การตั้งค่าที่จำเป็นทั้งหมด (`EncodeTypes`, `XDimension`, `BarHeight`) ถูกกำหนดก่อนแต่ละคำสั่ง `Save` อินสแตนซ์ `BarcodeGenerator` เดียวกันถูกใช้ซ้ำ ทำให้ประหยัดหน่วยความจำและอ่านง่าย

## สรุป

ตอนนี้คุณรู้วิธี **สร้างภาพบาร์โค้ด** ใน C# และปรับ **ความสูงของบาร์โค้ด** อย่างแม่นยำด้วย API `BarcodeGenerator` โดยการปรับ `BarHeight.Pixels` คุณจะได้ **custom barcode height** โดยไม่ต้องสร้าง generator ใหม่ ซึ่งเหมาะสำหรับการสร้างป้ายแบบไดนามิก การเรนเดอร์ UI หรือกระบวนการแบตช์

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้อง เช่น **วิธีปรับความกว้าง**, **การเพิ่มข้อความที่อ่านได้โดยมนุษย์**, หรือ **การส่งออกเป็น SVG สำหรับเว็บที่ขยายได้** แนวคิดเดียวกัน — ตั้งค่าคุณสมบัติ, เรียก `Save` — ใช้ได้กับทุกกรณี ทำให้คุณขยายตัวอย่างนี้ได้อย่างมั่นใจ

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example – create Planet and RM4SCC barcodes with custom height](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [How to create rm4scc barcode and control its height in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}