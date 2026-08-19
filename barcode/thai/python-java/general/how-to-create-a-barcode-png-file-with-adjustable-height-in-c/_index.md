---
category: general
date: 2026-08-19
description: เรียนรู้วิธีสร้างไฟล์ PNG ของบาร์โค้ดด้วย C# และปรับความสูงของมัน รวมถึงวิธีสร้างภาพบาร์โค้ดและเปลี่ยนความสูงของบาร์โค้ดได้อย่างง่ายดาย.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: th
lastmod: 2026-08-19
og_description: สร้างไฟล์ PNG ของบาร์โค้ดใน C# และเรียนรู้วิธีสร้างภาพบาร์โค้ด ปรับความสูงของบาร์โค้ด
  และเปลี่ยนความสูงของบาร์โค้ดเพื่อการสแกนที่เหมาะสมที่สุด
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: สร้างไฟล์ PNG ของบาร์โค้ดใน C# – คู่มือแบบขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: วิธีสร้างไฟล์ PNG ของบาร์โค้ดที่สามารถปรับความสูงได้ใน C#
url: /th/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ PNG ของบาร์โค้ดที่สามารถปรับความสูงได้ใน C#

หากคุณต้องการสร้าง **ไฟล์ PNG ของบาร์โค้ด** ใน C# คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียด คุณจะได้เห็นตัวอย่างที่สมบูรณ์และสามารถรันได้ซึ่งสาธิต **วิธีสร้างภาพบาร์โค้ด** และ **วิธีปรับความสูงของบาร์โค้ด** สำหรับกรณีการใช้งานที่แตกต่างกัน

การสร้างไฟล์ PNG ของบาร์โค้ดเป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, จุดขาย, และแอปพลิเคชันใด ๆ ที่ต้องพิมพ์หรือแสดงข้อมูลที่เครื่องอ่านได้ เมื่อจบบทเรียนนี้คุณจะสามารถเปลี่ยนความสูงของบาร์โค้ด, บันทึกไฟล์ PNG หลายไฟล์, และเข้าใจผลกระทบของความสูงต่อความน่าเชื่อถือของการสแกน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นใหม่กว่าที่ติดตั้งแล้ว  
* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)  
* แพ็กเกจ **Aspose.BarCode for .NET** จาก NuGet (ตัวอย่างโค้ดใช้ไลบรารีนี้)  

คุณสามารถเพิ่มแพ็กเกจจากบรรทัดคำสั่ง:

```bash
dotnet add package Aspose.BarCode
```

> **เคล็ดลับ:** เวอร์ชันทดลองฟรีของ Aspose.BarCode ใช้ได้สำหรับการพัฒนาและทดสอบ สำหรับการใช้งานจริงให้ขอรับคีย์ลิขสิทธิ์

## ติดตั้งไลบรารีบาร์โค้ด

ขั้นตอนแรกคือการอ้างอิงไลบรารีในโปรเจกต์ของคุณ เพิ่มคำสั่ง `using` ต่อไปนี้ที่ส่วนบนของไฟล์ C# ของคุณ:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

เนมสเปซเหล่านี้ทำให้คุณเข้าถึง `BarcodeGenerator`, `EncodeTypes`, และ `BarCodeImageFormat`

## สร้างไฟล์ PNG ของบาร์โค้ด

ตอนนี้เราจะสร้างอ็อบเจกต์ `BarcodeGenerator` ที่จะส่งออก **ไฟล์ PNG ของบาร์โค้ด** ตัวอย่างใช้สัญลักษณ์ Databar OmniDirectional แต่คุณสามารถเปลี่ยน `EncodeTypes.DatabarOmniDirectional` เป็นชนิดที่รองรับอื่นได้

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

สตริง `"(01)12345678901231"` เป็นรูปแบบ GS1 Application Identifier สำหรับ GTIN 14 หลัก ปรับข้อมูลให้ตรงกับตัวระบุสินค้าของคุณเอง

## ตั้งค่า X‑dimension (ไม่บังคับ)

X‑dimension กำหนดความกว้างของโมดูลบาร์โค้ดหนึ่งหน่วย ค่าที่เป็นพิกเซลให้การควบคุมขนาดภาพได้อย่างแม่นยำ

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

ค่าที่ `2` พิกเซลทำงานได้ดีสำหรับการแสดงบนหน้าจอส่วนใหญ่ หากต้องการบาร์โค้ดที่ใหญ่ขึ้นเมื่อพิมพ์ให้เพิ่มค่า

## ปรับความสูงของบาร์โค้ดและบันทึกไฟล์ PNG

คุณสมบัติ **BarHeight** ควบคุมขนาดแนวตั้งของบาร์ การเปลี่ยนค่าดังกล่าวทำให้คุณ **ปรับความสูงของบาร์โค้ด** ได้โดยไม่กระทบข้อมูลที่เข้ารหัส

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

ไฟล์ `DatabarBarHeight30Pixels.png` ตอนนี้เป็น **ไฟล์ PNG ของบาร์โค้ด** ที่สูง 30 พิกเซล  

เพื่อ **เปลี่ยนความสูงของบาร์โค้ด** และสร้างภาพที่สอง เพียงกำหนดค่าใหม่แล้วเรียก `Save` อีกครั้ง:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

