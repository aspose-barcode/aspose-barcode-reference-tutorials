---
category: general
date: 2026-08-15
description: Databar ขยายการสร้างบาร์โค้ดแบบซ้อนใน C#. เรียนรู้วิธีสร้างภาพบาร์โค้ด
  ตั้งค่าคอลัมน์และแถวสำหรับเค้าโครง DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: th
lastmod: 2026-08-15
og_description: Databar ขยายการสร้างบาร์โค้ดแบบซ้อนใน C#. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างภาพบาร์โค้ด
  ตั้งค่าคอลัมน์ และตั้งค่าแถวอย่างมีประสิทธิภาพ.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – สร้างภาพบาร์โค้ดใน C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: สร้างภาพบาร์โค้ดใน C#'
url: /th/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: สร้างภาพบาร์โค้ดใน C#

หากคุณต้องการสร้างภาพบาร์โค้ด **databar expanded stacked** ใน C# คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่า **วิธีการสร้างบาร์โค้ด** ด้วยการจัดเรียงคอลัมน์และแถวแบบกำหนดเอง คุณจะได้เห็นวิธีตั้งค่าคอลัมน์ วิธีตั้งค่าแถว และวิธีบันทึกภาพที่ได้โดยไม่ต้องออกจาก IDE

The tutorial covers:

* การสร้างตัวสร้างบาร์โค้ดสำหรับสัญลักษณ์ **databar expanded stacked**  
* การกำหนดค่าเลย์เอาต์ 4‑คอลัมน์และ 3‑แถว  
* การบันทึกแต่ละการกำหนดค่าเป็นไฟล์ PNG  
* เคล็ดลับการจัดการกรณีขอบเช่นจำนวนคอลัมน์ที่ไม่ถูกต้อง  

ไม่มีเอกสารภายนอกที่จำเป็น; ตัวอย่างที่สมบูรณ์และสามารถรันได้รวมอยู่ในนี้

![ตัวอย่างบาร์โค้ด Databar expanded stacked](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="บาร์โค้ด databar expanded stacked ที่สร้างด้วย C#" }

## ขั้นตอนการสร้างบาร์โค้ด Databar expanded stacked

### 1. ติดตั้งไลบรารี Aspose.BarCode

โค้ดนี้ใช้ไลบรารี **Aspose.BarCode for .NET** ซึ่งให้คลาส `BarcodeGenerator` ติดตั้งแพ็กเกจ NuGet ด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

หลังจากติดตั้งแพ็กเกจแล้ว ให้เพิ่มเนมสเปซที่จำเป็นที่ส่วนหัวของไฟล์ของคุณ:

```csharp
using Aspose.BarCode.Generation;
```

### 2. สร้างตัวสร้างบาร์โค้ดสำหรับ **databar expanded stacked**

ตัวสร้างเป็นจุดเริ่มต้นสำหรับการทำงานกับบาร์โค้ดทั้งหมด คุณต้องระบุสัญลักษณ์ (`EncodeTypes.DatabarExpandedStacked`) และข้อความที่ต้องการเข้ารหัส

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Why this matters:* enum `EncodeTypes` บอกไลบรารีว่าต้องสร้างรูปแบบบาร์โค้ดใด การใช้ **databar expanded stacked** จะทำให้ภาพที่ได้สอดคล้องกับสเปค GS1 DataBar สำหรับเลย์เอาต์แบบ stacked

### 3. วิธีตั้งค่าคอลัมน์สำหรับ DataBar

คุณสมบัติ `Columns` ควบคุมจำนวนโมดูลแนวตั้งที่ปรากฏในบาร์โค้ดแบบ stacked ค่าที่ถูกต้องคือ 2, 3 หรือ 4 การตั้งค่าคอลัมน์จะส่งผลต่อความกว้างของบาร์โค้ดและปริมาณข้อมูลที่สามารถเก็บได้

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** หากคุณพยายามกำหนดค่าที่อยู่นอกช่วงที่อนุญาต ไลบรารีจะโยน `ArgumentException` ควรตรวจสอบค่าที่รับเข้ามาเสมอเมื่อให้ผู้ใช้เลือกคอลัมน์

### 4. บันทึกภาพบาร์โค้ด 4‑คอลัมน์

การบันทึกภาพจะสร้างไฟล์ที่คุณสามารถฝังในรายงาน ใบแจ้งหนี้ หรือแอปมือถือได้ วิธี `Save` รับพาธไฟล์และรูปแบบภาพเป็นพารามิเตอร์

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

เมื่อไฟล์ถูกเขียนเสร็จ คุณสามารถเปิดด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันว่ารูปแบบ **databar expanded stacked** ปรากฏอย่างถูกต้อง

