---
category: general
date: 2026-09-29
description: วิธีตั้งความกว้างของบาร์โค้ด GS1 DataBar Omni‑Directional และวิธีเปลี่ยนความสูงโดยใช้
  C# ทำตามคู่มือขั้นตอนต่อขั้นตอนพร้อมโค้ดเต็ม
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: th
lastmod: 2026-09-29
og_description: วิธีตั้งความกว้างของบาร์โค้ด GS1 DataBar Omni‑Directional และวิธีเปลี่ยนความสูงใน
  C# เรียนรู้การเรียก API อย่างแม่นยำและดูตัวอย่างที่สามารถรันได้ครบถ้วน
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: วิธีตั้งความกว้างของบาร์โค้ด GS1 DataBar – คู่มือ C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: วิธีตั้งความกว้างและปรับความสูงสำหรับบาร์โค้ด GS1 DataBar Omni‑Directional
  ใน C#
url: /th/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งความกว้างและปรับความสูงสำหรับบาร์โค้ด GS1 DataBar Omni‑Directional ใน C#

การตั้งความกว้างของบาร์โค้ด GS1 DataBar Omni‑Directional เป็นงานที่พบบ่อยเมื่อคุณต้องการขนาดที่แม่นยำสำหรับอุปกรณ์สแกน ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเปลี่ยนความสูง** เพื่อให้บาร์โค้ดพอดีกับเลย์เอาต์ของคุณอย่างสมบูรณ์ คู่มือจะพาคุณผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าโปรเจกต์จนถึงตัวอย่างโค้ดที่สามารถรันได้เต็มรูปแบบ

เราจะครอบคลุม:

* แพคเกจ NuGet ที่จำเป็นและเวอร์ชัน .NET
* ทำไม X‑dimension (ความกว้างโมดูล) ถึงสำคัญต่อการอ่านบาร์โค้ด
* คำสั่ง API ที่ **วิธีตั้งความกว้าง** และ **วิธีเปลี่ยนความสูง**
* การจัดการกรณีขอบเช่นความกว้างโมดูลขั้นต่ำและการเรนเดอร์ความละเอียดสูง
* ตัวอย่างเต็มที่คัดลอก‑วางได้ซึ่งสร้างไฟล์ PNG สองไฟล์ที่มีความสูงบาร์ต่างกัน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

