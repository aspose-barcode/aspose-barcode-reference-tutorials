---
date: 2026-09-23
description: เรียนรู้วิธีใช้ Aspose.BarCode เพื่อสร้างบาร์โค้ด DataMatrix พร้อมข้อความโค้ดขยายใน
  .NET ซึ่งเหมาะสำหรับการใช้งานด้านสินค้าคงคลังและโลจิสติกส์
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: การกำหนดค่าข้อความโค้ดขยายของ DataMatrix
og_description: วิธีใช้ Aspose.BarCode เพื่อสร้างบาร์โค้ด DataMatrix พร้อมข้อความโค้ดขยายใน
  .NET. ทำตามคู่มือขั้นตอนสั้น ๆ สำหรับโซลูชันด้านสินค้าคงคลังและโลจิสติกส์
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: วิธีใช้ Aspose.BarCode เพื่อสร้างข้อความโค้ด DataMatrix ใน .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: วิธีใช้ Aspose.BarCode เพื่อสร้างข้อความโค้ด DataMatrix ใน .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ Aspose.BarCode เพื่อสร้างข้อความ DataMatrix ใน .NET

การรวมบาร์โค้ดเข้ากับแอปพลิเคชัน .NET สมัยใหม่ไม่ได้เป็นงานเฉพาะอีกต่อไป—มันเป็นความต้องการหลักสำหรับการจัดการสินค้าคงคลัง, โลจิสติกส์, และโซลูชันการสแกนบนมือถือ ในคู่มือนี้คุณจะ **เรียนรู้วิธีใช้ Aspose.BarCode** เพื่อกำหนดค่า DataMatrix barcode พร้อมข้อความโค้ดที่ขยาย, สร้างภาพ, และตรวจสอบโดยโปรแกรม คุณจะเห็นว่าทำไมวิธีนี้จึงเหมาะสำหรับการสร้างบาร์โค้ดสำหรับสินค้าคงคลังและวิธีที่มันเข้ากับโครงการ .NET Core หรือ .NET 6

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.BarCode for .NET  
- **ประเภทบาร์โค้ดคืออะไร?** DataMatrix with extended code text  
- **ฉันสามารถใช้ .NET Core / .NET 6 ได้หรือไม่?** ใช่, API รองรับหลายแพลตฟอร์ม  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน  

## Aspose.BarCode for .NET คืออะไร?
Aspose.BarCode for .NET เป็นไลบรารีเชิงพาณิชย์ที่ช่วยให้นักพัฒนาสามารถสร้างและอ่านบาร์โค้ดได้มากกว่า 30 รูปแบบ รวมถึง DataMatrix, QR, และ Code 128, และสามารถสร้างภาพขนาดสูงสุด 10,000 × 10,000 พิกเซลโดยไม่ต้องพึ่งพาไลบรารีภายนอก รองรับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7

## ทำไมต้องใช้ DataMatrix extended code text?
DataMatrix extended code text ช่วยให้คุณฝังหลายรูปแบบการเข้ารหัส—UTF‑8, C40, Text, X12—ในสัญลักษณ์เดียว, ทำให้สามารถบรรจุได้สูงสุด **3116 codewords** (ประมาณ 155 KB ของข้อมูล) ในสี่เหลี่ยมจัตุรัสขนาดกะทัดรัด ความสามารถนี้เหมาะอย่างยิ่งสำหรับการติดฉลากผลิตภัณฑ์หลายภาษา, การติดตามอุปกรณ์ทางการแพทย์, และบรรจุภัณฑ์อัจฉริยะที่ต้องรวมรหัสอัลฟานูเมอริกกับข้อมูลไบนารี

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Aspose.BarCode for .NET** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, Rider หรือ VS Code พร้อม .NET SDK.  
3. **ความรู้พื้นฐาน C#** – คุณควรคุ้นเคยกับคลาส, namespace, และคำสั่ง `using`.  

## นำเข้า namespace
เพิ่ม namespace ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณเพื่อให้คอมไพเลอร์รู้ว่าจะหา class ของบาร์โค้ดได้จากที่ไหน.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Namespace เหล่านี้ให้คุณเข้าถึงคุณลักษณะการสร้างและการอ่านบาร์โค้ดได้ทั้งสองอย่าง.

## วิธีกำหนดค่า DataMatrix extended code text?
โหลด builder, เพิ่มส่วนที่ต้องการ, และให้ Aspose.BarCode จัดการกับเครื่องหมาย ECI โดยอัตโนมัติ ย่อหน้านี้ให้ขั้นตอนที่ชัดเจน: สร้าง `DataMatrixExtCodetextBuilder`, เพิ่มส่วน Unicode, C40, plain‑text, และ Text mode, จากนั้นดึงสตริงที่รวมกันสำหรับตัวสร้าง.

