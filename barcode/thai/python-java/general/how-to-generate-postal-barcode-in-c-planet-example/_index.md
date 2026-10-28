---
category: general
date: 2026-10-28
description: สร้างบาร์โค้ดไปรษณีย์ใน C# โดยใช้รูปแบบ Planet ตัวอย่างบาร์โค้ด Planet
  นี้แสดงวิธีตั้งความกว้างของบาร์โค้ดและบันทึกบาร์ที่เต็มและบาร์ที่ว่าง.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: th
lastmod: 2026-10-28
og_description: สร้างบาร์โค้ดไปรษณีย์ใน C# พร้อมตัวอย่างบาร์โค้ด Planet ที่สมบูรณ์
  เรียนรู้การตั้งความกว้างของบาร์โค้ด สร้างบาร์ที่เต็ม และสร้างภาพบาร์ว่าง.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: สร้างบาร์โค้ดไปรษณีย์ใน C# – คู่มือแบบขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างบาร์โค้ดไปรษณีย์ใน C# – ตัวอย่าง Planet
url: /th/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างรหัสบาร์ไปรษณีย์ใน C# – ตัวอย่าง Planet

หากคุณต้องการสร้างรหัสบาร์ไปรษณีย์ใน C# คู่มือนี้จะพาคุณผ่านโซลูชันที่สมบูรณ์ คุณจะได้เห็นตัวอย่างรหัสบาร์ Planet ที่เข้ารหัสสตริงตัวเลข ให้คุณตั้งความกว้างของรหัสบาร์ และบันทึกภาพบาร์ที่เต็มและว่าง

การสร้างรหัสบาร์ไปรษณีย์ไม่ต้องการ pipeline การสร้างที่ซับซ้อน เมื่อจบบทเรียนนี้คุณจะสามารถรวมการสร้างรหัสบาร์เข้าไปในแอปพลิเคชัน .NET ใด ๆ ปรับแต่งมิติ X‑dimension และเลือกว่าบาร์จะแสดงเป็นแบบเต็มหรือว่าง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้แน่ใจว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า  
* สภาพแวดล้อมการพัฒนา C# (Visual Studio, VS Code หรือ Rider)  
* แพ็กเกจ **Aspose.BarCode for .NET** จาก NuGet (เวอร์ชัน 23.10 หรือใหม่กว่า)  

คุณสามารถเพิ่มแพ็กเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

โค้ดสแนปช็อตด้านล่างสมมติว่าคุณได้เพิ่ม `using Aspose.BarCode.Generation;` ไว้ที่ส่วนหัวของไฟล์แล้ว

## สร้างรหัสบาร์ไปรษณีย์ด้วยสัญลักษณ์ Planet

ขั้นตอนแรกคือการสร้างอินสแตนซ์ `BarcodeGenerator` ที่ใช้สัญลักษณ์ Planet ซึ่งเป็นรูปแบบรหัสบาร์ไปรษณีย์ที่หลายบริการไปรษณีย์แห่งชาติใช้

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมจึงสำคัญ:**  
`EncodeTypes.Planet` บอกไลบรารีให้ใช้มาตรฐานรหัสบาร์ Planet ซึ่งเข้ารหัสข้อมูลตัวเลขเป็นชุดของบาร์และช่องว่าง ตัวสร้างรับสตริงข้อมูล (`"123456"` ในตัวอย่างนี้) ที่คุณต้องการเข้ารหัส

เมื่อรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์ในไดเรกทอรีทำงานของไฟล์ปฏิบัติการ:

* **PostalPlanetFilledBars.png** – บาร์แสดงเป็นสี่เหลี่ยมสีดำทึบ  
* **PostalPlanetEmptyBars.png** – บาร์แสดงเป็นสี่เหลี่ยมสีขาวที่มีขอบสีดำ เหมาะสำหรับพิมพ์บนพื้นหลังสีเข้ม

## ตั้งความกว้างของรหัสบาร์ (X‑dimension) เป็นพิกเซล

ขนาดภาพของรหัสบาร์ถูกควบคุมโดย X‑dimension ซึ่งกำหนดความกว้างของบาร์แต่ละบาร์ การปรับค่าดังกล่าวช่วยให้รหัสบาร์สแกนได้อย่างถูกต้องที่ความละเอียดการพิมพ์ที่ตั้งไว้

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**ทำไมคุณควรตั้งค่า:**  
X‑dimension ที่ใหญ่ขึ้นทำให้รหัสบาร์สแกนง่ายขึ้นด้วยสแกนเนอร์ความละเอียดต่ำ ส่วนค่าที่เล็กลงจะลดขนาดภาพโดยรวมสำหรับการพิมพ์ความหนาแน่นสูง ความกว้างเริ่มต้นคือ 2 พิกเซล; 4 พิกเซลเป็นค่าที่สมดุลสำหรับเครื่องพิมพ์เดสก์ท็อปส่วนใหญ่

คุณสามารถทดลองค่าต่าง ๆ ได้:

