---
date: 2026-08-17
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครโดยใช้ Aspose.BarCode
  สำหรับ .NET และค้นพบวิธีใช้ DataMatrix ในแอปพลิเคชันของคุณ
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: การกำหนดค่าแมโคร DataMatrix
og_description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครโดยใช้ Aspose.BarCode
  สำหรับ .NET คู่มือนี้ให้โค้ดแบบขั้นตอนต่อขั้นตอน ตัวเลือกการปรับแต่ง และเคล็ดลับการตรวจสอบเพื่อการสร้างบาร์โค้ดที่เชื่อถือได้
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: สร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครโดยใช้ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: วิธีสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครใน .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครใน .NET

## บทนำ

การสร้าง **บาร์โค้ด DataMatrix** ที่รวมอักขระแมโครช่วยให้คุณบรรจุข้อมูลอ้างอิงเพิ่มเติมลงในสัญลักษณ์สี่เหลี่ยมจัตุรัสขนาดเล็ก ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้างบาร์โค้ด DataMatrix** ด้วยอักขระแมโครโดยใช้ Aspose.BarCode for .NET ปรับขนาดและระดับการแก้ไขข้อผิดพลาด และตรวจสอบผลลัพธ์ทันที เมื่อเสร็จแล้วคุณจะพร้อมฝังบาร์โค้ดที่เปิดใช้งานแมโครลงในป้ายสินค้า เอกสาร หรืออุปกรณ์ทางการแพทย์

