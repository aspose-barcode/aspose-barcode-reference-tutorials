---
category: general
date: 2026-08-09
description: ตัวอย่างบาร์โค้ดของ Aspose แสดงวิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้าง
  Macro PDF417 พร้อมการสนับสนุนเมตาดาต้าเต็มรูปแบบ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: th
lastmod: 2026-08-09
og_description: ตัวอย่างบาร์โค้ดของ Aspose แสดงการใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด
  Macro PDF417 ที่รวมไฟล์ ID, ข้อมูลเซกเมนต์, เวลาและเมตาดาต้าอื่น ๆ
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: ตัวอย่างบาร์โค้ด Aspose – สร้าง Macro PDF417 ด้วย C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'ตัวอย่างบาร์โค้ด Aspose: สร้าง Macro PDF417 ด้วย C#'
url: /th/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่าง Aspose barcode: สร้าง Macro PDF417 ด้วย C#

หากคุณต้องการ **ตัวอย่าง aspose barcode** ที่สร้างบาร์โค้ด Macro PDF417 คำแนะนำนี้จะแสดงวิธีทำด้วย **barcode generator C#** คุณจะได้เห็นการตั้งค่าที่จำเป็นทั้งหมด ตั้งแต่ขนาดพื้นฐานจนถึงชุดเต็มของฟิลด์เมตาดาต้า Macro PDF417 และสุดท้ายจะได้ภาพ PNG ที่พร้อมสำหรับการประมวลผลต่อไป

บทเรียนนี้ครอบคลุมขั้นตอนการทำงานทั้งหมด อธิบายว่าทำไมแต่ละพารามิเตอร์จึงสำคัญ และให้ตัวอย่างโค้ดที่พร้อมรัน ไม่ต้องอ้างอิงภายนอก คุณสามารถคัดลอกโค้ด ปรับค่า แล้วรันได้ทันที

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

- .NET 6.0 (หรือใหม่กว่า) ที่ติดตั้งแล้ว  
- Visual Studio 2022 หรือ IDE ที่รองรับ C# ใดก็ได้  
- ไลเซนส์ที่ถูกต้องสำหรับ **Aspose.BarCode for .NET** (รุ่นทดลองฟรีใช้งานได้กับตัวอย่างนี้)  

เพิ่มแพคเกจ Aspose.BarCode NuGet ลงในโปรเจกต์ของคุณ:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: สร้างอินสแตนซ์ barcode generator C#

ขั้นตอนแรกคือการสร้างอ็อบเจ็กต์ `BarcodeGenerator` ด้วยค่า enum `EncodeTypes.MacroPdf417` และข้อความที่ต้องการเข้ารหัส ข้อความสามารถมีอักขระ Unicode ซึ่งไลบรารีจะจัดการให้โดยอัตโนมัติ

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*ทำไมจึงสำคัญ*: `EncodeTypes.MacroPdf417` บอกให้เอนจินสร้างสัญลักษณ์ Macro PDF417 ซึ่งรองรับข้อมูลแบบแบ่งส่วนและเมตาดาต้าระดับไฟล์เพิ่มเติม คำสั่ง `using` รับประกันว่าทรัพยากรที่ไม่ได้จัดการจะถูกปล่อยหลังจากบันทึกภาพเสร็จ

## ขั้นตอนที่ 2: กำหนดลักษณะพื้นฐานของบาร์โค้ด

บาร์โค้ด Macro PDF417 ประกอบด้วยโมดูลสี่เหลี่ยมจัตุรัส การควบคุมขนาดโมดูลและจำนวนคอลัมน์มีผลต่อความอ่านง่ายและขนาดไฟล์

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*ทำไมจึงสำคัญ*: `XDimension.Pixels` กำหนดความหนาแน่นของภาพ; ค่า 2 pixels ทำงานได้ดีสำหรับการแสดงบนหน้าจอพร้อมคงขนาดภาพให้เล็ก ปรับจำนวนคอลัมน์ให้สอดคล้องกับข้อจำกัดการออกแบบของคุณ—คอลัมน์มากขึ้นจะทำให้บาร์โค้ดกว้างและสั้นลง

## ขั้นตอนที่ 3: ตั้งค่าเมตาดาต้าเฉพาะ Macro PDF417

Macro PDF417 ขยายรูปแบบ PDF417 มาตรฐานด้วยฟิลด์ที่ช่วยให้สามารถสร้างไฟล์ขนาดใหญ่จากหลายส่วนบาร์โค้ดได้ ฟิลด์แต่ละอันเป็นตัวเลือก แต่การตั้งค่าจะทำให้คุณเห็นความสามารถเต็มของ API

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*ทำไมจึงสำคัญ*:  
- `MacroPdf417FileID` เชื่อมโยงทุกส่วนที่เป็นของไฟล์ตรรกะเดียวกัน  
- `MacroPdf417SegmentID` และ `MacroPdf417SegmentsCount` ช่วยให้ตัวถอดรหัสจัดลำดับส่วนย่อยได้อย่างถูกต้อง  
- `MacroPdf417Checksum` ให้การตรวจสอบความสมบูรณ์อย่างรวดเร็วโดยไม่ต้องถอดรหัสทั้งหมด  
- `MacroPdf417FileSize` และ `MacroPdf417TimeStamp` ช่วยระบบต่อท้ายตรวจสอบว่าไฟล์ที่สร้างขึ้นตรงกับไฟล์ต้นฉบับหรือไม่  
- `MacroPdf417Addressee` / `MacroPdf417Sender` มีประโยชน์ในสถานการณ์โลจิสติกส์หรือการแลกเปลี่ยนเอกสาร  
- การตั้งค่า `MacroPdf417Terminator` เป็น `Set` ทำเครื่องหมายบาร์โค้ดนี้เป็นส่วนสุดท้าย ซึ่งทำให้ขั้นตอนการรวมไฟล์ง่ายขึ้น

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ดที่สร้างขึ้น

