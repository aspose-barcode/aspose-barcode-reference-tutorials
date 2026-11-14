---
category: general
date: 2026-11-14
description: เรียนรู้วิธีสร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว คู่มือนี้ยังแสดงวิธีสร้าง
  PDF417 และวิธีปรับแต่งการตั้งค่า PDF417 เพื่อควบคุมอย่างแม่นยำ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: th
lastmod: 2026-11-14
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# พร้อมคำแนะนำทีละขั้นตอน เรียนรู้วิธีสร้าง
  PDF417 และวิธีปรับแต่งพารามิเตอร์ของ PDF417 เพื่อให้ได้ผลลัพธ์ที่แม่นยำ
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือเต็มพร้อมการจัดรูปแบบแบบกำหนดเอง
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: วิธีสร้างบาร์โค้ด PDF417 ด้วยการจัดรูปแบบที่กำหนดเองใน C#
url: /th/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ด้วยการจัดวางแบบกำหนดเองใน C#

หากคุณต้องการ **สร้างบาร์โค้ด pdf417** สำหรับระบบตั๋ว, ป้ายสินค้าคงคลัง, หรือการสแกนในแอปมือถือ, บทเรียนนี้จะแสดงกระบวนการทั้งหมด คุณจะได้เห็นวิธีการสร้าง PDF417 อย่างรวดเร็วและวิธีการปรับแต่งการตั้งค่า PDF417 เช่น จำนวนคอลัมน์และแถว เพื่อให้บาร์โค้ดพอดีกับข้อจำกัดการออกแบบของคุณ

การสร้างบาร์โค้ดไม่จำเป็นต้องใช้ไลบรารีกราฟิกที่ซับซ้อน—เพียงแค่ Aspose.BarCode for .NET (หรือ API ที่เข้ากันได้) เพียงเท่านี้ หลังจากอ่านคู่มือนี้แล้วคุณจะมีไฟล์ PNG พร้อมใช้งานที่สามารถฝังลงใน PDF, หน้าเว็บ, หรือพิมพ์โดยตรงจากแอปพลิเคชันของคุณ

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือรุ่นใหม่กว่า (โค้ดยังทำงานได้กับ .NET Framework 4.7+)
- Aspose.BarCode for .NET (แพ็กเกจ NuGet `Aspose.BarCode`)
- ความคุ้นเคยพื้นฐานกับ C# และ Visual Studio (หรือ IDE ใดก็ได้)

> **เคล็ดลับ:** หากคุณใช้ CI/CD pipeline, ให้เพิ่มการอ้างอิงแพ็กเกจ NuGet ในไฟล์โครงการของคุณเพื่อให้การสร้างซ้ำได้

## ขั้นตอนที่ 1: ติดตั้งไลบรารีบาร์โค้ด

เปิดโฟลเดอร์โครงการของคุณในเทอร์มินัลและรัน:

```bash
dotnet add package Aspose.BarCode
```

แพ็กเกจนี้รวมคลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียนนี้ ไม่ต้องการการพึ่งพาเนทีฟเพิ่มเติม

## ขั้นตอนที่ 2: สร้างบาร์โค้ด PDF417 พื้นฐาน

เป้าหมายแรกคือ **สร้างบาร์โค้ด pdf417** ด้วยการตั้งค่าเริ่มต้น โปรแกรมต่อไปนี้จะตั้งค่า generator, เข้ารหัสสตริงตัวอย่าง, และบันทึกผลลัพธ์เป็นภาพ PNG

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**ทำไมวิธีนี้ถึงได้ผล:**  
`EncodeTypes.Pdf417` บอกไลบรารีให้ใช้สัญลักษณ์ PDF417 ตัวสร้างอัตโนมัติสร้างอ็อบเจ็กต์ `Barcode` พร้อมค่าคอลัมน์/แถวเริ่มต้นที่รับประกันการสแกนได้สำหรับกรณีใช้งานส่วนใหญ่

