---
category: general
date: 2026-09-26
description: เรียนรู้วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode คู่มือแบบขั้นตอนนี้รวมตัวอย่างการสร้างบาร์โค้ดและแสดงวิธีปรับความสูงของบาร์.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: th
lastmod: 2026-09-26
og_description: สร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode. ทำตามคู่มือนี้เพื่อสร้างบาร์โค้ด
  ปรับความสูงของบาร์ และบันทึกเป็นภาพ PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: สร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode – คู่มือเต็ม
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode
url: /th/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode  

หากคุณต้องการ **create barcode c#** โครงการอย่างรวดเร็ว, Aspose.BarCode มี API ที่ใช้งานง่ายซึ่งทำหน้าที่หนักให้คุณ ในบทเรียนนี้คุณจะได้เห็น **barcode generator example** อย่างครบถ้วน, เรียนรู้ **how to adjust bar height**, และส่งออกผลลัพธ์เป็นไฟล์ PNG.  

ไม่ว่าคุณจะกำลังสร้างระบบเช็คเอาท์สำหรับร้านค้าปลีก, สร้างแท็กสินค้าคงคลัง, หรืออัตโนมัติการพิมพ์ฉลากการจัดส่ง, ความสามารถในการเปลี่ยนขนาดภาพของบาร์โค้ดโดยโปรแกรมเป็นสิ่งสำคัญ คู่มือนี้สมมติว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับ C# และสภาพแวดล้อมการพัฒนาเช่น Visual Studio 2022.  

