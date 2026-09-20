---
category: general
date: 2026-09-19
description: ตัวอย่างการสร้างบาร์โค้ดด้วย C# แสดงวิธีการสร้างบาร์โค้ดด้วย C# โดยใช้
  Aspose.BarCode สำหรับการจัดวางเป็นคอลัมน์และแถว
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: th
lastmod: 2026-09-19
og_description: ตัวอย่างการสร้างบาร์โค้ดแสดงวิธีการสร้างบาร์โค้ดด้วย C# พร้อมการจัดเรียงเป็นคอลัมน์และแถวโดยใช้
  Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: ตัวอย่างเครื่องสร้างบาร์โค้ด – สร้างบาร์โค้ด DataBar Expanded Stacked ด้วย
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างตัวอย่างเครื่องสร้างบาร์โค้ดใน C# ด้วย DataBar Expanded Stacked
url: /th/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างตัวสร้างบาร์โค้ด – สร้างบาร์โค้ด DataBar Expanded Stacked ด้วย C#

หากคุณต้องการ **barcode generator example** ที่ทำงานได้ในโครงการ .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่า จะสร้างบาร์โค้ด C# ด้วยไลบรารี Aspose.BarCode อย่างไร คุณจะได้เห็นวิธีการตั้งค่า DataBar Expanded Stacked barcode ทั้งแบบจัดเรียงเป็นคอลัมน์และแบบจัดเรียงเป็นแถว พร้อมกับโค้ดที่พร้อมรันและสร้างภาพ PNG

บทเรียนนี้ครอบคลุมทุกขั้นตอนตั้งแต่การติดตั้งแพคเกจ NuGet จนถึงการบันทึกภาพขั้นสุดท้าย เพื่อให้คุณสามารถคัดลอกโค้ดไปใช้ในโซลูชันของคุณได้โดยไม่ต้องค้นคว้าเพิ่มเติม

## สิ่งที่คุณจะได้เรียนรู้

* วิธีติดตั้งและอ้างอิง Aspose.BarCode ในโครงการ C#  
* วิธีสร้าง **barcode generator example** ที่เข้ารหัสสตริงข้อมูลยาว  
* วิธีตั้งค่าเลย์เอาต์ 4‑คอลัมน์และ 3‑แถวบนประเภทบาร์โค้ดเดียวกัน  
* วิธีบันทึกภาพที่สร้างเป็นไฟล์ PNG  

เมื่ออ่านบทความนี้จนจบคุณจะมีไฟล์ PNG พร้อมใช้งานสองไฟล์คือ `ExpandedStackedCols4.png` (สี่คอลัมน์) และ `ExpandedStackedRows3.png` (สามแถว)

## ข้อกำหนดเบื้องต้น

* .NET 6.0 SDK หรือใหม่กว่า (โค้ดนี้ยังทำงานได้กับ .NET Framework 4.7.2)  
* Visual Studio 2022, VS Code หรือ IDE สำหรับ C# ที่คุณชื่นชอบ  
* การเชื่อมต่ออินเทอร์เน็ตเพื่อดาวน์โหลดแพคเกจ **Aspose.BarCode** NuGet  

ไม่จำเป็นต้องใช้บริการภายนอกเพิ่มเติม

## ขั้นตอนที่ 1: ติดตั้งแพคเกจ Aspose.BarCode NuGet

เปิดเทอร์มินัลในโฟลเดอร์โครงการของคุณและรันคำสั่ง:

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่มเวอร์ชันล่าสุดของ Aspose.BarCode ลงในไฟล์โครงการของคุณ หลังจากแพคเกจถูกกู้คืนแล้ว คุณก็สามารถอ้างอิงเนมสเปซในไฟล์ C# ของคุณได้

## ขั้นตอนที่ 2: เพิ่ม `using` directives ที่จำเป็น

สร้างแอปพลิเคชันคอนโซล C# ใหม่ (หรือเพิ่มโค้ดนี้ลงในโปรเจกต์ที่มีอยู่) และใส่ `using` statements ด้านล่างนี้ไว้ที่ส่วนหัวของไฟล์:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

คำสั่งเหล่านี้ทำให้คุณเข้าถึงคลาส `BarcodeGenerator` และ enumeration `EncodeTypes` ที่ใช้ใน **barcode generator example** ได้

## ขั้นตอนที่ 3: สร้างตัวอย่างตัวสร้างบาร์โค้ดด้วยเลย์เอาต์ 4‑คอลัมน์

ส่วนแรกของตัวอย่างจะสร้าง DataBar Expanded Stacked barcode ที่ใช้การจัดเรียงเป็นสี่คอลัมน์ โค้ดด้านล่างทำตามขั้นตอนเดียวกับในสแนปเพล็ตต้นฉบับ แต่เพิ่มคอมเมนต์อธิบายเหตุผลของแต่ละบรรทัด

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**ทำไมวิธีนี้ถึงได้ผล**

* `EncodeTypes.DatabarExpandedStacked` บอก Aspose.BarCode ให้สร้างสัญลักษณ์ DataBar Expanded Stacked ซึ่งเหมาะกับการใช้งานด้านการค้าปลีก  
* การตั้งค่า `DataBar.Columns` เป็น `4` ทำให้เครื่องสร้างบาร์โค้ดแบ่งสัญลักษณ์ออกเป็นสี่ส่วนแนวตั้ง ช่วยให้อ่านได้ง่ายบนป้ายที่แคบ  
* `Save` จะเขียนบาร์โค้ดลงดิสก์; อาร์กิวเมนต์ `BarCodeImageFormat.Png` ทำให้ได้คุณภาพภาพแบบ lossless  

