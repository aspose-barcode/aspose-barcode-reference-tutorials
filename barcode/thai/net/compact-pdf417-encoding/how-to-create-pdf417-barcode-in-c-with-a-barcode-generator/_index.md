---
category: general
date: 2026-11-17
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือครบถ้วนเกี่ยวกับวิธีสร้างบาร์โค้ดจากสตริงโดยใช้ตัวสร้างบาร์โค้ด
  C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: th
lastmod: 2026-11-17
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว บทเรียนนี้แสดงวิธีสร้างบาร์โค้ดจากสตริงด้วยตัวสร้างบาร์โค้ด
  C# และรวมซอร์สโค้ดเต็ม.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: วิธีสร้างบาร์โค้ด PDF417 ด้วย C# และเครื่องสร้างบาร์โค้ด
url: /th/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ด้วย C# และตัวสร้างบาร์โค้ด

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงวิธีทำอย่างละเอียด คุณจะได้เรียนรู้ **วิธีสร้างบาร์โค้ด** จากสตริงธรรมดา การกำหนดขนาดสัญลักษณ์ และการบันทึกผลลัพธ์เป็นไฟล์ PNG — ทั้งหมดโดยใช้ตัวสร้างบาร์โค้ด C# ที่เชื่อถือได้

การสร้างบาร์โค้ดโดยโปรแกรมช่วยลดขั้นตอนการทำงานด้วยมือและรับประกันคุณภาพที่สม่ำเสมอ ในบทแนะนำนี้เราจะครอบคลุมทุกอย่างตั้งแต่การตั้งค่าโปรเจกต์จนถึงภาพสุดท้าย เพื่อให้คุณสามารถบูรณาการการสร้างบาร์โค้ดเข้าสู่โซลูชัน C# ใดก็ได้ทันที

## ความต้องการเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า (โค้ดทำงานกับ .NET Core และ .NET Framework)
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ C#)
* ใบอนุญาตหรือการทดลองใช้ฟรีของ **Aspose.BarCode for .NET** – ไลบรารีที่ใช้ในตัวอย่าง
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

ไม่จำเป็นต้องติดตั้งแพ็กเกจเพิ่มเติม; แพ็กเกจ NuGet `Aspose.BarCode` มีคลาสทั้งหมดที่คุณต้องใช้แล้ว

## ขั้นตอนที่ 1 – ตั้งค่าตัวสร้างบาร์โค้ด C#

สิ่งแรกที่คุณทำเมื่อ **สร้างบาร์โค้ด PDF417** คือการสร้างอ็อบเจกต์ `BarcodeGenerator` อ็อบเจกต์นี้เป็นตัวแทนของ **c# barcode generator** ที่จะรับผิดชอบการเข้ารหัส การแสดงผล และการบันทึก

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*ทำไมจึงสำคัญ*: enum `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้สัญลักษณ์ PDF417 ซึ่งเป็นมาตรฐานเดียวกับที่ใช้ในบัตรประจำตัวและป้ายบรรจุสินค้า สตริง `"(01)12345678901234"` เป็นตัวอย่าง **generate barcode from string** ที่แสดงวิธี **create GS1 barcode** ด้วยข้อมูล

## ขั้นตอนที่ 2 – กำหนดค่า X‑dimension (ความกว้างโมดูล)

X‑dimension ควบคุมความกว้างของบาร์ที่เล็กที่สุด (โมดูล) ค่าที่นิยมสำหรับการแสดงผลบนหน้าจอคือ 2 พิกเซล

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

การกำหนด X‑dimension อย่างชัดเจนช่วยป้องกันไม่ให้ตัวสร้างใช้ค่าเริ่มต้นซึ่งอาจทำให้บาร์โค้ดเล็กเกินกว่าที่สแกนเนอร์บางรุ่นรับได้

## ขั้นตอนที่ 3 – กำหนดจำนวนคอลัมน์

PDF417 อนุญาตให้คุณปรับจำนวนคอลัมน์ ซึ่งส่งผลต่อรูปทรงและความจุของข้อมูล สำหรับป้ายที่ต้องการความกระชับ คอลัมน์สี่คอลัมน์ทำงานได้ดี

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

หากต้องการบาร์โค้ดที่สูงขึ้น ให้เพิ่มจำนวนคอลัมน์; ไลบรารีจะคำนวณจำนวนแถวที่จำเป็นโดยอัตโนมัติ

## ขั้นตอนที่ 4 – บันทึกบาร์โค้ดเป็นภาพ

สุดท้าย ส่งออกบาร์โค้ดเป็นไฟล์ PNG PNG ให้ความคมชัดของขอบและรองรับความโปร่งใส

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

เมื่อรันโปรแกรมจะสร้างไฟล์ `output/Gs1Pdf417.png` เปิดไฟล์ด้วยโปรแกรมดูภาพใดก็ได้ — คุณจะเห็น **บาร์โค้ด PDF417** ที่เข้ารหัสข้อมูล GS1 ที่คุณระบุไว้

### ผลลัพธ์ที่คาดหวัง

![บาร์โค้ด PDF417 ที่สร้างแสดง GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="บาร์โค้ด PDF417 ที่สร้างด้วยตัวสร้างบาร์โค้ด C#"}

*ภาพด้านบนแสดงผลลัพธ์ของตัวอย่างโค้ดเต็ม บาร์โค้ดสามารถสแกนได้ด้วยเครื่องอ่านที่รองรับ PDF417*

## ตัวเลือกเพิ่มเติมและรูปแบบที่พบบ่อย

### การเปลี่ยนรูปแบบภาพ

หากต้องการ JPEG หรือ BMP เพียงเปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Bmp` ส่วนของโค้ดยังคงเหมือนเดิม

