---
category: general
date: 2026-08-22
description: บทเรียนการสร้างบาร์โค้ดด้วย C# แสดงวิธีการสร้างไฟล์ PNG ของบาร์โค้ด,
  สร้างบาร์โค้ด DataBar, และปรับความสูงของบาร์โค้ดในไม่กี่ขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: th
lastmod: 2026-08-22
og_description: คู่มือการสร้างบาร์โค้ดด้วย C# จะพาคุณผ่านขั้นตอนการสร้างไฟล์ PNG ของบาร์โค้ด,
  สร้างบาร์โค้ด DataBar, และปรับความสูงของบาร์โค้ดอย่างมีประสิทธิภาพ.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: ตัวสร้างบาร์โค้ด C# – สร้างบาร์โค้ด DataBar และปรับความสูง
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด DataBar Omni‑directional
url: /th/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ barcode generator C# เพื่อสร้าง DataBar Omni‑directional barcodes

หากคุณต้องการ **barcode generator C#** ที่สามารถสร้างภาพ PNG คุณภาพสูง คู่มือนี้พร้อมให้คุณเรียนรู้วิธีสร้างไฟล์ PNG ของบาร์โค้ด, สร้าง DataBar Omni‑directional barcode, และปรับความสูงของบาร์โค้ดโดยไม่ต้องออกจาก IDE

การสร้างบาร์โค้ดด้วยโปรแกรมช่วยลดขั้นตอนการใช้โปรแกรมกราฟิกด้วยตนเอง เมื่อจบบทเรียนนี้คุณจะมีไฟล์ PNG สองไฟล์—หนึ่งไฟล์ความสูงบาร์ 30 พิกเซลและอีกไฟล์ความสูงบาร์ 60 พิกเซล—พร้อมใช้ในใบแจ้งหนี้, ป้าย, หรือระบบสินค้าคงคลัง

**Prerequisites**

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+)
- การอ้างอิงไปยังแพคเกจ NuGet `Aspose.BarCode` (หรือไลบรารีใด ๆ ที่มี API คล้ายกัน)
- ความคุ้นเคยพื้นฐานกับ C# และ Visual Studio หรือ IDE ที่คุณชื่นชอบ

---

## Step 1: ตั้งค่าโครงการ barcode generator C#

