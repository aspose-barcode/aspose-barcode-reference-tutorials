---
category: general
date: 2026-10-15
description: สร้าง PNG ของบาร์โค้ดใน C# ด้วยตัวอย่าง PDF417 แบบคอมแพค – เรียนรู้วิธีตั้งค่าคอลัมน์
  ปรับขนาด และสร้างภาพ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: th
lastmod: 2026-10-15
og_description: สร้างบาร์โค้ด PNG ใน C# ด้วยตัวอย่าง PDF417 แบบกะทัดรัด คู่มือนี้แสดงวิธีตั้งค่าคอลัมน์
  ปรับขนาด และบันทึกภาพ
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: สร้างบาร์โค้ด PNG ด้วย C# – การสอนเขียนโปรแกรมอย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: วิธีสร้างบาร์โค้ด PNG ด้วย C# – คู่มือขั้นตอนต่อขั้นตอน
url: /th/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ barcode PNG ด้วย C# – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **สร้างไฟล์ barcode PNG** จากโค้ด C# คู่มือนี้จะแสดงวิธีแก้ปัญหาแบบครบถ้วนในเพียงไม่กี่บรรทัด คุณจะได้เรียนรู้วิธีตั้งค่าคอลัมน์ ปรับขนาดโมดูล และบันทึก barcode PDF417 แบบกะทัดรัดเป็นภาพ PNG – ทั้งหมดในตัวอย่างที่อ่านง่ายเดียว

การสร้าง barcode แบบโปรแกรมมิ่งช่วยขจัดขั้นตอนการใช้โปรแกรมกราฟิกแบบแมนนวล และทำให้คุณสามารถฝัง barcode ลงในใบแจ้งหนี้ ตั๋ว หรือป้ายสินค้าต่าง ๆ ได้โดยตรง ในส่วนต่อไปนี้เราจะครอบคลุมทุกสิ่งที่คุณต้องรู้เกี่ยวกับ **วิธีสร้าง barcode** รูปภาพ ทำไมการตั้งค่าแต่ละอย่างจึงสำคัญ และวิธีปรับโค้ดให้เหมาะกับกรณีการใช้งานต่าง ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้แน่ใจว่าคุณมี:

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+ ด้วย)
* การอ้างอิงไลบรารี barcode ที่รองรับ PDF417 เช่น **Aspose.BarCode for .NET** หรือ **IronBarcode** ตัวอย่างใช้ Aspose.BarCode ซึ่งคุณสามารถติดตั้งผ่าน NuGet:

```bash
dotnet add package Aspose.BarCode
```

* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และ Visual Studio (หรือ IDE ใดก็ได้ที่คุณชอบ)

> **เคล็ดลับ:** หากคุณต้องการทางเลือกฟรี ไลบรารีโอเพ่นซอร์ส **ZXing.Net** ก็รองรับ PDF417 ด้วยเช่นกัน แต่ชื่อคุณสมบัติบางอย่างอาจแตกต่างกันเล็กน้อย แนวคิดที่อธิบายไว้ที่นี่ยังคงเหมือนเดิม

## วิธีสร้าง barcode PNG ด้วย C# (ขั้นตอนหลัก)

หัวใจของวิธีแก้คืออ็อบเจ็กต์ `BarcodeGenerator` ที่กำหนดค่าให้เข้ารหัสแบบ PDF417 ส่วนต่อไปนี้จะแยกอธิบายแต่ละบรรทัดของโค้ด บอก **วิธีตั้งค่าคอลัมน์** และแสดงว่าการตั้งค่าเหล่านี้ส่งผลต่อขนาด PNG อย่างไร

### ขั้นตอน 1: เริ่มต้นตัวสร้าง barcode ด้วยข้อความที่ต้องการ

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*เหตุผลที่สำคัญ*: ค่าคงที่ `EncodeTypes.Pdf417` บอกไลบรารีให้สร้าง barcode แบบสองมิติที่ซ้อนกัน ตัวสร้างยังรับข้อมูลที่คุณต้องการเข้ารหัสด้วย ทำให้ไม่ต้องเรียก `SetData` แยกต่างหาก

