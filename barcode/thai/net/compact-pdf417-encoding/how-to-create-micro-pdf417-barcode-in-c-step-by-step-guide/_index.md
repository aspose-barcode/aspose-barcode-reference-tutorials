---
category: general
date: 2026-08-22
description: เรียนรู้วิธีสร้างบาร์โค้ด micro PDF417 ด้วย C# และสร้างภาพบาร์โค้ด PNG
  รวมถึงการตั้งค่าขนาดบาร์โค้ดและการบันทึกไฟล์
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: th
lastmod: 2026-08-22
og_description: สร้างบาร์โค้ด micro PDF417 ด้วย C# และส่งออกเป็นไฟล์ PNG ทำตามคู่มือนี้เพื่อกำหนดขนาดบาร์โค้ดและสร้างภาพบาร์โค้ดอย่างรวดเร็ว
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: สร้างบาร์โค้ด micro PDF417 ด้วย C# – บทเรียนการเขียนโค้ดเต็มรูปแบบ
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: วิธีสร้างบาร์โค้ด micro PDF417 ใน C# – คู่มือแบบขั้นตอนต่อขั้นตอน
url: /th/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด micro PDF417 ด้วย C# – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **สร้างบาร์โค้ด micro PDF417** สำหรับระบบตั๋ว, ป้ายสินค้าคงคลัง, หรือการสแกนบนมือถือ, บทแนะนำนี้จะแสดงวิธีทำอย่างละเอียด คุณจะได้เห็นโปรแกรม C# ฉบับเต็มที่สร้างไฟล์ PNG ของบาร์โค้ด, เรียนรู้วิธีตั้งค่าขนาดบาร์โค้ด, และทำความเข้าใจแต่ละตัวเลือกการกำหนดค่า

เมื่ออ่านจบบทแนะนำนี้คุณจะสามารถสร้างภาพบาร์โค้ดความละเอียดสูง, ปรับค่า X‑dimension, เลือกจำนวนคอลัมน์, และบันทึกผลลัพธ์เป็นไฟล์ PNG – ทั้งหมดด้วยไม่กี่บรรทัดของโค้ด

## สิ่งที่คุณต้องมี

- .NET 6.0 SDK หรือใหม่กว่า (โค้ดทำงานได้กับ .NET Core และ .NET Framework)
- Visual Studio 2022 หรือ IDE ที่รองรับ C#
- แพคเกจ NuGet **Aspose.BarCode for .NET** (หรือไลบรารีใด ๆ ที่สนับสนุน `EncodeTypes.MicroPdf417`)
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **เคล็ดลับ:** รุ่น community edition ฟรีของ Aspose.BarCode เพียงพอสำหรับการพัฒนาและทดสอบ หากนำไปใช้ในผลิตภัณฑ์จริงควรซื้อไลเซนส์เพื่อเอา watermark การประเมินผลออก

## ขั้นตอนที่ 1: ติดตั้งไลบรารีบาร์โค้ด

เปิดเทอร์มินัลในโฟลเดอร์โปรเจกต์ของคุณและรัน:

```bash
dotnet add package Aspose.BarCode
```

คำสั่งนี้จะเพิ่ม assembly `Aspose.BarCode` ซึ่งให้คลาส `BarcodeGenerator` ที่ใช้ **สร้างภาพบาร์โค้ด C#** ในแอปพลิเคชันของคุณ

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้าง – สร้างบาร์โค้ด micro PDF417

บรรทัดแรกที่ทำงานได้สร้างอินสแตนซ์ `BarcodeGenerator` ที่กำหนดให้ใช้สัญลักษณ์ Micro PDF417 และใส่ข้อมูลที่คุณต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*ทำไมจึงสำคัญ*: enum `EncodeTypes.MicroPdf417` บอกไลบรารีให้ใช้เวอร์ชันกะทัดรัดของ PDF417 ซึ่งเหมาะกับป้ายขนาดเล็กและหน้าจอมือถือ

## ขั้นตอนที่ 3: วิธีตั้งค่าขนาดบาร์โค้ดใน C#

การปรับความกว้างของโมดูล (X‑dimension) จะควบคุมความหนาแน่นของบาร์โค้ด ค่าที่เล็กลงให้ภาพคมชัดมากขึ้น, ค่าที่ใหญ่ขึ้นทำให้บาร์โค้ดอ่านได้ง่ายจากระยะไกล

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **ทำไมต้องตั้งค่าขนาด**: หากไม่ปรับ X‑dimension ค่าเริ่มต้นอาจทำให้บาร์โค้ดดูเบลอเมื่อเรนเดอร์ที่ DPI สูง การตั้งค่าเป็น 2 พิกเซลเป็นสมดุลที่ดีสำหรับการสแกนบนหน้าจอส่วนใหญ่

## ขั้นตอนที่ 4: เลือกจำนวนคอลัมน์ – ควบคุมความกว้างของบาร์โค้ด