เมื่อรันบล็อกนี้จะสร้างไฟล์ `ExpandedStackedCols4.png` ในไดเรกทอรีทำงานของแอปพลิเคชัน ไฟล์นี้มีบาร์โค้ดความละเอียดสูงที่สามารถสแกนด้วยเครื่องอ่าน DataBar ใดก็ได้

## ขั้นตอนที่ 4: เริ่มต้นเครื่องสร้างใหม่สำหรับเลย์เอาต์อื่น

เพื่อสาธิตการจัดเรียงแบบแถว คุณต้องสร้างอินสแตนซ์ `BarcodeGenerator` ใหม่ การเริ่มต้นใหม่รับประกันว่าการตั้งค่าคอลัมน์ก่อนหน้านี้จะไม่ส่งผลต่อการกำหนดค่าใหม่

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## ขั้นตอนที่ 5: ตั้งค่าบาร์โค้ดให้ใช้เลย์เอาต์ 3‑แถว

API ของ DataBar ยังรองรับการจัดเรียงเป็นแถว การตั้งค่า `Rows` จะกำหนดจำนวนชิ้นส่วนแนวนอนของสัญลักษณ์

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**ทำไมคุณอาจเลือกใช้แถวแทนคอลัมน์**

แถวเป็นประโยชน์เมื่อความสูงของป้ายจำกัดแต่ความกว้างมีเพียงพอ การจัดเรียงแบบสามแถวจะบีบบาร์โค้ดในแนวตั้งขณะยังคงรักษาข้อมูลที่ต้องการได้ครบถ้วน

## ไฟล์ซอร์สเต็มรูปแบบ

ด้านล่างเป็นไฟล์ `Program.cs` ฉบับเต็มที่สามารถคอมไพล์และรันได้โดยตรง รวมตัวอย่างคอลัมน์และแถวไว้ในไฟล์เดียว ทำให้คุณได้ไฟล์ PNG สองไฟล์จากการรันครั้งเดียว

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อรันโปรแกรมคุณจะเห็นข้อความคอนโซลสองข้อความยืนยันการสร้างไฟล์:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

ไฟล์ PNG ทั้งสองจะแสดง DataBar Expanded Stacked barcode ที่เข้ารหัสสตริง `"Long data string"` การสแกนภาพใดภาพหนึ่งด้วยสแกนเนอร์บาร์โค้ดมาตรฐานจะคืนค่าข้อมูลเดิมกลับมา

## คำถามที่พบบ่อยและกรณีขอบ

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff` depending on your requirements. |
| **What if the data string is shorter?** | The DataBar format automatically adjusts the symbol size; you do not need to modify the layout settings. |
| **How do I set the barcode size (width/height)?** | Use `generator.Parameters.Image.Width` and `generator.Parameters.Image.Height` before calling `Save`. |
| **Is it possible to add a human‑readable caption?** | Set `generator.Parameters.Barcode.CodeText` and enable `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **What .NET versions are supported?** | Aspose.BarCode supports .NET Standard 2.0, .NET 5/6, and .NET Framework 4.6.1+. |

การตอบสนองต่อความหลากหลายเหล่านี้ทำให้ **barcode generator example** มีความทนทานพอสำหรับการใช้งานในระดับผลิต

## เคล็ดลับระดับมืออาชีพ

* **Reuse the generator object only when the layout stays the same.** การสร้างอินสแตนซ์ใหม่สำหรับแต่ละเลย์เอาต์ (ตามขั้นตอน 4‑5) จะช่วยป้องกันการสืบทอดคุณสมบัติที่ไม่ต้องการ  
* **Validate the generated barcode** ด้วย `generator.Validate()` หากคุณต้องการตรวจสอบความสอดคล้องตามมาตรฐาน ISO/GS1  
* **Batch processing:** ห่อหุ้มตรรกะคอลัมน์และแถวไว้ในลูปที่วนผ่านรายการการตั้งค่าเลย์เอาต์ต่าง ๆ จะช่วยลดการทำซ้ำโค้ดเมื่อคุณต้องการสร้างหลายรูปแบบ

## สรุป

**barcode generator example** นี้แสดงวิธี **generate barcode C#** ที่สร้าง DataBar Expanded Stacked barcode ทั้งแบบ 4‑คอลัมน์และ 3‑แถว คุณมีโปรแกรมที่พร้อมรัน, เข้าใจคุณสมบัติหลัก (`Columns`, `Rows`) และได้รับคำแนะนำในการขยายโซลูชันต่อไป

ต่อไปลองสำรวจหัวข้อที่เกี่ยวข้อง เช่น **customizing barcode colors**, **embedding barcodes in PDF documents**, หรือ **generating QR codes with Aspose.BarCode** แต่ละหัวข้อจะต่อยอดจากหลักการ API ที่อธิบายไว้ในบทนี้

อย่ากลัวที่จะทดลองเปลี่ยนสตริงข้อมูล, รูปแบบภาพ, หรือการจัดเรียงต่าง ๆ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมาพร้อมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้ในโครงการของคุณเอง

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}