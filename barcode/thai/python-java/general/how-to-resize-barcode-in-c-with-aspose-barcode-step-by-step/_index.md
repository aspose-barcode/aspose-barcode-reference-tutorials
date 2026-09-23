---
category: general
date: 2026-09-23
description: วิธีปรับขนาดบาร์โค้ดใน C# ด้วย Aspose.BarCode. เรียนรู้การสร้างบาร์โค้ดด้วยโค้ด
  C#, ปรับขนาดตามต้องการ, และส่งออกภาพบาร์โค้ดอย่างมีประสิทธิภาพ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: th
lastmod: 2026-09-23
og_description: วิธีปรับขนาดบาร์โค้ดใน C# ด้วย Aspose.BarCode. ทำตามคู่มือนี้เพื่อสร้างโค้ดบาร์โค้ด
  C#, ปรับขนาดมิติ, และส่งออกภาพบาร์โค้ด.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: วิธีปรับขนาดบาร์โค้ดใน C# – คู่มือ Aspose.BarCode อย่างครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: วิธีปรับขนาดบาร์โค้ดใน C# ด้วย Aspose.BarCode – คู่มือทีละขั้นตอน
url: /th/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับขนาดบาร์โค้ดใน C# ด้วย Aspose.BarCode – คู่มือขั้นตอนโดยละเอียด

หากคุณต้องการ **วิธีปรับขนาดบาร์โค้ด** ในแอปพลิเคชัน .NET นี้ การสอนนี้จะแสดงโค้ดที่คุณสามารถคัดลอก‑วางและรันได้ทันที คุณจะได้เรียนรู้วิธี **สร้างบาร์โค้ดด้วย C#** ปรับความสูงของบาร์ และ **ส่งออกภาพบาร์โค้ด** โดยไม่ต้องออกจาก IDE ของคุณ

การสร้างบาร์โค้ดเป็นเรื่องทั่วไปในระบบสินค้าคงคลัง, ป้ายจัดส่ง, และเครื่องจุดขาย (POS) เมื่อจบคู่มือนี้คุณจะสามารถ **สร้างภาพบาร์โค้ด Databar** ที่มีความสูงตามที่ต้องการได้ และคุณจะเข้าใจคุณสมบัติหลักที่ควบคุมขนาด, ความละเอียด, และรูปแบบไฟล์

## ข้อกำหนดเบื้องต้น

- .NET 6 หรือใหม่กว่า (ตัวอย่างทำงานกับ .NET Framework 4.6+ ด้วย)  
- แพ็กเกจ NuGet Aspose.BarCode สำหรับ .NET (`Install-Package Aspose.BarCode`)  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และ Visual Studio (หรือ IDE C# ใดก็ได้)  

ไม่มีไลบรารีเพิ่มเติมที่จำเป็น; Aspose.BarCode จัดการการเรนเดอร์, การสเกล, และการส่งออกภาพภายใน

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และนำเข้า Aspose.BarCode

สร้างโปรเจกต์คอนโซลใหม่ (หรือรวมเข้ากับโปรเจกต์ที่มีอยู่) และเพิ่มเนมสเปซ Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **เคล็ดลับ:** ใช้เวอร์ชันล่าสุดของ Aspose.BarCode (ตั้งแต่เดือนกันยายน 2026) เพื่อรับประโยชน์จากการแก้บั๊กและสัญลักษณ์บาร์โค้ดใหม่

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้างบาร์โค้ด DataBar Omni‑directional

**ตัวอย่างตัวสร้างบาร์โค้ด** เริ่มต้นด้วยการระบุสัญลักษณ์ (`EncodeTypes.DatabarOmniDirectional`) และข้อมูล payload. Payload นี้ตามรูปแบบ GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

อ็อบเจกต์นี้เก็บพารามิเตอร์ทั้งหมดที่คุณจะปรับในภายหลัง เช่น X‑dimension, ความสูงของบาร์, และรูปแบบภาพ

## ขั้นตอนที่ 3: กำหนดพารามิเตอร์ขนาดทั่วไป

ก่อนส่งออก ให้ตั้งค่า X‑dimension (ความกว้างของบาร์ที่แคบที่สุด) และความสูงบาร์เริ่มต้น. X‑dimension แสดงเป็นพิกเซล; ค่า `2` ทำงานได้ดีสำหรับความละเอียดหน้าจอส่วนใหญ่

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **ทำไมเรื่องนี้สำคัญ:** คุณสมบัติ `BarHeight` มีผลโดยตรงต่อขนาดภาพของบาร์โค้ด การเปลี่ยนแปลงเป็นหัวใจของ **วิธีปรับขนาดบาร์โค้ด** ใน Aspose.BarCode

## ขั้นตอนที่ 4: ส่งออกภาพบาร์โค้ดแรก (ความสูง 30 px)

ตอนนี้คุณสามารถ **ส่งออกภาพบาร์โค้ด** เป็นไฟล์ PNG ได้ วิธี `Save` จะเรนเดอร์บาร์โค้ดด้วยพารามิเตอร์ปัจจุบันโดยอัตโนมัติ

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

ไฟล์ที่ได้จะมีลักษณะดังนี้:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="ตัวอย่างวิธีปรับขนาดบาร์โค้ด – ความสูง 30 พิกเซล"}

