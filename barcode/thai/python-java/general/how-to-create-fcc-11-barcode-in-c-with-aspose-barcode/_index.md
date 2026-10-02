---
category: general
date: 2026-08-22
description: สร้างบาร์โค้ด FCC 11 ด้วย C# โดยใช้ Aspose.BarCode เรียนรู้โค้ดแบบขั้นตอนต่อขั้นตอน
  กำหนดขนาด และสร้างภาพ PNG สำหรับ Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: th
lastmod: 2026-08-22
og_description: สร้างบาร์โค้ด FCC 11 ด้วย C# และ Aspose.BarCode. ทำตามบทแนะนำสั้น
  ๆ นี้เพื่อสร้างบาร์โค้ด PNG สำหรับ Australia Post รวมถึงรุ่น FCC 59 และ FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: สร้างบาร์โค้ด FCC 11 ด้วย C# – คู่มือ Aspose.BarCode ฉบับเต็ม
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: วิธีสร้างบาร์โค้ด FCC 11 ด้วย C# และ Aspose.BarCode
url: /th/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด FCC 11 ด้วย C# และ Aspose.BarCode

หากคุณต้องการ **สร้างบาร์โค้ด FCC 11** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงโค้ดที่จำเป็นอย่างละเอียด คุณจะได้เห็นวิธีกำหนดขนาดของบาร์โค้ด เลือกตารางการเข้ารหัสที่เหมาะสม และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ด Australia Post เป็นความต้องการทั่วไปสำหรับโลจิสติกส์ ระบบการส่งจดหมาย และการติดตามสินค้าคงคลัง บทเรียนนี้ครอบคลุมรูปแบบ FCC 11 และยังสาธิตวิธีสร้างบาร์โค้ด FCC 59 และ FCC 62 ด้วยตารางการเข้ารหัสที่แตกต่างกัน เพื่อให้คุณสามารถใช้รูปแบบเดียวกันกับบริการไปรษณีย์อื่น ๆ ได้

## สิ่งที่คุณต้องเตรียม

ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือเวอร์ชันใหม่กว่า ที่ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE ที่รองรับ C# ใด ๆ)  
* ใบอนุญาตที่ถูกต้องสำหรับ **Aspose.BarCode for .NET** – รุ่น community ใช้สำหรับการประเมินผลได้  
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก  

ข้อกำหนดเบื้องต้นเหล่านี้รับประกันว่าโค้ดจะคอมไพล์และทำงานได้โดยไม่มีการกำหนดค่าเพิ่มเติม

## ขั้นตอนที่ 1: ติดตั้งแพคเกจ Aspose.BarCode NuGet

เปิดเทอร์มินัลในโฟลเดอร์โครงการและรันคำสั่ง:

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่มเวอร์ชันที่เสถียรล่าสุดของไลบรารีลงในไฟล์โครงการของคุณ แพคเกจนี้ประกอบด้วยคลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียนนี้

## ขั้นตอนที่ 2: กำหนดโฟลเดอร์สำหรับผลลัพธ์

