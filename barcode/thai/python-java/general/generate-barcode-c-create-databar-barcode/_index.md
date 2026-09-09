---
category: general
date: 2026-07-21
description: สร้างบาร์โค้ดด้วย C# อย่างรวดเร็วด้วย Aspose.BarCode. เรียนรู้การสร้างบาร์โค้ด
  DataBar, ปรับขนาดบาร์โค้ด, และส่งออกภาพบาร์โค้ดในไม่กี่ขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: th
lastmod: 2026-07-21
og_description: สร้างบาร์โค้ดด้วย C# โดยใช้ Aspose.BarCode สร้างบาร์โค้ด DataBar ปรับขนาดตามต้องการ
  และส่งออกภาพทันที
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: สร้างบาร์โค้ด C# – สร้างบาร์โค้ด DataBar ด้วยขนาดกำหนดเอง
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: สร้างบาร์โค้ดด้วย C# – สร้างบาร์โค้ด DataBar
url: /th/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด C# – สร้างบาร์โค้ด DataBar

กำลังมองหา **generate barcode C#** โดยไม่ต้องคุ้ยผ่านเอกสารที่ไม่มีที่สิ้นสุด? คุณมาถูกที่แล้ว ในคู่มือนี้เราจะพาคุณผ่านการสร้าง **DataBar barcode**, ปรับขนาดของมัน, และสุดท้าย **exporting the barcode image**—ทั้งหมดด้วยไม่กี่บรรทัดของ C#.

ลองนึกภาพว่าคุณต้องการป้ายสินค้าแบบกะทัดรัดที่พอดีกับแท็กชั้นวางของขนาดเล็ก สัญลักษณ์ DataBar Expanded Stacked ทำหน้าที่นี้ได้, และด้วย Aspose.BarCode คุณสามารถควบคุมจำนวนคอลัมน์หรือแถวที่ใช้ได้อย่างแม่นยำ พร้อมหรือยัง? ไปดิ่งกันเลย.

## สิ่งที่คุณจะทำสำเร็จ

- **Create a DataBar barcode** (รูปแบบ “expanded stacked”) ตั้งแต่เริ่มต้น.  
- **Customize barcode size** โดยตั้งค่าคอลัมน์หรือแถวโดยตรง.  
- **Change barcode dimensions** อย่างรวดเร็วโดยไม่ต้องสร้าง generator ใหม่.  
- **Export barcode image** ไปเป็น PNG (หรือรูปแบบใดก็ได้ที่ Aspose รองรับ).  

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานบน .NET Framework 4.7+ ด้วย).  
- ใบอนุญาต Aspose.BarCode for .NET ที่ถูกต้อง (หรือคุณสามารถใช้ในโหมดทดลอง).  
- IDE ที่คุณเลือก—Visual Studio, Rider, หรือ VS Code ก็ได้.

หากคุณยังไม่ได้ติดตั้งแพคเกจ NuGet, ให้รัน:

```bash
dotnet add package Aspose.BarCode
```

เท่านี้—ไม่มีการพึ่งพาอื่นใด.

## ขั้นตอนที่ 1: ตั้งค่า barcode generator (วิธี **generate barcode C#**)

ก่อนอื่น, เราต้องการอินสแตนซ์ `BarcodeGenerator` ที่ชี้ไปที่สัญลักษณ์ **DataBar Expanded Stacked**. วัตถุนี้เป็นเอนจินที่สร้างภาพในภายหลัง.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*ทำไมเรื่องนี้สำคัญ*: enum `EncodeTypes.DatabarExpandedStacked` บอก Aspose ว่าเราต้องการเวอร์ชัน stacked, ซึ่งเหมาะกับพื้นที่แคบ. ข้อความที่เราผ่านเข้าไปจะกลายเป็นค่าที่เข้ารหัส; คุณสามารถแทนที่ด้วยสตริงตัวเลขใดก็ได้ที่แอปของคุณต้องการ.

## ขั้นตอนที่ 2: **Customize barcode size** – ตั้งค่าคอลัมน์

บาร์โค้ด DataBar ให้คุณควบคุมความหนาแน่นของภาพโดยระบุจำนวน **columns** *หรือ* **rows**. เรามาเริ่มที่คอลัมน์กันก่อน. จำนวนแถวจะคำนวณอัตโนมัติเพื่อให้บาร์โค้ดยังคงถูกต้อง.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*เคล็ดลับ*: คอลัมน์มีผลต่อความกว้างของบาร์โค้ด. คอลัมน์มากขึ้น → บาร์โค้ดกว้างขึ้น, ซึ่งอาจทำให้การสแกนมีความน่าเชื่อถือมากขึ้นบนเครื่องพิมพ์ความละเอียดต่ำ.

## ขั้นตอนที่ 3: **Export barcode image** ด้วยการตั้งค่าคอลัมน์

