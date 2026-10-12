---
category: general
date: 2026-09-29
description: สร้างบาร์โค้ด Planet ใน C# พร้อมบาร์ที่เต็มและว่าง – คู่มือขั้นตอนโดยใช้
  Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: th
lastmod: 2026-09-29
og_description: สร้างบาร์โค้ด Planet ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีการเรนเดอร์บาร์ที่เติมเต็ม
  สลับเป็นบาร์ว่าง และปรับมิติ X ด้วย Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: สร้างบาร์โค้ดดาวเคราะห์ด้วยบาร์ที่เต็มและว่าง – บทเรียน C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: วิธีสร้างบาร์โค้ดดาวเคราะห์ด้วยแถบเต็มและแถบว่าง
url: /th/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง Planet barcode ด้วยแถบเต็มและแถบว่าง

หากคุณต้องการ **สร้าง planet barcode** ใน C# คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่า如何สร้างทั้งเวอร์ชันแถบเต็มและแถบว่าง คุณจะได้เรียนรู้วิธีตั้งความกว้างของแถบ (X‑dimension) การสลับคุณสมบัติ `FilledBars` และการบันทึกผลลัพธ์เป็นไฟล์ PNG—ทั้งหมดด้วยไลบรารี Aspose.Barcode  

การสร้าง postal barcode เป็นความต้องการทั่วไปสำหรับระบบจัดส่ง แอปพลิเคชันรายการจดหมาย และแดชบอร์ดโลจิสติกส์ เมื่อจบบทเรียนนี้คุณจะมีไฟล์ PNG สองไฟล์พร้อมใช้งานที่สามารถฝังลงในรายงาน อีเมล หรือพิมพ์ออกได้

## ข้อกำหนดเบื้องต้น

