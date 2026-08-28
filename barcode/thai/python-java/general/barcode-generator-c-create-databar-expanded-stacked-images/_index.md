---
category: general
date: 2026-07-24
description: บทเรียนการสร้างบาร์โค้ดด้วย C# ที่แสดงวิธีสร้างภาพบาร์โค้ด ตั้งค่าคอลัมน์
  ตั้งค่าแถว และสร้างบาร์โค้ด Databar เพียงไม่กี่บรรทัดของโค้ด
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: th
lastmod: 2026-07-24
og_description: บทแนะนำการใช้ Barcode Generator ด้วย C# จะพาคุณผ่านขั้นตอนการสร้างภาพบาร์โค้ด
  การกำหนดคอลัมน์และแถว และการสร้างบาร์โค้ด Databar พร้อมตัวอย่างโค้ดที่ชัดเจน
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: ตัวสร้างบาร์โค้ด C# – สร้างบาร์โค้ด DataBar แบบซ้อนกันอย่างรวดเร็ว
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: ตัวสร้างบาร์โค้ด C# – สร้างภาพ DataBar Expanded Stacked
url: /th/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – คู่มือฉบับสมบูรณ์สำหรับ DataBar Expanded Stacked

เคยสงสัยไหมว่าจะใช้ **barcode generator c#** เพื่อสร้างภาพที่คมชัดและสแกนได้ในไม่กี่วินาทีอย่างไร? บางทีคุณอาจมองโปรเจกต์เปล่า ไม่แน่ใจว่าคอลัมน์หรือแถวควรอยู่ที่ไหน หรือจะ *generate barcode image* อย่างไรโดยไม่ต้องเจ็บหัว. ดีแล้วที่คุณมาถูกที่นี่. ในบทแนะนำนี้เราจะตั้งค่าแอปคอนโซลขนาดเล็ก, สร้างบาร์โค้ด DataBar Expanded Stacked, ปรับแต่งเลย์เอาต์, และบันทึกผลเป็น PNGs—ทั้งหมดด้วยไลบรารี **barcode generator c#**.

เราจะครอบคลุมทุกอย่างที่คุณต้องรู้: การติดตั้งแพคเกจ, การกำหนดค่าคอลัมน์และแถว (ใช่, เราจะตอบ *how to set columns* และ *how to set rows*), และสุดท้ายวิธี **create databar barcode** ที่คุณสามารถใส่ลงในใบแจ้งหนี้, ตั๋ว, หรือสิ่งใดที่ต้องการป้ายที่เครื่องอ่านได้. ไม่ต้องอ้างอิงเอกสารภายนอก; เพียงคัดลอก‑วาง, รัน, แล้วคุณจะเห็นไฟล์ PNG สองไฟล์ปรากฏในโฟลเดอร์ของคุณ.

## สิ่งที่คุณต้องการ

