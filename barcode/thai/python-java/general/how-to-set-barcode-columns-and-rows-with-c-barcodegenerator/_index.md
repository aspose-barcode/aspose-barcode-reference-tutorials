---
category: general
date: 2026-09-16
description: เรียนรู้วิธีตั้งค่าคอลัมน์บาร์โค้ดใน C# โดยใช้ BarcodeGenerator และตั้งค่าแถวบาร์โค้ดสำหรับ
  DataBar Expanded Stacked barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: th
lastmod: 2026-09-16
og_description: ตั้งค่าคอลัมน์บาร์โค้ดใน C# อย่างรวดเร็ว คู่มือนี้จะแสดงวิธีการกำหนดค่าคอลัมน์
  แถว และรูปแบบภาพด้วย BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: ตั้งค่าคอลัมน์และแถวของบาร์โค้ดใน C# – คู่มือ BarcodeGenerator อย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีตั้งค่าคอลัมน์และแถวของบาร์โค้ดด้วย C# BarcodeGenerator
url: /th/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าคอลัมน์และแถวของบาร์โค้ดด้วย C# BarcodeGenerator

หากคุณต้องการตั้งค่าคอลัมน์ของบาร์โค้ดในแอปพลิเคชัน C# บทแนะนำนี้จะแสดงขั้นตอนที่ต้องทำอย่างละเอียด คุณจะได้เห็นวิธีกำหนดทั้งคอลัมน์และแถวสำหรับบาร์โค้ด DataBar Expanded Stacked แล้วบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ดโดยอัตโนมัติช่วยให้คุณหลีกเลี่ยงการออกแบบด้วยมือและรับประกันความสม่ำเสมอในรายงาน ใบแจ้งหนี้ และป้ายสินค้า ตัวอย่างด้านล่างครอบคลุมกระบวนการทำงานทั้งหมด ตั้งแต่การติดตั้งไลบรารีจนถึงการสร้างภาพสองภาพ—หนึ่งที่มีจำนวนคอลัมน์ที่กำหนดเองและอีกหนึ่งที่มีจำนวนแถวที่กำหนดเอง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 หรือใหม่กว่า
* การอ้างอิงไปยังแพคเกจ **Aspose.BarCode for .NET** บน NuGet ติดตั้งด้วยคำสั่ง:

```bash
dotnet add package Aspose.BarCode
```

* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG ที่สร้างจะถูกบันทึก

ข้อกำหนดเหล่านี้ทำให้โค้ดคอมไพล์และทำงานได้โดยไม่ต้องตั้งค่าเพิ่มเติม

## วิธีตั้งค่าคอลัมน์ของบาร์โค้ดใน C#

ขั้นตอนสำคัญแรกคือการสร้างอินสแตนซ์ `BarcodeGenerator` สำหรับสัญลักษณ์ **DataBar Expanded Stacked** และกำหนดจำนวนคอลัมน์ที่ต้องการ

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมวิธีนี้ถึงได้ผล:**  
`EncodeTypes.DatabarExpandedStacked` บอกไลบรารีว่าต้องเรนเดอร์สัญลักษณ์ใด การตั้งค่า `Parameters.Barcode.DataBar.Columns` จะเปลี่ยนการจัดวางโมดูลภายใน ซึ่งส่งผลโดยตรงต่อความกว้างของบาร์โค้ดเมธอด `Save` จะเขียนภาพลงดิสก์ในรูปแบบ `BarCodeImageFormat` ที่ระบุ

### ผลลัพธ์ที่คาดหวัง
เปิด `C:\Barcodes\DatabarCols4.png` ด้วยโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ด DataBar Expanded Stacked ที่กว้างกว่าปกติ เนื่องจากใช้สี่คอลัมน์

## วิธีตั้งค่าแถวของบาร์โค้ดใน C#

หลังจากบันทึกภาพที่ตั้งค่าตามคอลัมน์แล้ว คุณอาจต้องการบาร์โค้ดที่มีความสูงแตกต่างโดยปรับแถว กระบวนการคล้ายกับการตั้งค่าคอลัมน์ แต่ใช้คุณสมบัติ `Rows` แทน

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมวิธีนี้ถึงได้ผล:**  
การสร้างตัวสร้างใหม่ทำให้การตั้งค่าคอลัมน์ก่อนหน้าไม่ส่งผลต่อการกำหนดค่าแถว การเปลี่ยน `Parameters.Barcode.DataBar.Rows` จะปรับความสูงของบาร์โค้ด ทำให้ภาพสูงขึ้นเมื่อจำนวนแถวเกินค่าปกติ