รันโปรแกรม (`dotnet run`). คุณจะพบไฟล์ `Pdf417Default.png` ในโฟลเดอร์โครงการ การเปิดภาพจะแสดงบาร์โค้ด PDF417 มาตรฐานพร้อมสแกน

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="ตัวอย่างการสร้างบาร์โค้ด PDF417 แสดงการจัดวางเริ่มต้น"}

## ขั้นตอนที่ 3: วิธีสร้าง PDF417 ด้วยมิติที่กำหนดเอง

บางครั้งป้ายขนาดคงที่หรือคอมโพเนนต์ UI ต้องการพื้นที่บาร์โค้ดที่กำหนดเฉพาะ นั่นคือเหตุผลที่ **วิธีการสร้าง pdf417** ด้วยคอลัมน์และแถวที่กำหนดเองเป็นสิ่งสำคัญ

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**เหตุผลที่คุณอาจต้องการแบบนี้:**  
- **ความกว้างจำกัด:** ลดจำนวนคอลัมน์และเพิ่มแถวทำให้บาร์โค้ดกว้างแต่สั้นลง เหมาะกับป้ายแคบ  
- **ความสูงจำกัด:** เพิ่มคอลัมน์และลดแถวทำให้บาร์โค้ดสูงแต่แคบ เหมาะเมื่อมีพื้นที่แนวตั้ง

ทั้ง `Columns` และ `Rows` ยอมรับค่าเฉพาะในช่วงที่ระบุในเอกสาร (2‑30 สำหรับคอลัมน์, 1‑90 สำหรับแถว) การใส่ค่าที่อยู่นอกช่วงจะทำให้เกิด `ArgumentOutOfRangeException` ดังนั้นควรตรวจสอบอินพุตของผู้ใช้เสมอหากคุณเปิดเผยการตั้งค่าเหล่านี้ใน UI

## ขั้นตอนที่ 4: วิธีปรับแต่ง PDF417 เพิ่มเติม

นอกจากคอลัมน์และแถวแล้ว สัญลักษณ์ PDF417 ยังมีพารามิเตอร์เลือกหลายอย่าง:

| คุณสมบัติ | วัตถุประสงค์ | ค่าที่พบบ่อย |
|----------|---------------|----------------|
| `ErrorLevel` | ควบคุมความสามารถในการแก้ไขข้อผิดพลาด | 0‑8 (higher = more robust) |
| `MacroPdf417` | เปิดใช้งาน macro PDF417 สำหรับข้อมูลหลายส่วน | `true`/`false` |
| `CompactPdf417` | สร้างบาร์โค้ดที่กะทัดรัดมากขึ้นโดยเสียการแก้ไขข้อผิดพลาดลง | `true`/`false` |
| `SecurityLevel` | เพิ่มเลขตรวจสอบความปลอดภัย | 0‑2 |

ต่อไปนี้คือตัวอย่างสั้นที่ตั้งระดับข้อผิดพลาดเป็นค่าสูงสุด (8) สำหรับสภาพแวดล้อมที่มีสัญญาณรบกวน:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**ทำไมจึงสำคัญ:**  
การแก้ไขข้อผิดพลาดที่สูงขึ้นทำให้สแกนเนอร์สามารถกู้ข้อมูลได้แม้บางส่วนของบาร์โค้ดจะเสียหาย อย่างไรก็ตาม มันจะทำให้ขนาดบาร์โค้ดเพิ่มขึ้น ดังนั้นควรปรับสมดุลการตั้งค่ากับข้อจำกัดการจัดวางของคุณ

## ขั้นตอนที่ 5: ตรวจสอบว่าบาร์โค้ดทำงานได้

หลังจากสร้างไฟล์ PNG แล้ว ให้ทดสอบด้วยแอปสแกนบาร์โค้ดใดก็ได้ (สมาร์ทโฟนส่วนใหญ่มีโปรแกรมอ่าน PDF417 ฟรี) หากสแกนเนอร์คืนข้อความต้นฉบับ (`Custom layout text`) บาร์โค้ดถือว่าถูกต้อง

หากคุณพบปัญหาในการสแกน:

