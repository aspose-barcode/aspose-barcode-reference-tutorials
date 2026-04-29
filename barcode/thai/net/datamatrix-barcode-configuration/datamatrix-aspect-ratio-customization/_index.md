---
date: 2026-01-12
description: เรียนรู้วิธีสร้างไฟล์ PNG ของบาร์โค้ดด้วยอัตราส่วน DataMatrix ที่กำหนดเองโดยใช้
  Aspose.BarCode สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนสำหรับการสร้างบาร์โค้ดและการปรับขนาดตามต้องการ
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: สร้างบาร์โค้ด PNG – อัตราส่วนภาพ DataMatrix – Aspose.BarCode
url: /th/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Barcode PNG – อัตราส่วน DataMatrix – Aspose.BarCode

การสร้าง **barcode PNG** ด้วยอัตราส่วน DataMatrix ที่กำหนดเองเป็นความต้องการทั่วไปเมื่อคุณต้องการให้บาร์โค้ดพอดีกับข้อจำกัดการจัดวางเฉพาะ ในบทเรียนนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อ **สร้าง barcode PNG** ด้วย Aspose.BarCode สำหรับ .NET, อธิบายเหตุผลที่คุณอาจต้องการปรับอัตราส่วน, และแสดงวิธีการปรับแต่งผลลัพธ์ให้เหมาะกับแอปพลิเคชันของคุณ.

## คำตอบด่วน
- **อะไรคือการควบคุมของ “aspect ratio”?** มันกำหนดอัตราส่วนความกว้างต่อความสูงของโมดูล DataMatrix.  
- **ฉันสามารถส่งออกเป็น PNG, JPEG หรือ SVG ได้หรือไม่?** ใช่ – เมธอด `Save` รองรับ PNG, JPEG, BMP, GIF และอื่น ๆ.  
- **ฉันต้องมีลิขสิทธิ์สำหรับฟีเจอร์นี้หรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการผลิต.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **ค่าของอัตราส่วนที่เป็นไปได้มีเท่าไหร่?** ค่า float บวกใด ๆ; ค่าที่ทั่วไปคือ 0.5 – 2.0.

## DataMatrix barcode คืออะไรและทำไมต้องปรับอัตราส่วน?
DataMatrix คือบาร์โค้ดเมทริกซ์สองมิติที่เก็บข้อมูลจำนวนมากในพื้นที่เล็ก ๆ การปรับ **aspect ratio** ช่วยให้คุณขยายหรือบีบอัดโมดูลในแนวนอน ซึ่งเป็นประโยชน์สำหรับการใส่บาร์โค้ดลงในคอลัมน์แคบหรือป้ายกว้างโดยไม่เสียความอ่านได้.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มปรับแต่งอัตราส่วน DataMatrix, ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้จะใช้ได้.  
2. **Aspose.BarCode for .NET** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – โปรเจกต์ของคุณต้องกำหนดเป้าหมายเป็นเวอร์ชันที่รองรับ.

## นำเข้า Namespaces

ก่อนอื่นคุณต้องนำเข้า namespace ที่จำเป็นในโปรเจกต์ C# ของคุณ:

```csharp
using Aspose.BarCode.Generation;
```

> **เคล็ดลับ:** เก็บคำสั่ง `using` นี้ไว้ที่ส่วนบนของไฟล์เพื่อให้คลาส `BarcodeGenerator` พร้อมใช้งานเสมอ.

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์คอนโซลหรือ Windows Forms ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยัง DLL ของ Aspose.BarCode.

### ขั้นตอนที่ 2: เริ่มต้น Barcode Generator
สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภท DataMatrix และข้อมูลที่คุณต้องการเข้ารหัส:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> บรรทัดนี้สร้าง generator ที่พร้อมผลิตบาร์โค้ด DataMatrix ที่มีข้อความตัวอย่าง.

