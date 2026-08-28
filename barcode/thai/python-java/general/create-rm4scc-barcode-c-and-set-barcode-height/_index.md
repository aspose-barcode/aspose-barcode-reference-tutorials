---
category: general
date: 2026-08-25
description: สร้างบาร์โค้ด RM4SCC ด้วย C# พร้อมโค้ดขั้นตอนต่อขั้นตอนและเรียนรู้วิธีตั้งความสูงของบาร์โค้ดเพื่อให้ได้ขนาดที่แม่นยำ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: th
lastmod: 2026-08-25
og_description: สร้างบาร์โค้ด RM4SCC ด้วย C# และ Aspose.BarCode และเรียนรู้วิธีตั้งความสูงของบาร์โค้ดเพื่อการควบคุมที่แม่นยำในแอปพลิเคชัน
  .NET ของคุณ
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: สร้างบาร์โค้ด RM4SCC ด้วย C# – คู่มือการตั้งค่าความสูงของบาร์โค้ด
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: สร้างบาร์โค้ด RM4SCC ด้วย C# และตั้งค่าความสูงของบาร์โค้ด
url: /th/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด RM4SCC ด้วย C# และตั้งค่าความสูงของบาร์โค้ด

สร้างบาร์โค้ด RM4SCC ด้วย C# อย่างรวดเร็วโดยใช้ไลบรารี Aspose.BarCode บทเรียนนี้แสดง **วิธีตั้งค่าความสูงของบาร์โค้ด** และปรับแต่งคุณสมบัติภาพอื่น ๆ เพื่อให้บาร์โค้ดพอดีกับเลย์เอาต์ของคุณอย่างแม่นยำ.

คุณจะได้เห็นโปรแกรมคอนโซลที่พร้อมทำงานเต็มรูปแบบซึ่งสร้างไฟล์ PNG สามไฟล์:

* บาร์โค้ด Planet ความสูงค่าเริ่มต้น (เพื่อเปรียบเทียบ)  
* บาร์โค้ด RM4SCC ที่มีความสูงกำหนดเองที่ 100 px  
* บาร์โค้ด Planet ที่มีบาร์ว่าง (ไม่มีการเติม)  

ตัวอย่างนี้สมมติว่าคุณมี Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET 6+) และใบอนุญาต Aspose.BarCode for .NET ที่ถูกต้องหรือสำเนาแบบประเมินผล.

## ข้อกำหนดเบื้องต้น

| ความต้องการ | เหตุผล |
|-------------|--------|
| .NET 6 SDK (หรือรุ่นต่อไป) | ให้ runtime สำหรับแอปคอนโซล |
| แพ็กเกจ NuGet Aspose.BarCode for .NET | จัดหา `BarcodeGenerator`, `EncodeTypes` และ API การส่งออกภาพ |
| ความรู้พื้นฐาน C# | จำเป็นสำหรับการเข้าใจการทำงานของโค้ด |

ติดตั้งแพ็กเกจ NuGet ด้วย:

```bash
dotnet add package Aspose.BarCode
```

> **เคล็ดลับ:** หากคุณรันโค้ดโดยไม่มีใบอนุญาต ภาพที่สร้างขึ้นจะมีลายน้ำ Aspose เล็ก ๆ.

## ขั้นตอนที่ 1: ตั้งค่าโครงสร้างโปรเจกต์

สร้างโปรเจกต์คอนโซลใหม่และเพิ่ม `using` directives ที่จำเป็น:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

`using` statements จะทำให้คุณเข้าถึงคลาสตัวสร้างบาร์โค้ดและ enum ของรูปแบบ PNG.

## ขั้นตอนที่ 2: กำหนดโฟลเดอร์เอาต์พุต

เลือกโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก โฟลเดอร์ต้องมีอยู่ก่อนที่คุณจะเรียก `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

การสร้างไดเรกทอรีโดยโปรแกรมช่วยหลีกเลี่ยง *FileNotFoundException* เมื่อโค้ดทำงานบนเครื่องใหม่.

## ขั้นตอนที่ 3: สร้างบาร์โค้ด Planet ด้วยความสูงค่าเริ่มต้น (baseline)

บาร์โค้ด Planet ไม่ใช่จุดสนใจของคู่มือนี้ แต่เป็นฐานภาพเพื่อเปรียบเทียบกับบาร์โค้ด RM4SCC ที่กำหนดขนาดด้วยตนเอง.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*ทำไมเรื่องนี้สำคัญ:*  
`XDimension` กำหนดความกว้างของบาร์หนึ่งบาร์ การคงค่าคงที่ขณะเปลี่ยน `BarHeight` จะทำให้เห็นผลของความสูงอย่างชัดเจน.

## ขั้นตอนที่ 4: **สร้างบาร์โค้ด RM4SCC ด้วย C#** – ตั้งค่าความสูงด้วยตนเอง

ตอนนี้เราจะทำภารกิจหลัก: **สร้างบาร์โค้ด RM4SCC ด้วย C#** และควบคุมความสูงของมันอย่างชัดเจน.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### วิธีตั้งค่าความสูงของบาร์โค้ด

คุณสมบัติ `BarHeight` อยู่ภายใต้ `Parameters.Barcode` มันรับค่า `float` ที่ระบุเป็น **พิกเซล**, **จุด**, หรือ **มิลลิเมตร** ขึ้นอยู่กับ `Unit` ที่คุณเลือก (`Pixels`, `Points`, `Millimeters`). ในตัวอย่างเราใช้ `Pixels` เนื่องจากรูปแบบเอาต์พุตเป็น PNG.

หากคุณต้องการความสูงเป็นมิลลิเมตร ให้เปลี่ยนหน่วยก่อน:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## ขั้นตอนที่ 5: สร้างบาร์โค้ด Planet ที่มีบาร์ว่าง (ไม่มีการเติม)

ขั้นตอนนี้แสดงคุณสมบัติที่เป็นประโยชน์อีกอย่างหนึ่ง—`FilledBars` การตั้งค่าเป็น `false` จะสร้างบาร์โค้ดแบบ “เปลือย” ซึ่งอาจเป็นประโยชน์สำหรับการออกแบบ.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## โปรแกรมเต็มที่สามารถรันได้

คัดลอกโค้ดต่อไปนี้ไปยัง `Program.cs` สร้างและรันโปรเจกต์; ไฟล์ PNG สามไฟล์จะปรากฏในโฟลเดอร์ `GeneratedBarcodes`.



## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญคุณลักษณะ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ.

- [วิธีสร้างบาร์โค้ด code128 ด้วย Java และตั้งค่าความสูงของบาร์](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [วิธีสร้าง quiet zone ของบาร์โค้ด .NET สำหรับ Code 16K ด้วย Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วย Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}