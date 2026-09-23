---
date: 2026-05-19
description: เรียนรู้วิธีสร้าง Aztec Barcode ด้วยการเข้ารหัสข้อความและวิธีติดตั้ง
  Aspose.BarCode .NET – คู่มือขั้นตอนต่อขั้นสำหรับนักพัฒนา .NET
keywords:
- generate aztec barcode
- install aspose barcode .net
- aztec code encoding .net
- aspose barcode tutorial
linktitle: การเข้ารหัสข้อความ Aztec Code
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to generate aztec barcode with text encoding and how to install
    aspose barcode .net – step‑by‑step guide for .NET developers.
  headline: Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate aztec barcode with text encoding and how to install
    aspose barcode .net – step‑by‑step guide for .NET developers.
  name: Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET
  steps:
  - name: Define Your Directory Path
    text: Choose a folder where the barcode image will be stored. Replace **Your Directory
      Path** with an absolute or relative path on your machine.
  - name: Initialize Aztec Code Generator
    text: The `BarcodeGenerator` class is the core object that creates barcodes. `BarcodeGenerator`
      **is Aspose.BarCode's primary class for barcode creation**, handling all encoding
      options internally.
  - name: Set Barcode Parameters
    text: Here we configure the visual and encoding settings. `XDimension` defines
      pixel size per module, and `CodeTextEncoding` ensures UTF‑8 handling for international
      characters.
  - name: Save the Aztec Code Image
    text: Calling `Save` writes the barcode to the file system. The format can be
      PNG, JPEG, BMP, or TIFF – PNG is used in this example for lossless quality.
  - name: Recognize the Aztec Code
    text: '`BarCodeReader` **is the class that reads and decodes barcodes** from images
      or streams. It validates that the generated Aztec code contains the expected
      text.'
  type: HowTo
- questions:
  - answer: Up to 3 832 characters for text mode, or 2 880 bytes for binary mode,
      depending on error correction level.
    question: What is the maximum amount of data an Aztec barcode can hold?
  - answer: Yes, set the `ForeColor` and `BackColor` properties on the `BarcodeGenerator`
      before saving.
    question: Can I generate colored Aztec barcodes?
  - answer: The library can generate images up to 10 000 × 10 000 pixels; larger sizes
      may increase memory usage.
    question: Is there a limit on image size?
  - answer: Absolutely – the NuGet package targets .NET Standard 2.0, making it compatible
      with .NET 5, .NET 6, and later.
    question: Does Aspose.BarCode support .NET 6?
  - answer: 'Download the trial from [here](https://releases.aspose.com/). Community
      support and discussions are available on the Aspose Barcode forum: [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13).'
    question: Where can I get a free trial?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้าง Aztec Barcode ด้วยการเข้ารหัสข้อความโดยใช้ Aspose.BarCode สำหรับ .NET
url: /th/net/aztec-barcode-encoding/aztec-code-text-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด Aztec ด้วยการเข้ารหัสข้อความโดยใช้ Aspose.BarCode สำหรับ .NET

## บทนำ

พร้อมที่จะ **สร้างบาร์โค้ด Aztec** ด้วยการเข้ารหัสข้อความในโครงการ .NET หรือยัง? บทแนะนำนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การติดตั้งไลบรารีจนถึงการสร้างและการอ่านสัญลักษณ์ Aztec คุณจะเห็นว่าทำไม Aspose.BarCode จึงเป็นตัวเลือกอันดับต้น ๆ สำหรับนักพัฒนาที่ต้องการการสร้างบาร์โค้ด 2‑D ที่เชื่อถือได้ และคุณจะได้รับตัวอย่างโค้ดที่ใช้งานได้จริงซึ่งสามารถคัดลอกไปวางใน Visual Studio ได้ทันที มาทำให้ข้อมูลของคุณกลายเป็นภาพ Aztec ที่กะทัดรัดและสแกนได้ง่ายกันเถอะ!