สร้างโฟลเดอร์ที่ภาพที่สร้างขึ้นจะถูกจัดเก็บ พาธสามารถเป็นแบบเต็มหรือแบบสัมพันธ์กับไฟล์ปฏิบัติการได้

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` ทำให้แน่ใจว่าโฟลเดอร์มีอยู่แล้ว ป้องกันข้อผิดพลาดขณะรันไทม์เมื่อเมธอด `Save` เขียนไฟล์

## ขั้นตอนที่ 3: สร้างบาร์โค้ด FCC 11

รูปแบบ FCC 11 เป็นการเข้ารหัสเริ่มต้นสำหรับบาร์โค้ดไปรษณีย์ของ Australia Post โค้ดต่อไปนี้จะสร้างบาร์โค้ดที่เข้ารหัสสตริงตัวเลข `1101234567`

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**ทำไมวิธีนี้ถึงได้ผล:**  
* `EncodeTypes.AustraliaPost` บอกไลบรารีให้ใช้กฎการเข้ารหัสของ Australia Post  
* สตริงข้อมูล `1101234567` ปฏิบัติตามสเปค FCC 11: สองหลักแรก (`11`) ระบุรูปแบบ ตามด้วยอ้างอิงลูกค้า 7 หลัก  
* `XDimension` และ `BarHeight` ควบคุมขนาดของบาร์โค้ดที่พิมพ์ ซึ่งสำคัญต่อการอ่านของสแกนเนอร์  

หลังจากรันโปรแกรม คุณจะพบไฟล์ `PostalAustraliaPostFCC11.png` ในโฟลเดอร์ `Barcodes` รูปภาพจะมีลักษณะดังนี้:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## ขั้นตอนที่ 4: สร้างบาร์โค้ด Australia Post เพิ่มเติม (ไม่บังคับ)

แม้วัตถุประสงค์หลักจะเป็นการ **สร้างบาร์โค้ด FCC 11** คุณมักต้องการบาร์โค้ด FCC 59 หรือ FCC 62 สำหรับประเภทจดหมายที่ต่างกัน โค้ดด้านล่างใช้อินสแตนซ์ `BarcodeGenerator` เดียวกัน เพียงเปลี่ยนสตริงข้อมูลและตารางการเข้ารหัสที่เป็นตัวเลือก

### 4.1 FCC 59 ด้วยการเข้ารหัส N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 ด้วยการเข้ารหัส N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 ด้วยการเข้ารหัส C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 ด้วยการเข้ารหัส Other

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

ภาพสี่ภาพจะถูกบันทึกเคียงข้างกันในโฟลเดอร์เดียวกัน ทำให้เปรียบเทียบความแตกต่างของภาพได้ง่าย

## ขั้นตอนที่ 5: ทำความเข้าใจตารางการเข้ารหัส

Australia Post กำหนดตารางการเข้ารหัสสามประเภท:

* **N‑Table** – แปลข้อมูลลูกค้าเป็นตัวเลข ใช้เมื่อข้อมูลมีเฉพาะตัวเลขเท่านั้น  
* **C‑Table** – รองรับอักขระตัวอักษรและตัวเลข มีประโยชน์สำหรับหมายเลขอ้างอิงที่มีตัวอักษร  
* **Other** – ตัวสำรองสำหรับรูปแบบข้อมูลที่กำหนดเองหรือขยายเพิ่มเติม  

การเลือกตารางที่ถูกต้องทำให้สแกนเนอร์บาร์โค้ดถอดรหัสข้อมูลได้ตรงตามที่ต้องการ หากคุณละเว้นคุณสมบัติ `AustralianPostEncodingTable` ไลบรารีจะใช้ค่าเริ่มต้นเป็น N‑Table ซึ่งอาจตัดอักขระที่ไม่ใช่ตัวเลขออก

## เคล็ดลับ, กรณีขอบ, และข้อผิดพลาดทั่วไป

| Situation | Recommended approach |
|-----------|----------------------|
| ความยาวของสตริงข้อมูลสั้นกว่าที่ต้องการ | เติมส่วนตัวเลขด้วยศูนย์นำหน้าเพื่อให้ตรงตามสเปค FCC |
| บาร์โค้ดดูเบลอเมื่อพิมพ์ | เพิ่มค่า `XDimension` เป็น 5 หรือ 6 พิกเซลและตรวจสอบการตั้งค่า DPI ของเครื่องพิมพ์ |
| สแกนเนอร์คืนค่า “invalid format” | ตรวจสอบว่าตารางการเข้ารหัสที่เลือก (N‑Table, C‑Table, Other) ตรงกับข้อมูลที่ส่ง |
| ทำงานบน Linux โดยไม่มี GUI | ตรวจสอบให้มีการอ้างอิงแพคเกจ `System.Drawing.Common` หรือใช้เมธอด `Save` กับ `BarCodeImageFormat.Png` ซึ่งไม่ต้องการคอนเท็กซ์การแสดงผล |
| ต้องการรูปแบบภาพอื่น | เปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Tiff` ตามต้องการ |

เคล็ดลับเชิงปฏิบัติเหล่านี้มาจากการใช้งานจริงของโซลูชันบาร์โค้ดไปรษณีย์

## ตัวอย่างที่สามารถรันได้เต็มรูปแบบ

ด้านล่างเป็นโปรแกรมที่ทำงานได้เองซึ่งคุณสามารถคัดลอกไปยังโปรเจกต์คอนโซลใหม่ (`dotnet new console`) และรันได้โดยไม่ต้องแก้ไข



## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการใช้งานอื่น ๆ ในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด java – บาร์โค้ด Australia Post ด้วย Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [สร้าง One-Dimensional Databar การเข้ารหัส GS1 ด้วย Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [วิธีสร้าง quiet zone ของบาร์โค้ด .NET สำหรับ Code 16K ด้วย Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}