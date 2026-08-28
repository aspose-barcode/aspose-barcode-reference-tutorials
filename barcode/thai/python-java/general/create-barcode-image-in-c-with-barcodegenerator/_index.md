---
category: general
date: 2026-08-12
description: สร้างภาพบาร์โค้ดใน C# ด้วย BarCodeGenerator เรียนรู้วิธีสร้าง DataBar
  ควบคุมขนาดภาพบาร์โค้ด และสร้างบาร์โค้ดหลายรายการอย่างมีประสิทธิภาพ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: th
lastmod: 2026-08-12
og_description: สร้างภาพบาร์โค้ดใน C# ด้วย BarCodeGenerator. บทเรียนนี้แสดงขั้นตอนโดยละเอียดในการสร้างรหัส
  DataBar, ปรับขนาดภาพบาร์โค้ด, และสร้างบาร์โค้ดหลายรายการ.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: สร้างภาพบาร์โค้ดใน C# – คู่มือ BarCodeGenerator อย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: สร้างภาพบาร์โค้ดใน C# ด้วย BarCodeGenerator
url: /th/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดใน C# ด้วย BarCodeGenerator

หากคุณต้องการ **สร้างภาพบาร์โค้ด** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่าต้องทำอย่างไรด้วยคลาส `BarCodeGenerator` ไม่ว่าคุณจะกำลังสร้างระบบ POS สำหรับร้านค้าปลีกหรือเครื่องมือการติดตามสินค้าคงคลัง คุณจะได้เรียนรู้การสร้างสัญลักษณ์ DataBar การควบคุมขนาดภาพบาร์โค้ด และการผลิตบาร์โค้ดหลายรายการในหนึ่งการทำงาน

คุณยังจะได้ค้นพบว่า API **barcode generator c#** ช่วยให้คุณปรับขนาด เปลี่ยนรูปแบบผลลัพธ์ และจัดการกรณีขอบเช่นสตริงข้อมูลที่ไม่ถูกต้องได้อย่างไร เมื่อจบบทเรียนคุณจะสามารถ **สร้างบาร์โค้ดหลายรายการ** ได้อย่างมั่นใจโดยไม่ต้องเขียนโค้ดซ้ำซ้อน

## สิ่งที่ต้องเตรียมก่อน

- .NET 6.0 หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว  
- สภาพแวดล้อมการพัฒนา (Visual Studio, Rider หรือ VS Code)  
- แพคเกจ NuGet Aspose.BarCode for .NET (หรือไลบรารีที่เข้ากันได้ซึ่งให้ `BarCodeGenerator`)  

คุณสามารถเพิ่มแพคเกจด้วย:

```bash
dotnet add package Aspose.BarCode
```

## สิ่งที่บทเรียนนี้ครอบคลุม

1. ตั้งค่าอินสแตนซ์ **barcode generator c#** สำหรับการเข้ารหัส DataBar Omni‑directional.  
2. ปรับ **ขนาดภาพบาร์โค้ด** โดยการเปลี่ยน X‑dimension และความสูงของบาร์.  
3. ใช้ลูปเพื่อ **สร้างบาร์โค้ดหลายรายการ** ด้วยความสูงที่แตกต่างกัน.  
4. บันทึกภาพเป็นไฟล์ PNG และตรวจสอบผลลัพธ์.  

โค้ดสแนปทั้งหมดสมบูรณ์และพร้อมคัดลอก‑วางลงในโปรเจกต์คอนโซลใหม่

![Create barcode image example](barcode-example.png){alt="ตัวอย่างการสร้างภาพบาร์โค้ด"}

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้าง – พื้นฐานการสร้างภาพบาร์โค้ด

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarCodeGenerator` ด้วยสัญลักษณ์ที่ต้องการ สำหรับสัญลักษณ์ DataBar Omni‑directional คุณใช้ `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**ทำไมจึงสำคัญ:** การสร้างอินสแตนซ์ของตัวสร้างกำหนดกฎการเข้ารหัสและข้อมูลที่ส่ง หากคุณละเว้นค่า `EncodeTypes` ที่ถูกต้อง ไลบรารีจะสร้างบาร์โค้ดที่ไม่รองรับหรือโยนข้อยกเว้น

## ขั้นตอนที่ 2: กำหนดค่า X‑dimension และความสูงของบาร์ – ควบคุมขนาดภาพบาร์โค้ด

ขนาดภาพของบาร์โค้ดถูกกำหนดโดยสองพารามิเตอร์:

| Parameter | สิ่งที่ควบคุม | ช่วงทั่วไป |
|-----------|------------------|---------------|
| `x_dimension.pixels` | ความกว้างของโมดูลที่เล็กที่สุด ( “จุด” ) | 1 – 4 px |
| `bar_height.pixels`  | ความสูงของบาร์แนวตั้ง | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**เคล็ดลับ:** X‑dimension ที่เล็กลงจะให้ภาพความละเอียดสูงขึ้น แต่อาจสแกนได้ยากบนเครื่องพิมพ์คุณภาพต่ำ ปรับค่าตามอุปกรณ์สแกนที่คุณต้องการ

## ขั้นตอนที่ 3: บันทึกบาร์โค้ดแรก – สร้างภาพบาร์โค้ดความสูง 30 px

