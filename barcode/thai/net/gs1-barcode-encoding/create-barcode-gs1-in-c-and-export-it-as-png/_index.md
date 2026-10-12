---
category: general
date: 2026-09-29
description: สร้างบาร์โค้ด GS1 ด้วย C# และสร้างภาพ PNG ของบาร์โค้ดโดยใช้ BarcodeGenerator.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนเพื่อส่งออกภาพบาร์โค้ดอย่างมีประสิทธิภาพ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: th
lastmod: 2026-09-29
og_description: สร้างบาร์โค้ด GS1 ใน C# และสร้างไฟล์ PNG ของบาร์โค้ดด้วย BarcodeGenerator.
  ปฏิบัติตามคู่มือฉบับสมบูรณ์นี้เพื่อส่งออกภาพบาร์โค้ดอย่างรวดเร็ว.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: สร้างบาร์โค้ด GS1 ด้วย C# – ส่งออกเป็น PNG ภายในไม่กี่นาที
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: สร้างบาร์โค้ด GS1 ด้วย C# และส่งออกเป็น PNG
url: /th/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด GS1 ใน C# และส่งออกเป็น PNG

หากคุณต้องการ **สร้างบาร์โค้ด GS1** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงให้คุณเห็นขั้นตอนที่ทำได้อย่างชัดเจน คุณจะได้เห็นวิธีที่สั้นกระชับในการสร้างภาพบาร์โค้ด PNG และส่งออกภาพบาร์โค้ดไปยังดิสก์ทั้งหมดด้วยคลาส Aspose.BarCode `BarcodeGenerator`

การสร้างบาร์โค้ด GS1 เป็นความต้องการทั่วไปสำหรับระบบคลังสินค้า การจัดส่ง และระบบจุดขาย (POS) เมื่อจบบทเรียนนี้คุณจะสามารถเขียนโปรแกรม C# เล็ก ๆ ที่สร้างบาร์โค้ด MicroPDF417 ตามมาตรฐาน GS1 และบันทึกเป็นไฟล์ PNG คุณภาพสูงได้

## สิ่งที่ต้องเตรียม

ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

* **.NET 6** (หรือเวอร์ชัน .NET ใด ๆ ที่ใหม่กว่า) ติดตั้งอยู่
* **Visual Studio 2022** หรือ IDE ใด ๆ ที่รองรับ C#
* แพคเกจ NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – ให้ API `BarcodeGenerator` ที่ใช้ในตัวอย่าง
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **Pro tip:** ใช้รุ่น community edition ของ Aspose.BarCode ที่ให้ใช้ฟรีเมื่อต้องการทดลอง; รุ่นเต็มจะลบลายน้ำการประเมินผลออกทั้งหมด

## Step 1 – สร้างบาร์โค้ด GS1 ด้วย BarcodeGenerator

สิ่งแรกที่คุณต้องทำคือสร้างอินสแตนซ์ของ `BarcodeGenerator` สำหรับรูปแบบ *MicroPDF417* และป้อนสตริงข้อมูล GS1 ให้กับมัน ตัวระบุแอปพลิเคชัน GS1 (AI) จะถูกใส่ในวงเล็บ เช่น `(01)` สำหรับ GTIN‑14 และ `(21)` สำหรับหมายเลขซีเรียล

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**ทำไมจึงสำคัญ:**  
`EncodeTypes.MicroPdf417` จะพิจารณาข้อมูลอินพุตเป็นข้อมูล GS1 โดยอัตโนมัติเมื่อสตริงมี AI ที่ถูกต้อง ซึ่งทำให้บาร์โค้ดที่สร้างขึ้นสอดคล้องกับสเปค GS1 โดยไม่ต้องตั้งค่าเพิ่มเติม

## Step 2 – ตั้งค่าขนาดบาร์โค้ดให้เหมาะสม

ขนาดภาพของบาร์โค้ดถูกควบคุมโดย **X‑dimension** (ความกว้างของโมดูลเดียว) การปรับค่า `XDimension.Pixels` จะช่วยให้คุณปรับขนาดภาพสุดท้ายได้อย่างละเอียดในขณะที่ยังคงความอ่านได้

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **How to generate barcode PNG** – X‑dimension ไม่ได้มีผลต่อข้อมูลที่เข้ารหัส; มันเพียงเปลี่ยนขนาดทางกายภาพของภาพที่สร้างขึ้น หากคุณต้องการบาร์โค้ดขนาดใหญ่สำหรับการพิมพ์ความละเอียดสูง ให้เพิ่มค่าตัวนี้ (เช่น `3` หรือ `4`)

## Step 3 – สร้างบาร์โค้ด PNG และส่งออกภาพบาร์โค้ด

