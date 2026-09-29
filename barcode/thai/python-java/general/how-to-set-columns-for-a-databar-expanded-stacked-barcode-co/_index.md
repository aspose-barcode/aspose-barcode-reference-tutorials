---
category: general
date: 2026-08-06
description: วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked และเรียนรู้วิธีสร้างภาพบาร์โค้ด
  ตั้งค่าแถว และบันทึกไฟล์บาร์โค้ดด้วย C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set columns
- how to generate barcode
- how to set rows
- barcode save file
language: th
lastmod: 2026-08-06
og_description: วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked และเรียนรู้วิธีสร้างภาพบาร์โค้ดอย่างรวดเร็ว
  ตั้งค่าแถว และบันทึกไฟล์บาร์โค้ดด้วย Aspose.Barcode.
og_image_alt: Screenshot showing how to set columns for a Databar Expanded Stacked
  barcode in C#
og_title: วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked – คู่มือ C# ทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set columns for a Databar Expanded Stacked barcode and learn
    how to generate barcode images, set rows, and save the barcode file in C#.
  headline: How to set columns for a Databar Expanded Stacked barcode – complete C#
    guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked – คู่มือ C# ฉบับสมบูรณ์
url: /th/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked – คู่มือ C# ฉบับสมบูรณ์

หากคุณต้องการ **วิธีตั้งค่าคอลัมน์** สำหรับบาร์โค้ด Databar Expanded Stacked, บทแนะนำนี้จะแสดงขั้นตอนที่แน่นอน ไม่ว่าคุณจะกำลังสร้างระบบติดฉลากสำหรับร้านค้าปลีกหรือแอปพลิเคชันโลจิสติกส์ การควบคุมคอลัมน์และแถวจะช่วยให้คุณปรับขนาดบาร์โค้ดและความน่าเชื่อถือในการสแกนได้อย่างละเอียด นอกจากนี้คุณยังจะได้เห็น **วิธีสร้างภาพบาร์โค้ด**, ปรับจำนวนแถว, และ **บันทึกไฟล์บาร์โค้ด** ไปยังดิสก์อย่างถูกต้อง

คู่มือนี้จะพาคุณผ่าน:

* การติดตั้งไลบรารี Aspose.Barcode สำหรับ .NET  
* การสร้างตัวสร้างบาร์โค้ดสำหรับประเภท Databar Expanded Stacked  
* การตั้งค่าจำนวนคอลัมน์, จำนวนแถว, และรูปแบบภาพ  
* การบันทึกไฟล์ PNG ที่ได้ไปยังไดเรกทอรีที่เลือก  

ไม่จำเป็นต้องมีประสบการณ์กับ Aspose.Barcode มาก่อน—เพียงแค่มีสภาพแวดล้อมการพัฒนา C# พื้นฐาน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน, ตรวจสอบให้แน่ใจว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)  
* การอ้างอิง NuGet ไปยัง **Aspose.Barcode** (`dotnet add package Aspose.Barcode`)  

โค้ดทั้งหมดสามารถคอมไพล์ได้ด้วยเทมเพลตโปรเจกต์คอนโซลเริ่มต้น

## ขั้นตอนที่ 1: สร้างตัวสร้างบาร์โค้ดสำหรับ Databar Expanded Stacked

การดำเนินการแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วย enum `EncodeTypes.DatabarExpandedStacked` ซึ่งจะตั้งค่าเลเอาต์เริ่มต้น (stacked) และเตรียมอ็อบเจกต์สำหรับการกำหนดค่าต่อไป

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the Databar Expanded Stacked type.
        // The text "Databar Expanded Stacked long" is the data encoded in the barcode.
        BarcodeGenerator barcodeGeneratorCols = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

**ทำไมเรื่องนี้สำคัญ:** ตัวสร้างบาร์โค้ดจะเก็บพารามิเตอร์การเรนเดอร์ทั้งหมด การเลือก `DatabarExpandedStacked` จะบอกไลบรารีให้ใช้เลเอาต์แบบ stacked ซึ่งเป็นเลเอาต์เดียวที่รองรับการปรับคอลัมน์และแถว

## วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked

เมื่อมีตัวสร้างแล้ว, คุณสามารถควบคุมจำนวนคอลัมน์ได้ คุณสมบัติ `DataBar.Columns` รับค่าเต็มระหว่าง 1 ถึง 4 การตั้งค่าเป็น **4** จะสร้างบาร์โค้ดที่กว้างที่สุดที่ยังคงอยู่ในเลเอาต์ stacked

```csharp
        // Step 2: Configure the generator to use 4 columns.
        barcodeGeneratorCols.Parameters.Barcode.DataBar.Columns = 4;
```

**เคล็ดลับปฏิบัติ:** ใช้จำนวนคอลัมน์สูงสุดเฉพาะเมื่อคุณมีพื้นที่สีขาวเพียงพอบนฉลาก การมีคอลัมน์มากเกินไปบนฉลากขนาดเล็กอาจทำให้การสแกนล้มเหลว

## วิธีสร้างภาพบาร์โค้ดและบันทึกลงไฟล์

หลังจากกำหนดค่าคอลัมน์แล้ว, คุณต้องเรนเดอร์บาร์โค้ดและเขียนภาพลงดิสก์ วิธี `Save` รับพาธไฟล์และ enum รูปแบบภาพ

```csharp
        // Step 3: Save the barcode image as PNG.
        barcodeGeneratorCols.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
```

โฟลเดอร์ `output` ต้องมีอยู่แล้ว มิฉะนั้นคำสั่งจะโยนข้อยกเว้น คุณสามารถสร้างโฟลเดอร์นี้โดยโปรแกรมด้วย `Directory.CreateDirectory("output");` หากต้องการ

