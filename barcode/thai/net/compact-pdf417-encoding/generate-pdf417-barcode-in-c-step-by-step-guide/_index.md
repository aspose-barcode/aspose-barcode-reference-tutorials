---
category: general
date: 2026-08-09
description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีสร้าง PDF417 ด้วยโหมดคอมแพคท์
  การควบคุมคอลัมน์ และการส่งออกเป็น PNG โดยใช้ BarcodeGenerator API.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: th
lastmod: 2026-08-09
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# พร้อมตัวอย่างสั้น ๆ คู่มือนี้จะแสดงวิธีตั้งค่าโหมดคอมแพคท์
  กำหนดจำนวนคอลัมน์ และบันทึกผลลัพธ์เป็นภาพ PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – บทเรียนครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือแบบทีละขั้นตอน
url: /th/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด PDF417 ใน C# – คู่มือทีละขั้นตอน

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET นี้เป็นบทแนะนำที่แสดงวิธีทำอย่างละเอียด คุณจะได้เห็นโปรแกรมที่ทำงานได้เต็มรูปแบบซึ่งสร้างบาร์โค้ด PDF417 แบบกะทัดรัด ปรับขนาดตามต้องการ และบันทึกเป็นไฟล์ PNG

การสร้างบาร์โค้ด PDF417 เป็นความต้องการทั่วไปสำหรับการออกบัตรมือถือ การติดตามสินค้าคงคลัง และความปลอดภัยของเอกสาร คู่มือนี้ครอบคลุมตัวเลือกการกำหนดค่าที่สำคัญ อธิบายเหตุผลของแต่ละการตั้งค่า และให้เคล็ดลับการใช้งานจริงสำหรับสถานการณ์ต่าง ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* IDE สำหรับ C# เช่น Visual Studio 2022 หรือ Visual Studio Code  
* แพคเกจ **Aspose.BarCode for .NET** จาก NuGet (เวอร์ชัน 23.10 หรือใหม่กว่า)  

คุณสามารถติดตั้งแพคเกจด้วยคำสั่ง CLI ด้านล่าง:

```bash
dotnet add package Aspose.BarCode
```

โค้ดต่อไปนี้สมมติว่าแพคเกจถูกอ้างอิงแล้วและคุณมีสิทธิ์เขียนในไดเรกทอรีผลลัพธ์

## ขั้นตอนที่ 1: ตั้งค่าโครงการและนำเข้า namespace

สร้างโปรเจกต์คอนโซลใหม่และเพิ่ม `using` directives ที่จำเป็น namespace เหล่านี้ทำให้เข้าถึงคลาส `BarcodeGenerator` และ enumeration ของรูปแบบภาพได้

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**ทำไมต้องทำเช่นนี้:** การนำเข้า namespace ที่ถูกต้องทำให้คอมไพเลอร์ค้นพบประเภท `BarcodeGenerator` และ enum `BarCodeImageFormat` หากขาด namespace จะเกิดข้อผิดพลาดการคอมไพล์และกระบวนการสร้างบาร์โค้ดจะหยุดทำงาน

## ขั้นตอนที่ 2: เริ่มต้น `BarcodeGenerator` ด้วยการเข้ารหัส PDF417

