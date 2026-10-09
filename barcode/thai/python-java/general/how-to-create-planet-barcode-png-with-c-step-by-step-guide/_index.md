---
category: general
date: 2026-09-07
description: สร้างบาร์โค้ดดาวเคราะห์เป็นไฟล์ PNG ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีสร้างภาพบาร์โค้ดดาวเคราะห์โดยใช้
  Aspose.BarCode พร้อมบาร์ที่เต็มและบาร์ที่ว่าง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: th
lastmod: 2026-09-07
og_description: สร้างบาร์โค้ดดาวเคราะห์เป็นไฟล์ PNG ด้วย C# อย่างรวดเร็ว ทำตามคู่มือนี้เพื่อเรียนรู้วิธีสร้างภาพบาร์โค้ดดาวเคราะห์ที่มีแถบเต็มและแถบว่างโดยใช้
  Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: สร้างบาร์โค้ดดาวเคราะห์ PNG ด้วย C# – บทเรียนการเขียนโค้ดครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้าง Planet Barcode PNG ด้วย C# – คู่มือขั้นตอนโดยละเอียด
url: /th/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง Planet Barcode PNG ด้วย C# – คู่มือขั้นตอนต่อขั้นตอน

หากคุณต้องการ **สร้างไฟล์ planet barcode PNG** ด้วย C# คู่มือนี้จะแสดงขั้นตอนที่แน่นอน ไม่ว่าคุณจะกำลังสร้างการผสานรวมบริการไปรษณีย์หรือแดชบอร์ดโลจิสติกส์ คุณจะได้เรียนรู้ **วิธีสร้างภาพ planet barcode** ที่มีทั้งแถบเต็มและแถบว่างโดยใช้ไลบรารี Aspose.BarCode

ในบทเรียนนี้คุณจะได้ทำ:

* ตั้งค่าโฟลเดอร์ปลายทางสำหรับภาพของคุณ  
* กำหนดค่า `BarcodeGenerator` สำหรับสัญลักษณ์ Planet  
* สร้าง PNG ด้วยสไตล์แถบเต็มค่าเริ่มต้น  
* สร้าง PNG ด้วยแถบว่างเพื่อเพิ่มความคมชัดของภาพ  

ไม่ต้องใช้บริการภายนอก—ทุกอย่างทำงานบนเครื่องโดยใช้ .NET 6 หรือใหม่กว่า

## ความต้องการเบื้องต้น

ก่อนเริ่มทำโปรเจกต์ ตรวจสอบให้แน่ใจว่าคุณมี:

| ความต้องการ | ทำไมจึงสำคัญ |
|-------------|----------------|
| .NET 6 SDK (หรือใหม่กว่า) | ให้ runtime สำหรับแอปคอนโซล C# |
| Visual Studio 2022 หรือ VS Code | IDE ใดก็ได้ที่สามารถคอมไพล์โปรเจกต์ C# |
| Aspose.BarCode for .NET (แพ็กเกจ NuGet `Aspose.BarCode`) | มีคลาส `BarcodeGenerator` ที่ใช้ในการเรนเดอร์ Planet barcode |
| สิทธิ์การเขียนในโฟลเดอร์บนดิสก์ | ไฟล์ PNG จะถูกบันทึกลงในตำแหน่งนี้ |

ติดตั้งแพ็กเกจ NuGet ด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: สร้างโปรเจกต์คอนโซลใหม่

เปิดเทอร์มินัลและรัน:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

คำสั่งนี้จะสร้างแอปคอนโซล C# ขั้นพื้นฐานชื่อ **PlanetBarcodeDemo**

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีปลายทาง

โค้ดส่วนแรกนี้จะกำหนดตำแหน่งที่ไฟล์ PNG ที่สร้างขึ้นจะถูกจัดเก็บ คุณสามารถใช้พาธแบบเต็มหรือแบบสัมพันธ์ก็ได้; เพียงแค่ตรวจสอบให้โฟลเดอร์มีอยู่หรือให้โปรแกรมสร้างโฟลเดอร์ให้เอง

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*ทำไมต้องทำขั้นตอนนี้?* การแยกไฟล์ผลลัพธ์ออกจากซอร์สโค้ดช่วยให้โปรเจกต์เป็นระเบียบและหลีกเลี่ยงการเขียนทับโดยบังเอิญ

## ขั้นตอนที่ 3: สร้าง Planet barcode แบบแถบเต็ม

Planet barcode ประกอบด้วยวงกลมศูนย์กลางหลายวง (เติมสีโดยค่าเริ่มต้น) เราจะกำหนดค่า X‑dimension (ความกว้างพิกเซลของแต่ละแถบ) แล้วบันทึกภาพเป็น PNG

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**คำอธิบาย**

* `EncodeTypes.Planet` บอกให้ Aspose ใช้สัญลักษณ์ Planet ซึ่งเป็นที่นิยมในบริการไปรษณีย์  
* `XDimension.Pixels = 4` ให้ขนาดที่ชัดเจนและพิมพ์ได้โดยไม่ต้องสเกลด้วยตนเอง  
* เมธอด `Save` จะเขียนไฟล์ PNG; คุณสามารถเลือก JPEG หรือ BMP ได้โดยเปลี่ยนค่า `BarCodeImageFormat`

