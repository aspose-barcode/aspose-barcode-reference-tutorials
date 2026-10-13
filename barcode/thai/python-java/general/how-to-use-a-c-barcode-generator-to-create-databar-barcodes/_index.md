---
category: general
date: 2026-10-02
description: เรียนรู้วิธีตั้งค่าคอลัมน์และแถวในตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด
  DataBar คู่มือแบบขั้นตอนพร้อมโค้ดเต็ม
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: th
lastmod: 2026-10-02
og_description: คู่มือการสร้างบาร์โค้ดด้วย C# – เรียนรู้วิธีตั้งค่าคอลัมน์และแถวเพื่อสร้างบาร์โค้ด
  DataBar พร้อมตัวอย่างโค้ดเต็ม
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'ตัวสร้างบาร์โค้ด C#: ตั้งค่าคอลัมน์และแถวสำหรับบาร์โค้ด DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: วิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด DataBar ด้วยคอลัมน์และแถวที่กำหนดเอง
url: /th/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ C# barcode generator เพื่อสร้างบาร์โค้ด DataBar ด้วยคอลัมน์และแถวที่กำหนดเอง

หากคุณต้องการ **c# barcode generator** ที่สามารถสร้างบาร์โค้ด DataBar พร้อมการกำหนดคอลัมน์และแถวที่แม่นยำ บทแนะนำนี้จะแสดงให้คุณเห็นอย่างละเอียด คุณจะเข้าใจว่าการปรับคอลัมน์และแถวมีความสำคัญอย่างไร และจะได้รับตัวอย่างที่พร้อมรันครบถ้วนซึ่งสร้างบาร์โค้ด DataBar Expanded Stacked ทั้งแบบ 4 คอลัมน์และ 3 แถว

ในส่วนต่อไปนี้เราจะครอบคลุม:

* ข้อกำหนดเบื้องต้นสำหรับการใช้ไลบรารี Aspose.BarCode for .NET
* วิธีตั้งค่าคอลัมน์ (`how to set columns`) และแถว (`how to set rows`) บนบาร์โค้ด DataBar
* โปรแกรมคอนโซล C# เต็มรูปแบบที่คุณสามารถคัดลอก, คอมไพล์, และรันได้
* ไฟล์ผลลัพธ์ที่คาดหวังและเคล็ดลับการแก้ไขปัญหา

เมื่อจบคู่มือคุณจะสามารถ **create databar barcode** ภาพที่ปรับให้ตรงกับความต้องการของการจัดวางได้

## Prerequisites

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

| ข้อกำหนด | เหตุผล |
|-------------|--------|
| .NET 6.0 SDK หรือใหม่กว่า | ให้ runtime สำหรับโค้ด C# |
| Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET) | ทำให้การสร้างโปรเจกต์และการดีบักง่ายขึ้น |
| Aspose.BarCode for .NET NuGet package | จัดหา class `BarcodeGenerator` ที่ใช้ในตัวอย่าง |
| สิทธิ์การเขียนในโฟลเดอร์สำหรับไฟล์ PNG ผลลัพธ์ | ตัวสร้างจะบันทึกรูปบาร์โค้ดลงดิสก์ |

ติดตั้งแพคเกจ Aspose.BarCode ด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a basic DataBar Expanded Stacked barcode

ขั้นตอนแรกคือการสร้าง **c# barcode generator** ด้วยรูปแบบ `EncodeTypes.DatabarExpandedStacked` รูปแบบนี้เป็นบาร์โค้ด DataBar สองมิติที่สามารถเข้ารหัสได้สูงสุด 74 ตัวอักษรเชิงตัวเลข

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

คอนสตรัคเตอร์รับอาร์กิวเมนต์สองค่า:

* `EncodeTypes.DatabarExpandedStacked` – บอกไลบรารีว่าจะใช้สัญลักษณ์ใด
* `"Databar Expanded Stacked long"` – ข้อความที่จะถูกเข้ารหัส

## Step 2: How to set columns

คอลัมน์มีผลต่อความหนาแน่นในแนวนอนของบาร์โค้ด DataBar การเพิ่มจำนวนคอลัมน์ทำให้บาร์โค้ดกว้างขึ้น ซึ่งอาจช่วยเพิ่มความน่าเชื่อถือในการสแกนบนเครื่องพิมพ์ความละเอียดต่ำ

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**ทำไมต้อง 4 คอลัมน์?**  
สี่คอลัมน์ให้สมดุลที่ดีระหว่างขนาดและความอ่านได้สำหรับแอปพลิเคชันค้าปลีกส่วนใหญ่ คุณสามารถทดลองค่าตั้งแต่ 1 ถึง 8; ไลบรารีจะปรับความกว้างของโมดูลโดยอัตโนมัติ

## Step 3: Save the column‑configured barcode

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

ภาพจะถูกบันทึกเป็นไฟล์ PNG ซึ่งรักษาขอบคมที่จำเป็นสำหรับสแกนเนอร์บาร์โค้ด

## Step 4: Create a separate generator for row configuration

การกำหนดค่าแถวทำงานในลักษณะเดียวกันแต่ส่งผลต่อความหนาแน่นในแนวตั้ง เพื่อหลีกเลี่ยงการผสมค่าคอลัมน์และแถว เราจะสร้างอินสแตนซ์ generator ใหม่

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: How to set rows

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**เมื่อใดควรใช้แถวเพิ่ม?**  
การเพิ่มแถวทำให้บาร์โค้ดสูงขึ้น ซึ่งมีประโยชน์เมื่อพื้นที่พิมพ์แนวนอนจำกัดแต่มีความสูงเพียงพอ (เช่น ป้ายสินค้าที่สูงกว่ากว้าง)

