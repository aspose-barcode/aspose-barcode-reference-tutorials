---
date: 2026-05-30
description: เรียนรู้วิธีสร้าง barcode PNG ด้วยอัตราส่วน DataMatrix ที่กำหนดเองโดยใช้
  Aspose.BarCode สำหรับ .NET. คู่มือขั้นตอนต่อขั้นตอนสำหรับการสร้าง barcode และการปรับขนาด
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: การปรับแต่งอัตราส่วนของ DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้าง Barcode PNG – อัตราส่วนของ DataMatrix – Aspose.BarCode
url: /th/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Barcode PNG – อัตราส่วนภาพ DataMatrix – Aspose.BarCode

การสร้าง **barcode PNG** ด้วยอัตราส่วนภาพ DataMatrix ที่กำหนดเองเป็นความต้องการทั่วไปเมื่อคุณต้องการ **สร้างไฟล์ barcode PNG** ที่เข้ากับข้อจำกัดของการจัดวางเฉพาะ ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อ **สร้างไฟล์ barcode PNG** ด้วย Aspose.BarCode สำหรับ .NET, อธิบายเหตุผลที่คุณอาจต้องการปรับอัตราส่วนภาพ, และแสดงวิธีปรับแต่งผลลัพธ์ให้เหมาะกับแอปพลิเคชันของคุณ.

## คำตอบสั้น
- **อัตราส่วนภาพ (aspect ratio) ควบคุมอะไร?** มันกำหนดอัตราส่วนความกว้างต่อความสูงของโมดูล DataMatrix.  
- **ฉันสามารถส่งออกเป็น PNG, JPEG หรือ SVG ได้หรือไม่?** ได้ – เมธอด `Save` รองรับ PNG, JPEG, BMP, GIF, TIFF, SVG และ PDF.  
- **ฉันต้องการไลเซนส์สำหรับฟีเจอร์นี้หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **ค่าของอัตราส่วนภาพที่เป็นค่าที่ถูกต้องมีจำนวนเท่าไหร่?** ค่า float บวกใดก็ได้; ค่าที่พบบ่อยคือ 0.5 – 2.0.

## DataMatrix barcode คืออะไรและทำไมต้องปรับอัตราส่วนภาพ?
DataMatrix barcode คือรหัสเมทริกซ์สองมิติที่เก็บข้อมูลจำนวนมากในรูปแบบสี่เหลี่ยมจัตุรัสที่กะทัดรัด การปรับ **aspect ratio** ทำให้คุณสามารถยืดหรือบีบอัดโมดูลในแนวนอนได้ ซึ่งมีประโยชน์เมื่อคุณต้องการใส่บาร์โค้ดลงในคอลัมน์แคบหรือป้ายกว้างโดยไม่ลดทอนความน่าเชื่อถือของการสแกน.