| ข้อกำหนด | เหตุผล |
|------------|--------|
| .NET 6.0 SDK หรือใหม่กว่า | ตัวอย่างใช้คุณลักษณะ C# สมัยใหม่และทำงานได้บน Windows, Linux หรือ macOS |
| Visual Studio 2022 (หรือ IDE C# ใดก็ได้) | ให้ IntelliSense สำหรับ Aspose.Barcode API |
| **Aspose.Barcode for .NET** NuGet package | มี `BarcodeGenerator`, `EncodeTypes` และการสนับสนุนรูปแบบภาพ ติดตั้งด้วย `dotnet add package Aspose.Barcode` |
| สิทธิ์การเขียนในโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก | ตัวสร้างบาร์โค้ดจะเขียนภาพผลลัพธ์ลงดิสก์ |

## วิธีตั้งความกว้างของบาร์โค้ด

ขั้นตอน **วิธีตั้งความกว้าง** ทำโดยการกำหนดคุณสมบัติ `XDimension` ของพารามิเตอร์บาร์โค้ด `XDimension` แทนความกว้างโมดูล (บาร์หรือช่องที่เล็กที่สุด) ในพิกเซล, จุด หรือมิลลิเมตร การตั้งค่าอย่างถูกต้องจะทำให้บาร์โค้ดตรงตามสเปคของสแกนเนอร์

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### ทำไม X‑dimension ถึงสำคัญ

* **ความทนทานของสแกนเนอร์** – สแกนเนอร์ส่วนใหญ่ต้องการความกว้างโมดูลขั้นต่ำ; ค่าที่เล็กเกินไปอาจทำให้อ่านผิดพลาด
* **ความละเอียดการพิมพ์** – เมื่อพิมพ์ที่ 300 dpi โมดูล 2 px จะเท่ากับประมาณ 0.17 mm ซึ่งอยู่ในช่วงที่แนะนำสำหรับ GS1 DataBar
* **ขนาดภาพ** – ค่าที่สูงขึ้นของ X‑dimension จะเพิ่มความกว้างโดยรวมของบาร์โค้ด ซึ่งอาจส่งผลต่อข้อจำกัดของเลย์เอาต์

### เคล็ดลับสำหรับการตั้งค่าความกว้างที่เชื่อถือได้

* **ห้ามตั้ง XDimension ต่ำกว่า 1 px** – ไลบรารีจะบังคับค่าให้เป็นขั้นต่ำ แต่บาร์โค้ดอาจอ่านไม่ได้
* **ให้สอดคล้องกับ DPI ที่ต้องการ** – หากเรนเดอร์เป็นรูปแบบความละเอียดสูง (เช่น TIFF ที่ 600 dpi) ให้เพิ่ม XDimension อย่างสัดส่วน
* **ทดสอบกับสแกนเนอร์จริง** – หลังจากเปลี่ยนความกว้าง ให้ตรวจสอบบาร์โค้ดบนอุปกรณ์ที่ใช้สแกนจริง

## วิธีเปลี่ยนความสูงของบาร์โค้ด

เมื่อกำหนดความกว้างแล้ว คุณสามารถควบคุมขนาดแนวตั้งด้วยคุณสมบัติ `BarHeight` โค้ดต่อไปนี้สาธิต **วิธีเปลี่ยนความสูง** จาก 30 px เป็น 60 px และบันทึกเป็นสองภาพแยกกัน

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### ทำความเข้าใจความสูงของบาร์

* **สมดุลภาพ** – บาร์ที่สูงขึ้นทำให้อ่านง่ายขึ้นบนพื้นหลังที่มีคอนทราสต์ต่ำ แต่เพิ่มพื้นที่แนวตั้งของภาพ
* **ข้อจำกัดตามกฎระเบียบ** – มาตรฐานบางอย่าง (เช่น ป้ายสินค้า) กำหนดความสูงบาร์สูงสุด; ปรับให้สอดคล้อง
* **อัตราส่วน** – การเปลี่ยนความสูงไม่กระทบต่อความกว้างโมดูล; คุณสามารถปรับทั้งสองได้อย่างอิสระ

### การจัดการกรณีขอบสำหรับการปรับความสูง

| สถานการณ์ | แนวทางที่แนะนำ |
|-----------|----------------------|
| ความสูง < 10 px | เพิ่มเป็นอย่างน้อย 10 px; บาร์สั้นมากอาจถูกสแกนเนอร์ละเลย |
| บาร์สูงมาก (≥ 100 px) | ตรวจสอบสื่อที่ใช้ (กระดาษ, ป้าย) ว่าสามารถรับพื้นที่เพิ่มได้หรือไม่ |
| ต้องการสเกลแบบสัดส่วน | คำนวณ `BarHeight = XDimension * desiredRatio` เพื่อรักษาความสอดคล้องของภาพ |

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นโปรแกรมครบชุดที่รวมขั้นตอน **วิธีตั้งความกว้าง** และ **วิธีเปลี่ยนความสูง** เข้าไว้ด้วยกัน คัดลอกโค้ดไปยังโปรเจกต์คอนโซลใหม่, รีสโตร์แพคเกจ Aspose.Barcode NuGet, แล้วรัน จะได้ไฟล์ PNG สองไฟล์ในโฟลเดอร์ `bin/Debug/net6.0`

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**ผลลัพธ์ที่คาดหวัง**

การรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์:

* `DatabarBarHeight30Pixels.png` – บาร์โค้ดสูง 30 px, โมดูลกว้าง 2 px
* `DatabarBarHeight60Pixels.png` – บาร์โค้ดเดียวกันแต่ความสูงเป็นสองเท่า

เปิดภาพใดภาพหนึ่งในโปรแกรมดูภาพใดก็ได้; คุณจะเห็นสัญลักษณ์ GS1 DataBar Omni‑Directional ที่สะอาดพร้อมสแกน

## คำถามที่พบบ่อย

| คำถาม | คำตอบ |
|----------|--------|
| *ฉันสามารถใช้มิลลิเมตรแทนพิกเซลได้ไหม?* | ใช่. ตั้งค่า `generator.Parameters.Barcode.XDimension.Millimeters` และ `BarHeight.Millimeters`. ไลบรารีจะเปลี่ยนเป็นพิกเซลของอุปกรณ์ตาม DPI ของภาพ |
| *ถ้าต้องการประเภทบาร์โค้ดอื่น?* | แทนที่ `EncodeTypes.DatabarOmniDirectional` ด้วยค่า `EncodeTypes` อื่น (เช่น `EncodeTypes.QR`). คุณสมบัติความกว้างและความสูงทำงานเช่นเดียวกัน |
| *มีวิธีสร้าง SVG แทน PNG หรือไม่?* | ใช้ `BarCodeImageFormat.Svg` ในคำสั่ง `Save`. การตั้งค่าความกว้าง/ความสูงยังคงใช้ได้ |
| *จำเป็นต้องเรียก `generator.Dispose()` หรือไม่?* | `BarcodeGenerator` implements `IDisposable`. ในแอปคอนโซลคุณสามารถใส่ในบล็อก `using`, แต่สำหรับตัวอย่างสั้น ๆ นี้เป็นทางเลือก |

## สรุป

คุณได้เรียนรู้ **วิธีตั้งความกว้าง** ของบาร์โค้ด GS1 DataBar Omni‑Directional และ **วิธีเปลี่ยนความสูง** ด้วย Aspose.Barcode API ใน C# ตัวอย่างเต็มแสดงการสร้าง generator, ตั้งค่า `XDimension` และ `BarHeight`, แล้วบันทึกไฟล์ PNG ที่มีความสูงแนวตั้งต่างกัน

ต่อจากนี้คุณสามารถ:

* ทดลองกับ `EncodeTypes` อื่น ๆ (เช่น QR, Code128)
* เรนเดอร์เป็นรูปแบบความละเอียดสูงเช่น TIFF สำหรับการพิมพ์
* ผสาน generator เข้าใน Web API เพื่อให้บริการบาร์โค้ดแบบเรียลไทม์

ขอให้เขียนโค้ดสนุกและบาร์โค้ดของคุณสแกนได้อย่างสะอาด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอน‑ต่อ‑ขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณเอง

- [วิธีเปลี่ยนความสูงของบาร์โค้ดใน C# – คู่มือฉบับสมบูรณ์](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [ตัวอย่างตัวสร้างบาร์โค้ดใน C# – ตั้งความกว้างและความสูง](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [วิธีใช้ตัวสร้างบาร์โค้ด C# เพื่อสร้างบาร์โค้ด DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}