Micro PDF417 รองรับตั้งแต่ 1 ถึง 4 คอลัมน์ คอลัมน์มากขึ้นจะบีบข้อมูลในแนวนอน, ลดความกว้างของภาพโดยรวม

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*กรณีขอบ*: หากคุณระบุ 5 คอลัมน์ ไลบรารีจะโยน `ArgumentOutOfRangeException` ควรอยู่ในช่วงที่ระบุในเอกสารเท่านั้น

## ขั้นตอนที่ 5: วิธีสร้าง PNG ของบาร์โค้ด – บันทึกภาพ

ตอนนี้คุณสามารถส่งออกบาร์โค้ดที่สร้างเป็นไฟล์ PNG ได้แล้ว PNG จะรักษาคุณภาพแบบ lossless ซึ่งจำเป็นต่อการสแกนที่เชื่อถือได้

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

เมื่อรันโปรแกรม คุณจะเห็นข้อความในคอนโซลยืนยันตำแหน่งไฟล์ `MicroPdf417.png` ที่สร้างขึ้น จะมีลักษณะดังนี้:

![ภาพหน้าจอแสดงบาร์โค้ด micro PDF417 ที่สร้างด้วย C#](micro-pdf417-example.png "บาร์โค้ด micro PDF417 ที่สร้างแล้ว")

*ข้อความแทนภาพ*: **บาร์โค้ด micro PDF417 ที่สร้างด้วย C#** – แสดงผลลัพธ์สุดท้ายหลังจากปรับค่า X‑dimension และจำนวนคอลัมน์

## ขั้นตอนที่ 6: รันและตรวจสอบผลลัพธ์

1. สร้างโปรเจกต์: `dotnet build`  
2. เรียกใช้: `dotnet run`  
3. เปิดไฟล์ `MicroPdf417.png` บนเดสก์ท็อปและสแกนด้วยแอปสแกนบาร์โค้ดบนมือถือ

คุณควรเห็นข้อความ **“Sample text”** ถูกถอดรหัส หากสแกนเจอข้อผิดพลาด ให้ตรวจสอบ X‑dimension และจำนวนคอลัมน์อีกครั้ง – ค่าที่สุดขีดอาจทำให้บาร์โค้ดหนาเกินไปสำหรับอุปกรณ์บางรุ่น

## ความแปรผันทั่วไปและการแก้ไขปัญหา

| สถานการณ์ | การปรับแต่ง |
|-----------|------------|
| **ต้องการบาร์โค้ดขนาดใหญ่สำหรับเครื่องพิมพ์ความละเอียดต่ำ** | เพิ่มค่า `XDimension.Pixels` เป็น 3 หรือ 4 |
| **ต้องการบาร์โค้ดสูงขึ้นโดยไม่เปลี่ยนความกว้าง** | ตั้งค่า `generator.Parameters.Barcode.Pdf417.Rows` (ช่วงแถว 3‑90) |
| **สร้างบาร์โค้ดหลายรายการในลูป** | ใช้อินสแตนซ์ `BarcodeGenerator` เดียวกันและเปลี่ยน `CodeText` ก่อนแต่ละ `Save` |
| **บันทึกเป็น JPEG แทน PNG** | แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` |
| **รันบน .NET Framework 4.7** | โค้ดเดียวกันทำงานได้; เพียงแค่อ้างอิง `Aspose.BarCode.dll` ที่เหมาะกับเวอร์ชันนั้น |

## รายการโค้ดเต็ม (พร้อมรัน)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง** – ไฟล์ PNG ขนาด 200 × 100 พิกเซล ที่มีบาร์โค้ด Micro PDF417 คมชัดและถอดรหัสได้เป็น “Sample text”

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด micro PDF417 ด้วย C#**, **ตั้งค่าขนาดบาร์โค้ด**, และ **สร้างภาพ PNG ของบาร์โค้ด** ตัวอย่างเต็มแสดงขั้นตอนทั้งหมด – ตั้งแต่การติดตั้งไลบรารีจนถึงการบันทึกไฟล์สุดท้าย – เพื่อให้คุณสามารถฝังการสร้างบาร์โค้ดลงในแอปพลิเคชันของคุณได้โดยตรง

ต่อไปลองสำรวจหัวข้อที่เกี่ยวข้องเช่น **การสร้าง QR code ด้วย Aspose.BarCode**, **การปรับสี**, หรือ **การฝังบาร์โค้ดในเอกสาร PDF** ทั้งหมดอิงจากพื้นฐาน `BarcodeGenerator` ที่อธิบายไว้ในที่นี้

อย่ากลัวที่จะทดลองเปลี่ยนสตริงข้อมูล, จำนวนคอลัมน์, และค่า X‑dimension เพื่อให้เหมาะกับสภาพแวดล้อมการสแกนของคุณเอง ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}