### ผลลัพธ์ที่คาดหวัง
เปิด `C:\Barcodes\DatabarRows3.png` บาร์โค้ดจะดูสูงขึ้น แสดงการตั้งค่าแถวสามแถว

## ตัวอย่างเต็มขั้นตอนจากต้นจนจบ

ด้านล่างเป็นโปรแกรมเดียวที่สร้างภาพทั้งสองภาพในการรันครั้งเดียว การเก็บโค้ดไว้ในไฟล์เดียวแสดงให้เห็นว่าคุณสามารถสลับระหว่างการตั้งค่าคอลัมน์และแถวโดยไม่ต้องรีสตาร์ทแอปพลิเคชัน

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

การรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์:

* **DatabarCols4.png** – บาร์โค้ดที่มีสี่คอลัมน์  
* **DatabarRows3.png** – บาร์โค้ดที่มีสามแถว

ไฟล์ทั้งสองใช้ **รูปแบบภาพบาร์โค้ด** PNG ซึ่งรักษาขอบคมและรองรับการบีบอัดแบบไม่มีการสูญเสีย—เหมาะสำหรับการพิมพ์และการแสดงผลดิจิทัล

## คำถามที่พบบ่อยและเคล็ดลับ

| คำถาม | คำตอบ |
|----------|--------|
| *ฉันสามารถใช้ JPEG แทน PNG ได้หรือไม่?* | ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg`. JPEG มีขนาดไฟล์เล็กลงแต่จะเกิด artefacts จากการบีบอัด ซึ่งอาจส่งผลต่อความแม่นยำของสแกนเนอร์ |
| *จำนวนคอลัมน์หรือแถวสูงสุดคือเท่าไหร่?* | ไลบรารีจะตรวจสอบค่าตามสเปคของ DataBar ค่าที่อยู่นอกช่วงที่กำหนดจะทำให้เกิด `ArgumentException`. ตรวจสอบเอกสาร Aspose.BarCode เพื่อดูขีดจำกัดที่แน่นอน |
| *ฉันต้องทำการ dispose ตัว `BarcodeGenerator` หรือไม่?* | คลาสนี้ implements `IDisposable`. ควรห่อ generator ด้วยบล็อก `using` หากคุณสร้างหลายอินสแตนซ์ในลูป เพื่อปล่อยทรัพยากรที่ไม่ได้จัดการโดยเร็ว |
| *ฉันจะเปลี่ยนขนาดบาร์โค้ดโดยไม่ปรับคอลัมน์/แถวได้อย่างไร?* | ใช้ `barcodeGenerator.Parameters.Image.Width` และ `Height` เพื่อสเกลภาพผลลัพธ์โดยไม่เปลี่ยนแปลงการจัดวางโมดูล |

**เคล็ดลับพิเศษ:** เมื่อคุณสร้างบาร์โค้ดสำหรับการพิมพ์ความละเอียดสูง ให้เพิ่มขนาดภาพเอาต์พุต (`Width`/`Height`) แทนการเพิ่มจำนวนคอลัมน์หรือแถว วิธีนี้จะรักษาขนาดโมดูลมาตรฐานของสัญลักษณ์ไว้ในขณะที่ให้ภาพที่คมชัดยิ่งขึ้น

## สรุป

ตอนนี้คุณรู้วิธีตั้งค่าคอลัมน์และแถวของบาร์โค้ดใน C# ด้วยคลาส **BarcodeGenerator** คู่มือได้อธิบายการเริ่มต้น generator, การกำหนดจำนวนคอลัมน์และแถว, การบันทึกบาร์โค้ดเป็น PNG, และการจัดการกับการเปลี่ยนแปลงรูปแบบภาพรวมถึงการจัดการทรัพยากร

ต่อไปสำรวจหัวข้อที่เกี่ยวข้องเช่น **การปรับสีบาร์โค้ด**, **การเพิ่มข้อความที่อ่านได้โดยมนุษย์**, และ **การฝังบาร์โค้ดลงในเอกสาร PDF**. การขยายเหล่านี้ทั้งหมดอิงจากรูปแบบการกำหนดค่าที่แสดงในที่นี้ ทำให้คุณสามารถสร้างโซลูชันบาร์โค้ดครบวงจรสำหรับแอปพลิเคชัน .NET ใดก็ได้

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}