### ขั้นตอนที่ 3: ปรับแต่งอัตราส่วนและบันทึกไฟล์ PNG
ตอนนี้คุณสามารถเปลี่ยน **aspect ratio** และบันทึกแต่ละเวอร์ชันเป็นภาพ PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- การเรียกครั้งแรกสร้างบาร์โค้ดที่มีสัดส่วนเป็นสี่เหลี่ยมจัตุรัส (`AspectRatio = 1`).  
- การเรียกครั้งที่สองบีบัดบาร์โค้ดในแนวนอน (`AspectRatio = 0.5`), ทำให้ดูกว้างขึ้น.

ตอนนี้คุณมีไฟล์ **barcode PNG** สองไฟล์ที่มีอัตราส่วนต่างกันพร้อมใช้งานในรายงาน, ป้าย, หรือองค์ประกอบ UI.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **ภาพที่สร้างออกมาดูเบลอ** | เพิ่มพารามิเตอร์ `Resolution` ก่อนบันทึก (`gen.Parameters.ImageResolution = 300`). |
| **บาร์โค้ดไม่สามารถสแกนได้** | ตรวจสอบให้อัตราส่วนอยู่ในช่วง 0.5 – 2.0 และรักษา quiet zone ที่เพียงพอ (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **ข้อผิดพลาดของเส้นทางไฟล์** | ใช้ `Path.Combine` เพื่อสร้างเส้นทางออกและตรวจสอบว่าโฟลเดอร์มีอยู่. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถปรับแต่งอัตราส่วนของประเภทบาร์โค้ดอื่น ๆ ด้วย Aspose.BarCode for .NET ได้หรือไม่?**  
**ตอบ:** ใช่, บาร์โค้ด 2‑D หลายประเภท (เช่น QR, PDF417) รองรับการปรับอัตราส่วนผ่านอ็อบเจ็กต์พารามิเตอร์เฉพาะของพวกมัน.

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.BarCode for .NET หรือไม่?**  
**ตอบ:** มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.BarCode for .NET ได้จาก [ที่นี่](https://releases.aspose.com/).

**ถาม: ฉันสามารถซื้อไลเซนส์สำหรับ Aspose.BarCode for .NET ได้จากที่ไหน?**  
**ตอบ:** คุณสามารถซื้อไลเซนส์ได้บนเว็บไซต์ Aspose [ที่นี่](https://purchase.aspose.com/buy).

**ถาม: Aspose.BarCode for .NET เข้ากันได้กับเวอร์ชัน .NET Framework ต่าง ๆ หรือไม่?**  
**ตอบ:** ใช่, มันทำงานได้กับ .NET Framework 4.x, .NET Core 3.1+, และเวอร์ชัน .NET ล่าสุด.

**ถาม: ฉันสามารถสร้างบาร์โค้ดในรูปแบบต่าง ๆ ด้วย Aspose.BarCode for .NET ได้หรือไม่?**  
**ตอบ:** แน่นอน – PNG, JPEG, BMP, GIF, TIFF, SVG, และ PDF ทั้งหมดได้รับการสนับสนุนโดยตรง.

## สรุป

การปรับแต่ง **aspect ratio** ของบาร์โค้ด DataMatrix และ **การสร้าง barcode PNG** ทำได้อย่างง่ายดายด้วย Aspose.BarCode for .NET โดยทำตามขั้นตอนข้างต้นคุณสามารถสร้างบาร์โค้ดขนาดพอดีที่ตรงตามข้อกำหนดการจัดวางของโปรเจกต์ของคุณ สำรวจพารามิเตอร์อื่น ๆ เช่น `Resolution`, `Margin`, และ `Color` เพื่อปรับผลลัพธ์เพิ่มเติม.

สำหรับการสำรวจเพิ่มเติม, ดูที่ [เอกสารอย่างเป็นทางการ](https://reference.aspose.com/barcode/net/) หรือเข้าร่วมชุมชนใน [ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**อัปเดตล่าสุด:** 2026-01-12  
**ทดสอบกับ:** Aspose.BarCode 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}