---
category: general
date: 2026-08-19
description: บทเรียนการสร้างบาร์โค้ดด้วย C# แสดงวิธีสร้างบาร์โค้ด DataBar Expanded
  Stacked ปรับขนาดบาร์โค้ด และกำหนดแถวและคอลัมน์
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: th
lastmod: 2026-08-19
og_description: บทเรียนการสร้างบาร์โค้ดด้วย C# สอนวิธีสร้างบาร์โค้ด DataBar ปรับขนาดตามต้องการ
  และกำหนดแถวและคอลัมน์เพื่อผลลัพธ์ที่แม่นยำ
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: ตัวสร้างบาร์โค้ด C# – คู่มือขั้นตอนต่อขั้นตอนสำหรับบาร์โค้ด DataBar แบบกำหนดเอง
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'ตัวสร้างบาร์โค้ด C#: สร้างบาร์โค้ด DataBar แบบกำหนดเอง'
url: /th/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวสร้างบาร์โค้ด C#: สร้างบาร์โค้ด DataBar แบบกำหนดเอง

หากคุณต้องการ **c# barcode generator** ที่สามารถสร้างสัญลักษณ์ DataBar Expanded Stacked ได้ คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่า如何สร้างภาพบาร์โค้ดด้วยแถวและคอลัมน์ที่กำหนดเอง คุณจะได้เรียนรู้การกำหนดค่าพารามิเตอร์ databar, ปรับขนาดบาร์โค้ด, และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ดโดยโปรแกรมช่วยขจัดขั้นตอนการออกแบบด้วยมือและรับประกันผลลัพธ์ที่สม่ำเสมอข้ามแพลตฟอร์ม ในบทเรียนนี้คุณจะได้ทำ:

* ติดตั้งและอ้างอิงไลบรารี Aspose.BarCode for .NET (หรือแพคเกจที่เข้ากันได้)
* สร้างตัวสร้างบาร์โค้ดสำหรับสัญลักษณ์ DataBar Expanded Stacked
* **วิธีการสร้างภาพบาร์โค้ด** ด้วยการตั้งค่าคอลัมน์และแถวเฉพาะ
* **ปรับขนาดบาร์โค้ด** โดยควบคุมแถวและคอลัมน์ของ DataBar
* **กำหนดค่าพารามิเตอร์ databar** เช่น ข้อความ, รูปแบบ, และคุณภาพภาพ

## Prerequisites

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า
* สภาพแวดล้อมการพัฒนา C# (Visual Studio, VS Code, Rider ฯลฯ)
* แพคเกจ NuGet `Aspose.BarCode` (หรือไลบรารีที่เทียบเท่าที่ให้ `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`)

เพิ่มแพคเกจด้วย .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Using the C# barcode generator to create DataBar barcodes

ส่วนต่อไปนี้จะพาคุณผ่านแต่ละขั้นตอน จุดเน้นหลักอยู่ที่ API **c# barcode generator** แต่รูปแบบเดียวกันสามารถใช้กับไลบรารีบาร์โค้ดอื่นที่มีคุณสมบัติคล้ายกันได้

### Step 1: Initialise the barcode generator with sample text

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*ทำไมต้องทำขั้นตอนนี้?*  
`BarcodeGenerator` เป็นจุดเริ่มต้นสำหรับงานสร้างบาร์โค้ดทั้งหมด การระบุ enum `EncodeTypes.DatabarExpandedStacked` บอกไลบรารีว่าจะใช้สัญลักษณ์ประเภทใด ส่วนอาร์กิวเมนต์ข้อความจะกลายเป็นค่าที่มนุษย์อ่านได้ที่ถูกเข้ารหัสในสัญลักษณ์

### Step 2: Set the number of columns (default rows are used)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*ทำไมต้องทำขั้นตอนนี้?*  
สัญลักษณ์ DataBar Expanded Stacked ประกอบด้วยองค์ประกอบเชิงเส้นที่ซ้อนกัน การปรับคุณสมบัติ `Columns` จะเปลี่ยนความหนาแน่นในแนวนอน ทำให้คุณสามารถใส่ข้อมูลยาวขึ้นโดยไม่ต้องเพิ่มความสูงโดยรวม ซึ่งเป็นการ **customize barcode size** โดยตรง

### Step 3: Save the barcode image that uses four columns

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*สิ่งที่คุณเห็น:*  
ภาพที่บันทึกไว้ `DatabarCols4.png` แสดงบาร์โค้ด DataBar ที่กว้างกว่าค่าปริยาย เนื่องจากมีสี่คอลัมน์ คุณสามารถเปิดไฟล์ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันผลลัพธ์

### Step 4: Re‑initialise the generator for a new configuration

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*ทำไมต้องเริ่มใหม่?*  
การเปลี่ยนค่า `Rows` ขณะยังคงใช้การตั้งค่าคอลัมน์เดิมอาจทำให้เกิดการผสมค่าที่ไม่คาดคิด การเริ่มต้นอินสแตนซ์ใหม่ทำให้มั่นใจว่าเฉพาะพารามิเตอร์ที่ตั้งใจ (`Rows`) เท่านั้นที่ส่งผลต่อภาพถัดไป