### ขั้นตอน 2: ตั้งค่าขนาดโมดูล (X) เป็นพิกเซล

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**มิติ X** ควบคุมความหนาแน่นของภาพ barcode ค่าเล็กลงจะทำให้ภาพกระชับขึ้น ซึ่งเหมาะเมื่อคุณต้องการ PNG ขนาดกะทัดรัดสำหรับหน้าจอมือถือหรือพื้นที่พิมพ์ที่จำกัด

### ขั้นตอน 3: กำหนดจำนวนคอลัมน์สำหรับ barcode PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

บรรทัดนี้แสดง **วิธีตั้งค่าคอลัมน์** PDF417 สามารถเลือกจำนวนคอลัมน์ที่เหมาะสมโดยอัตโนมัติได้ แต่การกำหนดค่าอย่างชัดเจนจะทำให้ความกว้างคาดเดาได้ง่าย โดยเฉพาะเมื่อคุณฝัง PNG ลงในเลย์เอาต์ที่มีขนาดคงที่

### ขั้นตอน 4: เปิดใช้งานโหมดกะทัดรัดโดยตัดส่วนที่ไม่จำเป็นของ barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

เมื่อ `Truncate` เป็น true ไลบรารีจะลบแถวที่ไม่มีข้อมูลออก ทำให้ความสูงของภาพลดลงโดยไม่สูญเสียข้อมูลใด ๆ

### ขั้นตอน 5: บันทึกภาพ barcode เป็น PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียน barcode ลงดิสก์ในรูปแบบที่คุณระบุ PNG เป็นรูปแบบ loss‑less ทำให้เหมาะกับแอปพลิเคชันสแกนที่ต้องการการตรวจจับขอบที่แม่นยำ

### ตัวอย่างเต็มที่สามารถรันได้

รวมทุกอย่างเข้าด้วยกัน นี่คือโปรแกรมอิสระที่คุณสามารถคัดลอก วาง และรันได้:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง** – หลังจากรันโปรแกรม คุณจะพบไฟล์ `CompactPdf417.png` ในโฟลเดอร์ที่ทำงานอยู่ ภาพนี้มี barcode PDF417 แบบสามคอลัมน์ ที่กะทัดรัดพอที่จะพอดีกับป้ายขนาด 2 × 2 ซม. มาตรฐาน พร้อมยังคงสแกนได้เต็มที่

![ตัวอย่างการสร้าง barcode PNG](placeholder.png){alt="สร้าง barcode PNG ด้วย C#"}

## วิธีตั้งค่าคอลัมน์สำหรับขนาดข้อมูลที่ต่างกัน (คีย์เวิร์ดรอง)

จำนวนคอลัมน์มีผลต่อความกว้างและความอ่านง่ายของ barcode:

| คอลัมน์ | ความกว้างโดยประมาณ (px) | กรณีใช้งานทั่วไป |
|--------|-------------------|------------------|
| 1‑2    | แคบ, สูง          | ป้ายเล็ก, พิมพ์แบบ RFID‑like |
| 3‑5    | สมดุล             | ป้ายใช้งานทั่วไป |
| 6‑9    | กว้าง, ต่ำ        | โปสเตอร์ขนาดใหญ่หรือบรรจุภัณฑ์ |

หากสตริงข้อมูลของคุณยาวขึ้น ไลบรารีอาจเพิ่มจำนวนแถวโดยอัตโนมัติเพื่อให้ barcode อยู่ในขอบเขตคอลัมน์ที่กำหนด อย่างไรก็ตาม การบังคับให้คอลัมน์ต่ำเกินไปอาจทำให้ barcode สูงเกินไปและอาจไม่พอดีกับเครื่องพิมพ์ใบเสร็จ ปรับจำนวนคอลัมน์ตามข้อจำกัดทางกายภาพของสื่อที่คุณจะส่งออก

## วิธีสร้างภาพ barcode ในรูปแบบอื่น ๆ (คีย์เวิร์ดรอง)

แม้ PNG จะเป็นรูปแบบที่นิยมที่สุดสำหรับเว็บและมือถือ คุณอาจต้องการ **วิธีสร้าง barcode** ใน JPEG, BMP หรือ SVG สำหรับกระบวนการทำงานเฉพาะด้าน:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