คุณจะมีไฟล์ PNG สองไฟล์ — หนึ่งไฟล์ที่ 30 px และอีกไฟล์ที่ 60 px — แสดงให้เห็นวิธี **ปรับความสูงของบาร์โค้ด** อย่างรวดเร็ว

### ทำไมความสูงของบาร์จึงสำคัญ

* **ความอ่านได้:** เครื่องสแกนคาดหวังความสูงขั้นต่ำเพื่อการตรวจจับที่เชื่อถือได้ บาร์โค้ดสั้นเกินไปอาจพลาดได้ โดยเฉพาะกับกล้องความละเอียดต่ำ  
* **ความสวยงาม:** การทำให้ความสูงของบาร์โค้ดสอดคล้องกับองค์ประกอบการออกแบบรอบข้างทำให้ UI ดูเรียบร้อยขึ้น  
* **ข้อจำกัดการพิมพ์:** เครื่องพิมพ์ฉลากบางรุ่นมีช่องความสูงคงที่ การปรับความสูงของบาร์โค้ดช่วยให้พอดีกับช่องนั้น  

**แนวทางปฏิบัติที่ดีที่สุด:** ให้ความสูงเป็นหลายเท่าของ X‑dimension (เช่น 30 px เมื่อ X‑dimension เป็น 2 px) เพื่อรักษาสัดส่วนและหลีกเลี่ยงการบิดเบือน

## ตัวอย่างเต็ม

ด้านล่างเป็นโปรแกรมเต็มรูปแบบที่คุณสามารถคัดลอกไปวางในแอปพลิเคชันคอนโซลและรันได้ทันที

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

เมื่อรันโปรแกรมจะสร้างไฟล์สองไฟล์ในไดเรกทอรีทำงานของไฟล์ executable:

* `DatabarBarHeight30Pixels.png` – ไฟล์ PNG ของบาร์โค้ดที่สูง 30 พิกเซล  
* `DatabarBarHeight60Pixels.png` – ไฟล์ PNG ของบาร์โค้ดที่สูง 60 พิกเซล  

เปิดไฟล์ PNG ใดไฟล์หนึ่งด้วยโปรแกรมดูภาพใดก็ได้ คุณจะเห็นบาร์โค้ด Databar OmniDirectional ชัดเจนพร้อมสแกน

## กรณีขอบและการแก้ไขปัญหา

| สถานการณ์ | สิ่งที่ต้องตรวจสอบ | วิธีแก้แนะนำ |
|-----------|-------------------|--------------|
| บาร์โค้ดดูเบลอ | X‑dimension ต่ำเกินไปสำหรับความสูงที่เลือก | เพิ่ม `XDimension.Pixels` (เช่น จาก 2 เป็น 3) |
| เครื่องสแกนไม่ทำงานกับบาร์โค้ดความสูงต่ำ | ความสูงต่ำกว่าขั้นต่ำของเครื่องสแกน | ตั้ง `BarHeight.Pixels` อย่างน้อย 30 px (หรือตามสเปคของเครื่องสแกน) |
| ไฟล์ PNG ว่างหรือเสีย | เส้นทางออกไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ใช้เส้นทางแบบ absolute หรือให้แอปมีสิทธิ์เขียน |
| ต้องการสัญลักษณ์อื่น | `EncodeTypes` ปัจจุบันไม่เหมาะสม | แทนที่ `EncodeTypes.DatabarOmniDirectional` ด้วยค่า enum อื่น (เช่น `EncodeTypes.Code128`) |

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างรูปแบบภาพอื่นได้หรือไม่ (JPEG, BMP)?**  
A: ได้ เพียงเปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` เป็นต้น

**Q: ฉันจะฝัง PNG ลงในหน้าเว็บได้อย่างไร?**  
A: ให้ให้บริการ PNG ที่สร้างขึ้นผ่าน endpoint HTTP หรือแปลงเป็นสตริง Base64 แล้วใส่ลงในแอตทริบิวต์ `src` ของแท็ก `<img>`

**Q: มีวิธีตั้งค่าสีพื้นหลังหรือไม่?**  
A: ใช้ `generator.Parameters.Image.BackgroundColor = Color.White;` (หรือ `System.Drawing.Color` ใดก็ได้)

## สรุป

คุณได้เรียนรู้วิธี **สร้างไฟล์ PNG ของบาร์โค้ด** ใน C# และ **ปรับความสูงของบาร์โค้ด** อย่างแม่นยำเพื่อให้ตรงกับความต้องการด้านการสแกนหรือการออกแบบ โดยการเปลี่ยนคุณสมบัติ `BarHeight.Pixels` คุณสามารถ **เปลี่ยนความสูงของบาร์โค้ด** ได้ทันทีและสร้างไฟล์ PNG หลายไฟล์จากโค้ดเดียว

ต่อไปลองสำรวจตัวเลือกการปรับแต่งอื่น ๆ เช่น สีพื้นหน้า, ระยะขอบ, และการเพิ่มข้อความที่อ่านได้โดยมนุษย์ คุณยังสามารถทดลองสัญลักษณ์ต่าง ๆ (`EncodeTypes.Code128`, `EncodeTypes.QR`) เพื่อขยายขอบเขตของข้อมูลที่สามารถเข้ารหัสได้

ขอให้เขียนโค้ดอย่างสนุกสนานและบาร์โค้ดของคุณสแกนได้สำเร็จตั้งแต่ครั้งแรก!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ ทุกแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}