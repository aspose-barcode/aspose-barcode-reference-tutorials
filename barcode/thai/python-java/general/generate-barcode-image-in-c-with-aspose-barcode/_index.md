---
category: general
date: 2026-08-06
description: สร้างภาพบาร์โค้ดใน C# ด้วย Aspose.BarCode เรียนรู้วิธีสร้าง Databar ปรับขนาดบาร์โค้ดที่กำหนดเอง
  และเปลี่ยนความสูงของบาร์โค้ดด้วยโค้ดง่าย ๆ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: th
lastmod: 2026-08-06
og_description: สร้างภาพบาร์โค้ดใน C# ด้วย Aspose.BarCode. บทเรียนนี้จะแสดงวิธีสร้างบาร์โค้ด
  Databar Omnidirectional ปรับขนาดตามต้องการ และเปลี่ยนความสูงของบาร์โค้ดอย่างมีประสิทธิภาพ.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: สร้างภาพบาร์โค้ดใน C# – คู่มือเต็มของ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: สร้างภาพบาร์โค้ดใน C# ด้วย Aspose.BarCode
url: /th/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดใน C# ด้วย Aspose.BarCode

หากคุณต้องการ **สร้างภาพบาร์โค้ด** อย่างอัตโนมัติ คู่มือนี้จะแสดงวิธีทำอย่างละเอียด ไม่ว่าคุณจะกำลังสร้างระบบจัดการสินค้าปลีกหรือพอร์ทัลติดตามโลจิสติกส์ คุณจะได้เห็นขั้นตอนครบถ้วนสำหรับการสร้างบาร์โค้ด Databar Omnidirectional ปรับขนาดและบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างภาพบาร์โค้ดเป็นความต้องการทั่วไป แต่ผู้พัฒนามักสงสัย **วิธีสร้าง Databar** ด้วยขนาดที่ต้องการอย่างแม่นยำ ในบทเรียนนี้คุณจะได้เรียนรู้การสร้างบาร์โค้ด Databar ปรับความกว้างและความสูงของบาร์โค้ด และเปลี่ยนความสูงของบาร์โค้ดโดยไม่ต้องเขียนโค้ดสร้างใหม่ทั้งหมด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า (โค้ดทำงานได้กับ .NET Core และ .NET Framework)
* Visual Studio 2022 (หรือ IDE ใดก็ได้ที่รองรับ C#)
* ใบอนุญาต Aspose.BarCode for .NET ที่ถูกต้อง (รุ่นประเมินฟรีใช้สำหรับการทดสอบ)
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#

## ขั้นตอนที่ 1: ติดตั้ง Aspose.BarCode

เพิ่มแพ็กเกจ Aspose.BarCode NuGet ลงในโปรเจกต์ของคุณ:

```bash
dotnet add package Aspose.BarCode
```

แพ็กเกจนี้ประกอบด้วยคลาส `BarcodeGenerator` ที่ใช้ตลอดบทเรียน หลังจากติดตั้งเสร็จ ให้ทำการ restore โปรเจกต์เพื่อดึง dependencies

## ขั้นตอนที่ 2: สร้างตัวสร้างบาร์โค้ดพื้นฐาน

บรรทัดแรกของโค้ดสร้าง **ตัวสร้างบาร์โค้ด** ที่จะผลิตสัญลักษณ์ Databar Omnidirectional ค่าตัวแปร `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีว่าจะใช้ symbology ใด และสตริงข้อมูลจะตามไวยากรณ์ GS1 Application Identifier

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**ทำไมเรื่องนี้ถึงสำคัญ:** วัตถุ `BarcodeGenerator` เป็นจุดเริ่มต้นของทุกการทำงานกับบาร์โค้ด การเลือก `DatabarOmniDirectional` จะทำให้ผลลัพธ์สอดคล้องกับมาตรฐาน GS1 สำหรับการสแกนในร้านค้า

## ขั้นตอนที่ 3: ตั้งค่า X‑dimension แบบกำหนดเอง (ความกว้างโมดูล)

X‑dimension ควบคุมความกว้างของบาร์ที่แคบที่สุด การตั้งค่าเป็นค่าพิกเซลเล็กจะทำให้บาร์โค้ดกระชับ ส่วนค่าที่ใหญ่ขึ้นจะเพิ่มความกว้างโดยรวม

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**คำอธิบาย:** X‑dimension ขนาด 2 พิกเซลเป็นค่าที่นิยมใช้สำหรับหน้าจอความละเอียดสูง หากต้องการความหนาแน่นภาพที่แน่นหรือกระจาย สามารถปรับค่าได้ตามต้องการ

## ขั้นตอนที่ 4: สร้างภาพบาร์โค้ดแรกด้วยความสูงที่กำหนด

ความสูงของบาร์โค้ดเป็นอิสระจาก X‑dimension ที่นี่เราตั้งค่าความสูงของบาร์เป็น **30 px** แล้วบันทึกภาพเป็น PNG

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**ผลลัพธ์:** ตอนนี้คุณจะมีไฟล์ชื่อ `DatabarBarHeight30Pixels.png` ที่แสดงบาร์โค้ด Databar สูง 30 px ซึ่งเป็นการสาธิตความสามารถ **กำหนดขนาดบาร์โค้ด** สำหรับกรณีใช้งานเช่นป้ายเล็ก

## ขั้นตอนที่ 5: เปลี่ยนความสูงของบาร์โค้ดสำหรับเวอร์ชันที่ใหญ่ขึ้น

หากบาร์โค้ดเดียวกันต้องแสดงบนป้ายที่ใหญ่กว่า เพียงแก้ไขคุณสมบัติความสูงและใช้ตัวสร้างเดียวกันต่อ

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมคุณถึงใช้ตัวสร้างซ้ำได้:** การเปลี่ยน `BarHeight.Pixels` จะอัปเดตการจัดวางภายในโดยไม่ต้องสร้างอ็อบเจกต์ใหม่ ซึ่งช่วยประหยัดหน่วยความจำและรักษาสตริงข้อมูลไว้ นี่เป็นวิธีที่แนะนำสำหรับการ **เปลี่ยนความสูงของบาร์โค้ด** แบบไดนามิก

## ขั้นตอนที่ 6: ตรวจสอบผลลัพธ์

เปิดไฟล์ PNG สองไฟล์ในโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ด Databar Omnidirectional สองแบบที่เข้ารหัส GTIN เดียวกันแต่มีความสูงแนวตั้งต่างกัน:

* `DatabarBarHeight30Pixels.png` – สูง 30 px เหมาะสำหรับใบเสร็จที่กะทัดรัด
* `DatabarBarHeight60Pixels.png` – สูง 60 px เหมาะสำหรับป้ายชั้นวางที่ใหญ่กว่า

ทั้งสองภาพใช้ X‑dimension เดียวกัน ทำให้อัตราส่วนบาร์‑ช่องว่างคงที่ในขณะที่ความสูงโดยรวมเพิ่มขึ้น

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | วิธีจัดการ |
|-----------|------------|
| **สัญลักษณ์บาร์โค้ดที่แตกต่าง** | แทนที่ `EncodeTypes.DatabarOmniDirectional` ด้วยค่า enum อื่น (เช่น `EncodeTypes.Code128`). โค้ดส่วนอื่นคงเดิม |
| **Non‑pixel dimensions** | ใช้ `generator.Parameters.Barcode.XDimension.Millimeters` หรือ `BarHeight.Millimeters` หากต้องการหน่วยวัดจริงสำหรับการพิมพ์ |
| **Transparent background** | ตั้งค่า `generator.Parameters.ImageBackgroundColor = Color.Transparent;` ก่อนเรียก `Save` |
| **High‑resolution output** | เพิ่มค่า `XDimension.Pixels` และ `BarHeight.Pixels` อย่างสัดส่วน หรือบันทึกเป็น `BarCodeImageFormat.Tiff` เพื่อคุณภาพไม่มีการสูญเสีย |
| **Multiple barcodes in one image** | สร้างอินสแตนซ์ `BarcodeGenerator` แยกกัน เรนเดอร์แต่ละอันเป็น `Bitmap` แล้วจัดวางด้วย `Graphics.DrawImage` |

**เคล็ดลับมืออาชีพ:** ควรทดสอบบาร์โค้ดที่สร้างด้วยเครื่องสแกนจริงก่อนนำไปใช้งานจริง เนื่องจากสแกนอาจตีความบาร์ที่บางมากแตกต่างกันตามแสงและคุณภาพเซ็นเซอร์

## โค้ดต้นฉบับเต็มสำหรับอ้างอิง

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

คัดลอกโค้ดไปยังโปรเจกต์คอนโซลใหม่ รันแล้วคุณจะเห็นไฟล์ PNG สองไฟล์ปรากฏในโฟลเดอร์ผลลัพธ์

## คำถามที่พบบ่อย

**Q: สามารถสร้างบาร์โค้ดโดยไม่ติดตั้งใบอนุญาตได้หรือไม่?**  
**A:** เวอร์ชันประเมินของ Aspose.BarCode ทำงานได้โดยไม่มีใบอนุญาต แต่จะมีลายน้ำเล็กน้อย สำหรับการใช้งานจริง ควรใช้ใบอนุญาตที่ซื้อแล้วโดยเรียก `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: การเปลี่ยน X‑dimension มีผลต่อการอ่านได้หรือไม่?**  
**A:** มีผล. X‑dimension ที่เล็กเกินไปอาจทำให้บาร์โค้ดอ่านไม่ได้บนเครื่องพิมพ์ความละเอียดต่ำ ค่าต่ำสุดที่แนะนำสำหรับการแสดงบนหน้าจอคือ 1 px; สำหรับการพิมพ์ควรใช้อย่างน้อย 0.25 mm

**Q: หากต้องการสร้างบาร์โค้ดในรูปแบบ JPEG จะทำอย่างไร?**  
**A:** แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` และสามารถตั้งค่า `generator.Parameters.ImageQuality` เพื่อควบคุมระดับการบีบอัดได้

## สรุป

คุณได้เรียนรู้วิธี **สร้างภาพบาร์โค้ด** ใน C# ด้วย Aspose.BarCode วิธี **สร้างบาร์โค้ด Databar** ปรับ **ขนาดบาร์โค้ดแบบกำหนดเอง** และ **เปลี่ยนความสูงของบาร์โค้ด** ตามต้องการ ตัวอย่างครบถ้วนแสดงขั้นตอนทำงานที่พบบ่อยที่สุด และตารางความแปรผันช่วยให้คุณรับมือกับกรณีจริงได้อย่างมั่นใจ

ต่อไปให้สำรวจหัวข้อที่เกี่ยวข้อง เช่น **การฝังบาร์โค้ดในเอกสาร PDF**, **การสร้างบาร์โค้ดหลายรายการเป็นชุด**, และ **การใช้ QR Code สำหรับการชำระเงินผ่านมือถือ** ทุกสถานการณ์เหล่านี้ต่อยอดจากหลักการเดียวกันที่อธิบายไว้ที่นี่ ทำให้คุณสามารถขยายความรู้ได้อย่างมั่นใจ

ขอให้เขียนโค้ดอย่างสนุกและบาร์โค้ดของคุณสแกนได้อย่างไม่มีข้อผิดพลาด!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ

- [สร้างภาพบาร์โค้ด – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพกำหนดเองโดยใช้ Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [วิธีสร้างบาร์โค้ด – การกำหนดค่า Code 39 ด้วย Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}