### Step 5: Set the number of rows (default columns are used)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*ทำไมต้องทำขั้นตอนนี้?*  
คุณสมบัติ `Rows` ควบคุมการซ้อนในแนวตั้ง การเพิ่มจำนวนแถวทำให้บาร์โค้ดสูงขึ้น ซึ่งเป็นประโยชน์เมื่อพื้นที่แนวนอนจำกัดแต่มีพื้นที่แนวตั้งเพียงพอ นี่เป็นอีกวิธีหนึ่งในการ **customize barcode size**

### Step 6: Save the barcode image that uses three rows

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*ผลลัพธ์:*  
`DatabarRows3.png` แสดงบาร์โค้ดที่สูงขึ้นด้วยสามแถวซ้อนกัน แสดงให้เห็นว่า **configure databar parameters** มีผลต่อรูปลักษณ์อย่างไร

## Full runnable example

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก, วาง, และรันได้ รวมการนำเข้า, การจัดการข้อผิดพลาด, และคอมเมนต์เพื่อความชัดเจน

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

เมื่อรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์:

* `DatabarCols4.png` – บาร์โค้ด DataBar กว้างที่มีสี่คอลัมน์
* `DatabarRows3.png` – บาร์โค้ด DataBar สูงที่มีสามแถว

เปิดภาพเพื่อยืนยันว่าขนาดบาร์โค้ดตรงกับพารามิเตอร์ที่กำหนด

## Common questions and edge‑case handling

| Question | Answer |
|----------|--------|
| *What if I need both custom rows **and** columns?* | ตั้งค่า `Rows` **และ** `Columns` บนอินสแตนซ์ `BarcodeGenerator` เดียวก่อนเรียก `Save` ไลบรารีจะรวมค่าทั้งสองเพื่อสร้างกริดขนาดที่ต้องการ |
| *Can I change the image format?* | ได้ สามารถแทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp`, หรือ `Gif` ตามกระบวนการทำงานของคุณ |
| *What happens when the text is longer than the symbol can hold?* | ตัวสร้างจะโยน `ArgumentException` ให้สั้นข้อความหรือเพิ่ม `Columns`/`Rows` เพื่อเพิ่มความจุ |
| *Is there a way to set DPI or image resolution?* | ใช้ `generator.Parameters.ImageResolution` เพื่อระบุ DPI ที่ต้องการก่อนบันทึก ซึ่งช่วย **customize barcode size** สำหรับการพิมพ์ความละเอียดสูง |
| *Does the library support other DataBar variants?* | มี สามารถเปลี่ยน `EncodeTypes.DatabarExpandedStacked` เป็น `DatabarExpanded`, `DatabarLimited` ฯลฯ โดยคงโครงสร้างพารามิเตอร์เดิม |

## Tips for reliable barcode generation

* **Pro tip:** ตรวจสอบภาพที่สร้างด้วยสแกนเนอร์หรือแอปมือถือก่อนนำไปใช้งานจริงเสมอ |
* **Watch out for:** โฟลเดอร์ปลายทางเป็น null หรือว่างเปล่า — `Save` จะโยนข้อยกเว้นหากพาธไม่มีอยู่ สร้างโฟลเดอร์โดยโปรแกรมหากจำเป็น |
* **Performance note:** การใช้อินสแตนซ์ `BarcodeGenerator` เพียงอันเดียวและเปลี่ยนเฉพาะ `Rows` หรือ `Columns` สามารถลดภาระการสร้างอ็อบเจ็กต์เมื่อต้องสร้างบาร์โค้ดหลาย ๆ ตัวในลูป |

## Conclusion

ตอนนี้คุณรู้วิธีใช้ **c# barcode generator** เพื่อ **สร้างภาพบาร์โค้ด databar**, **ปรับขนาดบาร์โค้ด**, และ **กำหนดค่าพารามิเตอร์ databar** เช่น แถวและคอลัมน์ ด้วยการปรับตั้งค่าเหล่านี้คุณสามารถทำให้บาร์โค้ดพอดีกับข้อกำหนดการจัดวางใด ๆ ในขณะเดียวกันยังคงความน่าเชื่อถือในการสแกน

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้องเช่น **วิธีการสร้างบาร์โค้ด** ในรูปแบบ PDF, การฝังบาร์โค้ดในรายงาน, หรือการเปลี่ยนไปใช้สัญลักษณ์อื่น (QR, Code‑128 ฯลฯ) ทดลองเปลี่ยนค่า `Rows`, `Columns`, และความละเอียดภาพเพื่อหาการกำหนดค่าที่เหมาะสมที่สุดสำหรับกรณีการใช้งานของคุณ

---


## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}