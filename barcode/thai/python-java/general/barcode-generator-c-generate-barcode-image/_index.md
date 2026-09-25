---
category: general
date: 2026-08-03
description: บทเรียนการสร้างบาร์โค้ดด้วย C# แสดงวิธีสร้างภาพบาร์โค้ดด้วย Aspose.BarCode
  ตั้งค่าคอลัมน์และแถว และบันทึกไฟล์ PNG สำหรับ DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: th
lastmod: 2026-08-03
og_description: บทแนะนำการสร้างบาร์โค้ดด้วย C# อธิบายวิธีสร้างภาพบาร์โค้ดโดยใช้ Aspose.BarCode,
  ตั้งค่าคอลัมน์และแถวของ DataBar Expanded Stacked, และบันทึกเป็นไฟล์ PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: เครื่องสร้างบาร์โค้ด C# – คู่มือขั้นตอนต่อขั้นตอนในการสร้างภาพบาร์โค้ด
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: เครื่องสร้างบาร์โค้ด C# – สร้างภาพบาร์โค้ด
url: /th/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวสร้างบาร์โค้ด C# – สร้างภาพบาร์โค้ด

หากคุณต้องการตัวสร้างบาร์โค้ด C# ที่สามารถสร้างภาพบาร์โค้ดสำหรับ DataBar Expanded Stacked คู่มือนี้จะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เรียนรู้วิธีกำหนดค่าคอลัมน์และแถว, บันทึกผลลัพธ์เป็น PNG, และปรับโค้ดสำหรับสัญลักษณ์อื่น ๆ