ตอนนี้เราจะบันทึกภาพลงดิสก์. คุณสามารถเลือก PNG, JPEG, BMP, หรือแม้แต่ SVG. นี่คือ PNG สำหรับผลลัพธ์ที่คมชัดและไม่มีการสูญเสีย.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **ผลลัพธ์ที่คาดหวัง** – เปิด `DatabarCols4.png` แล้วคุณควรเห็น DataBar ที่จัดเรียงเป็นชั้นอย่างเรียบร้อยด้วยสี่คอลัมน์. มันดูเหมือนกองแถบแนวตั้งหนาแน่น, เหมาะสำหรับป้ายเล็ก.

## ขั้นตอนที่ 4: **Change barcode dimensions** – ตั้งค่าแถวแทน

บางครั้งคุณอาจต้องการบาร์โค้ดที่สูงกว่าแทนที่จะกว้าง. สลับไปใช้การควบคุมแถว; Aspose จะคำนวณคอลัมน์ใหม่โดยอัตโนมัติ.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*ทำไมต้องสลับ?* แถวมีผลต่อความสูงของบาร์โค้ด. แถวมากขึ้นทำให้สัญลักษณ์สูงขึ้น, ซึ่งเป็นประโยชน์เมื่อคุณมีพื้นที่แนวตั้งแต่ความกว้างจำกัด.

## ขั้นตอนที่ 5: **Export barcode image** ด้วยการตั้งค่าแถว

บันทึกเวอร์ชันที่สอง. สังเกตว่าชื่อไฟล์สะท้อนการเปลี่ยนแปลง; คุณอาจเก็บภาพทั้งสองไว้เพื่อเปรียบเทียบ.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **ผลลัพธ์** – `DatabarRows3.png` ตอนนี้แสดงเวอร์ชันที่สูงขึ้นของข้อมูลเดียวกัน, ยังสแกนได้อย่างสมบูรณ์.

## ตัวอย่างทำงานเต็มรูปแบบ

รวมทุกอย่างเข้าด้วยกัน, นี่คือแอปคอนโซลที่ทำงานอิสระซึ่งคุณสามารถคัดลอก‑วางและรันได้ทันที:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

รันโปรแกรม, แล้วเปิดไฟล์ PNG สองไฟล์. ตอนนี้คุณได้ **generated barcode C#**, **customized barcode size**, **changed barcode dimensions**, และ **exported the barcode image**—ทั้งหมดในเวลาน้อยกว่านาทีหนึ่ง.

## คำถามทั่วไป & กรณีขอบ

- **What if I need a different image format?**  
  แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp`, `Gif`, หรือ `Svg`. API จะจัดการการแปลงโดยอัตโนมัติ.

- **Can I change both rows and columns simultaneously?**  
  โดยเทคนิคคุณสามารถตั้งค่าทั้งสองได้, แต่ Aspose จะให้ความสำคัญกับคุณสมบัติสุดท้ายที่คุณแก้ไข. จึงปลอดภัยกว่าให้ตั้งค่า *หนึ่ง* มิติและให้ไลบรารีคำนวณอีกมิติหนึ่งเพื่อให้ได้ DataBar ที่ถูกต้อง.

- **How do I apply a foreground/background color?**  
  ใช้ `barcodeGen.Parameters.Barcode.ForegroundColor` และ `BackgroundColor`. ตัวอย่าง:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked รองรับได้สูงสุด 74 ตัวอักษรตัวเลข (หรือ 30 ตัวอักษรอัลฟานูเมอริก). หากเกินจะทำให้เกิดข้อยกเว้น.

## ขั้นตอนต่อไป

ตอนนี้คุณได้เชี่ยวชาญพื้นฐานของ **create databar barcode** แล้ว, พิจารณา:

- เพิ่ม **text annotations** ใต้บาร์โค้ด (`barcodeGen.Parameters.CaptionAbove.Text`).
- ฝัง PNG โดยตรงลงใน PDF ด้วย Aspose.PDF.
- สร้างบาร์โค้ดเป็นชุดโดยวนลูปผ่าน CSV ของรหัสสินค้า.

แต่ละหัวข้อเหล่านี้สร้างบนอ็อบเจ็กต์ `BarcodeGenerator` เดียวกัน, ดังนั้นคุณไม่จำเป็นต้องเริ่มจากศูนย์.

---

**สรุป**: ตอนนี้คุณรู้วิธี **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, และ **export barcode image** ด้วย Aspose.BarCode. ลองปรับค่าคอลัมน์/แถว, สลับรูปแบบภาพ, และรวมโค้ดเข้ากับระบบสินค้าคงคลังหรือ POS ของคุณ. Happy coding!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการใช้งานอื่นในโครงการของคุณ.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}