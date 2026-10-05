---
category: general
date: 2026-08-09
description: สร้างภาพบาร์โค้ดใน C# ด้วยคู่มือขั้นตอนนี้ เรียนรู้วิธีสร้างบาร์โค้ด
  ปรับความสูงของบาร์โค้ดเป็นพิกเซล และสร้างบาร์โค้ดหลายรายการอย่างมีประสิทธิภาพ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: th
lastmod: 2026-08-09
og_description: สร้างภาพบาร์โค้ดใน C# อย่างรวดเร็ว ทำตามบทแนะนำนี้เพื่อเรียนรู้วิธีสร้างบาร์โค้ด
  ตั้งค่าความสูงของบาร์โค้ดเป็นพิกเซล และสร้างบาร์โค้ดหลายรายการ
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: สร้างภาพบาร์โค้ดใน C# – คู่มือเต็มสำหรับนักพัฒนา
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: สร้างภาพบาร์โค้ดใน C# – คู่มือการเขียนโปรแกรมครบถ้วน
url: /th/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดด้วย C# – คู่มือการเขียนโปรแกรมแบบครบถ้วน

หากคุณต้องการ **สร้างภาพบาร์โค้ด** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่า **วิธีสร้างบาร์โค้ด** ด้วยไลบรารี Aspose.BarCode คุณจะได้เห็นวิธีควบคุม **ความสูงของบาร์โค้ดเป็นพิกเซล**, การบันทึกภาพ, และการสร้าง **บาร์โค้ดหลายรายการ** โดยไม่ต้องทำซ้ำโค้ด

บทแนะนำนี้ครอบคลุมทุกอย่างตั้งแต่การติดตั้งแพ็กเกจจนถึงการปรับแต่งขนาด, เพื่อให้คุณสามารถคัดลอก‑วางตัวอย่างที่พร้อมใช้งานลงในโปรเจกต์ของคุณได้ทันที

## ข้อกำหนดเบื้องต้น

* .NET 6.0 SDK หรือเวอร์ชันที่ใหม่กว่า ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE สำหรับ C# ใดก็ได้)  
* NuGet package `Aspose.BarCode` – ติดตั้งด้วย  

```bash
dotnet add package Aspose.BarCode
```

ไม่ต้องการการพึ่งพาเพิ่มเติม

## วิธีสร้างภาพบาร์โค้ดด้วย BarcodeGenerator C#

คลาสหลักสำหรับการสร้างภาพบาร์โค้ดคือ `BarcodeGenerator` ซึ่งบรรจุประเภทการเข้ารหัส, สตริงข้อมูล, และพารามิเตอร์การเรนเดอร์ทั้งหมด

### ขั้นตอนที่ 1: กำหนดโฟลเดอร์ปลายทาง

เลือกโฟลเดอร์ที่ไฟล์ PNG ที่สร้างขึ้นจะถูกเก็บไว้ การใช้เส้นทางแบบเต็มจะช่วยหลีกเลี่ยงปัญหาเรื่องสิทธิ์

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **ทำไม?** การสร้างโฟลเดอร์โดยโปรแกรมจะรับประกันว่าการเรียก `Save` ต่อไปจะสำเร็จแม้บนเครื่องใหม่

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ของ barcode generator

สำหรับบาร์โค้ด DataBar Omnidirectional ให้ส่งค่า `EncodeTypes.DatabarOmniDirectional` และสตริงข้อมูล GS1‑128

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **หมายเหตุ:** ออบเจ็กต์ `BarcodeGenerator` สามารถใช้ซ้ำได้; คุณสามารถเปลี่ยนพารามิเตอร์ระหว่างการบันทึกเพื่อ **สร้างบาร์โค้ดหลายรายการ** จากข้อมูลเดียวกัน

### ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์บาร์โค้ดทั่วไป

การปรับแต่งภาพที่พบบ่อยที่สุดคือ X‑dimension (ความกว้างของโมดูล) และความสูงของบาร์ ทั้งสองค่าถูกระบุเป็นพิกเซล

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **ทำไมต้องตั้งค่า X‑dimension?** X‑dimension ที่เล็กลงจะให้ความละเอียดสูงขึ้น ซึ่งสำคัญเมื่อภาพจะถูกพิมพ์หรือแสดงบนหน้าจอที่มี DPI สูง

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ดแรก

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

ไฟล์ `DatabarBarHeight30Pixels.png` ตอนนี้มีบาร์โค้ด DataBar Omnidirectional ความสูง 30 พิกเซล

### ขั้นตอนที่ 5: ปรับความสูงของบาร์โค้ดเป็นพิกเซล

