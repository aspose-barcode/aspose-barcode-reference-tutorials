---
category: general
date: 2026-10-21
description: สร้างบาร์โค้ด pdf417 อย่างรวดเร็วด้วย C# เรียนรู้วิธีสร้างบาร์โค้ด pdf417
  ด้วยการจัดรูปแบบแบบกำหนดเอง, คอลัมน์, แถว และการส่งออกเป็น PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: th
lastmod: 2026-10-21
og_description: สร้างบาร์โค้ด pdf417 ด้วย C# ทำตามบทแนะนำนี้เพื่อเรียนรู้วิธีสร้างบาร์โค้ด
  pdf417 ด้วยคอลัมน์และแถวที่กำหนดเอง พร้อมผลลัพธ์เป็นไฟล์ PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: สร้างบาร์โค้ด pdf417 ใน C# – คู่มือเต็มขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: สร้างบาร์โค้ด pdf417 ใน C# ด้วยคอลัมน์และแถวที่กำหนดเอง
url: /th/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด pdf417 ใน C# – คู่มือการเขียนโปรแกรมแบบสมบูรณ์

หากคุณต้องการ **generate pdf417 barcode** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงวิธีทำด้วยไม่กี่บรรทัดของโค้ด คุณจะได้เห็นตัวอย่างเชิงปฏิบัติที่กำหนดจำนวนคอลัมน์และแถว แล้วบันทึกผลลัพธ์เป็นไฟล์ภาพ PNG วิธีเดียวกันนี้ใช้ได้กับข้อความใด ๆ ที่คุณต้องการเข้ารหัส ดังนั้นคุณสามารถปรับใช้กับใบแจ้งหนี้, ตั๋ว, หรือบัตรประจำตัวได้

การสร้าง **pdf417 barcode** มักรู้สึกเหมือนเป็นงานแยกจากส่วนอื่นของโค้ดของคุณ เมื่อจบบทเรียนนี้คุณจะเข้าใจว่าทำไมพารามิเตอร์การจัดวางจึงสำคัญ, วิธีควบคุมคุณภาพของภาพ, และการเรียกใช้ไลบรารีใดที่จำเป็นเพื่อ **generate pdf417 barcode** อย่างเชื่อถือได้

## สิ่งที่คุณต้องการ

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว  
* IDE ที่รองรับ C# (Visual Studio, VS Code, Rider, ฯลฯ)  
* แพคเกจ NuGet **Aspose.BarCode for .NET** (หรือไลบรารีบาร์โค้ดที่เข้ากันได้อื่น)

You can add the library with the following command:

```bash
dotnet add package Aspose.BarCode
```

ไลบรารีนี้ให้คลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียนนี้

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของตัวสร้างบาร์โค้ด

บรรทัดแรกสร้างอ็อบเจกต์ที่รู้วิธี **generate pdf417 barcode** คุณต้องระบุประเภทการเข้ารหัส (`EncodeTypes.Pdf417`) และข้อความที่ต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*ทำไมขั้นตอนนี้สำคัญ* – `BarcodeGenerator` รวมการตั้งค่าทั้งหมดสำหรับบาร์โค้ด การสร้างอินสแตนซ์ด้วย `EncodeTypes` ที่ถูกต้องบอกให้เอนจินใช้สัญลักษณ์ PDF417 แทน QR, Code128 หรือรูปแบบอื่น

## ขั้นตอนที่ 2: กำหนดการจัดวาง PDF417

PDF417 ให้คุณควบคุมจำนวนคอลัมน์และแถว ซึ่งส่งผลโดยตรงต่อขนาดและความหนาแน่นของบาร์โค้ด การปรับค่าต่าง ๆ เหล่านี้เป็นหัวใจของ **how to generate pdf417 barcode** ด้วยการจัดวางแบบกำหนดเอง

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*ทำไมคุณอาจเปลี่ยนค่าต่าง ๆ เหล่านี้* – คอลัมน์มากขึ้นจะทำให้ความสูงของบาร์โค้ดลดลง, ในขณะที่แถวมากขึ้นจะทำให้ความกว้างเพิ่มขึ้น เลือกค่าที่เหมาะกับอุปกรณ์สแกนเป้าหมายและพื้นที่พิมพ์ที่มี

> **เคล็ดลับ:** หากคุณละเว้นการกำหนดแถว, ไลบรารีจะคำนวณจำนวนที่เหมาะสมโดยอัตโนมัติตามความยาวของข้อมูล การกำหนดค่าแถวอย่างชัดเจนมีประโยชน์เมื่อคุณต้องการขนาดภาพคงที่สำหรับการจัดวาง UI

## ขั้นตอนที่ 3: เลือกรูปแบบภาพและบันทึกไฟล์

หลังจากกำหนดการจัดวางแล้ว คุณสามารถเรนเดอร์บาร์โค้ดเป็นภาพ ตัวอย่างด้านล่างบันทึกบาร์โค้ดเป็นไฟล์ PNG แต่คุณก็สามารถเลือก JPEG, BMP หรือ TIFF ได้เช่นกัน

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

เมื่อโค้ดทำงาน, `CustomLayout.png` จะมี **pdf417 barcode** ที่ชัดเจนซึ่งตรงกับการตั้งค่าคอลัมน์/แถวที่คุณกำหนด

### ผลลัพธ์ที่คาดหวัง