## คำตอบอย่างรวดเร็ว
- **ห้องสมุดหลักคืออะไร?** Aspose.BarCode for .NET  
- **ฉันสามารถสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครได้หรือไม่?** Yes – set the `MacroCharacters` property.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** A valid Aspose license is required for production use.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **มีการทดลองใช้ฟรีหรือไม่?** แน่นอน – ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการของ Aspose.

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกในการกำหนดค่าแมโคร โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Visual Studio** – รุ่นล่าสุดใดก็ได้จะทำงาน.  
2. **Aspose.BarCode for .NET** – ดาวน์โหลดได้จาก [the download link](https://releases.aspose.com/barcode/net/).  
3. **Basic .NET knowledge** – ความคุ้นเคยกับ C# และระบบนิเวศของ .NET.

## นำเข้าเนมสเปซ

เราจะเริ่มโดยการนำเข้าเนมสเปซที่จำเป็นสำหรับการสร้างและการจดจำบาร์โค้ด

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## อะไรคือ “generate DataMatrix barcode” ด้วยอักขระแมโคร?

`MacroCharacters` ทำให้บาร์โค้ด DataMatrix สามารถรวมสัญลักษณ์แมโครที่อ้างอิงข้อมูลเพิ่มเติมได้ การใช้อักขระแมโครเช่น Macro05 หรือ Macro06 บาร์โค้ดเดียวสามารถชี้ไปยังชุดข้อมูลที่ใหญ่ขึ้นหรือชุดของบาร์โค้ดที่เกี่ยวข้อง ซึ่งมีคุณค่าในโลจิสติกส์ การผลิต และการติดตามเอกสารที่ต้องการการเข้ารหัสข้อมูลที่เชื่อมโยงอย่างกะทัดรัด

## ทำไมต้องใช้ Aspose.BarCode เพื่อสร้างบาร์โค้ด DataMatrix?

Aspose.BarCode ให้การควบคุมที่แม่นยำต่อขนาด DataMatrix ระดับการแก้ไขข้อผิดพลาด และการตั้งค่าแมโคร รองรับสัญลักษณ์บาร์โค้ดมากกว่า 30 แบบและจัดการไฟล์ขนาดสูงสุด 10 MB โดยไม่ต้องโหลดภาพทั้งหมดเข้าสู่หน่วยความจำ การทำงานข้ามแพลตฟอร์มของ .NET ทำงานบน .NET Framework, .NET Core, และ .NET 5/6 และรวมการจดจำในตัวเพื่อให้คุณตรวจสอบบาร์โค้ดได้ทันที

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ

สร้างแอปพลิเคชันคอนโซลใหม่ (หรือโปรเจกต์ .NET ใด ๆ) ใน Visual Studio เพิ่มการอ้างอิงไปยัง DLL ของ Aspose.BarCode ที่คุณได้จากการดาวน์โหลด

### ขั้นตอนที่ 2: การกำหนดค่าแมโครของ DataMatrix

หัวใจของบทเรียน – ที่นี่เราจริง ๆ **สร้างบาร์โค้ด DataMatrix** ด้วยอักขระแมโคร

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **เคล็ดลับ:** แทนที่ `"ASPOSE"` ด้วยสตริงใดก็ได้ที่คุณต้องการเข้ารหัส อักขระแมโคร (`Macro05`) บอกสแกนเนอร์ว่าบาร์โค้ดนี้เป็นส่วนหนึ่งของลำดับแมโคร

### ขั้นตอนที่ 3: ปรับแต่งพารามิเตอร์บาร์โค้ดสำหรับการแก้ไขข้อผิดพลาด

ก่อนบันทึก คุณสามารถปรับแต่งการตั้งค่าเพิ่มเติมได้:

- **XDimension** – ควบคุมขนาดของแต่ละโมดูล (พิกเซล).  
- **Margin**, **ErrorCorrection**, และ **EncodingMode** – ทั้งหมดเข้าถึงได้ผ่าน `gen.Parameters.Barcode.DataMatrix`.

### ขั้นตอนที่ 4: บันทึกบาร์โค้ด

โค้ดข้างต้นบันทึกรูปภาพเป็น `DataMatrixMacro.png` ในโฟลเดอร์ที่คุณระบุ PNG เป็นรูปแบบที่ไม่มีการสูญเสียคุณภาพ ทำให้เหมาะสำหรับการประมวลผลต่อไป

### ขั้นตอนที่ 5: จดจำบาร์โค้ด

`BarCodeReader` เป็นคลาสของ Aspose.BarCode สำหรับถอดรหัสบาร์โค้ดจากภาพ การใช้ `BarCodeReader` เราจะอ่านภาพที่สร้างขึ้นกลับมาโดยทันทีเพื่อยืนยันว่าอักขระแมโครและข้อมูลถูกต้อง การตรวจสอบแบบรอบนี้มีประโยชน์อย่างยิ่งในระหว่างการทดสอบอัตโนมัติ

## วิธีใช้ DataMatrix ในสถานการณ์จริง?

คุณสามารถนำบาร์โค้ด DataMatrix ที่มีอักขระแมโครไปใช้ในการติดป้ายสินค้า เชื่อมหมายเลขซีเรียลกับฐานข้อมูลศูนย์กลาง การติดตามเอกสารโดยฝังการอ้างอิงไปยังบันทึกดิจิทัล และแท็กอุปกรณ์ทางการแพทย์ที่เก็บข้อมูลผู้ป่วยหรืออุปกรณ์ในสัญลักษณ์ขนาดเล็กที่สแกนได้ กรณีการใช้งานเหล่านี้ช่วยลดการป้อนข้อมูลด้วยมือและเพิ่มความสามารถในการติดตาม

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| บาร์โค้ดไม่ถูกจดจำ | ค่า `XDimension` ไม่ถูกต้องหรือความละเอียดภาพต่ำ | เพิ่ม `XDimension.Pixels` เป็น 4‑6 และบันทึกเป็น PNG หรือ TIFF |
| อักขระแมโครถูกละเลย | รีดเดอร์ไม่รองรับโหมดแมโคร | ใช้สแกนเนอร์/รีดเดอร์ที่รองรับแมโครของ DataMatrix อย่างชัดเจน (เช่น เวอร์ชัน ZXing ที่ใหม่กว่า) |
| ไม่พบเส้นทาง | ตัวแปร `path` ไม่ถูกต้อง | ตรวจสอบว่าไดเรกทอรีมีอยู่หรือใช้ `Path.Combine` กับ `Environment.CurrentDirectory` |

## คำถามที่พบบ่อย

**Q: Aspose.BarCode for .NET คืออะไร?**  
A: Aspose.BarCode for .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนา .NET สามารถสร้างและจดจำบาร์โค้ดในรูปแบบต่าง ๆ รวมถึง DataMatrix, QR, และอื่น ๆ

**Q: ทำไมต้องใช้บาร์โค้ด DataMatrix?**  
A: บาร์โค้ด DataMatrix มีขนาดกะทัดรัด มีความน่าเชื่อถือสูง และสามารถเก็บข้อมูลจำนวนมาก ทำให้เหมาะสำหรับการผลิต โลจิสติกส์ และการดูแลสุขภาพ

**Q: สามารถค้นหาเอกสารประกอบของ Aspose.BarCode for .NET ได้ที่ไหน?**  
A: คุณสามารถค้นหาเอกสารได้ที่ [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.BarCode for .NET หรือไม่?**  
A: มี คุณสามารถดาวน์โหลดการทดลองใช้ฟรีได้จาก [the free trial link](https://releases.aspose.com/).

**Q: จะหาการสนับสนุนสำหรับ Aspose.BarCode for .NET ได้จากที่ไหน?**  
A: หากคุณมีคำถามหรือจำเป็นต้องการสนับสนุน คุณสามารถเยี่ยมชมฟอรั่ม Aspose.BarCode for .NET ได้ที่ [the support forum](https://forum.aspose.com/c/barcode/13).

---

**อัปเดตล่าสุด:** 2026-08-17  
**ทดสอบด้วย:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างบาร์โค้ด aspose .net - การกำหนดค่า DataMatrix Code Text](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [วิธีสร้าง DataMatrix Barcodes (ECC 200) ด้วย Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [การกำหนดค่า DataMatrix Structured Append ด้วย Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}