## ขั้นตอนที่ 5: เปลี่ยนความสูงของบาร์เพื่อสร้างบาร์โค้ดที่ใหญ่ขึ้น

เพื่อสาธิต **วิธีปรับขนาดบาร์โค้ด** อย่างไดนามิก ให้ปรับคุณสมบัติ `BarHeight` แล้วบันทึกใหม่ การทำเช่นนี้ **ไม่** จำเป็นต้องสร้างอินสแตนซ์ `BarcodeGenerator` ใหม่; เพียงแก้ไขอ็อบเจกต์ที่มีอยู่

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## ขั้นตอนที่ 6: ส่งออกภาพบาร์โค้ดที่ปรับขนาดแล้ว (ความสูง 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

ตอนนี้คุณมีไฟล์ PNG สองไฟล์—หนึ่งที่ 30 px และอีกหนึ่งที่ 60 px—แสดงให้เห็นว่าข้อมูลเดียวกันสามารถเรนเดอร์ในขนาดต่างกันได้อย่างไร

### ผลลัพธ์ที่คาดหวัง

| ชื่อไฟล์                     | ความสูงบาร์ (px) | ผลลัพธ์ภาพ |
|-------------------------------|----------------|---------------|
| `DatabarBarHeight30Pixels.png`| 30             | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="บาร์โค้ด DataBar Omni‑directional 30 พิกเซล"} |
| `DatabarBarHeight60Pixels.png`| 60             | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="บาร์โค้ด DataBar Omni‑directional 60 พิกเซล"} |

ทั้งสองภาพเป็นบาร์โค้ด GS1‑128 DataBar ที่พร้อมสแกน

## ขั้นตอนที่ 7: ตัวเลือก – ปรับการตั้งค่าภาพเพิ่มเติม

แม้เป้าหมายหลักจะเป็น **วิธีปรับขนาดบาร์โค้ด**, คุณอาจต้องการปรับแต่งเพิ่มเติม:

| คุณสมบัติ | คำอธิบาย | ค่าที่พบบ่อย |
|----------|-------------|----------------|
| `XDimension.Pixels` | ความกว้างของบาร์ที่แคบที่สุด | 1–4 |
| `BarHeight.Pixels`  | ความสูงของบาร์โค้ดทั้งหมด | 20–200 |
| `Resolution` | DPI สำหรับการแสดงผลแบบแรสเตอร์ | 72, 150, 300 |
| `ForeColor` / `BackColor` | สีพื้นหน้าและพื้นหลัง | `Color.Black`, `Color.White` |

ตัวอย่าง:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

