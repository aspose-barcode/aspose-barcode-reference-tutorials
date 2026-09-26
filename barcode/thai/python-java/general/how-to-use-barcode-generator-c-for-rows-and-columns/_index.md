---
category: general
date: 2026-09-26
description: คู่มือการสร้างบาร์โค้ด C# แสดงวิธีตั้งค่าแถวและคอลัมน์เมื่อสร้างบาร์โค้ด
  Databar Expanded Stacked ด้วย C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: th
lastmod: 2026-09-26
og_description: บทเรียนการสร้างบาร์โค้ดด้วย C# อธิบายวิธีตั้งค่าแถวและคอลัมน์สำหรับบาร์โค้ด
  Databar Expanded Stacked พร้อมโค้ดเต็มและเคล็ดลับ.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: เครื่องสร้างบาร์โค้ด C# – ตั้งค่าแถวและคอลัมน์แบบทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: วิธีใช้ตัวสร้างบาร์โค้ด C# สำหรับแถวและคอลัมน์
url: /th/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ barcode generator C# สำหรับแถวและคอลัมน์

หากคุณต้องการ **barcode generator C#** ที่ให้คุณควบคุมการจัดวางภาพของบาร์โค้ด Databar Expanded Stacked นี้ บทแนะนำนี้จะให้โซลูชันที่สมบูรณ์และสามารถรันได้ คุณจะได้เรียนรู้ **วิธีตั้งค่าแถว** และ **วิธีตั้งค่าคอลัมน์** เพื่อให้ภาพที่สร้างขึ้นตรงกับการออกแบบที่คุณต้องการ

การสร้างบาร์โค้ดโดยโปรแกรมมักรู้สึกเหมือนเดาว่าคุณสมบัติต่าง ๆ ทำอะไร โดยเมื่ออ่านจบคู่มือนี้คุณจะเข้าใจ API อย่างครบถ้วน หลีกเลี่ยงข้อผิดพลาดทั่วไป และมีตัวอย่างโค้ดที่พร้อมรันที่คุณสามารถคัดลอกไปใช้ในโปรเจกต์ของคุณได้

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดทำงานได้กับ .NET Core และ .NET Framework ด้วย)
* อ้างอิงไปยังไลบรารีการสร้างบาร์โค้ดที่ให้ `BarcodeGenerator` และ `EncodeTypes` (เช่น Aspose.BarCode, Dynamsoft หรือ SDK ที่เข้ากันได้อื่น ๆ)
* IDE เช่น Visual Studio หรือ VS Code
* สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

ไม่จำเป็นต้องติดตั้งแพคเกจ NuGet เพิ่มเติมนอกจาก barcode SDK เอง

## Barcode generator C# – การตั้งค่าแถวและคอลัมน์

ส่วนต่อไปนี้จะอธิบายขั้นตอนการกำหนดค่าแต่ละขั้นตอน ตัวอย่างโค้ดสมบูรณ์และสามารถวางลงในเมธอด `Main` ของแอปพลิเคชันคอนโซลได้โดยตรง

### ขั้นตอนที่ 1: สร้างตัวสร้างสำหรับบาร์โค้ด Databar Expanded Stacked

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*ทำไมจึงสำคัญ:* การสร้างอินสแตนซ์ของ `BarcodeGenerator` เป็นการกระทำแรกในกระบวนการทำงานของ **barcode generator C#** ตัวสร้างรับประเภทการเข้ารหัสและสตริงข้อมูลที่จะเข้ารหัส

### ขั้นตอนที่ 2: วิธีตั้งค่าคอลัมน์ – กำหนดบาร์โค้ดให้ใช้ 4 คอลัมน์

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

การตั้งค่าคุณสมบัติ `Columns` จะเปลี่ยนจำนวนโมดูลแนวตั้งที่ DataBar ใช้ ค่า `4` จะสร้างบาร์โค้ดที่หนาแน่นและกะทัดรัดมากขึ้น ซึ่งมีประโยชน์เมื่อพื้นที่แนวนอนจำกัด

### ขั้นตอนที่ 3: บันทึกภาพบาร์โค้ดพร้อมการตั้งค่าคอลัมน์

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนภาพที่สร้างขึ้นลงดิสก์ ตรวจสอบไฟล์ผลลัพธ์เพื่อยืนยันว่าการจัดวางแบบสี่คอลัมน์แสดงตามที่คาดหวัง

