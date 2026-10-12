---
category: general
date: 2026-10-02
description: สร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode. เรียนรู้วิธีสร้างบาร์โค้ด
  PDF417 และดูวิธีสร้างบาร์โค้ด PDF417 ในโหมดคอมแพคท์.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: th
lastmod: 2026-10-02
og_description: สร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode คู่มือนี้แสดงวิธีสร้างบาร์โค้ด
  PDF417 และวิธีสร้างบาร์โค้ด PDF417 ในโหมดคอมแพคท์
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: สร้างบาร์โค้ดจากข้อความใน C# – คู่มือแบบทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: วิธีสร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode
url: /th/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดจากข้อความใน C# ด้วย Aspose.BarCode

หากคุณต้องการ **สร้างบาร์โค้ดจากข้อความ** ในแอปพลิเคชัน .NET คู่มือนี้จะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เห็นตัวอย่างที่พร้อมรันที่ **สร้างบาร์โค้ด PDF417** และยังตอบ **วิธีสร้างบาร์โค้ด PDF417** ในรูปแบบกะทัดรัด

การสร้างบาร์โค้ดโดยโปรแกรมช่วยลดขั้นตอนการทำงานด้วยมือและรับประกันความสอดคล้องกันในทุกเอกสาร เมื่อจบบทเรียนนี้คุณจะมีไฟล์ PNG ที่มีบาร์โค้ด PDF417 ซึ่งคุณสามารถฝังลงในใบแจ้งหนี้, ตั๋ว, หรือบัตรประจำตัวได้

## สิ่งที่คุณต้องเตรียม

- .NET 6.0 SDK หรือใหม่กว่า (โค้ดยังทำงานกับ .NET Framework 4.7.2+ ด้วย)
- Visual Studio 2022 หรือเครื่องมือแก้ไขใด ๆ ที่รองรับ C#
- ไลเซนส์ NuGet สำหรับ **Aspose.BarCode for .NET** (ทดลองใช้ฟรีก็เพียงพอสำหรับการทดสอบ)

> **Pro tip:** เพิ่มแพ็กเกจ NuGet ผ่าน CLI เพื่อให้โครงการสะอาดเรียบร้อย:  
> `dotnet add package Aspose.BarCode`

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์คอนโซล

สร้างแอปพลิเคชันคอนโซลใหม่และอ้างอิงไลบรารี Aspose.BarCode

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

คำสั่ง `dotnet new console` จะสร้างไฟล์ `Program.cs` ที่เราจะเปลี่ยนเป็นตัวอย่างเต็มด้านล่าง

## ขั้นตอนที่ 2: วิธีสร้างบาร์โค้ดจากข้อความ – โค้ดหลัก

เปิดไฟล์ `Program.cs` แล้วแทนที่เนื้อหาด้วยโค้ดต่อไปนี้ ทุกบรรทัดมีคอมเมนต์อธิบายเหตุผลที่มีอยู่

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### ทำไมแต่ละการตั้งค่าถึงสำคัญ

| Setting | Purpose |
|--------|----------|
| `EncodeTypes.Pdf417` | เลือกสัญลักษณ์ PDF417 ซึ่งสามารถเก็บข้อมูลจำนวนมากในเมทริกซ์สองมิติ |
| `XDimension.Pixels = 2` | ควบคุมความกว้างของแต่ละโมดูล; ค่า 2 พิกเซลให้ความสมดุลระหว่างความอ่านง่ายและขนาดไฟล์ |
| `Pdf417.Columns = 3` | ลดจำนวนคอลัมน์ ทำให้บาร์โค้ดกระชับขึ้นโดยไม่สูญเสียข้อมูล |
| `Pdf417.Truncate = true` | เปิดโหมดกระชับ, ลบพื้นที่ว่างที่ไม่จำเป็นและทำให้บาร์โค้ดสั้นลง |
| `BarCodeImageFormat.Png` | PNG รักษาคุณภาพแบบไม่มีการสูญเสีย เหมาะสำหรับการประมวลผลต่อหรือการพิมพ์ |