การสร้างอินสแตนซ์ **barcode generator C#** เป็นขั้นตอนแรกที่ทำ คอนสตรัคเตอร์รับอากิวเมนต์สองค่า: ประเภทบาร์โค้ด (`EncodeTypes.DatabarOmniDirectional`) และข้อมูลที่ต้องเข้ารหัส ในตัวอย่างนี้ข้อมูลเป็นรูปแบบ GS1 Application Identifier สำหรับ GTIN 14 หลัก

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**ทำไมจึงสำคัญ:** enum `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีให้เรนเดอร์ DataBar ที่อ่านได้จากทุกทิศทาง ซึ่งเหมาะกับป้ายเล็กของร้านค้าปลีก

---

## Step 2: กำหนดมิติของโมดูล (X‑dimension)

X‑dimension ควบคุมความกว้างของโมดูลบาร์โค้ดแต่ละตัว การตั้งค่าเป็น 2 พิกเซลให้ภาพคมชัดและขนาดไฟล์เล็ก

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**เคล็ดลับ:** หากต้องการบาร์โค้ดแคบเพื่อประหยัดพื้นที่ ให้ลดค่าเป็น 1 พิกเซล แต่ต้องทดสอบความสามารถในการอ่านด้วยสแกนเนอร์

---

## Step 3: สร้าง PNG แรกด้วยความสูงบาร์ 30 พิกเซล

ความสูงบาร์กำหนดความสูงของเส้นบาร์ 30 พิกเซลเป็นค่าเริ่มต้นทั่วไปสำหรับป้ายมาตรฐาน

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

ไฟล์ `DatabarBarHeight30Pixels.png` ตอนนี้เป็น **generate barcode PNG** ที่สามารถใช้โดยตรงในหน้าเว็บหรือพิมพ์ตามต้องการ

---

## Step 4: ปรับความสูงบาร์เป็น 60 พิกเซลและบันทึก PNG ที่สอง

การเปลี่ยนความสูงบาร์ทำได้ง่ายโดยกำหนดค่าต่าง ๆ ให้กับ property เดียวกัน นี่แสดงความสามารถ **adjust barcode height** ของ generator

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

ตอนนี้คุณมี `DatabarBarHeight60Pixels.png` ซึ่งเหมาะกับบรรจุภัณฑ์ขนาดใหญ่ที่ต้องสแกนจากระยะไกล

**ผลลัพธ์ที่คาดหวัง**

- `DatabarBarHeight30Pixels.png` – DataBar Omni‑directional ขนาดกะทัดรัด สูง 30 px
- `DatabarBarHeight60Pixels.png` – บาร์โค้ดเดียวกัน สูงเป็นสองเท่าสำหรับการมองเห็นที่ดียิ่งขึ้น

ทั้งสองไฟล์เป็น PNG คุณภาพ lossless และรองรับความโปร่งใสหากต้องการ

---

## วิธีสร้างไฟล์ barcode PNG ในรูปแบบต่าง ๆ

แม้บทเรียนนี้เน้น PNG แต่เมธอด `Save` รองรับรูปแบบอื่นเช่น `Jpeg`, `Bmp` และ `Svg` หากต้องการ **how to generate barcode** ในรูปแบบอื่น เพียงเปลี่ยน `BarCodeImageFormat.Png` เป็นค่า enum ที่ต้องการ:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

การเลือก SVG มีประโยชน์เมื่อคุณต้องการภาพเวกเตอร์ที่ขยายได้โดยไม่เสียความคมชัด

---

## ข้อผิดพลาดทั่วไปเมื่อคุณ **create DataBar barcode** รูปภาพ

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| Barcode appears blurry | X‑dimension too low for the target resolution | Increase `XDimension.Pixels` to 3 or 4 |
| Scanner cannot read the code | Bar height too short for the scanner’s optics | Use a minimum of 30 pixels or follow the scanner’s specifications |
| Data string is rejected | Incorrect GS1 formatting | Ensure the string starts with the proper Application Identifier, e.g., `(01)` for GTIN‑14 |

การแก้ไขจุดเหล่านี้ตั้งแต่ต้นจะช่วยประหยัดเวลาเมื่อนำบาร์โค้ดเข้าสู่กระบวนการผลิต

---

## เคล็ดลับขั้นสูง: ใช้ generator เดียวกันสำหรับหลายบาร์โค้ด

หากต้องการ **generate barcode PNG** สำหรับหลายผลิตภัณฑ์ ให้ใช้อินสแตนซ์ `BarcodeGenerator` เดียวกันและอัปเดตเฉพาะ property `CodeText` เท่านั้น:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

รูปแบบนี้ช่วยลดภาระการสร้างอ็อบเจ็กต์ใหม่และทำให้โค้ดของคุณกระชับขึ้น

---

## สรุป

คุณได้เรียนรู้เวิร์กโฟลว์ **barcode generator C#** ครบวงจรที่ **creates DataBar barcodes**, **generates barcode PNG** files, และให้คุณ **adjust barcode height** เพียงเปลี่ยนค่า property เดียว ตัวอย่างครอบคลุมตั้งแต่การตั้งค่าโครงการจนถึงการจัดการกรณีขอบ เพื่อให้คุณสามารถรวมการสร้างบาร์โค้ดเข้าในแอปพลิเคชัน .NET ใด ๆ ได้อย่างมั่นใจ

**ขั้นตอนต่อไป**

- สำรวจ symbology อื่น ๆ (`EncodeTypes.QR`, `EncodeTypes.Code128`) เพื่อขยายโซลูชันของคุณ
- ผสาน generator กับ ASP.NET Core เพื่อให้บริการบาร์โค้ดแบบ on‑the‑fly ผ่าน API endpoint
- ทดลองใช้ตัวเลือกสี (`generator.Parameters.Barcode.ForeColor`) เพื่อสร้างแบรนด์ที่โดดเด่น

ขอให้เขียนโค้ดสนุกและสแกนได้เร็วเสมอ!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}