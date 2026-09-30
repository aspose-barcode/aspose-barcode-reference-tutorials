---
category: general
date: 2026-08-03
description: บทเรียนการสร้างบาร์โค้ดด้วย C# แสดงวิธีสร้างบาร์โค้ดแบบ Planet ด้วย Aspose.BarCode
  ตั้งค่า X‑dimension และบันทึกเป็นไฟล์ PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: th
lastmod: 2026-08-03
og_description: บทแนะนำการสร้างบาร์โค้ดด้วย C# จะพาคุณผ่านขั้นตอนการสร้างบาร์โค้ดแบบ
  Planet, การปรับค่า X‑dimension, และการบันทึกเป็น PNG ด้วย Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: ตัวสร้างบาร์โค้ด C# – สร้างบาร์โค้ด Planet ทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: ตัวสร้างบาร์โค้ด C# – ตัวอย่างการสร้างบาร์โค้ด Planet และ RM4SCC
url: /th/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวสร้างบาร์โค้ด C# – สร้างตัวอย่าง Planet barcode และ RM4SCC

หากคุณต้องการ **barcode generator C#** ที่สามารถสร้างสัญลักษณ์เฉพาะไปรษณีย์ได้ คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่า **สร้าง Planet barcode** อย่างไรด้วย Aspose.BarCode คุณจะได้เห็นวิธีตั้งค่า X‑dimension, สร้างบาร์โค้ด RM4SCC ที่ตรงกัน, และบันทึกทั้งสองเป็นไฟล์ PNG—ทั้งหมดในไม่กี่ขั้นตอนสั้น ๆ

บทแนะนำนี้ครอบคลุมทุกอย่างที่คุณต้องการเพื่อรันโค้ดบน .NET 6 หรือรุ่นที่ใหม่กว่า อธิบายว่าทำไมแต่ละการตั้งค่าถึงสำคัญ และชี้ให้เห็นข้อผิดพลาดทั่วไป เช่น ความกว้างโมดูลที่ไม่ถูกต้องหรือการขาดสิทธิ์โฟลเดอร์ เมื่อเสร็จสิ้นคุณจะมีภาพบาร์โค้ดสองภาพพร้อมพิมพ์ที่สอดคล้องกับมาตรฐาน Planet และ RM4SCC

## Prerequisites

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6 SDK (หรือเวอร์ชัน .NET ใด ๆ ที่รองรับโดย Aspose.BarCode)
* Visual Studio 2022 หรือ IDE C# ใด ๆ ที่คุณชอบ
* การอ้างอิง NuGet ไปยัง **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* สิทธิ์การเขียนไปยังโฟลเดอร์ที่คุณวางแผนจะเก็บไฟล์ PNG

ไม่จำเป็นต้องใช้บริการภายนอกเพิ่มเติม; ไลบรารีจะจัดการการเข้ารหัสทั้งหมดในเครื่อง

## Step 1: Initialise the barcode generator C# object

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ตัวสร้างรับพารามิเตอร์สัญลักษณ์บาร์โค้ด (`EncodeTypes.Planet`) และข้อมูลที่ต้องเข้ารหัส

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Why this step?*  
*ทำไมต้องทำขั้นตอนนี้?*  
`BarcodeGenerator` เป็นจุดเริ่มต้นสำหรับบาร์โค้ดทุกประเภทที่คุณสร้าง การเลือก `EncodeTypes.Planet` จะบอกไลบรารีให้ปฏิบัติตามข้อกำหนด ISO/IEC 24723 ที่หลายบริการไปรษณีย์ใช้

## Step 2: Set the X‑dimension (module width) for the Planet barcode

ตั้งค่า X‑dimension (ความกว้างโมดูล) สำหรับ Planet barcode

X‑dimension กำหนดความกว้างของโมดูลบาร์โค้ดหนึ่งหน่วย (บาร์หรือช่องว่างที่เล็กที่สุด) ค่า **4 pixels** ทำงานได้ดีสำหรับเครื่องพิมพ์ฉลากส่วนใหญ่

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters*  
*ทำไมเรื่องนี้ถึงสำคัญ*  
หากโมดูลแคบเกินไป บาร์โค้ดอาจอ่านไม่ออก; หากกว้างเกินไป ขนาดฉลากจะเพิ่มโดยไม่จำเป็น การปรับ `Pixels` ช่วยให้คุณปรับจูนบาร์โค้ดให้เหมาะกับความละเอียดของเครื่องพิมพ์ของคุณ

