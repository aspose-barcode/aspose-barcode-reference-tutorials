---
category: general
date: 2026-08-19
description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีสร้างบาร์โค้ด PDF417
  ด้วย C# โดยใช้ Aspose.BarCode พร้อมโหมดคอมแพคและการตั้งค่าที่กำหนดเอง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: th
lastmod: 2026-08-19
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# และ Aspose.BarCode บทเรียนนี้แสดงวิธีสร้างบาร์โค้ด
  PDF417 ด้วย C# ในโหมดคอมแพคต์ ตั้งค่า X‑dimension และบันทึกเป็น PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือครบถ้วนพร้อมการจัดวางแบบกะทัดรัด
url: /th/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือฉบับสมบูรณ์

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET นี้ คู่มือจะสาธิตขั้นตอนอย่างละเอียด คุณจะได้เห็นตัวอย่างสั้น ๆ ที่พร้อมใช้งานในสภาพแวดล้อมการผลิต ซึ่งสร้างบาร์โค้ด PDF417 แบบกะทัดรัด ปรับค่า X‑dimension และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ด PDF417 เป็นเรื่องทั่วไปเมื่อคุณต้องเข้ารหัสข้อมูลจำนวนมาก—เช่น ข้อมูลตั๋ว, รายการจัดส่ง, หรือเอกสารประจำตัว—in a machine‑readable format. การใช้ Aspose.BarCode ทำให้กระบวนการง่ายขึ้น และโค้ดทำงานกับ .NET 6+ หรือ .NET Framework 4.7.2 ขึ้นไป

ในคู่มือนี้คุณจะ:

