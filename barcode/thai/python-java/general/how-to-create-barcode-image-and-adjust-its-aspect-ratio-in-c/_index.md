---
category: general
date: 2026-10-08
description: เรียนรู้วิธีสร้างภาพบาร์โค้ดด้วย C# และค้นพบวิธีปรับอัตราส่วนภาพสำหรับบาร์โค้ด
  DataBar แบบซ้อนหลายทิศทาง
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: th
lastmod: 2026-10-08
og_description: สร้างภาพบาร์โค้ดด้วย C# และเรียนรู้วิธีปรับอัตราส่วนสำหรับบาร์โค้ด
  DataBar แบบซ้อนกันหลายทิศทางพร้อมตัวอย่างโค้ดเต็ม
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: สร้างภาพบาร์โค้ดด้วย C# – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีสร้างภาพบาร์โค้ดและปรับอัตราส่วนภาพใน C#
url: /th/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดและปรับอัตราส่วนภาพใน C#

หากคุณต้องการ **สร้างภาพบาร์โค้ด** อย่างอัตโนมัติ คู่มือนี้จะแสดงวิธีแก้ไขที่สมบูรณ์และพร้อมใช้งาน คุณจะได้เห็นอย่างชัดเจน **วิธีปรับอัตราส่วนภาพ** สำหรับบาร์โค้ด DataBar stacked omni‑directional ซึ่งเป็นความต้องการที่มักพบในแอปพลิเคชันด้านการค้าปลีกและโลจิสติกส์

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี:
* เริ่มต้น Aspose.BarCode `BarcodeGenerator` สำหรับสัญลักษณ์ DataBar stacked omni‑directional  
* ตั้งค่า X‑dimension (ความกว้างโมดูล) เป็นพิกเซลเพื่อควบคุมความหนาของบาร์  
* ใช้อัตราส่วนภาพสองค่าแตกต่างกันและบันทึกผลลัพธ์แต่ละไฟล์เป็น PNG  
* ตรวจสอบผลลัพธ์และเข้าใจว่าทำไมอัตราส่วนภาพจึงสำคัญ

ไม่ต้องใช้เครื่องมือภายนอก—เพียงแค่ไลบรารี Aspose.BarCode สำหรับ .NET และสภาพแวดล้อมการพัฒนา .NET 6 (หรือใหม่กว่า)

## วิธีสร้างภาพบาร์โค้ดด้วย Aspose.BarCode

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของตัวสร้างด้วยสัญลักษณ์และสตริงข้อมูลที่ต้องการ ค่าคงที่ `EncodeTypes.DatabarStackedOmniDirectional` บอก Aspose.BarCode ให้สร้างบาร์โค้ด DataBar stacked omni‑directional ซึ่งถูกใช้กันอย่างแพร่หลายสำหรับแอปพลิเคชัน GS1‑128

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**ทำไมเรื่องนี้ถึงสำคัญ:** วัตถุ `BarcodeGenerator` เป็นจุดเริ่มต้นสำหรับงานสร้างบาร์โค้ดทั้งหมด การระบุสัญลักษณ์และข้อมูลดิบตั้งแต่แรกทำให้มั่นใจว่าภาพที่สร้างขึ้นสอดคล้องกับมาตรฐาน GS1

## การตั้งค่า X‑dimension (ความกว้างโมดูล)

X‑dimension กำหนดความกว้างของบาร์ที่แคบที่สุด (โมดูล) X‑dimension ที่ใหญ่ขึ้นจะทำให้บาร์โค้ดหนาขึ้น ซึ่งอาจเป็นประโยชน์สำหรับเครื่องพิมพ์ความละเอียดต่ำ

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**ทำไมเรื่องนี้ถึงสำคัญ:** การปรับ X‑dimension เป็นส่วนหนึ่งของกระบวนการปรับแต่งภาพ มันไม่กระทบต่อข้อมูลที่เข้ารหัส แต่ส่งผลต่อความน่าเชื่อถือของการสแกนบนอุปกรณ์ต่าง ๆ

## วิธีปรับอัตราส่วนภาพ – เวอร์ชันแรก (15)

อัตราส่วนภาพควบคุมความสัมพันธ์ระหว่างความสูงและความกว้างของบาร์โค้ด DataBar คุณสมบัติ `DataBar.AspectRatio` รับค่าจำนวนเต็ม; ค่าที่ใหญ่กว่าจะทำให้บาร์สูงขึ้น

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**ทำไมเรื่องนี้ถึงสำคัญ:** อัตราส่วนภาพ 15 เป็นค่าเริ่มต้นที่นิยมสำหรับเครื่องสแกนจุดขายบาร์โค้ด ความสูงที่ได้จาก PNG (`DatabarAspectRatio15.png`) จะดูสูงขึ้น ซึ่งอาจช่วยเพิ่มอัตราการสแกนสำเร็จบนอุปกรณ์พกพา

## วิธีปรับอัตราส่วนภาพ – เวอร์ชันที่สอง (30)

คุณอาจต้องการบาร์โค้ดที่สูงกว่าเพื่อให้เหมาะกับรูปแบบป้ายบางประเภท การเปลี่ยนอัตราส่วนภาพทำได้ง่ายโดยกำหนดค่าจำนวนเต็มใหม่ก่อนเรียก `Save` อีกครั้ง

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**ทำไมเรื่องนี้ถึงสำคัญ:** ด้วยการสาธิต **วิธีปรับอัตราส่วนภาพ** คุณสามารถสร้างภาพบาร์โค้ดหลายรูปจากแหล่งข้อมูลเดียวโดยไม่ต้องสร้างตัวสร้างใหม่ ซึ่งช่วยลดการใช้หน่วยความจำและเร่งการประมวลผลเป็นชุด

