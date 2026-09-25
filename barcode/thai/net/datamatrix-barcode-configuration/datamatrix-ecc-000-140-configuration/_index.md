---
date: 2026-08-17
description: เรียนรู้วิธีสร้าง datamatrix barcode aspose โดยใช้ Aspose.BarCode สำหรับ
  .NET – เหมาะสำหรับการสร้าง barcode การจัดการสินค้าคงคลังและโครงการสร้าง barcode
  ด้วย C#
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 การกำหนดค่า
og_description: สร้าง datamatrix barcode aspose โดยใช้ Aspose.BarCode สำหรับ .NET
  – โซลูชันที่เร็วและมีประสิทธิภาพสูงสำหรับการจัดการสินค้าคงคลังและโครงการ barcode
  ด้วย C#
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: สร้าง datamatrix barcode aspose ด้วย Aspose.BarCode สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: วิธีสร้าง datamatrix barcode aspose ด้วย Aspose.BarCode
url: /th/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด datamatrix ด้วย Aspose.BarCode

## คำตอบอย่างรวดเร็ว
- **อะไรคือไลบรารีหลัก?** Aspose.BarCode for .NET  
- **ประเภทบาร์โค้ดที่ครอบคลุมคืออะไร?** DataMatrix ECC 000‑140  
- **ใช้ภาษาอะไร?** C# (C Sharp)  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **ระยะเวลาการทำงานโดยประมาณ?** ประมาณ 10‑15 นาทีสำหรับตัวสร้างพื้นฐาน  

## DataMatrix ECC 000‑140 คืออะไร?
DataMatrix เป็นบาร์โค้ดสองมิติที่เก็บข้อมูลจำนวนมากในรูปแบบสี่เหลี่ยมจัตุรัสที่กะทัดรัด ระดับการแก้ไขข้อผิดพลาด **ECC 000‑140** สามารถกู้คืนได้ถึง 140 % ของโค้ดเวิร์ดที่เสียหาย ทำให้เหมาะอย่างยิ่งสำหรับสภาพแวดล้อมคลังสินค้าที่รุนแรงที่ฉลากอาจถูกขีดข่วนหรือเปื้อน  

## ทำไมต้องเลือก Aspose.BarCode สำหรับ .NET?
- **API ที่แข็งแรง:** รองรับสัญลักษณ์บาร์โค้ดกว่า 30 ชนิดและใช้กฎการเข้ารหัสโดยอัตโนมัติ  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, macOS, และ Linux โดยไม่มีการพึ่งพาเนทีฟ  
- **ประสิทธิภาพสูง:** สร้าง DataMatrix ขนาด 200 × 200 พิกเซลภายในเวลาไม่ถึง 50 ms บน CPU 2.5 GHz ปกติ ทำให้สายการติดฉลากที่มีอัตราการทำงานสูง  