ตอนนี้คุณสามารถสร้างภาพและบันทึกลงดิสก์ได้ เมธอด `Save` รับพาธไฟล์และ enum ของรูปแบบภาพ

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**ผลลัพธ์ที่คาดหวัง:** ไฟล์ PNG ชื่อ `Databar30.png` จะปรากฏใน `C:\Barcodes` การเปิดไฟล์จะแสดงสัญลักษณ์ DataBar Omni‑directional ที่มีลวดลายคมชัดและคอนทราสต์สูง

## ขั้นตอนที่ 4: เปลี่ยนความสูงและสร้างภาพเพิ่มเติม – สร้างบาร์โค้ดหลายรายการ

เพื่อ **สร้างบาร์โค้ดหลายรายการ** ด้วยมิติที่แตกต่างกัน คุณเพียงแค่แก้ไขคุณสมบัติ `BarHeight` แล้วเรียก `Save` อีกครั้ง วิธีนี้หลีกเลี่ยงการสร้างอินสแตนซ์ใหม่ของตัวสร้าง ซึ่งช่วยประหยัดหน่วยความจำและเวลา CPU

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**ทำไมวิธีนี้ถึงได้ผล:** วัตถุ `BarCodeGenerator` เก็บสถานะการกำหนดค่าทั้งหมด การเปลี่ยนคุณสมบัติเดียวจะอัปเดตเอนจินการเรนเดอร์สำหรับการเรียก `Save` ครั้งต่อไป ทำให้คุณสามารถ **สร้างบาร์โค้ดหลายรายการ** ได้อย่างมีประสิทธิภาพ

## ขั้นตอนที่ 5: ขั้นสูง – วิธีสร้าง DataBar ด้วยข้อมูลกำหนดเอง

ตัวอย่างข้างต้นใช้ข้อมูล GS1 แบบคงที่ ในสถานการณ์จริงคุณมักต้องฝังตัวระบุผลิตภัณฑ์ที่เปลี่ยนแปลงได้ ไลบรารีรับสตริงใด ๆ ที่ตรงกับสเปค DataBar

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**ประเด็นสำคัญ:** การตั้งค่า `generator.CodeText` จะอัปเดตข้อมูลที่เข้ารหัสโดยไม่ต้องสร้างอ็อบเจกต์ใหม่ นี่เป็นรูปแบบ **how to generate databar** ที่แนะนำเมื่อจัดการชุดข้อมูลขนาดใหญ่

## ขั้นตอนที่ 6: ตรวจสอบและแก้ไขปัญหา – การรับประกันขนาดภาพบาร์โค้ดที่ถูกต้อง

หลังจากสร้างภาพแล้ว คุณอาจต้องการตรวจสอบโดยโปรแกรมว่าขนาดตรงกับที่คาดหวังหรือไม่ คลาส `Image` จาก `System.Drawing` สามารถอ่านไฟล์และรายงานขนาดได้

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

หากความสูงไม่ตรงกับค่าที่คุณตั้งไว้ ให้ตรวจสอบ:

- **X‑dimension**: ค่าที่เล็กมากอาจทำให้ตัวเรนเดอร์ปัดค่าความสูง  
- **รูปแบบภาพ**: รูปแบบบางอย่าง (เช่น JPEG) ใช้การบีบอัดที่อาจเปลี่ยนขนาดพิกเซลเมื่อบันทึก PNG จะรักษาขนาดที่แน่นอน  

## ขั้นตอนที่ 7: แนวทางปฏิบัติที่ดีที่สุดสำหรับขนาดภาพบาร์โค้ดและประสิทธิภาพ

| Recommendation | Reason |
|----------------|--------|
| รักษา `x_dimension.pixels` ระหว่าง 2 – 3 px สำหรับสแกนเนอร์ส่วนใหญ่. | สมดุลระหว่างความอ่านง่ายและขนาดไฟล์. |
| ใช้ PNG สำหรับผลลัพธ์แบบไม่มีการสูญเสียเมื่อภาพจะถูกพิมพ์. | รับประกันขนาดที่แม่นยำและขอบคมชัด. |
| ใช้ `BarCodeGenerator` ตัวเดียวซ้ำเมื่อสร้างบาร์โค้ดหลายรายการ. | ลดภาระการจัดสรรอ็อบเจกต์. |
| ตรวจสอบสตริงอินพุตกับมาตรฐาน GS1 ก่อนกำหนดให้ `CodeText`. | ป้องกันข้อยกเว้นในระหว่างรันและการสแกนที่ไม่ถูกต้อง. |
| เก็บภาพที่สร้างไว้ในโฟลเดอร์เฉพาะพร้อมรูปแบบการตั้งชื่อที่ชัดเจน (เช่น `Databar_{GTIN}.png`). | ทำให้การประมวลผลต่อเนื่องและการตรวจสอบง่ายขึ้น. |

## ตัวอย่างการทำงานเต็มรูปแบบ

ด้านล่างเป็นโปรแกรมเต็มที่รวมทุกขั้นตอนตั้งแต่การเริ่มต้นจนถึงการตรวจสอบ คัดลอกโค้ดไปยังโปรเจกต์คอนโซลใหม่และรันมัน



## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้ทางเลือกในโครงการของคุณ

- [สร้างภาพบาร์โค้ด – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [สร้างภาพบาร์โค้ด DotCode – แถวและคอลัมน์ (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [วิธีสร้าง Quiet Zone ของบาร์โค้ดสำหรับ ITF-14 ด้วย Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}