| ความต้องการ | ทำไมจึงสำคัญ |
|-------------|----------------|
| .NET 6.0 หรือใหม่กว่า | ให้ runtime สำหรับตัวอย่าง C# |
| Visual Studio 2022 (หรือ IDE C# ใดก็ได้) | ช่วยให้คุณคอมไพล์และรันโค้ด |
| **Aspose.Barcode for .NET** NuGet package | จัดเตรียมคลาส `BarcodeGenerator` และ `EncodeTypes.Planet` ติดตั้งด้วยคำสั่ง `dotnet add package Aspose.Barcode` |
| สิทธิ์การเขียนในโฟลเดอร์บนดิสก์ | เมธอด `Save` จะเขียนไฟล์ PNG ไปยังพาธที่คุณระบุ |

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespace

สร้างโปรเจกต์คอนโซลใหม่ (หรือเพิ่มโค้ดนี้ลงในโปรเจกต์ที่มีอยู่) แล้วอ้างอิง namespace ของ Aspose.Barcode  

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

`using` directives เหล่านี้ทำให้คุณเข้าถึงคลาส `BarcodeGenerator` , `EncodeTypes` และ enum รูปแบบภาพที่จำเป็นสำหรับบทเรียนนี้

## ขั้นตอนที่ 2: สร้าง Planet barcode ด้วยแถบเต็ม (default)

Barcode ตัวแรกใช้การเรนเดอร์ค่าเริ่มต้นของไลบรารี ซึ่งจะเติมสีให้แถบทั้งหมด  

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**ทำไมวิธีนี้ถึงได้ผล:**  
`EncodeTypes.Planet` บอก Aspose.Barcode ให้ใช้สัญลักษณ์ **Planet** ซึ่งเป็น postal barcode ที่ใช้โดย United States Postal Service คุณสมบัติ `XDimension` ควบคุมความกว้างของแต่ละแถบ; การตั้งค่าเป็น 4 พิกเซลจะทำให้ barcode พิมพ์ได้ดีบนเครื่องพิมพ์ฉลากมาตรฐาน โดยค่าเริ่มต้น `FilledBars` เป็น `true` ทำให้แถบเป็นสีทึบ

## ขั้นตอนที่ 3: สร้าง Planet barcode ด้วยแถบว่าง

เพื่อสร้างข้อมูลเดียวกันโดยใช้แถบ *ว่าง* เพียงสลับค่า `FilledBars` ส่วนการตั้งค่าอื่น ๆ คงเดิม  

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**ทำไมเรื่องนี้ถึงสำคัญ:**  
บางระบบการส่งจดหมายต้องการสไตล์ **empty‑bars** เพื่อเพิ่มความอ่านง่ายเมื่อ barcode พิมพ์บนพื้นหลังสีเข้มหรือใช้โทนสีตัดกัน การตั้งค่า `FilledBars = false` จะทำให้ตัวสร้างวาดเฉพาะเส้นขอบของแถบ ส่วนภายในจะโปร่งใส

## ผลลัพธ์ที่คาดหวัง

หลังจากรันโปรแกรม โฟลเดอร์ `C:\Barcodes` (หรือพาธที่คุณเลือก) จะมีไฟล์ PNG สองไฟล์:

| ไฟล์ | คำอธิบายภาพ |
|------|---------------------|
| `PlanetFilledBars.png` | แถบเป็นสี่เหลี่ยมสีดำทึบบนพื้นหลังสีขาว |
| `PlanetEmptyBars.png`  | แถบเป็นเส้นขอบสีดำ; ภายในของแต่ละแถบโปร่งใส (แสดงพื้นหลัง) |

ทั้งสองภาพเข้ารหัสสตริงตัวเลขเดียวกัน `"123456"` และใช้ความกว้างแถบ 4 พิกเซล ทำให้ลักษณะโดยรวมเหมือนกัน ยกเว้นสไตล์การเติมสี

## การเปลี่ยนแปลงทั่วไปและกรณีขอบ

### การเปลี่ยนความกว้างของแถบ

หากเครื่องพิมพ์ฉลากของคุณต้องการความกว้างแถบที่ต่างออกไป ให้แก้ค่า `XDimension.Pixels` สำหรับเครื่องพิมพ์ความละเอียดสูงอาจใช้ค่า **2** หรือ **3** พิกเซล; สำหรับเครื่องพิมพ์ความละเอียดต่ำอาจใช้ **5** หรือ **6** พิกเซลเพื่อเพิ่มความน่าเชื่อถือในการสแกน  

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### การใช้รูปแบบภาพอื่น

Aspose.Barcode รองรับ PNG, JPEG, BMP, GIF และ TIFF เปลี่ยน `BarCodeImageFormat.Png` เป็นค่า enum อื่นตามกระบวนการทำงานของคุณ  

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### การสร้างหลาย barcode ในลูป

เมื่อคุณต้องการชุดของ Planet barcode (เช่นสำหรับรายการจดหมาย) ให้ใส่ตรรกะการสร้างไว้ในลูป `foreach` และเปลี่ยนสตริงข้อมูลในแต่ละรอบ  

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### การจัดการอินพุตที่ไม่ถูกต้อง

สัญลักษณ์ Planet ยอมรับเฉพาะสตริงตัวเลขที่มี **5‑8** หลักเท่านั้น การใส่ค่าที่ไม่ถูกต้องจะทำให้เกิด `ArgumentException` ป้องกันด้วยเมธอดตรวจสอบง่าย ๆ  

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## เคล็ดลับพิเศษ: ตรวจสอบ barcode ด้วยเครื่องจำลองสแกนเนอร์

Aspose.Barcode มีคลาส `BarcodeReader` ที่คุณสามารถใช้เพื่อยืนยันว่าภาพที่สร้างขึ้นถอดรหัสกลับเป็นข้อมูลเดิมได้  

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

หากผลลัพธ์แสดง `"123456"` สำหรับทั้งสองไฟล์ หมายความว่า barcode ถูกสร้างอย่างถูกต้อง

## สรุป

ตอนนี้คุณรู้วิธี **สร้าง planet barcode** ใน C# ด้วยสไตล์แถบเต็มและแถบว่าง ควบคุม **Planet barcode XDimension** และบันทึกผลลัพธ์เป็น PNG ด้วยไลบรารี **Aspose.Barcode** ปรับความกว้างของแถบ เปลี่ยนรูปแบบภาพ หรือวนลูปค่าต่าง ๆ เพื่อให้เข้ากับกระบวนการทำงานของรหัสไปรษณีย์ใด ๆ  

ต่อไปคุณอาจสนใจ:

* **เพิ่มข้อความที่อ่านได้โดยมนุษย์** ใต้ barcode (`barcodeGenerator.Parameters.Caption.Show = true`)  
* **ฝัง barcode ลงในเอกสาร PDF** ด้วย Aspose.PDF  
* **สร้างสัญลักษณ์ไปรษณีย์อื่น** เช่น **USPS POSTNET** หรือ **Intelligent Mail**

ลองปรับพารามิเตอร์ต่าง ๆ และผสานโค้ดนี้เข้ากับระบบจัดส่งหรือระบบจดหมายของคุณได้เลย ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [สร้าง Planet Barcode ใน C# – คู่มือเต็มขั้นตอน](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [สร้าง planet barcode ใน C# – คู่มือการเขียนโปรแกรมเต็มรูปแบบ](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – ตัวอย่างการสร้าง Planet barcode และ RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}