### ผลลัพธ์ที่คาดหวัง

หลังจากรันโปรแกรมคุณจะพบไฟล์ PNG สองไฟล์ในไดเรกทอรีที่ทำงาน:

| ชื่อไฟล์                     | อัตราส่วนภาพ | คำอธิบายภาพ |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | ความสูงมาตรฐาน เหมาะกับเครื่องสแกนจุดขายส่วนใหญ่ |
| `DatabarAspectRatio30.png`    | 30           | บาร์สูงกว่า มีประโยชน์สำหรับป้ายขนาดใหญ่หรือเครื่องพิมพ์ความละเอียดต่ำ |

ทั้งสองภาพมี GTIN ที่เข้ารหัสเดียวกัน `(01)12345678901231` แต่สัดส่วนภาพแตกต่างกันตามอัตราส่วนที่คุณตั้งค่า

## คำถามทั่วไปและการจัดการกรณีขอบ

### ถ้าฉันต้องการ X‑dimension ที่แตกต่าง?

คุณสามารถเปลี่ยน `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` เป็นจำนวนเต็มใด ๆ ที่มากกว่าศูนย์ สำหรับผลลัพธ์ความละเอียดสูงมาก (เช่น 300 dpi) ค่า 3‑4 พิกเซลมักให้ภาพที่คมชัดกว่า

### จะเลือกอัตราส่วนภาพที่เหมาะสมอย่างไร?

อัตราส่วนที่ดีที่สุดขึ้นอยู่กับสภาพแวดล้อมการสแกน:
* **ป้ายแบบ Low‑profile** – ใช้อัตราส่วนที่เล็กกว่า (เช่น 10‑15) เพื่อให้บาร์โค้ดกระชับ
* **ตู้ขนส่งขนาดใหญ่** – อัตราส่วนที่สูงกว่า (เช่น 25‑35) ช่วยให้อ่านได้จากระยะไกล
* **ข้อกำหนดตามกฎหมาย** – มาตรฐานบางอย่างกำหนดความสูงขั้นต่ำ; ตรวจสอบสเปค GS1 เพื่อดูตัวเลขที่แน่นอน

### ฉันสามารถสร้างรูปแบบบาร์โค้ดอื่นด้วยโค้ดเดียวกันได้หรือไม่?

ได้. แทนที่ `EncodeTypes.DatabarStackedOmniDirectional` ด้วยค่า `EncodeTypes` ใด ๆ (เช่น `EncodeTypes.Code128`) ส่วนที่เหลือของโค้ด—X‑dimension, อัตราส่วนภาพ (ถ้ามี) และการบันทึก—จะยังคงเหมือนเดิม

### ถ้าฉันต้องการสร้างภาพในรูปแบบอื่น?

`BarCodeImageFormat` รองรับ PNG, JPEG, BMP, GIF, และ TIFF เพียงเปลี่ยนอาร์กิวเมนต์ที่สองของ `Save` ตัวอย่างเช่น:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## เคล็ดลับพิเศษ: ใช้ตัวสร้างซ้ำสำหรับการประมวลผลเป็นชุด

เมื่อคุณต้องสร้างบาร์โค้ดหลายสิบรายการด้วยการตั้งค่าภาพเดียวกัน ให้สร้างอินสแตนซ์ของตัวสร้างเพียงครั้งเดียว, ปรับเฉพาะคุณสมบัติ `CodeText` แล้วเรียก `Save` ซ้ำ ๆ วิธีนี้ช่วยลดภาระการจัดสรรบัฟเฟอร์ภายในซ้ำ ๆ

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## สรุป

คุณได้เรียนรู้วิธี **สร้างภาพบาร์โค้ด** ใน C# ด้วย Aspose.BarCode และ **วิธีปรับอัตราส่วนภาพ** อย่างแม่นยำสำหรับสัญลักษณ์ DataBar stacked omni‑directional ด้วยการควบคุม X‑dimension และอัตราส่วนภาพ คุณสามารถผลิตบาร์โค้ดที่ตอบสนองต่อความต้องการการสแกนหรือการจัดวางใด ๆ พร้อมกับการทำงานที่ง่ายและดูแลรักษาได้

### ขั้นตอนต่อไป

* สำรวจสัญลักษณ์อื่น ๆ เช่น **Code128** หรือ **QR Code** โดยสลับค่า `EncodeTypes`  
* ผสานการสร้างบาร์โค้ดกับการสร้าง PDF (เช่น ใช้ Aspose.PDF) เพื่อฝังบาร์โค้ดโดยตรงลงในใบแจ้งหนี้  
* ทดลองเลือกอัตราส่วนภาพแบบไดนามิกตามขนาดป้าย—แนวคิดนี้ขยายรูปแบบ **วิธีปรับอัตราส่วนภาพ** ไปสู่เครื่องมือออกแบบป้ายแบบเต็มรูปแบบ

อย่าลังเลที่จะแก้ไขตัวอย่าง, แบ่งปันผลลัพธ์ของคุณ, หรือถามคำถามต่อเนื่องในคอมเมนต์ ขอให้เขียนโค้ดอย่างสนุกสนาน!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณเอง

- [วิธีสร้างบาร์โค้ด databar stacked ใน C# ด้วย Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [วิธีสร้างภาพบาร์โค้ดด้วย Aspose.Barcode ใน C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [วิธีปรับขนาดบาร์โค้ด – อัตราส่วน Codablock F ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}