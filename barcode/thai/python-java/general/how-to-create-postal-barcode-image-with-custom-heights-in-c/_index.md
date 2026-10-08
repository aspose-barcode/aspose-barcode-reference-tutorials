---
category: general
date: 2026-09-26
description: เรียนรู้วิธีสร้างภาพบาร์โค้ดไปรษณีย์ใน C# คู่มือนี้จะแสดงวิธีสร้างบาร์โค้ด
  Planet และตั้งความสูงของบาร์โค้ดสำหรับผลลัพธ์ที่กำหนดเอง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: th
lastmod: 2026-09-26
og_description: สร้างภาพบาร์โค้ดไปรษณีย์ใน C# อย่างรวดเร็ว ทำตามบทเรียนนี้เพื่อสร้างบาร์โค้ด
  Planet ตั้งความสูงของบาร์โค้ด และสร้างไฟล์ PNG คุณภาพสูง
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: สร้างภาพบาร์โค้ดไปรษณีย์ด้วยความสูงที่กำหนดเองใน C# – คู่มือแบบขั้นตอนต่อขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: วิธีสร้างภาพบาร์โค้ดไปรษณีย์ด้วยความสูงที่กำหนดเองใน C#
url: /th/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดไปรษณีย์ด้วยความสูงที่กำหนดเองใน C#

หากคุณต้องการ **สร้างภาพบาร์โค้ดไปรษณีย์** สำหรับป้ายจดหมาย, บทเรียนนี้จะแสดงขั้นตอนที่แน่นอน คุณจะได้เรียนรู้วิธีสร้างบาร์โค้ด Planet, ปรับความสูงของบาร์, และบันทึกผลลัพธ์เป็นไฟล์ PNG — ทั้งหมดนี้ด้วยไลบรารี Aspose.BarCode สำหรับ .NET.

การสร้างภาพบาร์โค้ดไม่จำเป็นต้องใช้เครื่องมือออกแบบภายนอก เมื่อจบคู่มือคุณจะสามารถสร้างบาร์โค้ดที่มีความสูงเริ่มต้นและความสูงที่กำหนดเองสำหรับมาตรฐาน Planet และ RM4SCC พร้อมสำหรับการผสานรวมในกระบวนการจัดส่งใด ๆ

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า ที่ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE C# ใดก็ได้)  
* Aspose.BarCode สำหรับ .NET ที่เพิ่มผ่าน NuGet (`Install-Package Aspose.BarCode`)  

ไม่ต้องกำหนดค่าพิเศษเพิ่มเติม; ไลบรารีจะจัดการการเรนเดอร์ภาพภายในเอง

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า namespace

สร้างแอปพลิเคชันคอนโซลใหม่และเพิ่มคำสั่ง `using` ที่จำเป็น

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Namespace เหล่านี้ทำให้เข้าถึงคลาส `BarcodeGenerator` และ enumeration `EncodeTypes` ที่คุณจะใช้เพื่อ **สร้างบาร์โค้ด Planet** และรูปแบบไปรษณีย์อื่น ๆ

## ขั้นตอนที่ 2: สร้างบาร์โค้ด Planet ด้วยความสูงบาร์เริ่มต้น

ตัวอย่างแรกสร้างบาร์โค้ด Planet โดยใช้ความสูงบาร์เริ่มต้นของไลบรารี ซึ่งแสดงผลลัพธ์พื้นฐานก่อนที่คุณจะปรับขนาดตามต้องการ

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**ทำไมเรื่องนี้สำคัญ:** ความสูงเริ่มต้นเหมาะกับเครื่องพิมพ์ป้ายส่วนใหญ่ แต่บางกระบวนการต้องการบาร์ที่สูงกว่าเพื่อเพิ่มความน่าเชื่อถือในการสแกน โค้ดข้างต้นให้ภาพอ้างอิงเพื่อเปรียบเทียบกับเวอร์ชันความสูงที่กำหนดเอง

## ขั้นตอนที่ 3: ปรับความสูงบาร์แบบกำหนดเองให้กับบาร์โค้ด Planet

เพื่อ **กำหนดความสูงของบาร์โค้ด** ด้วยตนเอง ให้กำหนดค่าพิกเซลให้กับ `BarHeight.Pixels` โค้ดต่อไปนี้สร้างบาร์โค้ด Planet ความสูง 100 พิกเซล

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**เคล็ดลับ:** เลือกความสูงบาร์ที่ตรงกับ DPI ของเครื่องพิมพ์ของคุณ สำหรับเครื่องพิมพ์ 300 dpi บาร์ 100 พิกเซลเท่ากับประมาณ 0.33 นิ้ว ซึ่งมักแนะนำสำหรับสแกนเนอร์ไปรษณีย์

## ขั้นตอนที่ 4: สร้างบาร์โค้ด RM4SCC ด้วยความสูงเริ่มต้น

RM4SCC เป็นสัญลักษณ์ไปรษณีย์ที่พบบ่อยอีกแบบหนึ่ง กระบวนการคล้ายกับตัวอย่าง Planet แต่ใช้ `EncodeTypes.RM4SCC`

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

ขั้นตอนนี้ยืนยันว่าตรรกะ **กำหนดความสูงบาร์โค้ดแบบกำหนดเอง** ของตัวสร้างบาร์โค้ดทำงานได้กับรูปแบบไปรษณีย์ต่าง ๆ

## ขั้นตอนที่ 5: ปรับความสูงบาร์แบบกำหนดเองให้กับบาร์โค้ด RM4SCC