## Step 6: Save the row‑configured barcode

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

ไฟล์ PNG ทั้งสอง (`DatabarCols4.png` และ `DatabarRows3.png`) จะปรากฏในโฟลเดอร์ `C:\Barcodes`

## Full, runnable example

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่รวมทุกขั้นตอนที่อธิบายไว้ คัดลอกโค้ดไปยังโปรเจกต์ .NET คอนโซลใหม่และรันได้เลย

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### What the code does

| ส่วน | วัตถุประสงค์ |
|---------|---------|
| **Namespace imports** | ดึง `Aspose.BarCode` และ `Aspose.BarCode.Generation` เข้ามา |
| **Output directory** | รวมพาธไว้ที่เดียวเพื่อให้แก้ไขได้เพียงบรรทัดเดียวหากย้ายโฟลเดอร์ |
| **Column generator** | แสดง **how to set columns** บน `c# barcode generator` |
| **Row generator** | แสดง **how to set rows** บน `c# barcode generator` |
| **Save calls** | เขียนไฟล์ PNG ลงดิสก์ ทำให้พร้อมสแกนหรือใส่ในรายงาน |
| **Console output** | ให้ฟีดแบ็กทันที มีประโยชน์ระหว่างการพัฒนา |

## Expected output

หลังจากรันโปรแกรม คุณควรเห็นไฟล์ PNG สองไฟล์:

* **DatabarCols4.png** – บาร์โค้ดที่กว้างกว่า แสดงผลเป็นสี่คอลัมน์
* **DatabarRows3.png** – บาร์โค้ดที่สูงกว่า แสดงผลเป็นสามแถว

ทั้งสองภาพมีข้อความ *“Databar Expanded Stacked long”* เข้ารหัสในสัญลักษณ์ DataBar Expanded Stacked คุณสามารถเปิดดูด้วยโปรแกรมดูภาพใดก็ได้หรือส่งให้สแกนเนอร์บาร์โค้ดเพื่อตรวจสอบความอ่านได้

## Common pitfalls and how to avoid them

| ปัญหา | เหตุผล | วิธีแก้ |
|-------|--------|-----|
| **File‑access exception** | โฟลเดอร์ผลลัพธ์ไม่มีอยู่หรือคุณไม่มีสิทธิ์เขียน | สร้างโฟลเดอร์ด้วยตนเองหรือรันโปรแกรมด้วยสิทธิ์ผู้ดูแล |
| **Incorrect column/row values** | ไลบรารีรับค่าได้แค่ 1‑8 สำหรับคอลัมน์และ 1‑4 สำหรับแถว | ตรวจสอบค่าก่อนกำหนด เช่น `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();` |
| **Barcode not scanning** | ภาพที่สร้างมีขนาดเล็กเกินกว่าความละเอียดของสแกนเนอร์ | เพิ่ม `ImageHeight` หรือ `ImageWidth` ผ่าน `generator.Parameters.Image.Height` / `...Width` |
| **Text truncation** | ข้อความที่เข้ารหัสยาวเกินกว่าความจุสูงสุดของ DataBar แบบนี้ | ใช้ข้อความสั้นลงหรือสลับไปใช้ `EncodeTypes.DatabarExpanded` หากต้องการความจุมากกว่า |

## Pro tips

* **Cache the generator** – หากต้องสร้างบาร์โค้ดหลายรายการที่ใช้คอลัมน์/แถวเดียวกัน ให้ใช้ instance `BarcodeGenerator` เดียวและเปลี่ยนเฉพาะ property `CodeText` เท่านั้น
* **Batch processing** – วนลูปผ่านคอลเลกชันของรหัสสินค้า ตั้งค่า `generator.CodeText` ภายในลูปและเรียก `Save` ด้วยชื่อไฟล์ที่ไม่ซ้ำกันในแต่ละรอบ
* **Performance** – สำหรับสถานการณ์ที่ต้องสร้างจำนวนมาก ให้ปิด anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) เพื่อเร่งการสร้างภาพโดยไม่กระทบคุณภาพการสแกน

## Next steps

ตอนนี้คุณรู้ **how to set columns** และ **how to set rows** ด้วย **c# barcode generator** แล้ว อาจอยากสำรวจต่อ:

* **เพิ่มข้อความที่อ่านได้โดยมนุษย์** ใต้บาร์โค้ด (`generator.Parameters.Barcode.CodeTextLocation`)
* **เปลี่ยนสี** (`generator.Parameters.Image.ForegroundColor` และ `BackgroundColor`)
* **สร้าง DataBar variant อื่น ๆ** เช่น `DatabarLimited` หรือ `DatabarExpanded`
* **ฝังบาร์โค้ดในรายงาน PDF** ด้วย Aspose.PDF

หัวข้อเหล่านี้ต่อยอดจากพื้นฐานที่อธิบายไว้ที่นี่และช่วยให้คุณสร้างโซลูชันบาร์โค้ดที่พร้อมใช้งานในระดับการผลิต

---

*Happy coding! If you run into any issues, feel free to leave a comment or check the Aspose.BarCode documentation for deeper API details.*

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set barcode columns and rows with C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}