การเลือกรูปแบบที่เหมาะสมขึ้นอยู่กับผู้รับผลลัพธ์ต่อไป:

* **PNG** – lossless, เหมาะสำหรับสแกนเนอร์
* **JPEG** – ขนาดไฟล์เล็กลง, ยอมรับได้เมื่อรับมือกับการบีบอัดเล็กน้อย
* **SVG** – เหมาะสำหรับการพิมพ์ความละเอียดสูงหรือการปรับขนาด UI

## ตัวอย่าง C# barcode: การจัดการข้อผิดพลาดและกรณีขอบ

ตัวอย่าง **c# barcode** ที่แข็งแรงควรคาดการณ์ปัญหาในขณะรัน:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*ทำไมต้องห่อด้วย `try/catch`?* ตัวอักษรที่ไม่ถูกต้องในข้อความ, มิติที่ไม่รองรับ, หรือปัญหาการเขียนไฟล์จะทำให้เกิดข้อยกเว้น การจัดการอย่างเหมาะสมช่วยป้องกันแอปพลิเคชันของคุณจากการหยุดทำงานระหว่างการประมวลผลเป็นชุด

## การขยายตัวอย่าง: เพิ่มโลโก้หรือพื้นหลัง

หลายกรณีในโลกจริงต้องการการวางโลโก้เหนือ barcode หรือพื้นหลังสี ไลบรารี Aspose.BarCode API ให้คุณผสาน barcode กับ bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

เทคนิคนี้ทำให้ **workflow การสร้าง barcode PNG** ยังคงอยู่ในสภาพเดิม พร้อมเพิ่มแบรนด์ภาพสุดท้ายให้ดูเป็นมืออาชีพ

## สรุป

ในคู่มือนี้เราได้สาธิต **วิธีสร้างไฟล์ barcode PNG** ด้วย C# โดยใช้การตั้งค่า PDF417 แบบกะทัดรัด คุณได้เรียนรู้:

* โค้ดที่จำเป็นสำหรับการเริ่มต้น `BarcodeGenerator`
* **วิธีตั้งค่าคอลัมน์** และเหตุผลที่จำนวนคอลัมน์สำคัญต่อขนาดและความอ่านง่าย
* วิธีปรับมิติ X และเปิดใช้งานการตัดส่วนเพื่อให้ PNG กระชับยิ่งขึ้น
* วิธีบันทึกภาพในรูปแบบ PNG, JPEG หรือ SVG
* รูปแบบการจัดการข้อผิดพลาดสำหรับ **c# barcode example** ที่พร้อมใช้งานในสภาพแวดล้อมการผลิต
* การขยายเพิ่มเติมเช่นการใส่โลโก้และการปรับพื้นหลัง

ตอนนี้คุณมีโค้ดสั้น ๆ ที่พร้อมรันและสามารถนำไปผสานกับระบบสร้างใบแจ้งหนี้ ระบบตั๋ว หรือเครื่องมือจัดการสินค้าคงคลังของคุณ ทดลองเปลี่ยนค่าคอลัมน์, ขนาดโมดูล หรือประเภท barcode (เช่น QR, Code128) เพื่อดูผลลัพธ์ที่แตกต่าง

## ขั้นตอนต่อไป

* สำรวจประเภทการเข้ารหัสอื่น ๆ (`EncodeTypes.QR`, `EncodeTypes.Code128`) เพื่อรองรับกรณีการใช้งานที่หลากหลาย
* ผสานการสร้าง barcode กับไลบรารีสร้าง PDF (เช่น **iTextSharp**) เพื่อฝัง PNG ลงในเอกสารโดยตรง
* ศึกษาการคำนวณขนาดแบบไดนามิก: คำนวณจำนวนคอลัมน์ที่เหมาะสมตามความยาวของสตริงอินพุตและขนาดป้ายเป้าหมาย

ขอให้สนุกกับการเขียนโค้ดและเพลิดเพลินกับความง่ายของการสร้าง barcode PNG ที่คมชัดแบบโปรแกรมมิ่งใน C#!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบต่าง ๆ ในโปรเจกต์ของคุณ

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}