1. **ตรวจสอบมิติ:** ตรวจให้แน่ใจว่าคอลัมน์/แถวอยู่ในช่วงที่อนุญาต  
2. **ปรับระดับข้อผิดพลาด:** เพิ่มค่า `ErrorLevel` สำหรับสื่อที่เสียหาย  
3. **ตรวจสอบคุณภาพภาพ:** บันทึกด้วย DPI สูงกว่า (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) หากคุณวางแผนพิมพ์

## โค้ดต้นฉบับเต็มสำหรับตัวช่วยที่นำกลับมาใช้ใหม่ได้

ด้านล่างเป็นคลาสขนาดกะทัดรัดที่นำกลับมาใช้ใหม่ได้ซึ่งคุณสามารถใส่ลงในโครงการ .NET ใดก็ได้ มันรวม **วิธีการสร้าง pdf417** และ **วิธีการปรับแต่ง pdf417** ไว้ในเมธอดเดียว

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

คุณสามารถเรียกใช้ตัวช่วยนี้ได้ดังนี้:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

เมธอดนี้แยกส่วนโค้ดซ้ำซ้อนออกไป ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจได้

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

- **ค่าที่อยู่นอกช่วง:** ตรวจสอบ `columns` และ `rows` เสมอก่อนกำหนดค่า  
- **รูปแบบภาพไม่ถูกต้อง:** สแกนเนอร์รุ่นเก่าบางรุ่นรับเฉพาะ BMP หรือ JPEG ใช้ `BarCodeImageFormat.Bmp` หากจำเป็น  
- **DPI ต่ำสำหรับการพิมพ์:** DPI เริ่มต้นคือ 96 สำหรับการพิมพ์คุณภาพสูง ให้ตั้งค่า DPI สูงกว่าอย่างชัดเจน (เช่น 300) เมื่อเรียก `Save`  
- **ไม่มีฟอนต์ที่รองรับ:** PDF417 เข้ารหัสข้อมูลไบนารี ดังนั้นโดยทั่วไปไม่จำเป็นต้องระบุฟอนต์ อย่างไรก็ตาม หากคุณวางข้อความบนภาพ ต้องแน่ใจว่าฟอนต์ได้ติดตั้งบนเครื่องเป้าหมาย

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด pdf417** ตั้งแต่ต้นจนจบ, วิธี **สร้าง pdf417** ด้วยการตั้งค่าคอลัมน์/แถวที่กำหนดเอง, และวิธี **ปรับแต่ง pdf417** สำหรับการแก้ไขข้อผิดพลาดและความกะทัดรัด ด้วยการใช้รูปแบบตัวช่วยที่นำกลับมาใช้ใหม่ คุณสามารถสร้างบาร์โค้ดตามความต้องการ ปรับให้เข้ากับข้อจำกัดการจัดวางใดก็ได้ และรับประกันการสแกนที่เชื่อถือได้ในสภาพแวดล้อมการผลิต

**ขั้นตอนต่อไป**

- สำรวจสัญลักษณ์อื่น ๆ เช่น QR หรือ Code128 ด้วยคลาส `BarcodeGenerator` เดียวกัน  
- รวมผลลัพธ์ PNG กับไลบรารีสร้าง PDF (เช่น iText7) เพื่อฝังบาร์โค้ดในใบแจ้งหนี้  
- ทดลองใช้ `MacroPdf417` สำหรับการส่งข้อมูลหลายส่วน ซึ่งเป็นคุณสมบัติที่มีประโยชน์ในแอปพลิเคชันโลจิสติกส์และการขนส่ง

ขอให้เขียนโค้ดอย่างสนุกสนาน และขอให้บาร์โค้ดของคุณสแกนสำเร็จตั้งแต่ครั้งแรก!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด PDF417 ใน C# – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [วิธีสร้างบาร์โค้ดและปรับแต่งบาร์โค้ด PDF417 ใน C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [วิธีสร้างบาร์โค้ด PDF417 และส่งออกเป็น PNG ใน C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}