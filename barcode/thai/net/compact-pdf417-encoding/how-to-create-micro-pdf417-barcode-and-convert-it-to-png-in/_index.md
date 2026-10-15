---
category: general
date: 2026-10-12
description: เรียนรู้การสร้างบาร์โค้ด micro PDF417 และแปลงบาร์โค้ดเป็น PNG ด้วย C#
  คู่มือขั้นตอนโดยละเอียดพร้อมโค้ดเต็มและเคล็ดลับ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: th
lastmod: 2026-10-12
og_description: สร้างบาร์โค้ด micro PDF417 และแปลงบาร์โค้ดเป็น PNG ด้วย C# ปฏิบัติตามคู่มือฉบับเต็มนี้เพื่อสร้างทั้งเวอร์ชันมาตรฐานและ
  GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: สร้างบาร์โค้ด micro PDF417 และแปลงเป็น PNG – บทเรียน C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: วิธีสร้างบาร์โค้ด micro PDF417 และแปลงเป็น PNG ใน C#
url: /th/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง micro PDF417 barcode และแปลงเป็น PNG ใน C#

หากคุณต้องการ **สร้าง micro PDF417 barcode** ในแอปพลิเคชัน .NET นี้ การสอนนี้จะแสดงให้คุณเห็นอย่างละเอียด คุณจะได้เห็นตัวอย่างที่ทำงานได้เต็มรูปแบบซึ่งสร้างทั้งบาร์โค้ด Micro PDF417 มาตรฐานและเวอร์ชันที่สอดคล้องกับ GS1 แล้ว **แปลงบาร์โค้ดเป็น PNG** เพื่อใช้ต่อในงานเช่นการพิมพ์หรือแสดงบนเว็บ

การสร้างบาร์โค้ดเป็นมากกว่าการเรียกเมธอดเดียว—การเลือกขนาดโมดูล จำนวนคอลัมน์ และรูปแบบการเข้ารหัสที่เหมาะสมจะกำหนดความน่าเชื่อถือของการสแกนได้ ในตอนท้ายของคู่มือนี้คุณจะเข้าใจว่าทำไมการตั้งค่าแต่ละอย่างจึงสำคัญและจะปรับใช้ได้อย่างไรในโครงการของคุณเอง

## ความต้องการเบื้องต้น