ตอนนี้คุณสามารถเรนเดอร์บาร์โค้ดและบันทึกเป็นไฟล์ PNG ได้แล้ว เมธอด `Save` รับพาธเป้าหมายและรูปแบบภาพที่ต้องการ

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**สิ่งที่เกิดขึ้นเบื้องหลัง:**  
`BarcodeGenerator.Save` จะทำการเรสเตอร์ไบร์โค้ดเป็นบิตแมป, ใช้ค่า X‑dimension ที่ตั้งไว้ก่อนหน้า, แล้วเข้ารหัสบิตแมปเป็นไฟล์ PNG ไฟล์ที่ได้สามารถใช้โดยตรงในหน้าเว็บ, พิมพ์บนป้าย, หรือฝังในไฟล์ PDF ได้

## ตัวอย่างโค้ดเต็ม

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่สมบูรณ์และทำงานได้โดยอิสระ คุณสามารถคัดลอก, วาง, และรันได้ ตัวอย่างนี้สาธิต **วิธีสร้างบาร์โค้ด PNG** , **ส่งออกภาพบาร์โค้ด**, พร้อมการจัดการข้อผิดพลาดพื้นฐาน

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### ผลลัพธ์ที่คาดหวัง

เมื่อคุณรันโปรแกรม ควรเห็นผลลัพธ์ดังนี้

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

การเปิดไฟล์ PNG จะแสดงบาร์โค้ด **GS1 MicroPDF417** ที่ชัดเจน ซึ่งเข้ารหัส GTIN‑14 `12345678901234` และหมายเลขซีเรียล `ABC123` การสแกนด้วยเครื่องสแกนที่รองรับ GS1 ใด ๆ จะคืนค่าข้อมูลสตริงเดิมกลับมา

## ข้อผิดพลาดทั่วไปและแนวทางปฏิบัติที่ดีที่สุด

| ปัญหา | สาเหตุ | วิธีหลีกเลี่ยง |
|-------|--------|----------------|
| **รูปแบบ AI ไม่ถูกต้อง** | ขาดวงเล็บหรือเรียงลำดับผิดทำให้บาร์โค้ดไม่เป็น GS1 | ต้องใส่วงเล็บรอบแต่ละ AI เสมอ เช่น `(01)` |
| **X‑dimension เล็กเกินไป** | บาร์โค้ดอ่านไม่ออกบนอุปกรณ์ความละเอียดต่ำ | ตั้งค่า `XDimension.Pixels` ≥ 2 สำหรับเครื่องพิมพ์ส่วนใหญ่; เพิ่มค่าสำหรับการพิมพ์ความละเอียดสูง |
| **โฟลเดอร์ปลายทางไม่มี** | `Save` จะโยน `DirectoryNotFoundException` | ใช้ `Directory.CreateDirectory` ก่อนเรียก `Save` |
| **ใช้ EncodeType ผิด** | บางประเภท (เช่น `Code128`) ไม่รองรับข้อมูล GS1 โดยอัตโนมัติ | เลือก `EncodeTypes.MicroPdf417` หรือประเภทที่รองรับ GS1 |
| **ขาดการอ้างอิง NuGet** | เกิดข้อผิดพลาดคอมไพล์เช่น `The type or namespace name 'Aspose' could not be found` | ติดตั้งแพคเกจ `Aspose.BarCode` ผ่าน NuGet |

## การขยายตัวอย่าง

* **รูปแบบภาพอื่น** – แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Gif` หรือ `Bmp` หากต้องการรูปแบบอื่น
* **ผลลัพธ์ความละเอียดสูง** – ตั้งค่า `generator.Parameters.ImageResolution.DpiX` และ `DpiY` ก่อนบันทึก
* **ฝังใน PDF** – ใช้ `Aspose.Pdf` เพื่อใส่ PNG ลงในใบแจ้งหนี้หรือป้าย PDF

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด GS1** ใน C# ด้วย Aspose.BarCode `BarcodeGenerator`, **สร้างบาร์โค้ด PNG**, และ **ส่งออกภาพบาร์โค้ด** ไปยังระบบไฟล์แล้ว คำแนะนำนี้ครอบคลุมทุกขั้นตอน ตั้งแต่การเริ่มต้นตัวสร้างด้วยข้อมูล GS1, การปรับ X‑dimension, จนถึงการบันทึกไฟล์ PNG สุดท้าย พร้อมการอธิบายข้อผิดพลาดทั่วไปและแนวคิดการขยายเพิ่มเติม

อย่าลังเลที่จะทดลองใช้ GS1 Application Identifiers อื่น ๆ, สัญลักษณ์บาร์โค้ดประเภทต่าง ๆ, หรือภาพความละเอียดสูง เมื่อคุณเชี่ยวชาญพื้นฐานเหล่านี้ การสร้างบาร์โค้ดที่สอดคล้องมาตรฐานสำหรับคลังสินค้า, การจัดส่ง, หรือการค้าปลีกจะกลายเป็นส่วนหนึ่งของเครื่องมือ .NET ของคุณอย่างเป็นระบบ

## What Should You Learn Next?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}