สุดท้ายให้บันทึกบาร์โค้ดเป็นไฟล์ PNG คุณสามารถเลือกฟอร์แมตที่รองรับได้ทุกแบบ (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`)

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*ทำไมจึงสำคัญ*: PNG เก็บข้อมูลพิกเซลแบบ lossless ทำให้เครื่องสแกนอ่านรูปแบบโมดูลที่คุณกำหนดได้อย่างแม่นยำ การเปลี่ยนฟอร์แมตอาจส่งผลต่อคุณภาพภาพและขนาดไฟล์

### ผลลัพธ์ที่คาดหวัง

เมื่อรันโปรแกรมครบถ้วนจะสร้างไฟล์ชื่อ **ExtPDF417Meta.png** การเปิดภาพจะแสดงบาร์โค้ด Macro PDF417 รูปสี่เหลี่ยมที่เข้ารหัสข้อความ “Åspóse.Barcóde©” และความหนาแน่นของภาพตรงกับค่า X‑dimension 2‑pixel ที่คุณตั้งไว้ การสแกนภาพด้วยรีดเดอร์ที่รองรับ PDF417 จะคืนค่าฟิลด์เมตาดาต้าทั้งหมดที่กำหนดในขั้นตอน 3

## ตัวอย่างทำงานเต็มรูปแบบ

คัดลอกโค้ดด้านล่างไปยังโปรเจกต์คอนโซลใหม่ (`dotnet new console`) แล้วแทนที่ `YOUR_DIRECTORY` ด้วยพาธแบบ absolute หรือ relative ที่มีอยู่บนเครื่องของคุณ

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

รันโปรแกรม (`dotnet run`) หลังจากทำงานเสร็จ ให้ตรวจสอบว่าไฟล์ PNG ปรากฏในตำแหน่งที่คุณระบุ ใช้แอปอ่านบาร์โค้ดใดก็ได้ที่รองรับ Macro PDF417 เพื่อยืนยันว่าเมตาดาต้าถูกฝังอย่างถูกต้อง

## ความแตกต่างทั่วไปและกรณีขอบ

- **ฟอร์แมตภาพต่าง ๆ**: แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Tiff` หากระบบต่อท้ายของคุณต้องการฟอร์แมตอื่น  
- **การเปลี่ยนขนาดโมดูล**: ค่า `XDimension.Pixels` ที่ใหญ่ขึ้นช่วยเพิ่มความน่าเชื่อถือในการสแกนบนสแกนเนอร์ความละเอียดต่ำ แต่จะทำให้ไฟล์ใหญ่ขึ้น  
- **หลายส่วน**: หากต้องการสร้างไฟล์หลายส่วน ให้สร้างบาร์โค้ดชุดต่อเนื่อง เพิ่มค่า `MacroPdf417SegmentID` สำหรับแต่ละส่วนและคงค่า `MacroPdf417FileID` คงที่ ส่วนสุดท้ายควรตั้ง `MacroPdf417Terminator` เป็น `Set` เท่านั้น  
- **การสนับสนุน Unicode**: ตัวสร้างจะเข้ารหัสอักขระ Unicode อัตโนมัติ; ตรวจสอบให้แน่ใจว่า string ต้นทางของคุณใช้การเข้ารหัส UTF‑8 หากอ่านจากไฟล์ภายนอก  
- **การจัดการข้อผิดพลาด**: ห่อบล็อก `using` ด้วย try‑catch เพื่อดักจับ `BarCodeException` สำหรับพารามิเตอร์ที่ไม่ถูกต้อง (เช่น จำนวนคอลัมน์อยู่นอกช่วง)

## เคล็ดลับระดับมืออาชีพ

- **ประสิทธิภาพ**: ใช้อ็อบเจ็กต์ `BarcodeGenerator` ตัวเดียวซ้ำเมื่อสร้างบาร์โค้ดหลาย ๆ ตัวที่มีการตั้งค่าเดียวกัน; เพียงเปลี่ยนค่า `CodeText` ระหว่างการบันทึก  
- **การประมาณขนาดไฟล์**: ฟิลด์ `MacroPdf417FileSize` ควรตรงกับจำนวนไบต์ของข้อมูลต้นฉบับ; ความไม่ตรงกันอาจทำให้การตรวจสอบของระบบต่อท้ายล้มเหลว  
- **การทดสอบ**: ตรวจสอบบาร์โค้ดที่สร้างด้วยตัวถอดรหัสในตัวของ Aspose (`BarCodeReader`) และสแกนเนอร์ของบุคคลที่สามเพื่อยืนยันความเข้ากันได้

## สรุป

ตัวอย่าง **aspose barcode** นี้แสดงให้เห็นวิธีสร้าง Macro PDF417 ด้วย C# ตั้งแต่การกำหนดค่าเบื้องต้นจนถึงการบันทึกภาพพร้อมเมตาดาต้าเต็มรูปแบบ คุณสามารถนำไปปรับใช้ในโครงการของคุณเพื่อสร้างบาร์โค้ดที่รองรับการแบ่งส่วนไฟล์และข้อมูลเมตาดาต้าได้อย่างง่ายดาย

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอน‑ขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการใช้งานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}