| ข้อกำหนด | เหตุผล |
|-------------|--------|
| .NET 6.0 SDK or later | ให้ runtime สำหรับแอปคอนโซล C# |
| Visual Studio 2022 (or any C# IDE) | ทำให้การแก้ไขและดีบักง่ายขึ้น |
| **Aspose.BarCode for .NET** NuGet package | จัดหาคลาส `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat` |
| Write permission to the output folder | จำเป็นสำหรับการเรียก `Save` ที่สร้างไฟล์ PNG |

คุณสามารถเพิ่มแพ็กเกจ Aspose.BarCode ผ่าน CLI ได้ดังนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการคอนโซลแบบขั้นต่ำ

สร้างโครงการคอนโซลใหม่และอ้างอิงไลบรารีบาร์โค้ด โค้ด `Program.cs` ด้านล่างนี้มีทั้งหมดที่คุณต้องการ; ไม่ต้องใช้ไฟล์ภายนอกใด ๆ

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### ทำไมแต่ละบรรทัดจึงสำคัญ

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – ตัวแรกสร้างบาร์โค้ด Micro PDF417 ธรรมดา ส่วนตัวที่สองสอดคล้องกับมาตรฐาน GS1 โดยฝัง Application Identifiers (AIs) เลือกใช้ตามว่าระบบต่อไปของคุณต้องการข้อมูล GS1 หรือไม่  
* **`XDimension.Pixels = 2`** – ควบคุมความกว้างของโมดูล ค่าเล็กจะทำให้ภาพหนาแน่นมากขึ้นแต่บางครั้งอาจอ่านไม่ได้บนสแกนเนอร์ความละเอียดต่ำ พิกเซลสองจุดเป็นค่าเริ่มต้นที่ปลอดภัยสำหรับเครื่องพิมพ์ฉลากส่วนใหญ่  
* **`Pdf417.Columns = 4`** – Micro PDF417 อนุญาตให้จำกัดจำนวนคอลัมน์ เพื่อลดความกว้างโดยรวม คอลัมน์สี่คอลัมน์ทำให้บาร์โค้ดกระชับโดยไม่สูญเสียความจุข้อมูลสำหรับ payload สั้น ๆ  
* **`BarCodeImageFormat.Png`** – PNG รักษาคุณภาพ lossless ซึ่งจำเป็นสำหรับความคมชัดของบาร์โค้ด นั่นคือเหตุผลที่เราต้อง **แปลงบาร์โค้ดเป็น PNG** แทนการใช้ JPEG  

## ขั้นตอนที่ 2: รันโปรแกรมและตรวจสอบผลลัพธ์

1. Build the project: `dotnet build`.  
2. Execute: `dotnet run`.

คุณควรเห็นข้อความคอนโซลที่คล้ายกับ:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

เปิดไฟล์ PNG ที่สร้างขึ้นด้วยโปรแกรมดูรูปภาพใด ๆ ทั้งสองภาพจะแสดงบาร์โค้ดที่คมชัดและคอนทราสต์สูงพร้อมสแกน

### ผลลัพธ์ภาพที่คาดหวัง

| ประเภทบาร์โค้ด | ลักษณะ |
|--------------|------------|
| **Micro PDF417** | รูปแบบสี่เหลี่ยมเล็ก ๆ ที่มี 4 คอลัมน์ สามารถอ่านได้โดยสแกนเนอร์ 2‑D ส่วนใหญ่ |
| **GS1 Micro PDF417** | ขนาดเดียวกันแต่เข้ารหัส GS1 AI; สแกนเนอร์ที่รองรับ GS1 จะคืนค่า GTIN และหมายเลขซีเรียล |

หากสแกนเนอร์ไม่สามารถอ่านภาพได้ ให้ลองเพิ่มค่า `XDimension.Pixels` เป็น **3** หรือ **4** หรือ ลดจำนวนคอลัมน์สำหรับ Micro PDF417 มาตรฐาน

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| บาร์โค้ดเบลอหลังการพิมพ์ | การตั้งค่าพรินเตอร์ DPI ต่ำ | ส่งออก PNG ที่ 300 dpi หรือสูงกว่า หรือให้ไดรเวอร์พรินเตอร์จัดการการสเกล |
| สแกนเนอร์คืนค่า “invalid data” | รูปแบบ GS1 AI ขาดหายหรือผิดรูปแบบ | ตรวจสอบให้แน่ใจว่า AI ทุกตัวอยู่ในวงเล็บและเป็นไปตามสเปค GS1 (เช่น `(01)` สำหรับ GTIN‑14) |
| ไฟล์ภาพไม่ถูกสร้าง | โฟลเดอร์ปลายทางไม่มีสิทธิ์เขียน | รันโปรแกรมด้วยสิทธิ์ระดับสูงหรือเลือกโฟลเดอร์เช่น `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` |
| บาร์โค้ดใหญ่เกินขนาดป้าย | จำนวนคอลัมน์เริ่มต้นสูงเกินไป | ลด `Pdf417.Columns` (เช่นเป็น **3**) หรือเพิ่ม `XDimension` เพื่อลดขนาดโดยรวม |

## การขยายตัวอย่าง

* **Different image formats** – แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg` หรือ `Bmp` หากเวิร์กโฟลว์ของคุณต้องการ PNG ยังคงเป็นตัวเลือกที่ดีที่สุดสำหรับคุณภาพ lossless  
* **Dynamic data** – ส่งค่าที่รับจากผู้ใช้หรือฐานข้อมูลไปยังคอนสตรัคเตอร์ `BarcodeGenerator` เพื่อสร้างบาร์โค้ดแบบเรียลไทม์  
* **Batch generation** – ห่อโลจิกการสร้างในลูปที่อ่านแถวจากไฟล์ CSV แล้วบันทึกบาร์โค้ดแต่ละอันด้วยชื่อไฟล์ที่ไม่ซ้ำกัน  

## สรุป

คุณตอนนี้รู้วิธี **สร้าง micro PDF417 barcode** ใน C# และ **แปลงบาร์โค้ดเป็น PNG** สำหรับทั้งกรณีมาตรฐานและที่สอดคล้องกับ GS1 โค้ดเต็มที่ทำงานได้แสดงการตั้งค่าที่สำคัญ—X dimension, column count, และ encoding type—เพื่อให้คุณปรับใช้กับโครงการ .NET ใด ๆ ที่ต้องการบาร์โค้ด 2‑D ขนาดกะทัดรัดและคุณภาพสูง

*ขั้นตอนต่อไป*: สำรวจสัญลักษณ์อื่น ๆ ที่ Aspose.BarCode รองรับ (เช่น QR, DataMatrix) ทดลองค่า `XDimension` ต่าง ๆ สำหรับการพิมพ์ความละเอียดสูง หรือรวม PNG ที่สร้างขึ้นเข้าไปใน Web API ที่ให้บริการบาร์โค้ดตามความต้องการ

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณ

- [วิธีสร้าง micro pdf417 barcode ใน C# และบันทึกเป็น PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [สร้าง PNG ของบาร์โค้ดใน C# – คู่มือเต็มสำหรับ GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [สร้าง Micro PDF417 Barcode ใน C# – คู่มือเต็ม](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}