## ทำไมต้องใช้ Aspose.BarCode เพื่อสร้าง barcode PNG?
Aspose.BarCode รองรับ **7 รูปแบบภาพ** — PNG, JPEG, BMP, GIF, TIFF, SVG และ PDF — และสามารถประมวลผล **รูปแบบอินพุตและเอาต์พุตกว่า 50 แบบ** ในหน่วยความจำ, จัดการเอกสารหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมด ไลบรารีนี้มี API ที่ใช้งานง่ายที่ช่วยให้คุณสร้าง DataMatrix barcode ด้วยบรรทัดโค้ดเดียว, รับประกันการเรนเดอร์ที่พิกเซลสมบูรณ์และความเข้ากันได้เต็มรูปแบบกับ .NET.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มปรับแต่งอัตราส่วนภาพ DataMatrix, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ก็พอ.  
2. **Aspose.BarCode for .NET** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/barcode/net/).  
3. คุณสามารถสำรวจการปล่อยผลิตภัณฑ์ Aspose อื่น ๆ ได้จาก [ที่นี่](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – โปรเจกต์ของคุณต้องกำหนดเป้าหมายเป็นเวอร์ชันที่รองรับ.

## นำเข้า Namespaces
ก่อนอื่นคุณต้องนำเข้า namespace ที่จำเป็นในโปรเจกต์ C# ของคุณ: `using Aspose.BarCode.Generation;` นำเข้า namespace ที่มีคลาสการสร้างบาร์โค้ด.

```csharp
using Aspose.BarCode.Generation;
```

> **เคล็ดลับ:** เก็บคำสั่ง `using` นี้ไว้ที่ส่วนบนของไฟล์ของคุณเพื่อให้คลาส `BarcodeGenerator` พร้อมใช้งานเสมอ.

## วิธีสร้าง barcode PNG ด้วยอัตราส่วนภาพที่กำหนดเอง?
โหลด `BarcodeGenerator`, ตั้งค่าชนิด DataMatrix, ปรับคุณสมบัติ `AspectRatio`, แล้วเรียก `Save`. รูปแบบบรรทัดเดียวนี้จะสร้าง barcode PNG ที่สอดคล้องกับอัตราส่วนที่คุณระบุ, และไลบรารีจะจัดการการสเกลโมดูลและ quiet zone โดยอัตโนมัติ.

`BarcodeGenerator` สร้างภาพบาร์โค้ดจากสัญลักษณ์และข้อมูลที่ระบุ.

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์คอนโซลหรือ Windows Forms ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยัง DLL ของ Aspose.BarCode.

### ขั้นตอนที่ 2: เริ่มต้น Barcode Generator
สร้างอินสแตนซ์ด้วยสัญลักษณ์ DataMatrix และข้อมูลที่คุณต้องการเข้ารหัส: `BarcodeGenerator` สร้างภาพบาร์โค้ดจากสัญลักษณ์และข้อมูลที่ระบุ.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> บรรทัดนี้สร้าง generator ที่พร้อมสร้าง DataMatrix barcode ที่มีข้อความตัวอย่าง.

### ขั้นตอนที่ 3: ปรับแต่งอัตราส่วนภาพและบันทึกไฟล์ PNG
ตอนนี้คุณสามารถเปลี่ยน **aspect ratio** และบันทึกแต่ละเวอร์ชันเป็นภาพ PNG: `AspectRatio` ตั้งค่าอัตราส่วนความกว้างต่อความสูงของโมดูล DataMatrix. `Save` เขียนภาพบาร์โค้ดที่สร้างขึ้นไปยังไฟล์ในรูปแบบที่เลือก.

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- การเรียกครั้งแรกสร้างบาร์โค้ดที่มีอัตราส่วนสี่เหลี่ยมจัตุรัส (`AspectRatio = 1`).  
- การเรียกครั้งที่สองบีบอัดบาร์โค้ดในแนวนอน (`AspectRatio = 0.5`), ทำให้ดูกว้างขึ้น.

ตอนนี้คุณมีไฟล์ **barcode PNG** สองไฟล์ที่มีอัตราส่วนภาพต่างกันพร้อมใช้งานในรายงาน, ป้าย, หรือส่วน UI.

## ปัญหาทั่วไป & วิธีแก้ไข
| ปัญหา | วิธีแก้ไข |
|-------|----------|
| **ภาพที่สร้างออกมาดูเบลอ** | เพิ่มพารามิเตอร์ `Resolution` ก่อนบันทึก (`gen.Parameters.ImageResolution = 300`). |
| **บาร์โค้ดไม่สามารถสแกนได้** | ตรวจสอบให้แน่ใจว่าอัตราส่วนภาพอยู่ในช่วง 0.5 – 2.0 และรักษา quiet zone ที่เพียงพอ (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **ข้อผิดพลาดของเส้นทางไฟล์** | ใช้ `Path.Combine` เพื่อสร้างเส้นทางออกและตรวจสอบว่าโฟลเดอร์มีอยู่. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถปรับแต่งอัตราส่วนภาพของประเภทบาร์โค้ดอื่น ๆ ด้วย Aspose.BarCode สำหรับ .NET ได้หรือไม่?**  
**ตอบ:** ได้, บาร์โค้ด 2‑D หลายประเภท (เช่น QR, PDF417) รองรับการปรับอัตราส่วนภาพผ่านอ็อบเจ็กต์พารามิเตอร์เฉพาะของพวกมัน.

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode สำหรับ .NET หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.BarCode สำหรับ .NET ได้จาก [ที่นี่](https://releases.aspose.com/).

**ถาม: ฉันสามารถซื้อไลเซนส์สำหรับ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?**  
**ตอบ:** คุณสามารถซื้อไลเซนส์ได้ที่เว็บไซต์ Aspose [ที่นี่](https://purchase.aspose.com/buy).

**ถาม: Aspose.BarCode สำหรับ .NET เข้ากันได้กับเวอร์ชัน .NET Framework ต่าง ๆ หรือไม่?**  
**ตอบ:** ได้, มันทำงานกับ .NET Framework 4.x, .NET Core 3.1+, และเวอร์ชัน .NET ล่าสุด.

**ถาม: ฉันสามารถสร้างบาร์โค้ดในรูปแบบต่าง ๆ ด้วย Aspose.BarCode สำหรับ .NET ได้หรือไม่?**  
**ตอบ:** แน่นอน – PNG, JPEG, BMP, GIF, TIFF, SVG, และ PDF ทั้งหมดรองรับโดยตรง.

## สรุป
การปรับแต่ง **aspect ratio** ของ DataMatrix barcode และ **การสร้าง barcode PNG** เป็นเรื่องง่ายด้วย Aspose.BarCode สำหรับ .NET. ด้วยการทำตามขั้นตอนข้างต้น, คุณสามารถสร้างบาร์โค้ดที่มีขนาดพอดีตามความต้องการของโครงการของคุณ. สำรวจพารามิเตอร์เพิ่มเติมเช่น `Resolution`, `Margin`, และ `Color` เพื่อปรับผลลัพธ์ให้เหมาะสมยิ่งขึ้น, และพิจารณาความสามารถในการ `generate datamatrix barcode` เมื่อสร้างแอปพลิเคชันที่เป็นมิตรกับการสแกนใน Visual Studio.

สำหรับการสำรวจเพิ่มเติม, ดูเอกสารอย่างเป็นทางการ [documentation](https://reference.aspose.com/barcode/net/) หรือเข้าร่วมชุมชนใน [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

---

**อัปเดตล่าสุด:** 2026-05-30  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง DataMatrix Barcode – คู่มือระดับมืออาชีพกับ Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [วิธีสร้าง DataMatrix Barcode (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [เชี่ยวชาญการเข้ารหัส DataMatrix ใน ASCII ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}