![Barcode generator C# example showing rows and columns settings](./images/barcode-rows-columns.png)

*ภาพด้านบนแสดงผลลัพธ์ของการกำหนดค่าคอลัมน์*

### ขั้นตอนที่ 4: เริ่มต้นตัวสร้างใหม่สำหรับการจัดวางที่แตกต่าง

เมื่อคุณต้องการบาร์โค้ดแยกต่างหากที่มีการจัดวางภาพแตกต่าง ให้สร้างอินสแตนซ์ใหม่แทนการใช้ตัวเดิม วิธีนี้รับประกันว่าการตั้งค่าก่อนหน้า (เช่น คอลัมน์) จะไม่ส่งผลต่อการกำหนดค่าใหม่

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### ขั้นตอนที่ 5: วิธีตั้งค่าแถว – กำหนดบาร์โค้ดให้ใช้ 3 แถว

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

คุณสมบัติ `Rows` ควบคุมการซ้อนกันแนวตั้งของโมดูล DataBar การจัดวางแบบสามแถวเป็นค่าเริ่มต้นสำหรับอุปกรณ์สแกนหลายรุ่น แต่คุณสามารถเพิ่มจำนวนเพื่อความหนาแน่นของข้อมูลที่สูงขึ้น

### ขั้นตอนที่ 6: บันทึกภาพบาร์โค้ดที่รวมการตั้งค่าแถว

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

เปิดไฟล์ `DatabarRows3.png` เพื่อดูการจัดเรียงแบบสามแถว หากบาร์โค้ดไม่สามารถสแกนได้ ให้ตรวจสอบค่าของแถว/คอลัมน์อีกครั้งกับสเปคของสแกนเนอร์ของคุณ

## โค้ดต้นฉบับเต็ม – พร้อมคัดลอก

ด้านล่างเป็นโปรแกรมเต็มที่รวมทุกขั้นตอนข้างต้น แทนที่ `YOUR_DIRECTORY` ด้วยพาธแบบเต็มหรือแบบสัมพันธ์ที่มีอยู่บนเครื่องของคุณ

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์:

| ชื่อไฟล์            | คำอธิบายการจัดวาง                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked พร้อม **4 columns** |
| `DatabarRows3.png`   | Databar Expanded Stacked พร้อม **3 rows**    |

ทั้งสองภาพควรสแกนได้ด้วยเครื่องอ่านบาร์โค้ดมาตรฐานที่รองรับสัญลักษณ์ Databar Expanded Stacked

## ข้อผิดพลาดทั่วไปและเคล็ดลับมืออาชีพ

| ปัญหา | ทำไมจึงเกิดขึ้น | วิธีแก้ / เคล็ดลับ |
|--------------------------------------|----------------------------------------------|-----------|
| ใช้อินสแตนซ์ `BarcodeGenerator` เดียวกันสำหรับทั้งแถวและคอลัมน์ | SDK เก็บการกำหนดค่าก่อนหน้า ดังนั้นการตั้งค่าแถวหลังคอลัมน์อาจทำให้เกิดการผสมผสานที่ไม่คาดคิด | เริ่มต้นตัวสร้างใหม่ (ตามที่แสดงในขั้นตอน 4) ก่อนเปลี่ยนมิติอื่น |
| ลืมตั้งค่า `EncodeTypes` อย่างถูกต้อง | SDK มีค่าเริ่มต้นเป็นสัญลักษณ์อื่น ทำให้บาร์โค้ดไม่ถูกต้อง | ต้องส่งค่า `EncodeTypes.DatabarExpandedStacked` เสมอเมื่อคุณต้องการรูปแบบนี้ |
| บันทึกไปยังโฟลเดอร์ที่ไม่มีอยู่ | `Save` จะโยนข้อยกเว้นหากพาธไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่า `YOUR_DIRECTORY` มีอยู่หรือใช้ `Directory.CreateDirectory` ก่อนเรียก `Save` |
| ใช้ค่าที่อยู่นอกช่วงที่อนุญาต (เช่น 0 คอลัมน์) | SDK ตรวจสอบช่วงและโยน `ArgumentOutOfRangeException` | ค่าคอลัมน์ที่ถูกต้องคือ 1‑4; ค่แถวที่ถูกต้องคือ 1‑3 สำหรับสัญลักษณ์นี้ |

### เคล็ดลับพิเศษ

หากคุณต้องการสร้างบาร์โค้ดจำนวนมากที่มีแถวและคอลัมน์ต่างกัน ให้ห่อหุ้มตรรกะการกำหนดค่าในเมธอดช่วยเหลือ:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

## สรุป

ตอนนี้คุณมีตัวอย่างแบบครบวงจรของการใช้ **barcode generator C#** เพื่อควบคุมจำนวนแถวและคอลัมน์ในบาร์โค้ด Databar Expanded Stacked ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถสร้างภาพบาร์โค้ดที่แม่นยำตรงตามข้อกำหนดการจัดวางของฮาร์ดแวร์สแกนของคุณ

จากนี้คุณอาจสำรวจต่อ:

* ปรับคุณสมบัติ `DataBar` อื่น ๆ เช่น **AspectRatio** หรือ **BarHeight**
* สร้างสัญลักษณ์อื่น (เช่น QR, Code128) ด้วยคลาส `BarcodeGenerator` เดียวกัน
* ฝัง PNG ที่สร้างลงใน PDF หรือพิมพ์โดยตรงจาก C#

ลองทดลองผสมแถว/คอลัมน์ต่าง ๆ ได้ตามต้องการ และแบ่งปันผลลัพธ์ของคุณในความคิดเห็น ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโปรเจกต์ของคุณ

- [วิธีตั้งค่าคอลัมน์สำหรับบาร์โค้ด Databar Expanded Stacked – คู่มือ C# ฉบับสมบูรณ์](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [คู่มือบาร์โค้ด Databar Expanded Stacked – วิธีสร้างและกำหนดขนาดใน C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [ตัวอย่าง Barcode Generator ใน C# – ตั้งค่าคอลัมน์, แถว & ส่งออกภาพ](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}