## คำตอบสั้น
- **ไลบรารีใดสร้างบาร์โค้ด Aztec?** Aspose.BarCode for .NET.
- **ต้องใช้บรรทัดโค้ดกี่บรรทัด?** มีเพียงสองบรรทัดสำหรับการสร้างและหนึ่งบรรทัดสำหรับการอ่าน.
- **ต้องมีใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่ จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้งาน.
- **ฉันสามารถปรับขนาดและการเข้ารหัสได้หรือไม่?** แน่นอน – สามารถกำหนดค่า XDimension, ระดับการแก้ไขข้อผิดพลาด, และข้อความ UTF‑8 ได้.
- **รองรับ .NET Core และ .NET 6 หรือไม่?** ใช่ ไลบรารีรองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## การสร้างบาร์โค้ด Aztec คืออะไร?
**การสร้างบาร์โค้ด Aztec** หมายถึงการสร้างสัญลักษณ์เมทริกซ์สองมิติที่เก็บข้อความหรือข้อมูลไบนารีโดยใช้สัญลักษณ์ Aztec ผลลัพธ์คือภาพสี่เหลี่ยมจัตุรัสที่สามารถสแกนด้วยอุปกรณ์มือถือหรือเครื่องอ่านเฉพาะได้โดยไม่ต้องมีพื้นที่เงียบรอบ ๆ

