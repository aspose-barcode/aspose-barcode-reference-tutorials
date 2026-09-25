---
date: 2026-08-02
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix, สร้าง DataMatrix, และสำรวจการสร้างบาร์โค้ดความหนาแน่นสูงด้วย
  Aspose.BarCode สำหรับโครงการ .NET
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: การกำหนดค่า DataMatrix ECC 200
og_description: สร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET บทเรียนนี้แสดงการสร้างบาร์โค้ดความหนาแน่นสูง,
  การตั้งค่าใบอนุญาต Aspose ชั่วคราว, และโค้ด C# ทีละขั้นตอน
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: สร้างบาร์โค้ด DataMatrix – คู่มือ Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET

## คำแนะนำ

ในคู่มือนี้คุณจะ **สร้างบาร์โค้ด DataMatrix** (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างระบบติดตามสินค้าคงคลัง ระบบจุดขาย หรืออัตโนมัติกระบวนการทำงานของเอกสาร บาร์โค้ดความหนาแน่นสูงสามารถเก็บข้อมูลจำนวนมากในพื้นที่ขนาดเล็ก เราจะเดินผ่านทุกขั้นตอนการกำหนดค่า อธิบายว่าทำไมการตั้งค่าแต่ละอย่างถึงสำคัญ และให้ตัวอย่างโค้ด C# ที่พร้อมใช้งาน

## คำตอบสั้น
- **ไลบรารีที่ดีที่สุดสำหรับ DataMatrix ใน .NET คืออะไร?** Aspose.BarCode สำหรับ .NET  
- **ECC ระดับใดที่ ECC 200 ให้?** การแก้ไขข้อผิดพลาดความหนาแน่นสูงสำหรับการสแกนที่มั่นคง  
- **ต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ชั่วคราวใช้ได้สำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **สามารถส่งออกเป็น PNG, JPEG หรือ TIFF ได้หรือไม่?** ใช่ – เมธอด `Save` รองรับหลายรูปแบบภาพ

## DataMatrix ECC 200 คืออะไร?

DataMatrix ECC 200 เป็นบาร์โค้ดสองมิติความหนาแน่นสูงที่สามารถเก็บได้สูงสุด 2,335 ตัวอักษรอัลฟานูเมอริกหรือ 1,556 ไบต์ของข้อมูลไบนารีในรูปแบบสี่เหลี่ยมจัตุรัสหรือสี่เหลี่ยมผืนผ้ากระชับ ใช้การแก้ไขข้อผิดพลาด Reed‑Solomon เพื่อกู้คืนโมดูลที่สูญหายหรือเสียหาย ทำให้เหมาะสำหรับการใช้งานเช่นการทำเครื่องหมายชิ้นส่วนอากาศยาน การติดฉลากเภสัชกรรม และโลจิสติกส์ที่ความน่าเชื่อถือเป็นสิ่งสำคัญ

## ทำไมต้องใช้การสร้างบาร์โค้ดของ Aspose?

Aspose.BarCode รองรับ **symbologies มากกว่า 30** ประเภท สามารถเรนเดอร์ภาพได้สูงสุด 10,000 × 10,000 px โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ และให้ผลลัพธ์ที่คาดเดาได้บน Windows, Linux, และ macOS API ของมันทำให้คุณควบคุมพารามิเตอร์การเรนเดอร์ทุกอย่าง ทำให้เป็นตัวเลือกที่ยืดหยุ่นที่สุดสำหรับ **การสร้างบาร์โค้ดใน ASP.NET**  

## ข้อกำหนดเบื้องต้น

1. **สภาพแวดล้อมการพัฒนา** – Visual Studio พร้อม .NET framework ที่เหมาะสมติดตั้งไว้  
2. **Aspose.BarCode สำหรับ .NET** – ดาวน์โหลดและติดตั้งจากเว็บไซต์, [ที่นี่](https://releases.aspose.com/barcode/net/)  
3. **ไลเซนส์** – รับไลเซนส์ชั่วคราวสำหรับการทดสอบจาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  
4. **พื้นฐาน C#** – ความคุ้นเคยกับไวยากรณ์ C# และโครงสร้างโปรเจกต์  

ตอนนี้เราได้ครอบคลุมพื้นฐานแล้ว ไปที่การกำหนดค่า DataMatrix ECC 200 ต่อ

## นำเข้า Namespaces

Namespace `Aspose.BarCode.Generation` มีคลาสทั้งหมดที่จำเป็นสำหรับการสร้างบาร์โค้ด นำเข้าที่ส่วนบนของไฟล์ของคุณ:

```csharp
using Aspose.BarCode.Generation;
```

## วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ทีละขั้นตอน

เพื่อสร้างบาร์โค้ด DataMatrix ECC 200 คุณเพียงโหลดข้อมูลที่ต้องการเข้ารหัส ตั้งค่าพารามิเตอร์สำคัญบางอย่างบน `BarcodeGenerator` แล้วเรียก `Save` เพื่อบันทึกไฟล์ภาพ กระบวนการสามขั้นตอนนี้จัดการการเข้ารหัส การแก้ไขข้อผิดพลาด และการเลือกรูปแบบเอาต์พุต ทำให้คุณสามารถรวมการสร้างบาร์โค้ดเข้าในแอปพลิเคชัน .NET ใดก็ได้ด้วยโค้ดเพียงเล็กน้อย

### ขั้นตอนที่ 1: เริ่มต้น Barcode Generator

`BarcodeGenerator` เป็นคลาสหลักของ Aspose.BarCode ที่สร้างและเรนเดอร์บาร์โค้ด มันรับประเภท symbology และข้อความที่ต้องการเข้ารหัส

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

แทนที่ `"Your Directory Path"` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกภาพ

### ขั้นตอนที่ 2: ตั้งค่า XDimension และ ECC Type

`XDimension` กำหนดขนาดพิกเซลของแต่ละโมดูล DataMatrix, ส่วน `DataMatrixEcc` เลือกระดับการแก้ไขข้อผิดพลาด ECC 200 ให้ความสามารถการแก้ไขสูงสุดสำหรับ symbology นี้

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

ปรับค่าพิกเซลหากต้องการโมดูลใหญ่หรือเล็กกว่า; ค่าโดยทั่วไปคือ 4‑6 px สำหรับการแสดงผลบนหน้าจอและ 8‑10 px สำหรับป้ายพิมพ์

### ขั้นตอนที่ 3: สร้างและบันทึกภาพบาร์โค้ด

เมธอด `Save` จะเขียนบาร์โค้ดลงไฟล์ คุณสามารถเลือก PNG, JPEG หรือ TIFF โดยส่งค่า enum `BarCodeImageFormat` ที่สอดคล้อง

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

เปลี่ยน `BarCodeImageFormat.Png` เป็น `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Tiff` หากกระบวนการทำงานของคุณต้องการรูปแบบอื่น

## ปัญหาทั่วไปและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| บาร์โค้ดดูเบลอ | XDimension ต่ำเกินไป | เพิ่ม `XDimension.Pixels` เป็น 6‑8 |
| การสแกนล้มเหลวบนมือถือ | ระดับ ECC ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่า `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| ไม่สร้างไฟล์ | สตริงเส้นทางไม่ถูกต้อง | ใช้เส้นทางแบบ absolute หรือให้แน่ใจว่าโฟลเดอร์มีอยู่ |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้โค้ดนี้ในแอปพลิเคชันคอนโซล .NET Core ได้หรือไม่?**  
ตอบ: ใช่, API เดียวกันทำงานใน .NET Core, .NET 5, และ .NET 6

**ถาม: จะเปลี่ยนรูปแบบเอาต์พุตเป็น JPEG อย่างไร?**  
ตอบ: แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` ในการเรียก `Save`

**ถาม: สามารถฝังบาร์โค้ดลงใน PDF ได้โดยตรงหรือไม่?**  
ตอบ: ได้ – สร้างภาพก่อน แล้วเพิ่มลงใน PDF ด้วย Aspose.PDF หรือไลบรารี PDF ใดก็ได้

**ถาม: หากต้องการเข้ารหัสอักขระ Unicode จะทำอย่างไร?**  
ตอบ: DataMatrix รองรับ UTF‑8; เพียงส่งสตริง Unicode ไปยัง generator ตามที่แสดง

**ถาม: ไลบรารีรองรับการสร้างบาร์โค้ดหลายรายการพร้อมกันหรือไม่?**  
ตอบ: แน่นอน – ใส่โค้ดการสร้างภายในลูปและเปลี่ยนข้อมูล/ค่าแต่ละรอบ

## สรุป

เราได้ครอบคลุมทุกอย่างที่คุณต้องการเพื่อ **สร้างบาร์โค้ด DataMatrix** (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET ตั้งแต่ข้อกำหนดเบื้องต้น การนำเข้า namespace ไปจนถึงการกำหนด X‑dimension, การเลือกระดับ ECC, และการบันทึกภาพในรูปแบบที่คุณต้องการ ทดลองใช้คุณสมบัติเพิ่มเติมเช่น margin, สีพื้นหลัง, และการหมุนเพื่อปรับแต่งผลลัพธ์ให้เหมาะกับกรณีการใช้งานของคุณ

หากพบปัญหาใด ๆ ชุมชนพร้อมช่วยเหลือที่ [ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13) ขอให้สนุกกับการเขียนโค้ด!

---

**อัปเดตล่าสุด:** 2026-08-02  
**ทดสอบกับ:** Aspose.BarCode 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างบาร์โค้ด DataMatrix ECC 000-140 ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [วิธีอ่านบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-reading/)
- [สร้าง Barcode PNG – อัตราส่วนภาพ DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}