---
category: general
date: 2026-08-22
description: วิธีสร้างบาร์โค้ดอย่างรวดเร็วและเรียนรู้วิธีเปลี่ยนขนาดบาร์โค้ดขณะส่งออกภาพบาร์โค้ดเป็น
  PNG ด้วย Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: th
lastmod: 2026-08-22
og_description: วิธีสร้างบาร์โค้ดใน C# และปรับขนาดบาร์โค้ดได้อย่างง่ายดายก่อนส่งออกภาพบาร์โค้ดเป็น
  PNG. อ่านคู่มือฉบับเต็มนี้.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: วิธีสร้างภาพบาร์โค้ดด้วยขนาดที่กำหนดเองใน C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างภาพบาร์โค้ดด้วยขนาดที่กำหนดเองใน C#
url: /th/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดด้วยขนาดกำหนดเองใน C#

หากคุณต้องการ **วิธีสร้างบาร์โค้ด** สำหรับระบบอัตโนมัติไปรษณีย์ การติดตามสินค้าคงคลัง หรือบัตรงานกิจกรรม คู่มือนี้จะแสดงวิธีแก้ปัญหาแบบครบถ้วนพร้อมรันได้ใน C# คุณยังจะได้เรียนรู้ **วิธีเปลี่ยนขนาดบาร์โค้ด** และ **การส่งออกไฟล์ภาพบาร์โค้ด** ในรูปแบบ PNG โดยไม่ต้องออกจาก IDE ของคุณ

เราจะใช้ไลบรารี Aspose.BarCode เนื่องจากรองรับสัญลักษณ์ OneCode ให้คุณควบคุมมิติพิกเซลต่อพิกเซลได้ และจัดการการส่งออกภาพด้วยการเรียกเมธอดเดียว เพียงสิ้นสุดบทเรียนคุณจะมีไฟล์ PNG สี่ไฟล์—แต่ละไฟล์เป็นบาร์โค้ด OneCode ที่มีจำนวนหลักต่างกัน

## ข้อกำหนดเบื้องต้น