การสร้างภาพบาร์โค้ดโดยโปรแกรมช่วยลดขั้นตอนที่ทำด้วยมือและทำให้ได้ผลลัพธ์ที่สม่ำเสมอในใบแจ้งหนี้, ป้ายจัดส่ง, และระบบสินค้าคงคลัง คู่มือนี้ครอบคลุมทุกสิ่งที่คุณต้องการ ตั้งแต่การตั้งค่าโครงการจนถึงโค้ดต้นฉบับเต็ม เพื่อให้คุณสามารถรันตัวอย่างได้ทันที

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า ที่ติดตั้งแล้ว  
* IDE เช่น Visual Studio 2022 (หรือเครื่องมือแก้ไขใด ๆ ที่รองรับ C#)  
* ไลเซนส์สำหรับ **Aspose.BarCode for .NET** – สามารถใช้รุ่นทดลองฟรีสำหรับการทดสอบ  
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#  

หากมีรายการใดขาดหาย ให้ติดตั้ง .NET SDK จาก dotnet.microsoft.com และรับแพ็กเกจ Aspose.BarCode NuGet ด้วย:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: สร้างโครงการตัวสร้างบาร์โค้ด C# 

สร้างแอปพลิเคชันคอนโซลใหม่และเพิ่ม `using` directives ที่จำเป็น:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

คลาส `BarcodeGenerator` คือหัวใจของ API ตัวสร้างบาร์โค้ด C# มันรับประเภทสัญลักษณ์และข้อความที่ต้องเข้ารหัส

## ขั้นตอนที่ 2: สร้างบาร์โค้ด DataBar Expanded Stacked และกำหนดคอลัมน์

ตัวอย่างแรกสร้างบาร์โค้ดที่มีสี่คอลัมน์ การปรับค่า `Columns` จะเปลี่ยนความหนาแน่นของสัญลักษณ์ DataBar Expanded Stacked

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**ทำไมเรื่องนี้ถึงสำคัญ:** จำนวนคอลัมน์มีผลต่อปริมาณข้อมูลที่สามารถเก็บในพื้นที่กะทัดรัด การตั้งค่าเป็น 4 จะทำให้บาร์โค้ดกว้างขึ้นแต่ยังคงอ่านได้โดยสแกนเนอร์ส่วนใหญ่

## ขั้นตอนที่ 3: สร้างบาร์โค้ดด้วยจำนวนแถวที่กำหนดเอง

ตัวอย่างที่สองแสดงวิธีควบคุมการจัดวางแนวตั้งโดยตั้งค่า `Rows` การกำหนดค่าเป็นสามแถวเป็นประโยชน์เมื่อคุณต้องการบาร์โค้ดที่สูงขึ้นเพื่อใช้พื้นที่แนวนอนที่จำกัด

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**ทำไมเรื่องนี้ถึงสำคัญ:** การปรับแถวช่วยให้คุณใส่บาร์โค้ดลงในคอลัมน์แคบ ๆ ขณะยังคงความอ่านได้ ตัวสร้างบาร์โค้ด C# จะคำนวณขนาดโมดูลใหม่อัตโนมัติเพื่อให้สอดคล้องกับสเปค

## ขั้นตอนที่ 4: ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมที่รวมขั้นตอนก่อนหน้าไว้ในไฟล์เดียว คัดลอกโค้ดไปยัง `Program.cs` แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางโฟลเดอร์ที่มีอยู่แล้ว แล้วรันแอปพลิเคชัน

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อคุณรันโปรแกรม จะมีไฟล์ PNG สองไฟล์ปรากฏในโฟลเดอร์เป้าหมาย:

* **DatabarCols4.png** – บาร์โค้ด DataBar Expanded Stacked ที่มีสี่คอลัมน์  
* **DatabarRows3.png** – ข้อมูลเดียวกันที่เข้ารหัสในสามแถว  

เปิดภาพด้วยโปรแกรมดูรูปใดก็ได้; ภาพจะแสดงบาร์โค้ดที่คมชัดและสแกนได้ พร้อมสำหรับการพิมพ์หรือฝังในไฟล์ PDF

## วิธีสร้างภาพบาร์โค้ดด้วยขนาดกำหนดเอง

หากคุณต้องการขนาดภาพเฉพาะ ให้ปรับคุณสมบัติ `ImageHeight` และ `ImageWidth` ก่อนเรียก `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

การเปลี่ยนขนาดไม่ส่งผลต่อข้อมูลที่เข้ารหัส; เพียงแค่ปรับสเกลการแสดงผล เทคนิคนี้มีประโยชน์เมื่อผสานบาร์โค้ดเข้ากับคอมโพเนนต์ UI ที่มีข้อจำกัดการจัดวางคงที่

## ปัญหาที่พบบ่อยและเคล็ดลับระดับมืออาชีพ

* **ตัวคั่นเส้นทาง:** ใช้สตริงแบบ verbatim (`@"C:\Path\file.png"`) หรือ `Path.Combine` เพื่อหลีกเลี่ยงปัญหาอักขระ escape บน Windows  
* **การบังคับใช้ไลเซนส์:** หากไม่มีไลเซนส์ที่ถูกต้อง ภาพที่สร้างจะมีลายน้ำ ใส่ไลเซนส์ของคุณตั้งแต่ต้นในแอปพลิเคชัน:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **ขีดจำกัดการเข้ารหัส:** DataBar Expanded Stacked รองรับได้สูงสุด 74 ตัวอักษรตัวเลข การเกินขีดจำกัดจะทำให้เกิดข้อยกเว้น ตรวจสอบความยาวอินพุตก่อนสร้างตัวสร้าง  
* **ประสิทธิภาพ:** การใช้ `BarcodeGenerator` ตัวเดียวสำหรับการบันทึกหลายครั้งช่วยลดการจัดสรรหน่วยความจำ ให้เปลี่ยนคุณสมบัติ `Rows` หรือ `Columns` ระหว่างการบันทึกเท่านั้น หากข้อความที่เข้ารหัสยังคงเดิม

## ขั้นตอนต่อไป

ตอนนี้คุณสามารถสร้างภาพบาร์โค้ดด้วยตัวสร้างบาร์โค้ด C# แล้ว ลองสำรวจต่อไปนี้:

* **สัญลักษณ์ต่าง ๆ** – ลอง `EncodeTypes.QR`, `EncodeTypes.Code128`, หรือ `EncodeTypes.Pdf417`  
* **การปรับสี** – ตั้งค่า `Parameters.Barcode.ForeColor` และ `BackColor` ให้ตรงกับแบรนด์ของคุณ  
* **การฝังใน PDF** – ผสาน PNG ที่สร้างกับ Aspose.PDF เพื่อสร้างเอกสารที่พิมพ์ได้  

ส่วนขยายเหล่านี้จะช่วยให้คุณสร้างโซลูชันบาร์โค้ดครบวงจรสำหรับการจัดการสินค้าคงคลัง, โลจิสติกส์, หรือการค้าปลีก

---

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณ

- [สร้างภาพบาร์โค้ด – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [สร้างภาพบาร์โค้ด DotCode – แถวและคอลัมน์ (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}