## ข้อกำหนดเบื้องต้น  

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:  

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว.  
* Visual Studio 2022 (หรือ IDE สำหรับ C# ใดก็ได้).  
* ใบอนุญาต Aspose.BarCode ที่ใช้งานได้ (รุ่นทดลองฟรีก็เพียงพอสำหรับการเรียนรู้).  

คุณยังต้องเพิ่มแพคเกจ Aspose.BarCode NuGet ลงในโปรเจกต์ของคุณ:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** หากคุณวางแผนจะสร้างบาร์โค้ดหลาย ๆ ตัวในลูป, ให้ใช้ตัวอย่าง `BarcodeGenerator` เพียงหนึ่งอันและปรับเปลี่ยนพารามิเตอร์ที่ต้องการเท่านั้น วิธีนี้จะลดการจัดสรรหน่วยความจำและเพิ่มประสิทธิภาพการทำงาน.

## วิธีสร้างบาร์โค้ดใน C# ด้วย Aspose.BarCode  

ส่วนต่อไปนี้จะอธิบายขั้นตอนแต่ละขั้นของ **barcode generator example**. โค้ดเป็นแบบ self‑contained; คัดลอกไปยังแอปพลิเคชันคอนโซลใหม่และรันได้เลย.  

### ขั้นตอน 1: นำเข้าเนมสเปซที่จำเป็น  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

เนมสเปซเหล่านี้ทำให้คุณเข้าถึงคลาส `BarcodeGenerator` และ enumeration `EncodeTypes`.  

### ขั้นตอน 2: เริ่มต้นตัวสร้างบาร์โค้ด  

เราจะสร้างสัญลักษณ์ **Databar Omni‑Directional** ที่เข้ารหัสค่า GTIN‑14. คอนสตรัคเตอร์รับพารามิเตอร์สัญลักษณ์และสตริงข้อมูลดิบ.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

ค่าที่เป็น `EncodeTypes.DatabarOmniDirectional` บอก Aspose.BarCode ว่าจะใช้มาตรฐานบาร์โค้ดแบบใด สตริงข้อมูลจะอยู่ในรูปแบบ GS1 Application Identifier ซึ่งเป็นรูปแบบที่ใช้กันทั่วไปในบาร์โค้ดสำหรับการค้าปลีก.  

### ขั้นตอน 3: ตั้งค่าพารามิเตอร์บาร์โค้ดทั่วไป  

สองพารามิเตอร์ภาพที่มักจะปรับบ่อยคือ X‑dimension (ความกว้างของบาร์แคบ) และความสูงของบาร์โดยรวม.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** ควบคุมความหนาแน่นของบาร์โค้ด, ส่วน **BarHeight** กำหนดขนาดแนวตั้งของแต่ละบาร์ การปรับ **BarHeight** คือสิ่งที่คุณต้องการเมื่อ **change barcode height** สำหรับสื่อการพิมพ์ที่แตกต่างกัน.  

### ขั้นตอน 4: บันทึกภาพแรก (ความสูง 30 พิกเซล)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนภาพที่เรนเดอร์แล้วลงดิสก์ ชื่อไฟล์บ่งบอกความสูงที่ใช้ชัดเจน ซึ่งช่วยให้คุณเปรียบเทียบผลลัพธ์ที่ต่างกันได้ง่าย.  

### ขั้นตอน 5: เปลี่ยนความสูงของบาร์เป็น 60 พิกเซล  

ตอนนี้เราจะแสดง **how to adjust bar height** ระหว่างรัน ตัวอย่าง `generator` เดียวกันจะถูกใช้ซ้ำ; เพียงแค่คุณเปลี่ยนค่า `BarHeight`.  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

เนื่องจากตัวสร้างยังคงรักษาการตั้งค่าอื่น ๆ (สัญลักษณ์, ข้อมูล, X‑dimension) ไว้, ความแตกต่างภาพเดียวระหว่างไฟล์ PNG สองไฟล์คือขนาดแนวตั้งของบาร์.  

### โค้ดเต็ม  

การรวมทุกอย่างเข้าด้วยกันจะได้โปรแกรมสั้น ๆ ที่รันได้:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง**  

การรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์ในไดเรกทอรีทำงานของไฟล์เอ็กซีคิวเทเบิล:  

* `DatabarBarHeight30Pixels.png` – บาร์โค้ดที่มีความสูงบาร์ 30 px.  
* `DatabarBarHeight60Pixels.png` – บาร์โค้ดเดียวกัน, แต่บาร์แต่ละบาร์สูงเป็นสองเท่า.  

เปิดภาพในโปรแกรมดูใด ๆ; คุณจะเห็นว่ารูปแบบโดยรวมยังคงเหมือนเดิมในขณะที่มิติแนวตั้งเปลี่ยนไป, ยืนยันว่าการ **change barcode height** ทำงานสำเร็จ.  

## การปรับใช้ขั้นสูง  

### การสลับไปใช้สัญลักษณ์อื่น  

หากคุณต้องการ QR code แทน Databar, ให้เปลี่ยนค่าของ `EncodeTypes` ดังนี้:  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

การตั้งค่าอื่น ๆ (X‑dimension, BarHeight) ยังคงใช้ได้ตามที่เหมาะสม.  

### ใช้ `BarHeight` เป็นมิลลิเมตร  

Aspose.BarCode ยังรองรับหน่วยทางกายภาพอีกด้วย เพื่อกำหนดความสูง 10 mm:  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

วิธีนี้สะดวกเมื่อคุณสร้างบาร์โค้ดสำหรับเลย์เอาต์การพิมพ์ที่ต้องการขนาดที่แม่นยำ.  

### การจัดการข้อผิดพลาด  

หากสตริงข้อมูลไม่สอดคล้องกับสัญลักษณ์ที่เลือก, `BarcodeGenerator` จะโยน `ArgumentException`. ให้ห่อรอบตรรกะการสร้างด้วยบล็อก try‑catch เพื่อแสดงข้อความที่เป็นมิตร:  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## คำถามที่พบบ่อย  

* **การเปลี่ยน BarHeight มีผลต่อการสแกนหรือไม่?**  
  บาร์โค้ดยังคงสแกนได้ตราบใดที่ X‑dimension และ quiet zone ทั้งหมดตรงตามข้อกำหนดของสัญลักษณ์ การเพิ่มความสูงทำให้บาร์ยาวขึ้นเท่านั้น; ไม่ทำให้ความคอนทราสต์ลดลง.  

* **ฉันสามารถตั้งความสูงที่แตกต่างกันให้กับบาร์แต่ละบาร์ได้หรือไม่?**  
  ไม่ได้. คุณสมบัติ `BarHeight` จะใช้กับสัญลักษณ์ทั้งหมดอย่างสม่ำเสมอ. หากต้องการออกแบบบาร์ที่มีความสูงเปลี่ยนแปลงได้ คุณต้องเขียน routine การเรนเดอร์แบบกำหนดเองซึ่งอยู่นอกขอบเขตของ Aspose.BarCode.  

* **PNG เป็นรูปแบบที่ดีที่สุดสำหรับการพิมพ์หรือไม่?**  
  PNG เก็บข้อมูลพิกเซลแบบ lossless ทำให้เหมาะสำหรับการแสดงบนหน้าจอ. สำหรับงานพิมพ์ความละเอียดสูง, ควรพิจารณาใช้ `BarCodeImageFormat.Tiff` หรือ `Pdf` เพื่อรักษาข้อมูลเวกเตอร์.  

## สรุป  

ตอนนี้คุณรู้วิธี **create barcode c#** ด้วย Aspose.BarCode, ดู **barcode generator example** อย่างครบถ้วน, และเข้าใจ **how to adjust bar height** เพื่อให้ตรงกับความต้องการของเลย์เอาต์ต่าง ๆ. โดยการใช้ตัวสร้างเดียวกันและปรับเฉพาะ `BarHeight` เท่านั้น คุณสามารถ **change barcode height** อย่างมีประสิทธิภาพโดยไม่ต้องสร้างอ็อบเจกต์ใหม่ทั้งหมด.  

ต่อไปคุณอาจสำรวจ:  

* การสร้างสัญลักษณ์อื่น (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* การส่งออกเป็น SVG หรือ PDF เพื่อกราฟิกที่ขยายได้.  
* การฝังบาร์โค้ดโดยตรงลงในเอกสาร Word หรือ Excel ด้วย Aspose.Words หรือ Aspose.Cells.  

ขอให้เขียนโค้ดอย่างสนุกสนาน, และเพลิดเพลินกับความยืดหยุ่นที่ Aspose.BarCode มอบให้กับโครงการบาร์โค้ด C# ของคุณ!  

## คุณควรเรียนรู้อะไรต่อไป?  

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้. แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ.  

- [วิธีสร้างและปรับความสูงบาร์โค้ดสำหรับ One-Dimensional Databar ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)  
- [วิธีสร้างไฟล์ PNG ของบาร์โค้ดพร้อมความสูงที่ปรับได้ใน C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)  
- [วิธีสร้างบาร์โค้ดใน C# – คู่มือ Aspose.BarCode ฉบับสมบูรณ์](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}