การปรับแต่งเหล่านี้ไม่กระทบต่อตรรกะ **การปรับขนาด** แต่ให้คุณควบคุมคุณภาพภาพขั้นสุดท้ายได้อย่างเต็มที่

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา | อาการ | วิธีแก้ |
|-------|---------|-----|
| ความสูงบาร์ไม่เปลี่ยน | ไฟล์ที่บันทึกดูเหมือนกัน | ตรวจสอบว่าคุณได้แก้ไข `barcode.Parameters.Barcode.BarHeight.Pixels` *ก่อน* การเรียก `Save` ทุกครั้ง |
| บาร์โค้ดอ่านไม่ออก | สแกนเนอร์รายงาน “cannot read” | รักษา `XDimension` ≥ 2 px สำหรับ DataBar Omni‑directional; บาร์ที่บางเกินไปอาจทำให้สแกนไม่สำเร็จ |
| ไฟล์ PNG เบลอ | ส่งออกที่ DPI ต่ำ | ตั้งค่า `barcode.Parameters.ImageResolution.DpiX/Y` อย่างน้อย 150 เพื่อให้ได้ภาพคุณภาพพิมพ์ |
| ไฟล์ถูกเขียนทับโดยไม่ได้ตั้งใจ | ภาพใหม่แทนที่ภาพเก่า | ใช้ชื่อไฟล์ที่ไม่ซ้ำกันหรือใส่ค่าความสูงในชื่อไฟล์ตามที่แสดงด้านบน |

## ตัวอย่างเต็มที่สามารถรันได้

คัดลอกบล็อกทั้งหมดด้านล่างไปยังแอปคอนโซลใหม่ (`Program.cs`). โค้ดจะคอมไพล์และทำงานได้ทันที สร้างไฟล์ PNG สองไฟล์ในโฟลเดอร์เอาต์พุตของโปรเจกต์

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

การรันโปรแกรมจะให้ผลลัพธ์:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

ตรวจสอบโฟลเดอร์เอาต์พุตสำหรับไฟล์ PNG สองไฟล์ ทั้งสองไฟล์พร้อมสำหรับการพิมพ์, ฝังใน PDF, หรือส่งไปยังอุปกรณ์ระยะไกล

## สรุป

ในคู่มือนี้เราได้ครอบคลุม **วิธีปรับขนาดบาร์โค้ด** ใน C# ด้วย Aspose.BarCode, แสดงตัวอย่าง **ตัวสร้างบาร์โค้ด** อย่างครบถ้วน, และสาธิตวิธี **ส่งออกภาพบาร์โค้ด** ในความสูงต่าง ๆ ตอนนี้คุณรู้วิธี:

1. สร้างอ็อบเจกต์ Databar barcode ด้วยข้อมูลที่กำหนดเอง.  
2. ปรับ `BarHeight` (หัวใจของการปรับขนาด).  
3. ส่งออกไฟล์ PNG สำหรับขนาดที่ต้องการใด ๆ.  

จากนี้คุณสามารถสำรวจการปรับแต่งเพิ่มเติม—สัญลักษณ์อื่น, โทนสี, หรือรูปแบบเวกเตอร์เช่น SVG. รูปแบบเดียวกัน (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) ทำงานกับบาร์โค้ดประเภทใดก็ได้ที่ Aspose.BarCode รองรับ ดังนั้นคุณจึงสามารถนำความรู้ **วิธีปรับขนาดบาร์โค้ด** ไปใช้ทั่วทั้งแอปพลิเคชันของคุณได้อย่างมั่นใจ

---

**ขั้นตอนต่อไป**

- ลองปรับขนาดสัญลักษณ์อื่น (QR, Code128) เพื่อดูว่าความสูงและความกว้างทำงานร่วมกันอย่างไร.  
- ใช้ `BarCodeImageFormat.Svg` เพื่อสร้างกราฟิกเวกเตอร์ที่ปรับขนาดได้สำหรับหน้าเว็บ.  
- รวมภาพที่สร้างไว้ในรายงาน PDF ด้วย Aspose.PDF หรือ iTextSharp.  

ขอให้เขียนโค้ดอย่างสนุกสนานและเพลิดเพลินกับความยืดหยุ่นที่มาพร้อมกับการสร้างบาร์โค้ดแบบโปรแกรมเมติก!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโครงการของคุณ

- [วิธีสร้างและปรับความสูงบาร์โค้ดสำหรับ One-Dimensional Databar ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [วิธีสร้างบาร์โค้ด – การกำหนดค่า Code 39 ด้วย Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอนโดยละเอียด](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}