### 5. วิธีตั้งค่าแถวสำหรับ DataBar

แถวเพิ่มมิติที่สองให้กับเลย์เอาต์แบบ stacked ทำให้สามารถเข้ารหัสข้อมูลได้มากขึ้นโดยไม่ต้องขยายความกว้างของบาร์โค้ด คุณสมบัติ `Rows` มีค่าเริ่มต้นเป็น 1; คุณสามารถเพิ่มได้สูงสุดถึง 3 สำหรับเวอร์ชัน expanded stacked

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Why rows matter:** การเพิ่มแถวจะลดความกว้างโดยรวมในขณะที่ยังคงความจุข้อมูลไว้ ซึ่งเป็นประโยชน์สำหรับป้ายแคบหรือหน้าจอมือถือที่มีพื้นที่จำกัด

### 6. บันทึกภาพบาร์โค้ด 3‑แถว

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์—หนึ่งไฟล์ที่มีเลย์เอาต์ 4‑คอลัมน์และอีกไฟล์ที่มีเลย์เอาต์ 3‑แถว—ทั้งสองใช้สัญลักษณ์ **databar expanded stacked**

### 7. ตัวอย่าง C# สมบูรณ์เพื่อสร้างภาพบาร์โค้ด

การรวมขั้นตอนทั้งหมดเข้าด้วยกันจะได้โปรแกรมที่ทำงานอิสระซึ่งคุณสามารถคัดลอกไปใส่ในแอปพลิเคชันคอนโซลได้:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Expected output**

การรันโปรแกรมจะแสดงผล:

```
4‑column barcode saved.
3‑row barcode saved.
```

และสร้างไฟล์ PNG สองไฟล์ใน `YOUR_DIRECTORY` เปิดไฟล์เหล่านั้นเพื่อยืนยันว่าภาพแต่ละภาพแสดงบาร์โค้ด **databar expanded stacked** ที่ถูกต้อง

## ปัญหาที่พบบ่อยและเคล็ดลับปฏิบัติ

* **Directory existence** – `Save` ไม่ได้สร้างโฟลเดอร์ที่หายไป ตรวจสอบให้แน่ใจว่า `YOUR_DIRECTORY` มีอยู่หรือใช้ `Directory.CreateDirectory` ก่อนบันทึก
* **Column limits** – ค่าที่ไม่ใช่ 2, 3 หรือ 4 จะทำให้เกิดข้อยกเว้น ใช้การตรวจสอบช่วงง่าย ๆ เพื่อป้องกันข้อผิดพลาดจากผู้ใช้:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Row limits** – เวอร์ชัน expanded stacked รองรับได้สูงสุด 3 แถว การตั้งค่า `Rows` เป็น 0 หรือค่าที่มากกว่า 3 จะทำให้เกิดข้อยกเว้นเช่นกัน
* **Image format** – `BarCodeImageFormat.Png` ให้คุณภาพแบบ lossless ซึ่งเหมาะสำหรับการพิมพ์ ใช้ `Jpeg` ก็ต่อเมื่อขนาดไฟล์เป็นปัจจัยสำคัญ

## ขั้นตอนต่อไป

ตอนนี้คุณรู้แล้วว่า **วิธีการสร้างบาร์โค้ด** ด้วยการกำหนดค่าคอลัมน์และแถวแบบกำหนดเอง คุณสามารถ:

* ผสานตัวสร้างเข้ากับ Web API เพื่อให้บริการภาพบาร์โค้ดตามความต้องการ  
* รวมบาร์โค้ดกับไลบรารีการสร้าง PDF เพื่อฝังลงในใบแจ้งหนี้  
* ทดลองใช้ DataBar เวอร์ชันอื่น (`DatabarExpanded`, `DatabarLimited`) ด้วยอ็อบเจกต์ `Parameters.Barcode.DataBar` เดียวกัน  

สำหรับการปรับแต่งขั้นสูง เช่น การเปลี่ยนสีของบาร์, การเพิ่มข้อความที่อ่านได้โดยมนุษย์, หรือการใส่ overlay QR‑code ให้ดูเอกสาร Aspose.BarCode เกี่ยวกับคุณสมบัติของ `BarcodeGenerator`

---

โดยการทำตามคู่มือนี้คุณได้เชี่ยวชาญกระบวนการ **databar expanded stacked**, เรียนรู้ **วิธีตั้งค่าคอลัมน์**, **วิธีตั้งค่าแถว**, และสร้างภาพบาร์โค้ดสองแบบที่พร้อมใช้งานในงานผลิตจริง ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณเอง

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}