### ขั้นตอนที่ 1: กำหนดโฟลเดอร์ผลลัพธ์
ระบุที่ที่ภาพบาร์โค้ดที่สร้างจะถูกบันทึก เปลี่ยน placeholder ให้เป็นพาธที่ถูกต้องบนเครื่องของคุณ.

```csharp
string path = "Your Directory Path";
```

### ขั้นตอนที่ 2: สร้าง extended code text
`DataMatrixExtCodetextBuilder` เป็นคลาสช่วยเหลือที่ประกอบ extended code text ตามสเปคของ DataMatrix โดยอัตโนมัติจะใส่เครื่องหมาย ECI (Extended Channel Interpretation) ที่จำเป็น.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

ตัวอย่างนี้แสดงให้เห็นว่าคุณสามารถผสานอักขระ Unicode, การเข้ารหัส C40, plain text, และ Text mode ในสัญลักษณ์ DataMatrix เดียวได้อย่างไร

### ขั้นตอนที่ 3: สร้างสตริง codetext สุดท้าย
หลังจากกำหนดค่าทั้งหมดแล้ว, ดึงสตริงที่รวมกันซึ่ง Aspose.BarCode จะฝังลงในบาร์โค้ด

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### ขั้นตอนที่ 4: สร้างบาร์โค้ด DataMatrix
`BarcodeGenerator` เป็นคลาสหลักที่สร้างภาพบาร์โค้ด สร้างอินสแตนซ์ด้วย `EncodeTypes.DataMatrix` และ extended codetext จากนั้นตั้งค่าพารามิเตอร์การแสดงผลเช่น X‑dimension, รูปแบบภาพ, และข้อความที่อ่านได้โดยมนุษย์ (ถ้าต้องการ)

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

โค้ดด้านบน **creates barcode aspose .net** พร้อมข้อความ extended code text ที่ต้องการและบันทึกเป็นไฟล์ PNG

### ขั้นตอนที่ 5: ตรวจสอบบาร์โค้ดโดยการอ่านกลับ
`BarCodeReader` ตรวจสอบว่าสัญลักษณ์ที่สร้างสามารถถอดรหัสได้อย่างถูกต้อง ซึ่งเป็นสิ่งสำคัญสำหรับ pipeline การทดสอบอัตโนมัติและการรับประกันคุณภาพ

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

หากทุกอย่างตั้งค่าอย่างถูกต้อง, คอนโซลจะพิมพ์ข้อความ extended code text ที่คุณสร้างไว้ก่อนหน้านี้ออกมา

## ปัญหาที่พบบ่อยและการแก้ไขปัญหา

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| บาร์โค้ดอ่านไม่ออก | X‑dimension ต่ำเกินไป | เพิ่ม `XDimension.Pixels` (เช่น 4 → 6) |
| อักขระเสียรูป | การเข้ารหัส ECI ผิด | ตรวจสอบให้ `ECIEncodings.UTF8` ตรงกับชุดอักขระ |
| ไฟล์ไม่ถูกบันทึก | พาธไม่ถูกต้อง | ใช้พาธเต็มหรือให้แน่ใจว่าโฟลเดอร์มีอยู่ |
| ข้อยกเว้นไลเซนส์ | รุ่นทดลองหมดอายุ | ใช้ไลเซนส์ชั่วคราวหรือเต็ม (ดู FAQ) |

## คำถามที่พบบ่อย

### Q1: Aspose.BarCode for .NET คืออะไร?
A1: Aspose.BarCode for .NET เป็นไลบรารีที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้างและอ่านบาร์โค้ดได้หลากหลายรูปแบบ รวมถึง DataMatrix, QR, Code128, และอื่น ๆ

### Q2: ฉันสามารถหาเอกสารสำหรับ Aspose.BarCode for .NET ได้ที่ไหน?
A2: คุณสามารถเข้าถึงเอกสารอ้างอิง API เต็มรูปแบบได้ที่ **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for .NET หรือไม่?
A3: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: ฉันจะขอไลเซนส์ชั่วคราวสำหรับการทดสอบได้อย่างไร?
A4: ไลเซนส์ชั่วคราวจะให้สำหรับการประเมินและสามารถขอได้ที่ **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: ฉันจะขอรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.BarCode for .NET ได้ที่ไหน?
A5: ฟอรั่มอย่างเป็นทางการของ Aspose.BarCode เป็นสถานที่ดีที่สุดสำหรับขอความช่วยเหลือ: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**อัปเดตล่าสุด:** 2026-09-23  
**ทดสอบด้วย:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode for .NET – คู่มือขั้นตอนต่อขั้นตอน](/barcode/net/datamatrix-barcode-configuration/)
- [สร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode for .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [สร้างบาร์โค้ด Aztec พร้อมการเข้ารหัสข้อความโดยใช้ Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}