- .NET 6.0 หรือใหม่กว่า (โค้ดยังทำงานได้กับ .NET Framework 4.6+)
- Visual Studio 2022 (หรือโปรแกรมแก้ไข C# ใด ๆ ที่คุณชอบ)
- อ้างอิง NuGet ไปยัง **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

> **เคล็ดลับ:** หากคุณกำลังประเมินไลบรารีนี้ Aspose มีการทดลองใช้ฟรี 30 วันที่รวมคุณสมบัติบาร์โค้ดทั้งหมด

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์คอนโซลขนาดเล็ก

สร้างแอปพลิเคชันคอนโซลใหม่และเพิ่มแพ็กเกจ Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

ไฟล์ `Program.cs` ที่สร้างขึ้นจะบรรจุตรรหัสการสร้างบาร์โค้ดทั้งหมด

## ขั้นตอนที่ 2: วิธีสร้างบาร์โค้ด – สร้างเมธอดที่ใช้ซ้ำได้

ด้านล่างเป็นเมธอดที่ทำงานอิสระซึ่งรับสตริงข้อมูล ชื่อไฟล์ที่ต้องการ และพารามิเตอร์ขนาดแบบเลือกได้ เมธอดนี้แสดงรูปแบบหลักของ **วิธีสร้างบาร์โค้ด**

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### ทำไมเมธอดนี้ถึงสำคัญ

- **การห่อหุ้ม (Encapsulation):** การตั้งค่าที่เกี่ยวกับขนาดทั้งหมดอยู่ในที่เดียว ทำให้เรียกเมธอดด้วยมิติที่ต่างกันได้อย่างง่ายดาย
- **การนำกลับมาใช้ใหม่ (Reusability):** คุณสามารถใช้เมธอดเดียวกันสำหรับความยาวสตริง OneCode ใด ๆ ซึ่งสำคัญเพราะ OneCode รองรับได้เพียง 20‑31 หลักเท่านั้น
- **ความชัดเจน (Clarity):** คอมเมนต์ที่มีอีโมจิช่วยนำผู้อ่านผ่านสามขั้นตอนเชิงตรรกะ—การเริ่มต้น การเปลี่ยนขนาด และการส่งออก

## ขั้นตอนที่ 3: เปลี่ยนขนาดบาร์โค้ดตามความต้องการที่แตกต่าง

บางครั้งสแกนเนอร์ต้องการบาร์โค้ดที่สูงกว่า หรือการจัดหน้าแบบพิมพ์ต้องการโมดูลที่แคบกว่า คุณสมบัติ `XDimension.Pixels` ควบคุมความกว้างของโมดูลบาร์โค้ดหนึ่งตัว ในขณะที่ `BarHeight.Pixels` กำหนดความสูงโดยรวม

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**จุดสำคัญเมื่อคุณเปลี่ยนขนาด:**

- **มิติ X ขั้นต่ำ:** 1 พิกเซลเป็นค่าที่เทคนิคอนุญาตได้ แต่สแกนเนอร์ส่วนใหญ่ต้องการอย่างน้อย 2 พิกเซลเพื่อการอ่านที่เชื่อถือได้
- **ความสูงสูงสุด:** ไม่มีขีดจำกัดที่แน่นอน แต่บาร์โค้ดที่สูงมากอาจเกินพื้นที่พิมพ์บนฉลากมาตรฐาน
- **อัตราส่วนภาพ:** รักษาสัดส่วนความสูงต่อความกว้างของโมดูลให้สมดุล (≈12‑15 × ความกว้างโมดูล) เพื่อหลีกเลี่ยงการบิดเบือน

## ขั้นตอนที่ 4: ส่งออกภาพบาร์โค้ดในรูปแบบอื่น (ทางเลือก)

เมธอด `Save` รองรับค่าต่าง ๆ ของ `BarCodeImageFormat` ได้แก่ `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. หากคุณต้องการรูปแบบเวกเตอร์ที่ไม่มีการสูญเสีย คุณสามารถส่งออกเป็น `Svg` แทนได้

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

การส่งออกเป็น PNG เป็นตัวเลือกที่นิยมที่สุด เพราะรักษาขอบคมชัดและได้รับการสนับสนุนอย่างกว้างขวางจากเว็บเบราว์เซอร์และกระบวนการพิมพ์

## ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ PNG สี่ไฟล์ในโฟลเดอร์โปรเจกต์:

- `PostalOneCodeBarcode20Digits.png` – บาร์โค้ด OneCode 20 หลัก
- `PostalOneCodeBarcode25Digits.png` – บาร์โค้ด OneCode 25 หลัก
- `PostalOneCodeBarcode29Digits.png` – บาร์โค้ด OneCode 29 หลัก
- `PostalOneCodeBarcode31Digits.png` – บาร์โค้ด OneCode 31 หลัก

แต่ละภาพจะมีลักษณะคล้ายกับภาพตัวอย่างด้านล่าง (กราฟิกจริงจะขึ้นอยู่กับข้อมูลตัวเลขที่คุณใส่)

![ตัวอย่างวิธีสร้างบาร์โค้ด](https://example.com/placeholder.png "ตัวอย่างวิธีสร้างบาร์โค้ด")

*ข้อความ alt ของภาพรวมถึงคีย์เวิร์ดหลักเพื่อการเข้าถึงและ SEO.*

## คำถามทั่วไปและกรณีขอบ

| คำถาม | คำตอบ |
|----------|--------|
| **ถ้าสตริงข้อมูลสั้นกว่า 20 หลักจะทำอย่างไร?** | OneCode ต้องการอย่างน้อย 20 หลัก เติมสตริงด้วยศูนย์นำหน้า หรือใช้สัญลักษณ์อื่น (เช่น Code128). |
| **ฉันสามารถสร้างบาร์โค้ดในสภาพแวดล้อมหลายเธรดได้หรือไม่?** | ได้. `BarcodeGenerator` ไม่ปลอดภัยต่อหลายเธรด ดังนั้นให้สร้างอินสแตนซ์ของ generator แยกสำหรับแต่ละเธรด. |
| **ฉันจะตั้งค่าสีพื้นหลังอย่างไร?** | ใช้ `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` ก่อนเรียก `Save`. |
| **มีวิธีใส่ภาพโดยตรงในหน้า HTML หรือไม่?** | บันทึกภาพลงใน `MemoryStream` แปลงเป็น Base64 แล้วใส่ลงใน `<img src="data:image/png;base64,..." />`. |

## สรุป

ตอนนี้คุณทราบ **วิธีสร้างภาพบาร์โค้ด** ใน C# ด้วย Aspose.BarCode, วิธี **เปลี่ยนขนาดบาร์โค้ด** โดยปรับ X‑dimension และความสูงของบาร์, และวิธี **ส่งออกไฟล์ภาพบาร์โค้ด** ในรูปแบบ PNG (หรือรูปแบบอื่น) เมธอด `GenerateOneCode` ที่ใช้ซ้ำได้ทำให้คุณสร้างบาร์โค้ด OneCode ใด ๆ ระหว่าง 20 ถึง 31 หลักด้วยบรรทัดโค้ดเดียว

ต่อจากนี้คุณอาจ:

- ทดลองใช้สัญลักษณ์อื่น (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- รวม generator เข้ากับ Web API ที่ส่งคืนภาพบาร์โค้ดตามคำขอ
- ผสานผลลัพธ์ PNG กับไลบรารี PDF เพื่อฝังบาร์โค้ดลงในฉลากจัดส่ง

ขอให้สนุกกับการเขียนโค้ด และอย่าลังเลที่จะแบ่งปันวิธีของคุณในความคิดเห็น!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญคุณลักษณะ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอน](/barcode/english/net/datamatrix-barcode-configuration/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพกำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [วิธีสร้างและปรับความสูงบาร์โค้ดสำหรับ One-Dimensional Databar โดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}