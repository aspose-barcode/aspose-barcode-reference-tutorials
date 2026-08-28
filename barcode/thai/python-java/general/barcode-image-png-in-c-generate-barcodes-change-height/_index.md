---
category: general
date: 2026-08-15
description: ภาพบาร์โค้ด PNG ใน C# – เรียนรู้วิธีสร้างบาร์โค้ดไปรษณีย์, สร้างบาร์โค้ด
  Planet, และปรับความสูงของบาร์โค้ดด้วยเครื่องสร้างง่าย ๆ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: th
lastmod: 2026-08-15
og_description: บทแนะนำการสร้างภาพบาร์โค้ด PNG ใน C# แสดงวิธีสร้างบาร์โค้ดไปรษณีย์,
  สร้างบาร์โค้ด Planet, และเปลี่ยนความสูงของบาร์โค้ดโดยใช้ BarcodeGenerator API.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: ภาพบาร์โค้ด PNG ใน C# – สร้างและปรับแต่งบาร์โค้ด
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: ภาพบาร์โค้ด PNG ใน C# สร้างบาร์โค้ด, ปรับความสูง
url: /th/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ภาพ Barcode PNG ใน C# – สร้าง barcode, ปรับความสูง

หากคุณต้องการ **ภาพ barcode PNG** ใน C# คำแนะนำนี้จะพาคุณผ่านกระบวนการทั้งหมด คุณจะได้เรียนรู้วิธีสร้าง postal barcode, สร้าง Planet barcode, และเปลี่ยนความสูงของ barcode โดยไม่ต้องออกจาก IDE ของคุณ

การสร้าง PNG barcode ที่เชื่อถือได้เป็นความต้องการทั่วไปสำหรับป้ายจัดส่ง, ระบบสินค้าคงคลัง, และโซลูชันการส่งจดหมายอัตโนมัติ เมื่อจบบทเรียนนี้คุณจะมีโค้ดสแนปช็อตที่สามารถนำกลับมาใช้ใหม่ได้ซึ่งสร้างไฟล์ PNG คุณภาพสูงสำหรับรูปแบบ Planet และ RM4SCC ทั้งสองแบบ และคุณจะเข้าใจวิธีปรับความสูงของบาร์ให้ตรงตามสเปคของไปรษณีย์

## สิ่งที่คุณต้องมี

- .NET 6+ หรือ .NET Framework 4.7.2 (API BarcodeGenerator ทำงานกับ .NET runtime ใดก็ได้ที่ทันสมัย)  
- การอ้างอิงไปยังแพคเกจ NuGet **Aspose.BarCode for .NET** (หรือไลบรารีที่เข้ากันได้ซึ่งให้ `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`)  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และการทำ I/O กับไฟล์  

ไม่ต้องใช้เครื่องมือเพิ่มเติม; โค้ดทำงานได้ใน Visual Studio, Rider หรือ `dotnet` CLI

## ภาพ Barcode PNG – การสร้างพื้นฐาน

ขั้นตอนแรกคือการสร้าง **ภาพ barcode PNG** ด้วยขนาดเริ่มต้น ซึ่งเป็นไฟล์ฐานที่คุณสามารถปรับแต่งต่อได้

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**ทำไมวิธีนี้ถึงได้ผล:**  
- `EncodeTypes.Planet` บอกให้ตัวสร้างใช้สัญลักษณ์ Planet ซึ่งจำเป็นสำหรับหลายบริการไปรษณีย์  
- `XDimension.Pixels` ควบคุมความกว้างของบาร์ที่เล็กที่สุด; ค่า 4 px ให้ barcode ที่อ่านได้ในขนาดป้ายทั่วไป  
- เมธอด `Save` จะบันทึกไฟล์ **ภาพ barcode PNG** ไปยังดิสก์ โดยเก็บข้อมูลเวกเตอร์ทั้งหมดเป็นพิกเซลเรสเตอร์

## ปรับความสูงของ barcode – ปรับน้ำหนักภาพ

แนวทางของไปรษณีย์มักกำหนดความสูงของบาร์เป็นค่าที่เฉพาะ โค้ดต่อไปนี้แสดงวิธีตั้งความสูงแบบกำหนดเอง 100 พิกเซลสำหรับ Planet barcode เดียวกัน

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**เหตุผลที่ต้องปรับความสูง:**  
บาร์ที่สูงขึ้นช่วยเพิ่มความน่าเชื่อถือในการสแกนบนเครื่องพิมพ์ความละเอียดต่ำ, ในขณะที่บาร์ที่สั้นลงจะลดพื้นที่บนป้าย `BarHeight.Pixels` ให้คุณปรับค่าลักษณะนี้ได้โดยไม่กระทบต่อ X‑dimension

## สร้าง postal barcode – ตัวอย่าง RM4SCC

รูปแบบ RM4SCC เป็น barcode ไปรษณีย์ที่ใช้กันทั่วไปในสหราชอาณาจักร ขั้นตอนการสร้างคล้ายกับตัวอย่าง Planet, ทำให้แนวคิด **barcode generator c#** เป็นรูปแบบที่สอดคล้องกัน

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## ปรับความสูงของ barcode – เวอร์ชัน RM4SCC

เช่นเดียวกับ Planet barcode, คุณสามารถปรับความสูงของบาร์ RM4SCC ได้ โค้ดด้านล่างตั้งความสูงเป็น 100 px, สร้าง **ภาพ barcode PNG** ที่สองสำหรับสตริงข้อมูลเดียวกัน

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## ตัวอย่างเต็มที่สามารถรันได้

การรวมทุกขั้นตอนเข้าด้วยกันให้โปรแกรมเดียวที่สร้างไฟล์ PNG สี่ไฟล์:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [สร้าง Barcode ความสูงกำหนดเอง – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [สร้าง Barcode PNG – อัตราส่วนภาพ DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [สร้างภาพ barcode C# – ตัวอย่าง GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}