### การปรับระดับการแก้ไขข้อผิดพลาด

PDF417 รองรับระดับการแก้ไขข้อผิดพลาดตั้งแต่ 0‑8 ระดับที่สูงขึ้นจะเพิ่มความซ้ำซ้อนแต่ก็ทำให้บาร์โค้ดใหญ่ขึ้น

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### การสร้างบาร์โค้ด GS1 ประเภทอื่น

`BarcodeGenerator` เดียวกันสามารถ **create GS1 barcode** สำหรับสัญลักษณ์อื่น ๆ เช่น `EncodeTypes.Gs1DataMatrix` หรือ `EncodeTypes.Gs1Qr` เพียงสลับค่า enum:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### การจัดการข้อมูลที่ว่างหรือเป็น null

เมื่อคุณ **generate barcode from string** ควรตรวจสอบค่าที่รับเข้าก่อนเสมอ:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

ช่วยป้องกันข้อยกเว้นในระหว่างรันและทำให้บาร์โค้ดสอดคล้องกับกฎการฟอร์แมตของ GS1

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก‑วางลงในโปรเจกต์คอนโซลใหม่ได้ รวมถึงการอ้างอิง `using` ที่จำเป็น การสร้างโฟลเดอร์ และการจัดการข้อผิดพลาด

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**รันโปรแกรม** (`dotnet run`) แล้วคุณจะพบไฟล์ `Gs1Pdf417.png` อยู่ในโฟลเดอร์ *output* สแกนด้วยเครื่องอ่าน PDF417 ใดก็ได้เพื่อยืนยันว่า GTIN `(01)12345678901234` ถูกเข้ารหัสอย่างถูกต้อง

## คำถามที่พบบ่อย

**ถาม: สามารถใช้โค้ดนี้บน .NET Framework 4.6 ได้หรือไม่?**  
ตอบ: ใช่ ไลบรารี Aspose.BarCode รองรับ .NET Standard 2.0 ซึ่งเข้ากันได้กับ .NET Framework 4.6 ขึ้นไป

**ถาม: หากต้องการภาพความละเอียดสูงขึ้นควรทำอย่างไร?**  
ตอบ: ตั้งค่าคุณสมบัติ `Resolution` ก่อนบันทึก:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**ถาม: บาร์โค้ดยังคงใช้ได้หรือไม่หากไม่มีตัวระบุแอปพลิเคชัน GS1?**  
ตอบ: จะเป็นบาร์โค้ด PDF417 ปกติ แต่จะไม่ถูกจำแนกว่าเป็นสัญลักษณ์ที่สอดคล้องกับ GS1 อย่าลืมใส่คำนำหน้า `(01)` เมื่อคุณต้องการความสอดคล้อง **create GS1 barcode**

## สรุป

คุณได้เรียนรู้วิธี **สร้างบาร์โค้ด PDF417** ด้วย C# โดยใช้ **c# barcode generator** ที่มั่นคง บทแนะนำได้ครอบคลุม:

* การสร้างอ็อบเจกต์ `BarcodeGenerator` พร้อมข้อมูล GS1  
* การกำหนดค่า X‑dimension และจำนวนคอลัมน์  
* การบันทึกผลลัพธ์เป็นไฟล์ PNG  
* การขยายโซลูชันด้วยการแก้ไขข้อผิดพลาด รูปแบบภาพต่าง ๆ และการตรวจสอบอินพุต  

ด้วยพื้นฐานนี้คุณสามารถสร้างบาร์โค้ด PDF417 หรือ GS1 ใด ๆ จากสตริงโดยตรง ฝังลงในรายงาน หรือส่งไปยังเครื่องพิมพ์ สำรวจ Aspose.BarCode API เพื่อเพิ่มสี, เพิ่มขอบ, หรือรวมหลายบาร์โค้ดเป็นภาพเดียว

**ขั้นตอนต่อไป**: ลองสร้าง **create GS1 barcode** สำหรับ DataMatrix, ทดลองคำนวณคอลัมน์แบบไดนามิก, หรือบูรณาการตัวสร้างเข้ากับบริการเว็บ ASP.NET Core ที่ส่งคืนภาพบาร์โค้ดตามคำขอ

ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือฉบับสมบูรณ์](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [วิธีสร้างบาร์โค้ด micro pdf417 และสร้าง PNG ด้วย C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [วิธีสร้างบาร์โค้ด macro PDF417 ด้วย C# โดยใช้ Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}