การเปิด `CustomLayout.png` จะเห็นบาร์โค้ดสี่เหลี่ยมที่มีคอลัมน์ข้อมูลสี่คอลัมน์และแถวเก้าคอลัมน์ การสแกนภาพด้วยเครื่องอ่าน PDF417 ใด ๆ จะคืนข้อความต้นฉบับ **“Sample Text”**.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Generated pdf417 barcode saved as a PNG file"}

## ขั้นตอนที่ 4: ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นแอปพลิเคชันคอนโซลแบบ self‑contained ที่รวมส่วนต่าง ๆ เข้าด้วยกัน คัดลอกโค้ดไปยังโปรเจกต์ `.csproj` ใหม่และรัน—ไม่ต้องมีไฟล์เพิ่มเติม

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

การรันโปรแกรมจะแสดงบรรทัดยืนยันและสร้างไฟล์ PNG ภายใต้โฟลเดอร์ย่อย `output` ภาพนี้สามารถฝังในรายงาน, พิมพ์บนป้าย, หรือส่งไปยังอุปกรณ์มือถือเพื่อสแกนได้

## การปรับเปลี่ยนทั่วไปและกรณีขอบ

| สถานการณ์ | สิ่งที่ต้องเปลี่ยน | เหตุผลที่สำคัญ |
|----------|----------------|----------------|
| **Encode a long string** | เพิ่ม `Rows` หรือให้ไลบรารีคำนวณอัตโนมัติโดยไม่กำหนดค่า `Rows` | PDF417 สามารถเก็บได้สูงสุด 1,850 ตัวอักษร; แถวไม่เพียงพอจะทำให้ข้อมูลถูกตัด |
| **Higher visual quality** | ตั้งค่า `generator.Parameters.ImageResolution` เป็น 600 DPI | มีประโยชน์สำหรับการพิมพ์บนเครื่องพิมพ์ความละเอียดสูง |
| **Different image format** | แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg` หรือ `Tiff` | JPEG ลดขนาดไฟล์; TIFF รักษาข้อมูลแบบไม่มีการสูญเสียสำหรับการเก็บถาวร |
| **Add a quiet zone** | `generator.Parameters.Barcode.XDimension = 2;` (หรือปรับ `Margins`) | โซนเงียบช่วยเพิ่มความน่าเชื่อถือของสแกนเนอร์ในสภาพแวดล้อมที่มีเสียงรบกวน |
| **Dynamic text from user input** | แทนที่สตริงที่กำหนดไว้ล่วงหน้าด้วย `Console.ReadLine()` | ทำให้สามารถสร้างบาร์โค้ดในเวลารันตามข้อมูลผู้ใช้ |

### วิธีการ generate pdf417 barcode ใน Web API

หากคุณต้องการเปิดเผยการสร้างบาร์โค้ดผ่าน endpoint ของ ASP.NET Core ให้ส่งคืนภาพเป็นอาเรย์ของไบต์:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

โค้ดส่วนนั้นตอบคำถาม **how to generate pdf417 barcode** แบบเรียลไทม์โดยไม่ต้องเขียนลงดิสก์ ซึ่งเหมาะสำหรับไมโครเซอร์วิสหรือแบ็กเอนด์บนมือถือ

## การทดสอบบาร์โค้ดที่สร้างขึ้น

เพื่อยืนยันว่าบาร์โค้ดถูกสร้างอย่างถูกต้อง:

1. เปิดไฟล์ PNG ด้วยโปรแกรมดูรูปใดก็ได้  
2. ใช้แอปสแกน PDF417 ฟรี (เช่น ZXing, PDF417 Decoder) เพื่อสแกนภาพ  
3. ยืนยันว่าข้อความที่ถอดรหัสตรงกับข้อมูลต้นฉบับ

หากสแกนเนอร์รายงานข้อผิดพลาด ให้ตรวจสอบค่าคอลัมน์/แถวอีกครั้งและตรวจสอบให้แน่ใจว่าความละเอียดของภาพสูงพอสำหรับอุปกรณ์ของคุณ

## สรุป

ตอนนี้คุณรู้วิธี **generate pdf417 barcode** ใน C# พร้อมการควบคุมเต็มที่ของคอลัมน์, แถว, และรูปแบบผลลัพธ์ ตัวอย่างเต็มแสดงกระบวนการทั้งหมด — ตั้งแต่การสร้าง `BarcodeGenerator` ไปจนถึงการบันทึกไฟล์ PNG — เพื่อให้คุณสามารถผสานการสร้างบาร์โค้ดเข้ากับโปรเจกต์ .NET ใดก็ได้

ต่อไป, สำรวจหัวข้อที่เกี่ยวข้องเช่นการปรับแต่ง **pdf417 barcode layout**, การฝังบาร์โค้ดในรายงาน PDF, หรือการถอดรหัสบาร์โค้ดบนอุปกรณ์มือถือ การปรับระดับการแก้ไขข้อผิดพลาดและการทดลองใช้ความละเอียดภาพต่าง ๆ จะช่วยให้คุณปรับโซลูชันให้เหมาะกับกรณีการใช้งานของคุณเอง ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ

- [วิธีการ generate PDF417 barcode ใน C# – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [วิธีการ Save Barcode ใน C# – สร้าง PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [วิธีการ Generate PDF417 Barcode – คู่มือการเขียนโปรแกรมแบบสมบูรณ์](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}