## ขั้นตอนที่ 3: สร้างบาร์โค้ด PDF417 – รันตัวอย่าง

สร้างและรันโปรเจกต์:

```bash
dotnet run
```

เมื่อการทำงานเสร็จสิ้นคุณจะเห็น:

```
Barcode saved to CompactPdf417.png
```

เปิดไฟล์ `CompactPdf417.png` เพื่อดูผลลัพธ์ ภาพนี้มีบาร์โค้ด PDF417 ที่เข้ารหัสสตริง **Åspóse.Barcóde©**

![ตัวอย่างการสร้างบาร์โค้ดจากข้อความ](barcode-example.png)

*ข้อความแทนภาพ: สร้างบาร์โค้ดจากข้อความ – บาร์โค้ด PDF417 บันทึกเป็น PNG*

## ขั้นตอนที่ 4: วิธีสร้างบาร์โค้ด PDF417 พร้อมการแก้ไขข้อผิดพลาดแบบกำหนดเอง (ทางเลือก)

หากสภาพแวดล้อมการสแกนของคุณมีสัญญาณรบกวน คุณสามารถเพิ่มระดับการแก้ไขข้อผิดพลาดได้:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

การเพิ่มระดับการแก้ไขข้อผิดพลาดทำให้บาร์โค้ดใหญ่ขึ้น แต่เพิ่มความทนทานต่อความเสียหาย

## ขั้นตอนที่ 5: ข้อผิดพลาดทั่วไปและการจัดการกรณีขอบ

1. **Invalid characters** – PDF417 รองรับ Unicode แต่สแกนเนอร์รุ่นเก่าอาจปฏิเสธสัญลักษณ์ที่ไม่ใช่ ASCII. ทดสอบกับฮาร์ดแวร์เป้าหมายของคุณ
2. **File path permissions** – ตรวจสอบให้แน่ใจว่าไดเรกทอรีที่คุณบันทึกมีสิทธิ์เขียน; มิฉะนั้นฟังก์ชัน `Save` จะโยน `UnauthorizedAccessException`
3. **Image size** – ค่า `XDimension` สูงมากจะทำให้ไฟล์ PNG ใหญ่ขึ้น. ควรตั้งค่าขนาดพิกเซลระหว่าง 1 ถึง 4 สำหรับการแสดงผลบนหน้าจอส่วนใหญ่

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ดจากข้อความ** ใน C# ด้วย Aspose.BarCode, วิธี **สร้างบาร์โค้ด PDF417** ด้วยรูปแบบกะทัดรัด, และขั้นตอนที่แน่นอนสำหรับ **วิธีสร้างบาร์โค้ด PDF417** ด้วยการตั้งค่าที่กำหนดเอง โค้ดที่ทำงานได้เต็มรูปแบบข้างต้นสามารถคัดลอกไปยังโปรเจกต์ .NET ใด ๆ และปรับให้เข้ากับข้อความหรือรูปแบบผลลัพธ์ที่ต่างกัน (เช่น JPEG, BMP)

## ขั้นตอนต่อไป

- สำรวจสัญลักษณ์อื่น ๆ เช่น QR Code หรือ Code128 โดยเปลี่ยนค่า `EncodeTypes`.
- ผสานรวม PNG ที่สร้างขึ้นเข้าสู่ PDF ด้วย Aspose.PDF เพื่อการสร้างเอกสารแบบครบวงจร.
- ทดลองใช้ `generator.Parameters.Barcode.Pdf417.Rows` เพื่อควบคุมความหนาแน่นแนวตั้ง.

คุณสามารถปรับเปลี่ยนตัวอย่าง ฝังบาร์โค้ดในแอปพลิเคชันของคุณ และแชร์ผลลัพธ์กับชุมชนได้ตามต้องการ. ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด PDF417 ใน C# – ตัวอย่างแบบกะทัดรัด](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยโหมดกะทัดรัด](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [วิธีสร้างบาร์โค้ด PDF417 ใน C# – คู่มือแบบขั้นตอนต่อขั้นตอน](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}