## ข้อกำหนดเบื้องต้น
1. **Visual Studio** – รุ่นใดก็ได้ที่ใหม่ล่าสุด (Community, Professional หรือ Enterprise).  
2. **Aspose.BarCode for .NET** – ดาวน์โหลดจาก [download link](https://releases.aspose.com/barcode/net/). คุณยังสามารถเยี่ยมชม [this link](https://releases.aspose.com/) เพื่อรับทรัพยากรเพิ่มเติม.  
3. **โครงการ .NET** – พร้อมอ้างอิงแอสเซมบลี Aspose.BarCode  

## นำเข้า namespace
ในไฟล์ C# ของคุณ ให้เพิ่มคำสั่ง `using` ที่จำเป็นเพื่อให้เข้าถึงคลาสบาร์โค้ดได้  

```csharp
using Aspose.BarCode.Generation;
```

**คลาส `BarcodeGenerator` เป็นเอนจิ้นหลักของ Aspose.BarCode สำหรับสร้างรูปภาพบาร์โค้ด**  
**คลาส `BarcodeGenerator` เป็นเอนจิ้นหลักของ Aspose.BarCode ที่สร้างและกำหนดค่ารูปภาพบาร์โค้ด**  

```csharp
using Aspose.BarCode.Generation;
```

## กรณีการใช้งานการสร้างบาร์โค้ดสำหรับการจัดการสินค้าคงคลัง
ลองนึกภาพว่าคุณต้องติดฉลากพันล้านพาเลทในศูนย์กระจายสินค้า โดยการสร้างบาร์โค้ด DataMatrix ECC 000‑140 คุณสามารถฝังรหัสสินค้า, หมายเลขล็อต, และวันหมดอายุในสัญลักษณ์เดียวที่ทนต่อข้อผิดพลาด ซึ่งสแกนเนอร์มือถือสามารถอ่านได้ทันที ลดข้อผิดพลาดจากการป้อนข้อมูลด้วยมือได้ถึง 95 %  

## วิธีสร้างบาร์โค้ด datamatrix ด้วย Aspose ใน C#
โหลดข้อมูล, กำหนดค่าตัวสร้าง, และบันทึกรูปภาพ – ทั้งหมดในสามขั้นตอนสั้น ๆ `BarcodeGenerator` จะเลือกขนาดโมดูลที่เหมาะสมโดยอัตโนมัติและใช้ระดับการแก้ไข ECC 140 ดังนั้นคุณไม่ต้องคำนวณค่า checksum เอง ทำได้อย่างรวดเร็วและมีประสิทธิภาพ  

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุต
เลือกโฟลเดอร์ที่ไฟล์ PNG จะถูกเขียนลงไป เส้นทางต้องมีอยู่ก่อนที่คุณจะเรียก `Save`  

```csharp
string path = "Your Directory Path";
```

### ขั้นตอนที่ 2: สร้างตัวสร้างบาร์โค้ด
สร้างอินสแตนซ์ `BarcodeGenerator`, ตั้งค่าสัญลักษณ์เป็น DataMatrix, ให้ payload, และเลือกระดับการแก้ไขข้อผิดพลาดสูงสุด  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

ในโค้ดนี้เราจะ:

* เลือก **DataMatrix** เป็นประเภทบาร์โค้ด  
* ระบุค่าตัวอย่าง (`"Åspóse.Barcóde©"`)  
* ตั้งค่า **XDimension** เพื่อควบคุมขนาดโมดูล (4 พิกเซลในที่นี้)  
* เลือกระดับการแก้ไขข้อผิดพลาดสูงสุด (**ECC 140**)  
* บันทึกผลลัพธ์เป็นไฟล์ PNG  

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **เส้นทางไม่ถูกต้อง** | ตรวจสอบให้แน่ใจว่า `path` ลงท้ายด้วยตัวคั่นไดเรกทอรี (`\` หรือ `/`) และโฟลเดอร์มีอยู่ |
| **อักขระที่ไม่รองรับ** | DataMatrix รองรับ UTF‑8; หลีกเลี่ยงอักขระควบคุมและใช้การเข้ารหัสที่เหมาะสม |
| **ไลเซนส์ไม่ได้ถูกนำไปใช้** | คลาส `Aspose.BarCode.License` จะนำไลเซนส์เชิงพาณิชย์มาใช้เพื่อเปิดฟังก์ชันเต็ม ให้เรียกใช้ก่อนสร้างบาร์โค้ดใด ๆ |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.BarCode สำหรับ .NET บนเซิร์ฟเวอร์ Linux ได้หรือไม่?**  
ตอบ: ใช่. ไลบรารีนี้เป็นข้ามแพลตฟอร์มเต็มรูปแบบและทำงานบน .NET 5+, .NET 6+, และ .NET Core บน Linux โดยไม่มีการพึ่งพาเพิ่มเติม  

**ถาม: ไลบรารีจัดการกับชุดบาร์โค้ดขนาดใหญ่อย่างไร?**  
ตอบ: คุณสามารถใช้อินสแตนซ์ `BarcodeGenerator` ตัวเดียวในลูป; ทุกครั้งที่เรียก `Save` จะเรนเดอร์ภาพใหม่ในประมาณ 40‑60 ms ทำให้เหมาะสำหรับการสร้างหลายพันฉลากต่อหนึ่งนาที  

**ถาม: ฉันต้องเข้ารหัสข้อมูลด้วยตนเองสำหรับ ECC 140 หรือไม่?**  
ตอบ: ไม่. การตั้งค่า `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` จะใช้ขั้นตอนการแก้ไขข้อผิดพลาดที่ถูกต้องโดยอัตโนมัติ  

**ถาม: เวอร์ชันทดลองเพียงพอสำหรับการพัฒนาหรือไม่?**  
ตอบ: รุ่นทดลองให้การเข้าถึงฟีเจอร์เต็มรวมถึง ECC 140 แต่จะใส่น้ำลายน้ำบนภาพที่สร้างขึ้น ใช้ไลเซนส์สำหรับการผลิตเพื่อเอาน้ำลายน้ำออก  

**ถาม: ฉันสามารถปรับแต่งสีของบาร์โค้ดได้หรือไม่?**  
ตอบ: แน่นอน. ใช้ `generator.Parameters.Barcode.Color` และ `generator.Parameters.Barcode.BackColor` เพื่อให้ตรงกับแบรนด์ของคุณ  

**อัปเดตล่าสุด:** 2026-08-17  
**ทดสอบกับ:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose  

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [การเข้ารหัส DataMatrix ขั้นสูงใน ASCII ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [วิธีอ่านบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}