## Step 3: Save the Planet barcode as a PNG image

บันทึก Planet barcode เป็นภาพ PNG

Aspose.BarCode คำนวณความสูงของบาร์โค้ดโดยอัตโนมัติตามสัญลักษณ์ที่เลือก ดังนั้นคุณเพียงแค่ระบุเส้นทางไฟล์และรูปแบบ

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
*เคล็ดลับ*  
แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางแบบ absolute หรือ relative ที่มีอยู่บนเครื่องของคุณ หากโฟลเดอร์ไม่มีอยู่ `Save` จะโยน `DirectoryNotFoundException`

**Expected output** – a PNG file that looks similar to the illustration below (the actual image is not displayed here, but you’ll see a classic Planet barcode with a numeric payload of `123456`).  

**ผลลัพธ์ที่คาดหวัง** – ไฟล์ PNG ที่มีลักษณะคล้ายภาพตัวอย่างด้านล่าง (ภาพจริงไม่ได้แสดงที่นี่ แต่คุณจะเห็น Planet barcode แบบคลาสสิกที่มีข้อมูลตัวเลข `123456`)

## Step 4: Initialise a second generator for the RM4SCC barcode

เริ่มต้นอ็อบเจ็กต์ generator ตัวที่สองสำหรับ RM4SCC barcode

หลายระบบไปรษณีย์ต้องการสัญลักษณ์ Planet และ RM4SCC บนชิ้นส่วนจดหมายเดียวกัน สร้างอินสแตนซ์ `BarcodeGenerator` ใหม่สำหรับสัญลักษณ์ RM4SCC

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Why a separate instance?*  
*ทำไมต้องใช้อินสแตนซ์แยก?*  
แต่ละสัญลักษณ์มีชุดพารามิเตอร์ของตนเอง การใช้ generator เดียวกันอาจทำให้การตั้งค่าที่ไม่เหมาะสม (เช่น X‑dimension) ถูกนำไปใช้กับบาร์โค้ดที่สองโดยไม่ได้ตั้งใจ

## Step 5: Configure the X‑dimension for the RM4SCC barcode

กำหนดค่า X‑dimension สำหรับ RM4SCC barcode

RM4SCC ยังคงเคารพการตั้งค่า X‑dimension ดังนั้นเราจึงใช้ความกว้างพิกเซลเดียวกันเพื่อความสอดคล้องด้านภาพ

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
*เคล็ดลับระดับมืออาชีพ*  
หากต้องการบาร์โค้ดที่สูงขึ้น (เช่น สำหรับฉลากขนาดใหญ่) คุณสามารถตั้งค่า `Height.Pixels` ได้เช่นกัน การไม่ตั้งค่าให้ไลบรารีคำนวณความสูงที่เหมาะสมโดยอัตโนมัติ

## Step 6: Save the RM4SCC barcode as a PNG image

บันทึก RM4SCC barcode เป็นภาพ PNG

สุดท้ายให้บันทึกบาร์โค้ด RM4SCC ลงดิสก์

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์—`PostalPlanetBarHeightNone.png` และ `PostalRM4SCCBarHeightNone.png`—ที่คุณสามารถฝังในฉลากไปรษณีย์, พิมพ์บนซองจดหมาย, หรือส่งให้บริการพิมพ์ของบุคคลที่สามได้

## Optional: Adjusting height or using other image formats

ปรับความสูงหรือใช้รูปแบบภาพอื่น ๆ (Optional)

หากกระบวนการทำงานของคุณต้องการความสูงของบาร์โค้ดที่กำหนดหรือรูปแบบภาพอื่น (เช่น JPEG หรือ BMP) คุณสามารถแก้ไขพารามิเตอร์ก่อนเรียก `Save` ได้

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – When you set a custom height, make sure the value respects the minimum height required by the ISO standard; otherwise the barcode may fail validation.  

**กรณีขอบ** – เมื่อคุณตั้งค่าความสูงแบบกำหนดเอง ต้องตรวจสอบว่าค่าดังกล่าวสอดคล้องกับความสูงขั้นต่ำตามมาตรฐาน ISO มิฉะนั้นบาร์โค้ดอาจไม่ผ่านการตรวจสอบความถูกต้อง

