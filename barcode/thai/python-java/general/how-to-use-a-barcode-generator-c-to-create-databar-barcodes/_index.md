---
category: general
date: 2026-09-07
description: บทเรียนการสร้างบาร์โค้ดด้วย C# ที่แสดงวิธีการสร้างไฟล์ PNG ของบาร์โค้ดและสร้างบาร์โค้ด
  DataBar พร้อมแถวและคอลัมน์ที่ปรับแต่งได้
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: th
lastmod: 2026-09-07
og_description: 'บทเรียนสร้างบาร์โค้ดด้วย C#: เรียนรู้การสร้างไฟล์ PNG ของบาร์โค้ดและสร้างบาร์โค้ด
  DataBar ด้วยแถวและคอลัมน์ที่กำหนดเองในเวลาเพียงไม่กี่นาที'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: เครื่องสร้างบาร์โค้ด C# – สร้างบาร์โค้ด DataBar และภาพ PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: วิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด DataBar
url: /th/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ barcode generator C# เพื่อสร้าง DataBar barcodes

หากคุณต้องการ **barcode generator C#** สำหรับสร้างบาร์โค้ดคุณภาพสูง คู่มือนี้จะแสดงวิธี **generate barcode PNG** ไฟล์และ **create DataBar barcodes** ด้วยแถวและคอลัมน์ที่กำหนดเอง ไม่ว่าคุณจะกำลังสร้างระบบจัดการสินค้าปลีกหรือแพลตฟอร์มจำหน่ายบัตร ขั้นตอนต่อไปนี้จะช่วยให้คุณผลิต DataBar Expanded Stacked barcode ได้ในตัวอย่างเดียวที่สมบูรณ์แบบ

ในบทเรียนนี้คุณจะได้เรียนรู้:

* วิธีสร้างอินสแตนซ์ `BarcodeGenerator` สำหรับสัญลักษณ์ DataBar Expanded Stacked  
* วิธีปรับค่าคอลัมน์และแถวให้สอดคล้องกับข้อกำหนด ISO / GS1  
* วิธีบันทึกผลลัพธ์เป็นภาพ PNG ที่สามารถฝังในหน้าเว็บหรือพิมพ์บนฉลากได้  

ไม่ต้องใช้บริการภายนอก—เพียงแค่ไลบรารี Aspose.BarCode for .NET (หรือไลบรารีที่เข้ากันได้ซึ่งใช้ API เดียวกัน) โค้ดทำงานบน .NET 6+ และทำงานได้ใน Visual Studio, Rider หรือ IDE ใด ๆ ที่รองรับ C#

## ความต้องการเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6 SDK หรือรุ่นที่ใหม่กว่า  
* การอ้างอิงไปยังแพคเกจ NuGet `Aspose.BarCode` (หรือไลบรารีที่ให้ `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`)  
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และโครงสร้างโปรเจกต์  

