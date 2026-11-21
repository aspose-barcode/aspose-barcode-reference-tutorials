---
category: general
date: 2026-11-20
description: เรียนรู้วิธีสร้างบาร์โค้ด macro PDF417 ด้วย C# โดยใช้ Aspose.BarCode
  คู่มือนี้ครอบคลุมเมตาดาต้า พารามิเตอร์ และการบันทึกรูปภาพ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: th
lastmod: 2026-11-20
og_description: สร้างบาร์โค้ด macro PDF417 ใน C# ด้วย Aspose.BarCode. ทำตามบทเรียนฉบับเต็มนี้เพื่อกำหนดเมตาดาต้า,
  ตั้งค่าพารามิเตอร์, และส่งออกเป็น PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: สร้างบาร์โค้ด macro PDF417 ด้วย C# – คู่มือขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: วิธีสร้างบาร์โค้ด Macro PDF417 ด้วย Aspose.BarCode ใน C#
url: /th/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด macro PDF417 ด้วย Aspose.BarCode ใน C#

หากคุณต้องการ **สร้างบาร์โค้ด macro PDF417** ในแอปพลิเคชัน .NET นี้ จะสอนขั้นตอนอย่างละเอียด คุณจะได้เห็นวิธีกำหนดค่าเมตาดาต้าเฉพาะ macro, ปรับการตั้งค่าการแสดงผล, และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ด macro PDF417 มีประโยชน์เมื่อคุณต้องการแบ่งชุดข้อมูลขนาดใหญ่เป็นหลายสัญลักษณ์พร้อมคงรหัสระบุไฟล์ทั้งหมดไว้ ในตัวอย่างด้านล่าง เราใช้ไลบรารี Aspose.BarCode ซึ่งให้ API ที่ใช้งานง่ายสำหรับคุณลักษณะทั้งหมดของ PDF417

เมื่อจบคู่มือนี้ คุณจะมีโปรแกรมคอนโซลที่พร้อมรันซึ่งสร้างภาพบาร์โค้ดที่มีข้อมูล macro ครบถ้วน