การเปลี่ยนความสูงไม่จำเป็นต้องสร้างอินสแตนซ์ `BarcodeGenerator` ใหม่—เพียงแก้ไขพารามิเตอร์

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### ขั้นตอนที่ 6: บันทึกภาพบาร์โค้ดที่สอง

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์ที่มี **ความสูงของบาร์โค้ดเป็นพิกเซล** ต่างกัน, แสดงให้เห็นว่าการสร้าง **ภาพบาร์โค้ด** แบบหลากหลายเป็นเรื่องง่ายแค่ไหน

## การตั้งค่าความสูงของบาร์โค้ดเป็นพิกเซลแบบไดนามิก

บ่อยครั้งคุณต้องการชุดบาร์โค้ดที่มีความสูงตรงกับองค์ประกอบ UI หรือป้ายพิมพ์ วิธีช่วยเหลือด้านล่างนี้ทำให้การเปลี่ยนความสูงเป็นเรื่องง่าย

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

คุณสามารถเรียก `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` เพื่อ **สร้างภาพบาร์โค้ด** ความสูง 45 พิกเซลในบรรทัดเดียว

## การสร้างบาร์โค้ดหลายรายการในลูป

เมื่อคุณมีคอลเลกชันของรหัสสินค้า, ลูป `foreach` จะช่วยลดโค้ดที่ซ้ำซ้อน ตัวอย่างนี้แสดงวิธี **สร้างบาร์โค้ดหลายรายการ** จากอาเรย์ของ GTIN

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

ลูปนี้สร้างไฟล์ PNG สามไฟล์, แต่ละไฟล์มีค่า **ความสูงของบาร์โค้ดเป็นพิกเซล** ที่แตกต่างกัน เนื่องจากฟังก์ชันช่วยเหลือ `SaveBarcodeWithHeight` จัดการการเปลี่ยนความสูง, ลูปหลักจึงสะอาดและมุ่งเน้นที่ข้อมูล

### ผลลัพธ์ที่คาดหวัง

หลังจากรันตัวอย่างเต็ม, โฟลเดอร์ `Barcodes` จะมี:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

การเปิดไฟล์ PNG ใดก็จะเห็นบาร์โค้ด DataBar Omnidirectional ที่คมชัดและสามารถสแกนได้ด้วยแอปมือถือมาตรฐาน

## ข้อผิดพลาดทั่วไปและเคล็ดลับระดับมืออาชีพ

| ปัญหา | สาเหตุที่เกิดขึ้น | วิธีหลีกเลี่ยง |
|-------|-------------------|-----------------|
| **EncodeTypes ผิด** | การใช้ประเภท 1D สำหรับ DataBar จะทำให้ได้ภาพที่อ่านไม่ออก | ควรเลือก `EncodeTypes.DatabarOmniDirectional` (หรือรูปแบบ DataBar อื่น) สำหรับข้อมูล GS1‑128 เสมอ |
| **X‑dimension ไม่เพียงพอ** | X‑dimension ที่ต่ำมากอาจทำให้บาร์บางหายไปบนจอที่ความละเอียดต่ำ | ตั้งค่า `XDimension.Pixels` ≥ 2 สำหรับการแสดงบนหน้าจอ; เพิ่มเป็น 3‑4 สำหรับการพิมพ์ |
| **ข้อผิดพลาดของเส้นทางไฟล์** | เส้นทางแบบ relative อาจชี้ไปยังไดเรกทอรีที่ไม่คาดคิด | ใช้ `Path.Combine` และ `Environment.CurrentDirectory` เพื่อสร้างเส้นทางแบบ absolute |
| **การเขียนทับภาพ** | การใช้ชื่อไฟล์เดียวกันในลูปจะทำให้ผลลัพธ์ก่อนหน้าถูกเขียนทับ | ใส่ตัวระบุที่ไม่ซ้ำกัน (เช่น GTIN หรือ timestamp) ลงในชื่อไฟล์ |
| **ขาดแพ็กเกจ NuGet** | โค้ดคอมไพล์สำเร็จแต่เกิด `FileNotFoundException` ขณะรัน | ตรวจสอบว่าได้ติดตั้ง `Aspose.BarCode` แล้วและโปรเจกต์อ้างอิงถึงมัน |

## ตัวอย่างการทำงานเต็มรูปแบบ

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอกไปใส่ในแอปพลิเคชันคอนโซลได้ รวมทุกขั้นตอน, เมธอดช่วยเหลือ, และการจัดการข้อผิดพลาด

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

การรันโปรแกรมนี้

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดที่ทำงานได้ครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [สร้างบาร์โค้ดความสูงกำหนดเอง – บาร์โค้ดแบบมิติเดียว](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [สร้างภาพบาร์โค้ด C# – ตัวอย่าง GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [สร้างภาพบาร์โค้ด DotCode – แถวและคอลัมน์ (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}