คุณสามารถเพิ่มแพคเกจผ่านบรรทัดคำสั่ง:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: เริ่มต้น barcode generator C# สำหรับ DataBar Expanded Stacked

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarcodeGenerator` ที่กำหนดสัญลักษณ์ **DataBar Expanded Stacked** วัตถุนี้จะเก็บพารามิเตอร์การเรนเดอร์ทั้งหมด รวมถึงข้อความที่ต้องเข้ารหัส

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**ทำไมจึงสำคัญ:** ค่าคงที่ `EncodeTypes.DatabarExpandedStacked` บอกไลบรารีว่าต้องใช้มาตรฐานบาร์โค้ดใด การใช้ enum ที่ถูกต้องจะทำให้ภาพที่สร้างขึ้นสอดคล้องกับข้อกำหนด GS1 DataBar

## ขั้นตอนที่ 2: ตั้งค่าจำนวนคอลัมน์ (ใช้ค่าแถวเริ่มต้น)

DataBar Expanded Stacked สามารถแบ่งเป็นหลายคอลัมน์ การปรับจำนวนคอลัมน์จะเปลี่ยนความหนาแน่นของภาพและช่วยให้ข้อมูลยาวสามารถใส่ในพื้นที่จำกัดได้

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**เคล็ดลับ:** ค่าเริ่มต้นของคอลัมน์คือ 1 การตั้งค่าเป็น 4 จะสร้างคอลัมน์ซ้อนกันสี่คอลัมน์ ซึ่งเหมาะกับสตริงตัวเลขยาวขณะยังคงความสูงของบาร์โค้ดอยู่ในระดับที่จัดการได้

## ขั้นตอนที่ 3: Generate barcode PNG ด้วยการตั้งค่าคอลัมน์ที่กำหนด

ต่อไปบันทึกบาร์โค้ดเป็นไฟล์ PNG PNG จะรักษาขอบคมที่สแกนเนอร์ต้องการและทำงานได้ดีทั้งบนเว็บและสื่อพิมพ์

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

ไฟล์ `DatabarCols4.png` มี **barcode PNG** ที่คุณสามารถฝังโดยตรงใน HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## ขั้นตอนที่ 4: สร้างอินสแตนซ์ generator แยกต่างหากสำหรับการตั้งค่าแถว

หากคุณต้องการควบคุมจำนวนแถวแทนคอลัมน์ ให้สร้าง `BarcodeGenerator` ใหม่ การใช้อินสแตนซ์เดิมหลังจากเปลี่ยนมิติอาจทำให้เกิดข้อบกพร่องของเลย์เอาต์ได้ ดังนั้นการสร้างออบเจกต์ใหม่เป็นวิธีที่ปลอดภัยที่สุด

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## ขั้นตอนที่ 5: ตั้งค่าจำนวนแถว (ใช้คอลัมน์เริ่มต้น)

แถวจะส่งผลต่อการซ้อนกันในแนวตั้งของโมดูลบาร์โค้ด การเพิ่มจำนวนแถวทำให้บาร์โค้ดสูงขึ้น ซึ่งอาจจำเป็นสำหรับขนาดฉลากบางประเภท

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**ทำไมต้องแถว vs. คอลัมน์:** คอลัมน์แบ่งบาร์โค้ดในแนวนอน ส่วนแถวขยายแนวตั้ง เลือกทิศทางที่เหมาะกับการจัดวางฉลากของคุณที่สุด

## ขั้นตอนที่ 6: Generate barcode PNG ด้วยการตั้งค่าแถวที่กำหนด

สุดท้ายบันทึกบาร์โค้ดที่ปรับแถวเป็นไฟล์ PNG

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์ที่แตกต่างกัน:

* `DatabarCols4.png` – 4 คอลัมน์, 1 แถว  
* `DatabarRows3.png` – 1 คอลัมน์, 3 แถว  

ภาพทั้งสองพร้อมใช้งานทันทีในแอปพลิเคชัน, รายงาน หรือฉลากที่พิมพ์

## วิธี generate barcode PNG files ใน C# ด้วยขนาดกำหนดเอง

รูปแบบที่แสดงด้านบนสามารถนำไปใช้ซ้ำได้กับ DataBar ใด ๆ หรือสัญลักษณ์อื่นที่ไลบรารีรองรับ นี่คือตัวอย่างเทมเพลตสั้น ๆ ที่คุณสามารถคัดลอก‑วางลงในคลาสยูทิลิตี้ได้

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

เรียกเมธอดดังนี้:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**กรณีที่ต้องพิจารณา**

* **ความยาวข้อมูล** – DataBar Expanded Stacked สามารถเข้ารหัสได้สูงสุด 74 ตัวอักษรตัวเลข หากเกินขีดจำกัดจะเกิดข้อยกเว้น ตรวจสอบความยาวอินพุตก่อนเรียก generator  
* **มิติที่ไม่ถูกต้อง** – ไลบรารีจำกัดคอลัมน์ที่ 1‑4 และแถวที่ 1‑3 สำหรับสัญลักษณ์นี้ การใส่ค่านอกช่วงนี้จะถูกละเว้นหรือทำให้เกิดข้อผิดพลาด  
* **DPI ของภาพ** – หากต้องการความละเอียดสูงสำหรับการพิมพ์ ให้ตั้งค่า `generator.Parameters.ImageResolution` ก่อนบันทึก

## ผลลัพธ์ที่คาดหวัง

เมื่อคุณเปิด `DatabarCols4.png` หรือ `DatabarRows3.png` คุณควรเห็น DataBar barcode ที่คมชัดและคอนทราสต์สูง การสแกนภาพด้วยสแกนเนอร์ที่รองรับ GS1 จะคืนค่าข้อความต้นฉบับ `"Databar Expanded Stacked long"`  

![ตัวอย่าง DataBar Expanded Stacked barcode ที่บันทึกเป็น PNG ด้วย barcode generator C#](image.png)

*Alt text: ตัวอย่าง DataBar Expanded Stacked barcode ที่บันทึกเป็น PNG ด้วย barcode generator C#*

## สรุป

บทเรียนนี้แสดงให้เห็นว่า **barcode generator C#** สามารถใช้เพื่อ **create DataBar barcodes** และ **generate barcode PNG** พร้อมการตั้งค่าแถวและคอลัมน์แบบกำหนดเองได้อย่างไร โดยทำตามหกขั้นตอน—เริ่มต้น generator, ตั้งค่าคอลัมน์หรือแถว, แล้วบันทึกเป็น PNG—คุณจะได้ภาพพร้อมใช้งานในระดับการผลิต เหมาะสำหรับระบบสินค้าคงคลัง, ระบบจำหน่ายบัตร, หรือสถานการณ์ใด ๆ ที่ต้องการการเรนเดอร์บาร์โค้ดที่เชื่อถือได้

ต่อไปคุณอาจอยากสำรวจ:

* เพิ่มสีหรือภาพพื้นหลังให้กับ PNG (ยังคงเข้ากันได้กับสแกนเนอร์ส่วนใหญ่)  
* ใช้สัญลักษณ์อื่น ๆ เช่น QR, Code 128, หรือ PDF417 ผ่าน API `BarcodeGenerator` เดียวกัน  
* ฝัง PNG ที่สร้างขึ้นโดยตรงในมุมมอง ASP.NET Core MVC หรือคอมโพเนนต์ Blazor  

ลองทดลองกับสตริงข้อมูล, ขนาด, และรูปแบบภาพต่าง ๆ (เช่น JPEG, BMP) ได้เลย รูปแบบเดียวกันนี้ใช้ได้กับ **barcode generator C#** ทำให้เป็นเครื่องมืออเนกประสงค์ในกล่องเครื่องมือของนักพัฒนา .NET ทุกคน ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดตัวอย่างทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้ในโปรเจกต์ของคุณเอง

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}