## ข้อกำหนดเบื้องต้น

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว
* Visual Studio 2022 (หรือ IDE ใดก็ได้ที่รองรับ C#)
* แพ็กเกจ NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้างบาร์โค้ดสำหรับ macro PDF417

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยค่า enum `EncodeTypes.MacroPdf417` ซึ่งบอกไลบรารีให้จัดบาร์โค้ดเป็นสัญลักษณ์ macro PDF417

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*ทำไมจึงสำคัญ*: การเลือก `MacroPdf417` จะเปิดใช้งานคุณสมบัติทั้งหมดที่เกี่ยวกับ macro บนวัตถุพารามิเตอร์ `Pdf417`

## ขั้นตอนที่ 2: ตั้งค่าการแสดงผลพื้นฐาน

บาร์โค้ดที่อ่านได้เริ่มจากขนาดโมดูลและจำนวนคอลัมน์ที่เหมาะสม คุณสมบัติ `XDimension.Pixels` ควบคุมความกว้างของโมดูลหนึ่งหน่วย ในขณะที่ `Pdf417.Columns` กำหนดจำนวนคอลัมน์ข้อมูลต่อแถว

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

การปรับค่าต่าง ๆ นี้มีผลต่อความน่าเชื่อถือของสแกนเนอร์และขนาดของภาพ

## ขั้นตอนที่ 3: กำหนดรายละเอียดการระบุไฟล์ macro

Macro PDF417 ต้องการรหัสไฟล์, รหัสส่วน, และจำนวนส่วนทั้งหมด ฟิลด์ทั้งสามนี้ช่วยให้สแกนเนอร์สามารถประกอบชุดข้อมูลเดิมได้

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

**พารามิเตอร์ macro PDF417** เหล่านี้เป็นแกนหลักของฟังก์ชัน macro หากไม่มีสแกนเนอร์จะไม่สามารถเชื่อมโยงสัญลักษณ์เข้าด้วยกัน

## ขั้นตอนที่ 4: เพิ่มเมตาดาต้า macro แบบเลือก

นอกเหนือจากตัวระบุที่จำเป็นแล้ว รูปแบบ macro ยังรองรับฟิลด์เพิ่มเติม เช่น checksum, ขนาดไฟล์, timestamp, ผู้รับ, ผู้ส่ง, และธง terminator การใส่ข้อมูลเหล่านี้ช่วยเพิ่มการตรวจจับข้อผิดพลาดและให้บริบทกับระบบต่อไป

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*เคล็ดลับ*: หากกระบวนการของคุณไม่ต้องการฟิลด์ใดฟิลด์หนึ่ง คุณสามารถปล่อยให้เป็นค่าปริยายได้ ไลบรารีจะละเว้นองค์ประกอบข้อมูลที่สอดคล้องจากบาร์โค้ด

## ขั้นตอนที่ 5: บันทึกภาพบาร์โค้ด

หลังจากกำหนดค่าทั้งหมดแล้ว เรียก `Save` เพื่อส่งออกบาร์โค้ด ตัวอย่างจะบันทึกไฟล์ PNG ลงในไดเรกทอรีที่ผู้ใช้ระบุ

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

เมื่อโปรแกรมทำงานเสร็จ `ExtPDF417Meta.png` จะมีบาร์โค้ด macro PDF417 ที่เข้ารหัสข้อความ `"Åspóse.Barcóde©"` พร้อมเมตาดาต้า macro ทั้งหมด

## โค้ดต้นฉบับเต็ม

ด้านล่างเป็นโปรแกรมที่สมบูรณ์และทำงานได้ด้วยตนเอง คัดลอกไปยังโปรเจกต์คอนโซลใหม่และรันหลังจากติดตั้งแพ็กเกจ NuGet ของ Aspose.BarCode

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะแสดงบรรทัดยืนยันที่คล้ายกับ:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

การเปิดไฟล์ PNG จะเห็นบาร์โค้ดที่หนาและคอนทราสต์สูง การสแกนด้วยสแกนเนอร์ที่รองรับ PDF417 จะคืนข้อความต้นฉบับพร้อมฟิลด์ macro ทั้งหมด

## คำถามทั่วไปและกรณีขอบ

### ถ้าฉันต้องการมากกว่า 20 ส่วนจะทำอย่างไร?

คุณสมบัติ `MacroPdf417SegmentsCount` สามารถตั้งค่าได้สูงสุดถึง `255` ตรวจสอบให้แน่ใจว่าระบบรับสามารถจัดการจำนวนส่วนที่มากขึ้นได้ และพิจารณาแบ่งข้อมูลเป็นจำนวนสัญลักษณ์ที่จัดการได้

### checksum มีผลต่อการสแกนอย่างไร?

CCITT‑16 checksum (`MacroPdf417Checksum`) ให้ชั้นการตรวจสอบข้อผิดพลาดเพิ่มเติม หากสแกนเนอร์ตรวจพบความไม่ตรงกัน จะปฏิเสธบาร์โค้ด คุณสามารถละเว้น checksum หากกระบวนการของคุณไม่จำเป็นต้องใช้

### ฉันสามารถสร้างบาร์โค้ด PDF417 macro โดยไม่ใช้ Aspose ได้หรือไม่?

ได้, ไลบรารีอื่น (เช่น ZXing.Net, Dynamsoft) รองรับ PDF417 แต่ฟิลด์เฉพาะ macro มักไม่มี Aspose.BarCode ให้การทำงานที่สมบูรณ์ที่สุดสำหรับเมตาดาต้า macro

### รูปแบบภาพใดบ้างที่รองรับการบันทึก?

เมธอด `Save` ยอมรับรูปแบบใดก็ได้ที่กำหนดใน `BarCodeImageFormat` เช่น `Png`, `Jpeg`, `Gif`, `Bmp`, และ `Tiff` เลือกรูปแบบที่สอดคล้องกับขั้นตอนการประมวลผลต่อไปของคุณ

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด macro PDF417** ใน C# ด้วย Aspose.BarCode แล้ว คู่มือได้ครอบคลุมการเริ่มต้นตัวสร้าง, การตั้งค่าการแสดงผล, ตัวระบุไฟล์ macro, เมตาดาต้าแบบเลือก, และการส่งออกภาพ ด้วยพื้นฐานนี้คุณสามารถฝัง macro PDF ในระบบสินค้าคงคลัง, การติดตามเอกสาร, หรือสถานการณ์ใด ๆ ที่ต้องการการส่งข้อมูลแบบแบ่งส่วน

ขั้นตอนต่อไปอาจรวมถึงการทดลองค่า `XDimension` ต่าง ๆ เพื่อความละเอียดสูงขึ้น, การปรับระดับการแก้ไขข้อผิดพลาด, หรือการรวมบาร์โค้ดเข้าสู่เว็บ API ที่ส่งสตรีม PNG โดยตรง สำหรับหัวข้อที่เกี่ยวข้อง ดูบทเรียนเกี่ยวกับ **ตัวอย่างตัวสร้างบาร์โค้ด**, **พารามิเตอร์ macro PDF417**, และการจัดการ **เมตาดาต้า macro PDF417**

ขอให้เขียนโค้ดอย่างสนุก!

## สิ่งที่คุณควรเรียนต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโครงการของคุณ

- [วิธีสร้างภาพบาร์โค้ด PDF417 ใน C# พร้อมตัวเลือก Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [อ่านบาร์โค้ดจากภาพ C# – คู่มือเต็มพร้อม Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [วิธีสร้างบาร์โค้ด PDF417 ด้วย Aspose – คู่มือขั้นตอนเต็ม](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}