## ทำไมต้องใช้ Aspose.BarCode สำหรับ .NET?
Aspose.BarCode รองรับ **70+ สัญลักษณ์บาร์โค้ด**, รวมถึงรหัส Aztec ขนาดสูงสุด **151 × 151 โมดูล** และสามารถเข้ารหัส **สูงสุด 3 832 ตัวอักษร** ในสัญลักษณ์เดียว ไลบรารีสามารถประมวลผลเอกสารหลายร้อยหน้าในโหมดที่ใช้หน่วยความจำน้อย หมายความว่าคุณสามารถสร้างชุดข้อมูลขนาดใหญ่ได้โดยไม่ต้องโหลดไฟล์ทั้งหมด สำหรับอ้างอิง API อย่างละเอียด ดูที่ [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **ติดตั้ง Aspose.BarCode .NET** – ดาวน์โหลดแพ็กเกจ NuGet หรือไฟล์ติดตั้ง MSI จากเว็บไซต์อย่างเป็นทางการ รายละเอียดขั้นตอนการติดตั้งอยู่ในเอกสารที่ [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/)
2. **Visual Studio** – รุ่นใดก็ได้ที่เป็นเวอร์ชันล่าสุด (2019, 2022 หรือใหม่กว่า) พร้อมการสนับสนุน .NET
3. **ความรู้พื้นฐานของ C#** – คุณควรคุ้นเคยกับการสร้างโปรเจกต์คอนโซลหรือ Windows Forms แต่โค้ดทั้งหมดมีคอมเมนต์อธิบายสำหรับผู้เริ่มต้น

## วิธีสร้างบาร์โค้ด Aztec ด้วยการเข้ารหัสข้อความ

โหลดข้อมูลของคุณ ตั้งค่าตัวสร้าง แล้วบันทึกภาพด้วยสองบรรทัดของโค้ด ขั้นแรกสร้างอินสแตนซ์ของ `BarcodeGenerator` ตั้งค่า `EncodeType` เป็น **Aztec** กำหนดข้อความ แล้วเรียก `Save` จากนั้นใช้ `BarCodeReader` เพื่อตรวจสอบสัญลักษณ์ที่สร้างขึ้น

### นำเข้า Namespaces

คำสั่ง `using` ให้คุณเข้าถึงคลาสของ Aspose.BarCode วางไว้ที่ส่วนบนของไฟล์ `.cs` ของคุณ:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

### ขั้นตอนที่ 1: กำหนดเส้นทางโฟลเดอร์ของคุณ

เลือกโฟลเดอร์ที่ภาพบาร์โค้ดจะถูกเก็บไว้ แทนที่ **Your Directory Path** ด้วยเส้นทางแบบเต็มหรือแบบสัมพันธ์บนเครื่องของคุณ

```csharp
string path = "Your Directory Path";
```

### ขั้นตอนที่ 2: เริ่มต้นตัวสร้างรหัส Aztec

คลาส `BarcodeGenerator` เป็นออบเจ็กต์หลักที่สร้างบาร์โค้ด  
`BarcodeGenerator` **เป็นคลาสหลักของ Aspose.BarCode สำหรับการสร้างบาร์โค้ด** ซึ่งจัดการตัวเลือกการเข้ารหัสทั้งหมดภายใน

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Aspose常に先を行く");
```

### ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์ของบาร์โค้ด

ที่นี่เราตั้งค่าการแสดงผลและการเข้ารหัส `XDimension` กำหนดขนาดพิกเซลต่อโมดูล, และ `CodeTextEncoding` ทำให้การจัดการ UTF‑8 สำหรับอักขระสากลเป็นไปได้

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.Aztec.CodeTextEncoding = Encoding.UTF8;
```

### ขั้นตอนที่ 4: บันทึกรูปภาพรหัส Aztec

การเรียก `Save` จะบันทึกบาร์โค้ดลงในระบบไฟล์ รูปแบบที่รองรับได้แก่ PNG, JPEG, BMP หรือ TIFF – ตัวอย่างนี้ใช้ PNG เพื่อคุณภาพที่ไม่สูญเสีย

```csharp
gen.Save($"{path}AztecCodeTextEncoding.png", BarCodeImageFormat.Png);
```

### ขั้นตอนที่ 5: ตรวจจับรหัส Aztec

`BarCodeReader` **เป็นคลาสที่อ่านและถอดรหัสบาร์โค้ด** จากภาพหรือสตรีม มันตรวจสอบว่ารหัส Aztec ที่สร้างขึ้นมีข้อความที่คาดหวังหรือไม่

```csharp
BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.Aztec);
foreach (BarCodeResult result in read.ReadBarCodes())
    Console.WriteLine("AztecCodeTextEncoding:" + result.GetCodeText(Encoding.UTF8));
```

## ปัญหาทั่วไปและวิธีแก้

- **ไม่พบภาพ** – ตรวจสอบว่าเส้นทางโฟลเดอร์ลงท้ายด้วย backslash (`\`) และแอปพลิเคชันมีสิทธิ์เขียน
- **ข้อความไม่ตรงหลังการอ่าน** – ตรวจสอบให้ `CodeTextEncoding` ตรงกับการเข้ารหัสที่ใช้ในขั้นตอนการสร้าง (แนะนำให้ใช้ UTF‑8)
- **สัญลักษณ์ Aztec ขนาดใหญ่** – เพิ่มค่า `XDimension` หรือปรับ `ErrorCorrectionLevel` เพื่อสมดุลขนาดและความอ่านได้

## คำถามที่พบบ่อย

**Q: ขนาดข้อมูลสูงสุดที่บาร์โค้ด Aztec สามารถเก็บได้คือเท่าไหร่?**  
A: สูงสุด 3 832 ตัวอักษรในโหมดข้อความ หรือ 2 880 ไบต์ในโหมดไบนารี ขึ้นอยู่กับระดับการแก้ไขข้อผิดพลาด

**Q: ฉันสามารถสร้างบาร์โค้ด Aztec สีได้หรือไม่?**  
A: ได้ โดยตั้งค่าคุณสมบัติ `ForeColor` และ `BackColor` ของ `BarcodeGenerator` ก่อนบันทึก

**Q: มีขีดจำกัดขนาดภาพหรือไม่?**  
A: ไลบรารีสามารถสร้างภาพได้สูงสุด 10 000 × 10 000 พิกเซล; ขนาดที่ใหญ่กว่านี้อาจทำให้ใช้หน่วยความจำเพิ่มขึ้น

**Q: Aspose.BarCode รองรับ .NET 6 หรือไม่?**  
A: แน่นอน – แพ็กเกจ NuGet ตั้งเป้าหมายที่ .NET Standard 2.0 ทำให้เข้ากันได้กับ .NET 5, .NET 6 และเวอร์ชันต่อไป

**Q: ฉันสามารถดาวน์โหลดรุ่นทดลองฟรีได้จากที่ไหน?**  
A: ดาวน์โหลดรุ่นทดลองได้จาก [here](https://releases.aspose.com/). การสนับสนุนจากชุมชนและการสนทนามีให้บนฟอรั่ม Aspose Barcode: [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13)

**อัปเดตล่าสุด:** 2026-05-19  
**ทดสอบกับ:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนภาพที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [การเข้ารหัส Aztec Bytes ด้วย barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [การใช้งาน Aztec Symbol Mode อย่างเชี่ยวชาญกับ Aspose.BarCode สำหรับ .NET](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}