| พิกเซล | การใช้งานทั่วไป |
|--------|-----------------|
| 2      | ป้ายความหนาแน่นสูง |
| 4      | การพิมพ์สำนักงานมาตรฐาน |
| 6‑8    | ป้ายขนาดใหญ่ |

**เคล็ดลับ:** ทดสอบรหัสบาร์ที่สร้างขึ้นกับสแกนเนอร์เป้าหมายของคุณทุกครั้งหลังเปลี่ยน X‑dimension

## ตัวอย่างรหัสบาร์ Planet – บาร์เต็ม vs บาร์ว่าง

รหัสบาร์ Planet สามารถเรนเดอร์เป็นบาร์เต็ม (solid) หรือบาร์ว่าง (outlined) ได้ คุณสมบัติ `FilledBars` จะสลับพฤติกรรมนี้

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**ทำไมคุณอาจเลือกบาร์ว่าง:**  
บาร์ว่างช่วยเพิ่มคอนทราสต์บนบรรจุภัณฑ์สีเข้ม เพราะภายในบาร์สีขาวโดดเด่นบนพื้นหลังสีมืด บาร์เต็มเป็นค่าเริ่มต้นและทำงานได้ดีบนสื่อสีอ่อน

**ผลลัพธ์ที่คาดหวัง:**  

*ทั้งสองภาพแสดงข้อมูลที่เข้ารหัสเดียวกัน (`123456`).* ความแตกต่างเพียงอย่างเดียวคือสไตล์ของบาร์ รายละเอียดข้อความที่คุณจะเห็น:

* **ภาพบาร์เต็ม:** บาร์สีดำแนวตั้งทึบบนพื้นหลังสีขาว  
* **ภาพบาร์ว่าง:** ขอบสีดำสร้างรูปแบบเดียวกัน แต่มีภายในสีขาว

คุณสามารถเปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันว่ารูปแบบตรงตามสเปค Planet

## ปรับแต่งคุณสมบัติเพิ่มเติมของรหัสบาร์ (ไม่บังคับ)

แม้ขั้นตอนหลักข้างต้นจะครอบคลุมกรณีส่วนใหญ่ คุณอาจต้องการปรับตั้งค่าอื่น ๆ เพิ่มเติม:

| คุณสมบัติ | คำอธิบาย | ค่าที่พบบ่อย |
|----------|-------------|---------------|
| `Barcode.Color` | สีของบาร์ | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | สีพื้นหลัง | `System.Drawing.Color.White` |
| `Barcode.CodeText` | ข้อความที่อ่านได้โดยมนุษย์แสดงใต้รหัสบาร์ | เหมือนข้อมูลที่เข้ารหัสหรือป้ายกำหนดเอง |
| `Barcode.ImageFormat` | รูปแบบไฟล์ผลลัพธ์ (PNG, JPEG, BMP, ฯลฯ) | `BarCodeImageFormat.Png` |

ตัวอย่างการตั้งค่าสีพื้นหน้าแบบกำหนดเอง:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

การปรับแต่งเหล่านี้ช่วยให้คุณสอดคล้องกับแบรนด์ของบริษัทหรือข้อกำหนดการพิมพ์เฉพาะ

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|---------|
| รหัสบาร์อ่านไม่ได้ | X‑dimension เล็กเกินไปสำหรับ DPI ของเครื่องพิมพ์ | เพิ่ม `XDimension.Pixels` เป็น 4 หรือมากกว่า |
| ไฟล์ภาพเสียหาย | ขาดสิทธิ์เขียนในโฟลเดอร์เป้าหมาย | ใช้พาธแบบเต็มหรือให้แน่ใจว่าโฟลเดอร์มีอยู่ |
| ใช้สัญลักษณ์ผิด | ส่ง `EncodeTypes.Code128` แทน `EncodeTypes.Planet` | ตรวจสอบอาร์กิวเมนต์ `EncodeTypes` ให้ตรงกับรูปแบบไปรษณีย์ |

**เคล็ดลับระดับมืออาชีพ:** สร้างรหัสบาร์ทดสอบและสแกนด้วยฮาร์ดแวร์ที่ใช้จริงก่อนนำไปใช้งานจริง

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นแอปพลิเคชันคอนโซลที่รวมทุกขั้นตอนที่กล่าวมา คัดลอกโค้ดไปยังโปรเจกต์คอนโซล .NET ใหม่และรันเพื่อดูไฟล์ PNG สองไฟล์ปรากฏในโฟลเดอร์ผลลัพธ์

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**ขั้นตอนการตรวจสอบ:**  

1. สร้างโปรเจกต์ (`dotnet build`)  
2. รันไฟล์ปฏิบัติการ (`dotnet run`)  
3. หาไฟล์ `PostalPlanetFilledBars.png` และ `PostalPlanetEmptyBars.png` ในโฟลเดอร์ `bin/Debug/net6.0`  
4. เปิดแต่ละภาพ; คุณควรเห็นชุดบาร์แนวตั้งที่แทนสตริงตัวเลข

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดตัวอย่างทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโครงการของคุณ

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}