## Common pitfalls and how to avoid them

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| `DirectoryNotFoundException` | The target folder does not exist or is misspelled. | Create the folder first or use `Path.Combine` with `Environment.CurrentDirectory`. |
| Barcode unreadable on low‑resolution printers | X‑dimension too small for the printer’s DPI. | Increase `XDimension.Pixels` to 5 – 6 for 203 dpi printers, or test with a sample label. |
| Wrong symbology used | Passing `EncodeTypes.Code128` instead of `EncodeTypes.Planet`. | Double‑check the `EncodeTypes` enum value matches the required postal standard. |
| Null reference on `Parameters` | Using an older version of Aspose.BarCode where the API differs. | Upgrade to the latest NuGet package (v23.12 or later). |

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| `DirectoryNotFoundException` | โฟลเดอร์เป้าหมายไม่มีอยู่หรือสะกดผิด | สร้างโฟลเดอร์ก่อนหรือใช้ `Path.Combine` ร่วมกับ `Environment.CurrentDirectory` |
| Barcode unreadable on low‑resolution printers | X‑dimension เล็กเกินไปสำหรับ DPI ของเครื่องพิมพ์ | เพิ่มค่า `XDimension.Pixels` เป็น 5 – 6 สำหรับเครื่องพิมพ์ 203 dpi หรือทดสอบด้วยฉลากตัวอย่าง |
| Wrong symbology used | ส่งค่า `EncodeTypes.Code128` แทน `EncodeTypes.Planet` | ตรวจสอบค่าใน enum `EncodeTypes` ให้ตรงกับมาตรฐานไปรษณีย์ที่ต้องการ |
| Null reference on `Parameters` | ใช้ Aspose.BarCode เวอร์ชันเก่าที่ API แตกต่าง | อัปเกรดเป็นแพคเกจ NuGet ล่าสุด (v23.12 หรือใหม่กว่า) |

## Full runnable example

ตัวอย่างโปรแกรมเต็มที่คุณสามารถคัดลอก, วาง, และรันได้ รวมถึง `using` statements, การจัดการข้อผิดพลาด, และคอมเมนต์อธิบายแต่ละบรรทัด

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

เมื่อรันโปรแกรมจะสร้างโฟลเดอร์ `Barcodes` ข้างไฟล์ executable และวางไฟล์ PNG สองไฟล์ไว้ภายใน เปิดด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันผลลัพธ์

## Conclusion

คุณตอนนี้มีโซลูชัน **barcode generator C#** ที่สามารถ **สร้าง Planet barcode** ปรับ X‑dimension เพื่อการพิมพ์ที่เหมาะสม และสร้าง RM4SCC barcode ที่ตรงกัน—ทั้งหมดด้วยไม่กี่บรรทัดของโค้ด วิธีนี้ทำงานกับ .NET 6+ เพียงแค่ใช้แพคเกจ NuGet Aspose.BarCode และสามารถขยายไปยังสัญลักษณ์อื่น ๆ เช่น Code128, QR, หรือ DataMatrix โดยเปลี่ยนค่า `EncodeTypes`

### What’s next?

* ทดลองเปลี่ยนค่า `XDimension.Pixels` เพื่อให้ตรงกับ DPI ของเครื่องพิมพ์ของคุณ
* สร้างบาร์โค้ดในรูปแบบอื่น (PDF, SVG) โดยเปลี่ยนค่า enum `BarCodeImageFormat`
* รวมไฟล์ PNG สองไฟล์เป็นฉลากเดียวโดยใช้ไลบรารีกราฟิกอย่าง **SkiaSharp**
* สำรวจ API ของ Aspose.BarCode อย่างเต็มที่เพื่อใช้ฟีเจอร์ขั้นสูง เช่น การตรวจสอบ checksum หรือการใช้ฟอนต์แบบกำหนดเอง

คุณสามารถปรับโค้ดสำหรับการประมวลผลแบบแบตช์หรือรวมเข้ากับบริการเว็บ ASP.NET Core ที่ส่งคืนภาพบาร์โค้ดตามคำขอได้เลย ขอให้สนุกกับการเขียนโค้ด!

## What Should You Learn Next?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานอื่น ๆ ในโครงการของคุณ

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}