- .NET 6.0 SDK หรือใหม่กว่า (โค้ดทำงานบน .NET Core, .NET Framework, และ .NET 5+)
- โปรเจกต์คอนโซลใหม่ (`dotnet new console`) – คุณสามารถใช้ Visual Studio หากชอบ UI
- แพคเกจ NuGet Aspose.BarCode for .NET (ไลบรารีที่ทำให้ **barcode generator c#** ทำงาน). ติดตั้งด้วย:

```bash
dotnet add package Aspose.BarCode
```

แค่นั้นเอง. เมื่อแพคเกจถูกกู้คืนแล้วคุณก็พร้อมเริ่มทำงาน.

## Barcode Generator C# – การตั้งค่าโปรเจกต์

ก่อนอื่น, เราจะนำเนมสเปซที่จำเป็นเข้ามาในสโคปและสร้างเมธอดช่วยเหลือเพื่อให้รหัสหลักของเราดูเป็นระเบียบ.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### ทำไมโครงสร้างนี้ถึงได้ผล

- **Separation of concerns** – แต่ละเมธอดช่วยเหลือมุ่งเน้นการตั้งค่าเดียว (คอลัมน์ vs แถว) ทำให้โค้ดอ่านง่ายและนำกลับมาใช้ใหม่ได้
- **Explicit parameters** – เราใส่ `columns` หรือ `rows` เป็นอาร์กิวเมนต์, ดังนั้นคุณสามารถเรียกเมธอดเดียวกันด้วยค่าใดก็ได้โดยไม่ต้องแก้ไขโค้ดภายใน
- **Immediate feedback** – `Console.WriteLine` บอกคุณทันทีว่าไฟล์ถูกบันทึกไว้ที่ไหน, เป็นประโยชน์เมื่อรันโปรแกรมจากเทอร์มินัล

## วิธีตั้งค่า Columns สำหรับ DataBar Expanded Stacked

พร็อพเพอร์ตี้ `DataBar.Columns` คือจุดควบคุมที่กำหนดจำนวนสไลซ์แนวตั้งของบาร์โค้ด. ค่าเริ่มต้นคือ `4`, แต่คุณอาจต้องการ `2` หรือ `6` ขึ้นอยู่กับปริมาณข้อมูลที่เข้ารหัสหรือข้อกำหนดของสแกนเนอร์. นี่คือตัวอย่างสั้น ๆ ที่แยกส่วนการตั้งค่า column ออกมา:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**เคล็ดลับ:** เมื่อเพิ่มจำนวนคอลัมน์ ความกว้างโดยรวมของบาร์โค้ดจะเพิ่มตามสัดส่วน. หากคุณวางแผนจะฝังภาพใน PDF หรือเว็บเพจ, ตรวจสอบให้แน่ใจว่าคอนเทนเนอร์สามารถรองรับความกว้างเพิ่มนี้, ไม่เช่นนั้นสแกนเนอร์อาจอ่านผิดพลาด.

## วิธีตั้งค่า Rows สำหรับ DataBar Expanded Stacked

แถวทำงานในลักษณะเดียวกัน, แต่ส่งผลต่อความสูงของบาร์โค้ด. จำนวนแถวเริ่มต้นคือ `3`. หากป้ายของคุณมีพื้นที่แนวตั้งจำกัด, คุณอาจลดลงเป็น `2`. ในทางกลับกัน, เพิ่มจำนวนแถวสามารถช่วยให้อ่านได้ชัดเจนบนเครื่องพิมพ์ความละเอียดต่ำ.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**ระวัง:** การตั้งค่าแถวเป็นค่าที่ต่ำกว่าขั้นต่ำที่จำเป็นสำหรับข้อมูลที่เข้ารหัสจะทำให้เกิดข้อยกเว้นขณะรันไทม์. ไลบรารีจะโยน `ArgumentException` พร้อมข้อความชัดเจน, ดังนั้นคุณจะรู้ทันทีว่าการกำหนดค่าไม่ถูกต้อง.

## สร้างภาพ Barcode – บันทึกเป็น PNG

เมธอดช่วยเหลือทั้งสองด้านบนจบด้วยการเรียก `Save`. ค่าตัวแปร enum `BarCodeImageFormat.Png` บอก Aspose.BarCode ให้ส่งออกไฟล์ PNG แบบ loss‑less, ซึ่งเหมาะกับสถานการณ์สแกนส่วนใหญ่เพราะรักษาขอบคม. หากคุณต้องการฟอร์แมตอื่น (JPEG สำหรับเว็บ, BMP สำหรับระบบเก่า), เพียงสลับค่า enum – ไม่ต้องแก้ไขโค้ดส่วนอื่น.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

ภาพ PNG ที่สร้างขึ้นจะมีลักษณะดังนี้ (จินตนาการภาพ; คำอธิบาย alt ด้านล่าง):

> **Alt text for the generated images:** *DataBar Expanded Stacked barcode with 4 columns (left) and 3 rows (right), rendered in high‑contrast black on a transparent background.*

## สร้าง DataBar Barcode – ตัวอย่างทำงานเต็มรูปแบบ

รวมทุกอย่างเข้าด้วยกัน, นี่คือเวอร์ชันกระชับที่คุณสามารถวางตรงลงใน `Program.cs`. มันแสดงการกำหนดค่าคอลัมน์และแถว, พร้อมการตรวจสอบอย่างรวดเร็วว่ามีไฟล์อยู่หลังการบันทึกหรือไม่.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อคุณรันโปรแกรม (`dotnet run`), คุณควรเห็นบรรทัดคอนโซลคล้ายกับ:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

เปิดไฟล์ PNG สองไฟล์ในโปรแกรมดูภาพใดก็ได้; คุณจะสังเกตว่าไฟล์ด้านซ้ายมีสี่โมดูลแนวตั้ง (คอลัมน์) ส่วนไฟล์ด้านขวามีสามโมดูลแนวตั้ง (แถว). ทั้งสองไฟล์สแกนได้อย่างสมบูรณ์ด้วยเครื่องอ่าน DataBar มาตรฐานใดก็ได้.

## ข้อผิดพลาดทั่วไป & วิธีหลีกเลี่ยง

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | ตั้งค่า Columns เป็น 0 หรือ > 8 (ไลบรารีจำกัดที่ 8) | ใช้ค่าระหว่าง **1** ถึง **8** |
| Barcode appears blurry in PDF | PNG ถูกบันทึกที่ DPI เริ่มต้น (96) แล้วถูกขยาย | ใช้ `generator.Parameters.ImageResolution = 300;` ก่อนบันทึก |
| Scanner fails on rows‑only configuration | เปลี่ยน Rows แต่ไม่ได้ปรับ Columns ที่ยังเป็นค่าเริ่มต้นซึ่งไม่ตรงกับความยาวข้อมูล | ปรับทั้ง Rows **และ** Columns พร้อมกัน, หรือให้ไลบรารีกำหนดขนาดอัตโนมัติโดยไม่ตั้งค่าด้วยตนเอง |

## ขั้นตอนต่อไป

ตอนนี้คุณรู้วิธี **generate barcode image**, **set columns**, **set rows**, และ **create databar barcode** ด้วย **barcode generator c#**, คุณสามารถ:

- ฝัง PNG ลงใน PDF ด้วย `Aspose.PDF` หรือ `iTextSharp`
- เปลี่ยนไปใช้ `EncodeTypes.DatabarLimited` หากต้องการพื้นที่เล็กลง
- ทดลองเปลี่ยนสี (`generator.Parameters.Barcode.ForeColor = Color.Blue`)
- เพิ่ม QR code หรือสิโมโบโลยีอื่นในโปรเจกต์เดียวกัน—Aspose.BarCode รองรับกว่า 150 ประเภท

หากเจออุปสรรคใด ๆ, แสดงความคิดเห็นด้านล่างหรือดูเอกสารอย่างเป็นทางการของ Aspose.BarCode (อ้างอิง API ครบถ้วนและมีตัวอย่างโค้ดหลายสิบชุด). Happy coding, and may your scanners never miss a mark!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ.

- [สร้างภาพบาร์โค้ด DotCode – แถวและคอลัมน์ (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [สร้างภาพบาร์โค้ด c# – กำหนดค่า Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [สร้างภาพบาร์โค้ด – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}