* ติดตั้งแพคเกจ NuGet ของ Aspose.BarCode
* เขียนโปรแกรม C# แบบ self‑contained ที่ **สร้างบาร์โค้ด PDF417** ด้วยจำนวนคอลัมน์น้อยและโหมดกะทัดรัด (truncated)
* ปรับความกว้างของบาร์ (X‑dimension) เพื่อให้การแสดงผลคมชัดขึ้น
* บันทึกบาร์โค้ดเป็นไฟล์ PNG
* สำรวจรูปแบบต่าง ๆ, กรณีขอบ, และเคล็ดลับปฏิบัติที่ดีที่สุด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* Visual Studio 2022 (หรือ IDE ของ C# ใดก็ได้) ที่ติดตั้ง .NET 6 SDK แล้ว
* การเชื่อมต่ออินเทอร์เน็ตเพื่อดาวน์โหลดแพคเกจ NuGet **Aspose.BarCode**
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

ไม่จำเป็นต้องใช้ไลบรารีเพิ่มเติม; Aspose.BarCode จัดการการเข้ารหัสภาพภายในเอง

## ขั้นตอนที่ 1: เพิ่มแพคเกจ Aspose.BarCode

เปิดโปรเจกต์ของคุณใน Visual Studio, คลิกขวาที่โซลูชัน, แล้วเลือก **Manage NuGet Packages** ค้นหา `Aspose.BarCode` และติดตั้งเวอร์ชัน stable ล่าสุด

```bash
dotnet add package Aspose.BarCode
```

> **เคล็ดลับระดับมืออาชีพ:** ควรอัปเดตแพคเกจอยู่เสมอ รุ่นใหม่มักมีการปรับปรุงประสิทธิภาพและรองรับ .NET runtime ล่าสุด

## ขั้นตอนที่ 2: สร้างแอปพลิเคชันคอนโซลขนาดเล็ก

สร้างโปรเจกต์คอนโซล C# ใหม่หากคุณยังไม่มี

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

แทนที่เนื้อหาในไฟล์ `Program.cs` ด้วยตัวอย่างเต็มด้านล่าง โปรแกรมนี้แสดง **วิธีสร้างบาร์โค้ด PDF417 ด้วย C#** ตั้งแต่เริ่มต้นจนจบ

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

* **`EncodeTypes.Pdf417`** – เลือกสัญลักษณ์ PDF417 ซึ่งรองรับข้อมูลได้สูงสุดประมาณ ~1.1 KB  
* **`XDimension.Pixels = 2`** – กำหนดความกว้างพื้นฐานของบาร์ ค่าเล็กทำให้บาร์บาง; ค่ามากทำให้อ่านง่ายบนอุปกรณ์ความละเอียดต่ำ  
* **`Pdf417.Columns = 3`** – จำกัดจำนวนคอลัมน์ ทำให้ตัวสร้างต้องใช้แถวมากขึ้น ส่งผลให้บาร์โค้ดสูงแต่แคบกว่า  
* **`Pdf417.Truncate = true`** – เปิดโหมดกะทัดรัด, ลบรูปแบบหยุดและทำให้ภาพเล็กลงโดยไม่สูญเสียความสมบูรณ์ของข้อมูล  
* **`Save(..., BarCodeImageFormat.Png)`** – บันทึกเป็นไฟล์ PNG คุณสามารถเลือก `Jpeg`, `Bmp`, หรือ `Svg` ตามความต้องการของระบบต่อไปได้  

Run the program:

```bash
dotnet run
```

คุณควรเห็นข้อความในคอนโซลที่ยืนยันตำแหน่งไฟล์ และโฟลเดอร์จะมีไฟล์ `CompactPdf417.png` การเปิดไฟล์ PNG จะเห็นบาร์โค้ด PDF417 แบบกะทัดรัดที่ชัดเจนซึ่งเข้ารหัสสตริง Unicode

## ขั้นตอนที่ 3: ตรวจสอบบาร์โค้ด (ไม่บังคับแต่แนะนำ)

เพื่อให้แน่ใจว่าบาร์โค้ดอ่านได้ คุณสามารถใช้แอปสแกน PDF417 มาตรฐานบนสมาร์ทโฟนหรือไลบรารีดีโคเดอร์บนเดสก์ท็อป ข้อความที่เข้ารหัสควรตรงกับสตริง `data` ดั้งเดิมอย่างสมบูรณ์ รวมถึงอักขระพิเศษ

หากคุณพบปัญหาในการดีโคด:

* เพิ่มค่า `XDimension` เป็น 3 หรือ 4 พิกเซล
* ลดจำนวนคอลัมน์ (เช่น ตั้งค่า `Columns = 2`)
* ปิดการใช้งาน `Truncate` (`Truncate = false`) เพื่อเพิ่มรูปแบบหยุด

การปรับเหล่านี้เป็นการแลกเปลี่ยนระหว่างขนาดกับความอ่านง่าย ซึ่งมีประโยชน์สำหรับเครื่องพิมพ์หรือสแกนเนอร์ที่ความละเอียดต่ำ

## ขั้นตอนที่ 4: สำรวจรูปแบบทั่วไป

### 4️⃣ สร้าง PDF417 ความหนาแน่นสูงสำหรับการพิมพ์

หากคุณต้องการบาร์โค้ดที่พอดีกับป้ายเล็ก ๆ ให้เพิ่มจำนวนคอลัมน์และลดค่า X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ เปลี่ยนรูปแบบเอาต์พุตเป็น SVG เพื่อการสเกลแบบเวกเตอร์

ผลลัพธ์ SVG สามารถสเกลได้โดยไม่สูญเสียคุณภาพ เหมาะสำหรับหน้าเว็บที่ตอบสนองต่อขนาดหน้าจอ

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ เข้ารหัสข้อมูลไบนารี (เช่น byte array)

หากคุณต้องการฝังข้อมูลไบนารี ให้แปลงเป็นสตริง Base64 ก่อน

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

บาร์โค้ดตอนนี้บรรจุข้อมูลไบนารี และดีโคเดอร์ต้องทำการแปลงกลับจาก Base64

## คำถามที่พบบ่อย

| Question | Answer |
|----------|--------|
| **ฉันสามารถสร้าง PDF417 ได้โดยไม่ใช้ Aspose หรือไม่?** | ได้, มีไลบรารีอื่นเช่น ZXing.Net หรือ Dynamsoft ที่สามารถใช้ได้, แต่ Aspose.BarCode ให้การควบคุมการจัดวางที่หลากหลายกว่า (คอลัมน์, การตัด) และการจัดการ Unicode ที่ดีกว่า |
| **ความยาวข้อมูลสูงสุดคือเท่าไหร่?** | PDF417 สามารถเข้ารหัสข้อมูลไบนารีได้สูงสุด 1,108 ไบต์ (≈ 1 KB) หากเกินขนาดนี้ ควรพิจารณาแบ่งข้อมูลเป็นหลายบาร์โค้ด |
| **โหมดกะทัดรัดสอดคล้องกับมาตรฐานหรือไม่?** | Truncated PDF417 เป็นส่วนหนึ่งของสเปค ISO/IEC 15438 และได้รับการสนับสนุนอย่างกว้างขวาง, แต่ควรตรวจสอบว่าเครื่องสแกนของคุณรองรับอย่างชัดเจนหรือไม่ |
| **ฉันจะเปลี่ยนสีพื้นหลังได้อย่างไร?** | ตั้งค่า `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` และ `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` ก่อนบันทึก |

## สรุป

ตอนนี้คุณรู้ **วิธีสร้างบาร์โค้ด PDF417 ด้วย C#** โดยใช้ Aspose.BarCode, วิธีปรับ X‑dimension อย่างละเอียด, เปิดโหมดกะทัดรัด, และส่งออกผลลัพธ์เป็นภาพ PNG ตัวอย่างที่สมบูรณ์และสามารถรันได้สามารถคัดลอกไปใส่ในโปรเจกต์ .NET ใดก็ได้ และรูปแบบที่แสดงให้คุณปรับบาร์โค้ดสำหรับการพิมพ์, เว็บ, หรือกรณีข้อมูลไบนารี

ขั้นตอนต่อไปที่คุณอาจสำรวจ:

* ผสานการสร้างบาร์โค้ดเข้ากับ ASP.NET Core API ที่ให้บริการภาพตามความต้องการ
* รวม PDF417 กับ QR code บนป้ายเดียวเพื่อการสแกนแบบสองรูปแบบ
* ใช้คลาส `Reader` ของ Aspose.BarCode เพื่อดีโคดภาพที่สร้างและตรวจสอบข้อมูลโดยโปรแกรม

ขอให้สนุกกับการเขียนโค้ด และเพลิดเพลินกับความยืดหยุ่นที่โซลูชัน **การสร้างบาร์โค้ด PDF417** มอบให้กับแอปพลิเคชันของคุณ!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด – PDF417 กะทัดรัดด้วย Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [วิธีสร้างภาพบาร์โค้ดพร้อมการปรับแต่งพื้นที่เสริมโดยใช้ Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}