สุดท้าย ปรับความสูงบาร์สำหรับบาร์โค้ด RM4SCC ด้วยวิธีเดียวกับที่ทำกับบาร์โค้ด Planet

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมเต็มจะสร้างไฟล์ PNG สี่ไฟล์ในไดเรกทอรีเอาต์พุตของโปรเจกต์:

| ชื่อไฟล์ | ความสูงบาร์ | สัญลักษณ์ |
|---|---|---|
| `PostalPlanetBarHeightDefault.png` | ค่าเริ่มต้น | Planet |
| `PostalPlanetBarHeight100Pixels.png` | 100 px | Planet |
| `PostalRM4SCCBarHeightDefault.png` | ค่าเริ่มต้น | RM4SCC |
| `PostalRM4SCCBarHeight100Pixels.png` | 100 px | RM4SCC |

แต่ละภาพแสดงบาร์โค้ดที่คมชัดและคอนทราสต์สูง พร้อมสำหรับการพิมพ์บนป้ายจดหมาย คุณสามารถเปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันขนาดของบาร์

## คำถามทั่วไปและกรณีขอบ

**ถ้าฉันต้องการความสูงบาร์เป็นมิลลิเมตรแทนพิกเซลล่ะ?**  
ไลบรารีทำงานในหน่วยพิกเซลเพราะตรงกับความละเอียดของบิตแมพโดยตรง แปลงมิลลิเมตรเป็นพิกเซลโดยใช้ DPI ของเครื่องพิมพ์:  
`pixels = (mm / 25.4) * DPI`. ตั้งค่า `BarHeight.Pixels` ด้วยค่าที่คำนวณได้

**ฉันสามารถเปลี่ยนความสูงบาร์หลังจากเรียก `Save` ได้ไหม?**  
ไม่ได้. ภาพบาร์โค้ดจะถูกเรนเดอร์ในขณะที่ `Save` ถูกเรียก ปรับพารามิเตอร์ทั้งหมดก่อนเรียก `Save`

**ต้องการ X‑Dimension ที่ใหญ่ขึ้นสำหรับบาร์ที่สูงขึ้นหรือไม่?**  
การเพิ่ม `XDimension` ทำให้โมดูลแต่ละตัวกว้างขึ้น ซึ่งอาจช่วยให้อ่านได้ง่ายขึ้นบนเครื่องพิมพ์ความละเอียดต่ำ อย่างไรก็ตาม มันก็ทำให้ความกว้างโดยรวมของบาร์โค้ดเพิ่มขึ้น ทดสอบค่าทั้งสองเพื่อหาจุดสมดุลที่เหมาะกับขนาดป้ายของคุณ

**โค้ดเดียวกันทำงานบน .NET Framework 4.8 ได้หรือไม่?**  
ได้. Aspose.BarCode รองรับ .NET Framework 4.6.2 ขึ้นไป ดังนั้นคุณสามารถกำหนดเป้าหมายรันไทม์เก่าได้โดยไม่ต้องแก้ไขโค้ด

## โค้ดต้นฉบับเต็มสำหรับคัดลอก‑วางอย่างรวดเร็ว

ด้านล่างเป็นโปรแกรมที่สมบูรณ์และสามารถรันได้ ซึ่งรวมขั้นตอนทั้งหมดที่อธิบายไว้ข้างต้น

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

รันโปรแกรม และคอนโซลจะแจ้งว่าภาพแต่ละไฟล์ถูกบันทึกแล้ว คุณสามารถฝังไฟล์ PNG เหล่านี้ลงในเทมเพลตป้ายจดหมายของคุณ พิมพ์ออก หรือส่งไปยัง API โลจิสติกส์ของบุคคลที่สาม

## สรุป

คุณตอนนี้รู้วิธี **สร้างภาพบาร์โค้ดไปรษณีย์** ใน C# ด้วย Aspose.BarCode คู่มือได้ครอบคลุมการสร้างบาร์โค้ด Planet, การปรับความสูงบาร์, และการใช้เทคนิคเดียวกันกับบาร์โค้ด RM4SCC โดยการควบคุม `XDimension` และ `BarHeight.Pixels` คุณจะได้ผลลัพธ์ที่แม่นยำตรงตามข้อกำหนดของบริการไปรษณีย์

ต่อไป, สำรวจหัวข้อที่เกี่ยวข้องเช่น **การสร้าง QR code สำหรับการติดตาม**, **การฝังบาร์โค้ดในใบแจ้งหนี้ PDF**, หรือ **การประมวลผลหลายภาพบาร์โค้ดเป็นชุด** การปรับความสูงบาร์เป็นเพียงหนึ่งในหลาย ๆ ตัวเลือก; คุณยังสามารถปรับสี, เพิ่มข้อความที่อ่านได้โดยมนุษย์, หรือส่งออกเป็น SVG สำหรับใช้บนเว็บได้อีกด้วย

ขอให้เขียนโค้ดสนุกและการส่งจดหมายของคุณสแกนได้อย่างไม่มีข้อผิดพลาด!

## สิ่งที่คุณควรเรียนต่อไป?

หัวข้อการสอนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณ

- [สร้างภาพบาร์โค้ดไปรษณีย์ใน C# – คู่มือขั้นตอนโดยละเอียด](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [สร้างภาพบาร์โค้ดไปรษณีย์ – ปรับความสูงบาร์โค้ดได้ง่าย](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [วิธีสร้างบาร์โค้ดไปรษณีย์ใน C# ด้วยมิติที่กำหนดเอง](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}