คอนสตรัคเตอร์ของ `BarcodeGenerator` รับอาร์กิวเมนต์สองค่า: สัญลักษณ์บาร์โค้ด (`EncodeTypes.Pdf417`) และข้อความที่ต้องการเข้ารหัส PDF417 รองรับอักขระหลายประเภทรวมถึงสัญลักษณ์ Unicode

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**คำอธิบาย:**  
* `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้มาตรฐาน PDF417  
* ตัวอย่างข้อความมีอักขระที่มีสำเนียงและสัญลักษณ์ลิขสิทธิ์เพื่อแสดงการจัดการ Unicode  

หากคุณต้องการเข้ารหัสเฉพาะตัวเลข สามารถส่งสตริงธรรมดาเช่น `"1234567890"` ได้

## ขั้นตอนที่ 3: ปรับ X‑dimension เพื่อความละเอียดที่ละเอียดกว่า

X‑dimension ควบคุมความกว้างของโมดูลบาร์โค้ดแต่ละตัว (องค์ประกอบสีดำหรือสีขาวที่เล็กที่สุด) การตั้งค่าค่าพิกเซลที่เล็กลงจะให้ภาพที่ความละเอียดสูงขึ้น

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**ทำไมต้องปรับ?** X‑dimension เริ่มต้นที่ 3–4 พิกเซลอาจทำให้บาร์โค้ดดูหยาบบนหน้าจอ DPI สูง การลดลงเป็น **2 พิกเซล** จะทำให้ความอ่านง่ายและขนาดไฟล์สมดุลกัน โดยเฉพาะเมื่อเปิดใช้โหมดกะทัดรัดต่อไป

## ขั้นตอนที่ 4: กำหนดจำนวนคอลัมน์

PDF417 ให้คุณระบุจำนวนคอลัมน์ที่บาร์โค้ดควรมี คอลัมน์น้อยทำให้บาร์โค้ดแคบแต่สูงขึ้น ส่วนคอลัมน์มากทำให้บาร์โค้ดกว้างแต่สั้นลง

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**เคล็ดลับปฏิบัติ:** สำหรับบัตรมือถือที่ต้องใส่ในป้ายแคบ จำนวนคอลัมน์ **3–5** ทำงานได้ดี หากมีข้อมูลมากและต้องการบาร์โค้ดสั้นลง ให้เพิ่มจำนวนคอลัมน์

## ขั้นตอนที่ 5: เปิดใช้งานโหมดกะทัดรัดเพื่อตัดแถวที่ว่างเปล่า

โหมดกะทัดรัดจะลบแถวที่ไม่จำเป็นออกจากเมทริกซ์บาร์โค้ด ลดขนาดภาพโดยไม่สูญเสียข้อมูลที่เข้ารหัส

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**เมื่อใดควรใช้:** หากคุณสร้างบาร์โค้ดเพื่อจัดเก็บหรือส่งผ่านเครือข่าย โหมดกะทัดรัดสามารถทำให้ไฟล์ PNG ลดลงได้ถึง 30 % อย่างไรก็ตาม เครื่องสแกนรุ่นเก่าอาจไม่รองรับ PDF417 ที่ถูกตัดแถว; ควรทดสอบกับฮาร์ดแวร์เป้าหมายของคุณ

## ขั้นตอนที่ 6: บันทึกบาร์โค้ดเป็นภาพ PNG

กำหนดเส้นทางผลลัพธ์และเรียก `Save` enum `BarCodeImageFormat.Png` จะสร้างภาพที่ไม่มีการสูญเสียคุณภาพ เหมาะกับการใช้งานส่วนใหญ่

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**การตรวจสอบผลลัพธ์:** เปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ดที่หนาแน่นและคอนทราสต์สูงซึ่งตรงกับข้อความตัวอย่าง การสแกนภาพด้วยโปรแกรมอ่าน PDF417 (เช่น ZXing หรือแอปบนสมาร์ทโฟน) จะคืนสตริงต้นฉบับ `"Åspóse.Barcóde©"`  

![บาร์โค้ด PDF417 ที่สร้างและบันทึกเป็น PNG](compact-pdf417.png "บาร์โค้ด PDF417 ที่สร้างใน C#")

*ภาพด้านบนแสดงผลลัพธ์สุดท้ายของโค้ดในบทแนะนำ*

## ตัวอย่างเต็มที่สามารถรันได้

รวมทุกส่วนเข้าด้วยกัน นี่คือโปรแกรมคอนโซลที่สมบูรณ์ คุณสามารถคัดลอก วาง และรันได้เลย

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อรันโปรแกรมจะพิมพ์:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

ไฟล์ `CompactPdf417.png` จะมีบาร์โค้ด PDF417 กะทัดรัดที่เข้ารหัสสตริง Unicode ที่ให้ไว้ การสแกนภาพด้วยโปรแกรมอ่าน PDF417 มาตรฐานจะคืนข้อความเดิมอย่างแม่นยำ

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับ | เหตุผล |
|-----------|------------|--------|
| **ข้อมูลปริมาณมาก** (เช่น > 150 อักขระ) | เพิ่ม `generator.Parameters.Barcode.Pdf417.Columns` เป็น 6‑8 | คอลัมน์เพิ่มจะป้องกันบาร์โค้ดสูงเกินไป |
| **ต้องการพื้นหลังโปร่งใส** | ใช้ `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG โปร่งใสทำให้รวมกับ UI ได้ดีขึ้น |
| **สร้าง JPEG สำหรับเว็บ** | เปลี่ยนฟอร์แมตเป็น `BarCodeImageFormat.Jpeg` และตั้งค่า `ImageQuality` ตามต้องการ | JPEG ลดขนาดไฟล์แต่เสียความคมชัดแบบ lossless |
| **รับค่า null หรือค่าว่าง** | ตรวจสอบอินพุตก่อนสร้าง generator: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | ป้องกันข้อยกเว้นขณะรันและทำให้บาร์โค้ดมีความหมาย |

## เคล็ดลับสำหรับการใช้งานในผลิตภัณฑ์

* **การจัดการข้อยกเว้น:** ห่อโลจิกการสร้างในบล็อก `try/catch` เพื่อบันทึกข้อผิดพลาดเช่น พื้นที่ดิสก์ไม่พอหรือพารามิเตอร์ไม่ถูกต้อง  
* **ประสิทธิภาพ:** ใช้ instance ของ `BarcodeGenerator` เพียงตัวเดียวเมื่อสร้างบาร์โค้ดหลายรายการที่มีการตั้งค่าเดียวกัน; เพียงอัปเดตคุณสมบัติ `CodeText` ระหว่างการบันทึก  
* **ความปลอดภัย:** หากข้อความที่เข้ารหัสมีข้อมูลสำคัญ ควรเข้ารหัสก่อนส่งให้ generator และถอดรหัสหลังสแกน  

## สรุป

คุณได้เรียนรู้วิธี **สร้างบาร์โค้ด PDF417** ใน C# ด้วยไลบรารี Aspose.BarCode ตั้งค่าโหมดกะทัดรัด ควบคุมจำนวนคอลัมน์ และส่งออกเป็นภาพ PNG บทแนะนำนี้ครอบคลุมทุกขั้นตอนตั้งแต่การตั้งค่าโครงการจนถึงการจัดการกรณีขอบ ทำให้คุณมีโซลูชันพร้อมใช้งานสำหรับแอปพลิเคชันที่ขับเคลื่อนด้วยบาร์โค้ด

ต่อไปสำรวจหัวข้อที่เกี่ยวข้อง เช่น **การสร้าง QR code ใน C#**, **การสร้างบาร์โค้ดเป็นชุด**, และ **การรวมการสแกนบาร์โค้ดกับแอปมือถือ** ทุกหัวข้ออ้างอิงพื้นฐาน `BarcodeGenerator` ที่คุณเพิ่งเชี่ยวชาญ

Happy coding!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}