## ขั้นตอนที่ 4: สร้าง Planet barcode แบบแถบว่าง

บางครั้งต้องการภาพที่มีแถบว่าง (โปร่งใส) เช่น เมื่อ barcode ถูกวางบนพื้นหลังสี การตั้งค่า `FilledBars` เป็น `false` จะให้สไตล์นี้

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**คำอธิบาย**

* `FilledBars = false` ปิดการเติมสีของวงกลม ทำให้เหลือเพียงเส้นขอบเท่านั้น  
* การตั้งค่าอื่น ๆ (X‑dimension, ข้อความข้อมูล) ยังคงเหมือนเดิม เพื่อให้แน่ใจว่าภาพทั้งสองแสดงข้อมูลเดียวกัน

## ขั้นตอนที่ 5: รันโปรแกรมและตรวจสอบผลลัพธ์

คอมไพล์และรัน:

```bash
dotnet run
```

คุณควรเห็นข้อความในคอนโซลยืนยันการบันทึกไฟล์ และโฟลเดอร์ `Barcodes` จะมี:

* `PostalPlanetFilledBars.png` – Planet barcode แบบแถบเต็มคลาสสิก  
* `PostalPlanetEmptyBars.png` – ข้อมูลเดียวกันแต่แสดงด้วยแถบว่าง  

เปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้ ทั้งสองภาพเข้ารหัสสตริงตัวเลข **123456** และสามารถสแกนด้วยเครื่องอ่าน barcode ของไปรษณีย์มาตรฐานได้

## คำถามทั่วไปและการจัดการกรณีขอบ

### ถ้าต้องการรูปแบบข้อมูลอื่น?

Planet barcode รองรับสตริงตัวเลขสูงสุด 12 หลัก หากใส่ค่าที่ไม่ใช่ตัวเลข Aspose จะโยน `ArgumentException` ตรวจสอบอินพุตก่อนสร้าง generator:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### จะปรับขนาดภาพโดยไม่เปลี่ยนความหนาของแถบอย่างไร?

ใช้คุณสมบัติ `Resolution` หรือสเกลบิตแมปที่บันทึกแล้ว:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### สามารถสร้างรูปแบบภาพอื่นได้หรือไม่?

ได้ เพียงเปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Jpeg`, `Bmp` หรือ `Gif` API รองรับฟอร์แมตเรสเตอร์ทั่วไปทั้งหมด

### จะปรับสีได้อย่างไร?

ตั้งค่า `BarColor` และ `BackColor` บนพารามิเตอร์ของ `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

ตัวเลือกเหล่านี้ทำงานได้ทั้งเวอร์ชันแถบเต็มและแถบว่าง

## เคล็ดลับสำหรับการใช้งานในโปรดักชัน

* **แคช generator** เมื่อจำเป็นต้องเรนเดอร์ barcode จำนวนมากด้วยการตั้งค่าเดียวกัน—การสร้างอ็อบเจ็กต์ซ้ำหลายครั้งจะเพิ่มภาระงาน  
* **Dispose** อ็อบเจ็กต์ `BarcodeGenerator` หากสร้างหลายอันในลูป (พวกมัน implements `IDisposable`)  
* **ตรวจสอบโฟลเดอร์ปลายทาง** ตั้งแต่ต้นเพื่อหลีกเลี่ยงข้อยกเว้นเวลารันบนไดเรกทอรีที่ป้องกันการเขียน

## สรุป

ตอนนี้คุณรู้วิธี **สร้างไฟล์ planet barcode PNG** ด้วย C# และเข้าใจ **วิธีสร้างภาพ planet barcode** ทั้งแบบแถบเต็มและแถบว่าง ตัวอย่างที่สมบูรณ์และสามารถรันได้แสดงการตั้งค่าโฟลเดอร์ผลลัพธ์, การกำหนดค่า `BarcodeGenerator` และการบันทึกผลเป็นไฟล์ PNG

ต่อไปคุณอาจสนใจ:

* เพิ่ม **ข้อความที่อ่านได้โดยมนุษย์** ใต้ barcode (`planetFilled.Parameters.Caption.Visible = true`)  
* นำ PNG ที่สร้างไปใส่ใน **ใบแจ้งหนี้ PDF** ด้วย Aspose.PDF  
* สลับไปใช้สัญลักษณ์ไปรษณีย์อื่น ๆ เช่น **IMB** หรือ **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`)  

อย่าลังเลที่จะทดลองปรับความหนาของแถบ, สี, และความละเอียดของภาพให้ตรงกับความต้องการของแอปพลิเคชันของคุณ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณเอง

- [สร้างภาพ Planet Barcode ใน C# – วิธีสร้าง Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [สร้าง Planet Barcode ใน C# – คู่มือเต็มขั้นตอน](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [สร้าง PNG Barcode ด้วย Aspose.BarCode for .NET: แถบเต็มแบบมิติเดียว](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}