## วิธีตั้งค่าแถวสำหรับบาร์โค้ด Databar Expanded Stacked

แถวทำงานคล้ายกับคอลัมน์ แต่จะส่งผลต่อการจัดเรียงแนวตั้งของโมดูลบาร์โค้ด คุณสมบัติ `DataBar.Rows` รับค่าตั้งแต่ 1 ถึง 5 ในตัวอย่างนี้เราใช้ **3** แถว

```csharp
        // Step 4: Create a second generator for the same barcode type.
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the generator to use 3 rows.
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        // Step 6: Save the row‑adjusted barcode.
        barcodeGeneratorRows.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมแถวถึงสำคัญ:** การเพิ่มแถวจะทำให้ความสูงของบาร์โค้ดเพิ่มขึ้น ซึ่งเป็นประโยชน์สำหรับฉลากความหนาแน่นสูงที่ต้องการโมดูลข้อมูลมากขึ้นโดยไม่ต้องทำให้บาร์โค้ดกว้างขึ้น

## ตัวเลือกการบันทึกไฟล์บาร์โค้ดและแนวทางปฏิบัติที่ดีที่สุด

วิธี `Save` รองรับหลายรูปแบบภาพ (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`) PNG เป็นแบบ lossless และทำงานได้ดีกับอุปกรณ์สแกนส่วนใหญ่ หากคุณต้องการไฟล์ขนาดเล็กกว่าและยอมรับการบีบอัดเล็กน้อย ให้เลือก JPEG:

```csharp
barcodeGeneratorCols.Save("output/DatabarCols4.jpg", BarCodeImageFormat.Jpeg);
```

**กรณีขอบ:** เมื่อบันทึกเป็น JPEG, ตรวจสอบให้แน่ใจว่าพารามิเตอร์คุณภาพตั้งค่าอย่างเหมาะสม (ค่าเริ่มต้นคือ 90) คุณภาพต่ำอาจทำให้โมดูลเล็ก ๆ เบลอและทำให้บาร์โค้ดอ่านไม่ได้

## ตัวอย่างสมบูรณ์ที่สามารถรันได้

รวมทุกอย่างเข้าด้วยกัน, นี่คือไฟล์เดียวที่คุณสามารถคัดลอกไปยังโปรเจกต์คอนโซลใหม่และรันได้ทันที:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists.
        Directory.CreateDirectory("output");

        // ------------------------------
        // How to set columns (4 columns)
        // ------------------------------
        BarcodeGenerator colsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        colsGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colsGenerator.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to output/DatabarCols4.png");

        // ------------------------------
        // How to set rows (3 rows)
        // ------------------------------
        BarcodeGenerator rowsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowsGenerator.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to output/DatabarRows3.png");

        // ------------------------------
        // How to generate barcode (additional format)
        // ------------------------------
        rowsGenerator.Save("output/DatabarRows3.jpg", BarCodeImageFormat.Jpeg);
        Console.WriteLine("Saved JPEG version to output/DatabarRows3.jpg");
    }
}
```

**ผลลัพธ์ที่คาดหวัง:** หลังจากรันโปรแกรม, โฟลเดอร์ `output` จะมีไฟล์สามไฟล์:

* `DatabarCols4.png` – บาร์โค้ดที่มี 4 คอลัมน์ (กว้าง)  
* `DatabarRows3.png` – บาร์โค้ดที่มี 3 แถว (สูง)  
* `DatabarRows3.jpg` – เวอร์ชัน JPEG ของบาร์โค้ด 3 แถว

เปิดไฟล์ PNG ใดไฟล์หนึ่งในโปรแกรมดูภาพ; คุณควรเห็นบาร์โค้ด Databar Expanded Stacked ที่ชัดเจนพร้อมสแกน

## คำถามที่พบบ่อยและการแก้ไขปัญหา

| Question | Answer |
|----------|--------|
| *What if the image is blurry?* | Verify you are using PNG for lossless output. If you need JPEG, increase the quality setting (`new JpegOptions { Quality = 95 }`). |
| *Can I change the barcode text?* | Yes—replace the second argument in `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Your Text")`. |
| *Do columns and rows work together?* | They can be combined; just set both `DataBar.Columns` and `DataBar.Rows` before calling `Save`. |
| *Is there a limit on directory depth?* | The path must be valid for the operating system. Use `Path.Combine` for cross‑platform safety. |

## สรุป

คุณได้เรียนรู้ **วิธีตั้งค่าคอลัมน์** สำหรับบาร์โค้ด Databar Expanded Stacked, **วิธีตั้งค่าแถว**, และ **วิธีสร้างภาพบาร์โค้ด** ที่สามารถ **บันทึกไฟล์บาร์โค้ด** ในรูปแบบ PNG หรือ JPEG ตัวอย่างสมบูรณ์แสดงขั้นตอนทั้งหมด ตั้งแต่การติดตั้งไลบรารีจนถึงการตรวจสอบไฟล์สุดท้าย

ต่อไป, ลองสำรวจ:

* **how to generate barcode** with error correction levels for QR codes.  
* **barcode save file** options for vector formats like SVG or PDF.  
* การรวมบาร์โค้ดที่สร้างขึ้นกับมุมมอง ASP.NET Core MVC เพื่อพิมพ์ฉลากแบบไดนามิก

อย่ากลัวที่จะทดลองผสมคอลัมน์/แถว, รูปแบบภาพ, และเนื้อหาบาร์โค้ดต่าง ๆ เพื่อให้ตรงกับสเปคของโครงการคุณ ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโปรเจกต์ของคุณเอง

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}