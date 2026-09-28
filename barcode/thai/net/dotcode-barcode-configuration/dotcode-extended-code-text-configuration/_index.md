---
date: 2026-09-28
description: เรียนรู้วิธีสร้างบาร์โค้ดเมทริกซ์ 2d ด้วย Aspose.BarCode for .NET – คู่มือ
  step‑by‑step สำหรับการสร้างบาร์โค้ด DotCode พร้อม extended code text
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: การกำหนดค่า DotCode Extended Code Text
og_description: เรียนรู้การสร้างบาร์โค้ดเมทริกซ์ 2d ด้วย Aspose.BarCode for .NET คู่มือนี้แสดงขั้นตอน
  step‑by‑step ในการสร้างบาร์โค้ด DotCode พร้อม extended code text
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: สร้างบาร์โค้ดเมทริกซ์ 2d ด้วย Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: วิธีสร้างบาร์โค้ดเมทริกซ์ 2d ด้วย Aspose.BarCode for .NET
url: /th/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ดเมทริกซ์ 2 มิติด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

ในด้านการสร้างและจัดการบาร์โค้ด, Aspose.BarCode สำหรับ .NET โดดเด่นในฐานะโซลูชันที่หลากหลายซึ่งรองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ** และสามารถประมวลผลเอกสารหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไม่ว่าคุณจะต้องการบาร์โค้ดสำหรับการติดตามสินค้า, การควบคุมสินค้าคงคลัง, หรือแอปพลิเคชันที่มีข้อมูลจำนวนมาก การสร้าง **บาร์โค้ดเมทริกซ์ 2 มิติ** เช่น DotCode พร้อม codetext ที่ขยาย จะทำให้คุณฝังข้อมูลข้อความและข้อมูลไบนารีในสัญลักษณ์สี่เหลี่ยมที่กะทัดรัด บทเรียนนี้จะพาคุณผ่านขั้นตอนการสร้าง codetext ที่ขยายแบบทีละขั้นตอนและการแสดงผลภาพสุดท้าย

## คำตอบสั้น

- **อะไรหมายถึง “create dotcode extended codetext”**? หมายถึงการสร้างบาร์โค้ด DotCode ที่รวม FNC1, ECICodetext, plain text, และตัวคั่นสัญลักษณ์ใน payload ที่ขยายเดียว  
- **ต้องใช้ไลบรารีใด?** Aspose.BarCode for .NET.  
- **ฉันต้องการไลเซนส์หรือไม่?** ไลเซนส์ชั่วคราวทำงานสำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน.  

## วิธีสร้าง dotcode extended codetext

โหลดโปรเจกต์ของคุณ, ตั้งค่าไดเรกทอรี, สร้าง extended codetext, และสร้างภาพ – ทั้งหมดในไม่ถึงสิบสองบรรทัดของโค้ด คำตอบโดยตรงต่อไปนี้สรุปกระบวนการทั้งหมด:

โหลด `BarcodeGenerator` ด้วย `EncodeTypes.DotCode`, สร้าง extended codetext โดยใช้ `DotCodeExtendedCodetextBuilder` (เพิ่ม FNC1, ECICodetext, plain text, และตัวคั่น FNC3), จากนั้นเรียก `Save` เพื่อเขียนไฟล์ PNG ลำดับนี้สร้างบาร์โค้ดเมทริกซ์ 2 มิติที่สอดคล้องอย่างเต็มที่ในหนึ่งคำสั่ง

## dotcode extended codetext คืออะไร?

**dotcode extended codetext** คือสตริงเชิงประกอบที่รวมหลายส่วนของข้อมูล—เช่นตัวระบุ FNC1, ECICodetext, plain text, และตัวคั่น FNC3—เป็น payload เดียวที่ DotCode สามารถถอดรหัสได้ มันทำให้สามารถเข้ารหัสข้อความหลายภาษา, ไบต์ข้อมูลไบนารี, และข้อมูลโครงสร้างภายในบาร์โค้ดเมทริกซ์ 2 มิติเดียว ทำให้เหมาะสำหรับห่วงโซ่อุปทาน, การดูแลสุขภาพ, และสถานการณ์ IoT

## ทำไมต้องใช้ Aspose.BarCode สำหรับงานนี้?

Aspose.BarCode ประมวลผล **สูงสุด 500 หน้าต่อวินาที** บนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไปและรองรับ **สัญลักษณ์บาร์โค้ดกว่า 30 แบบ**, รวมถึง DotCode API `GetExtendedCodetext` ของมันรับประกันการวางตำแหน่งอักขระควบคุมที่ถูกต้อง, ขจัดข้อผิดพลาดจากการต่อสตริงด้วยมือและทำให้สอดคล้องกับ ISO/IEC 24724 นอกจากนี้ยังมีการแก้ไขข้อผิดพลาดในตัวและการจัดการ quiet‑zone อัตโนมัติ, ลดความจำเป็นในการปรับแต่งด้วยมือ

## ข้อกำหนดเบื้องต้น

- **Aspose.BarCode for .NET** – ดาวน์โหลดจาก [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- สภาพแวดล้อมการพัฒนา .NET (แนะนำ Visual Studio 2022 หรือใหม่กว่า).  
- ตัวเลือก: ไฟล์ไลเซนส์ชั่วคราวสำหรับการประเมิน.

## นำเข้า namespace

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Namespace เหล่านี้เปิดเผยคลาส `BarcodeGenerator` และตัวช่วย `DotCodeExtendedCodetextBuilder` ที่จำเป็นสำหรับตัวอย่างนี้.

```csharp
using Aspose.BarCode.Generation;
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว, เรามาแยกกระบวนการสร้าง DotCode Extended Code Text เป็นคำแนะนำทีละขั้นตอนกัน.

## ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรี

ระบุที่ที่ไฟล์ PNG ที่สร้างจะถูกบันทึก ใช้เส้นทางแบบเต็มหรือแบบสัมพันธ์ที่แอปพลิเคชันของคุณสามารถเขียนได้.

```csharp
string path = "Your Directory Path";
```

แทนที่ `"Your Directory Path"` ด้วยเส้นทางจริงบนระบบของคุณ.

## ขั้นตอนที่ 2: สร้าง dotcode extended codetext

คลาส `DotCodeExtendedCodetextBuilder` ประกอบส่วนต่าง ๆ ให้เป็นสตริง codetext ที่ขยายเป็นหนึ่งเดียว.

เพื่อสร้าง DotCode Extended Code Text, ทำตามขั้นตอนย่อยต่อไปนี้:

### 2.1 เพิ่มตัวระบุรูปแบบ fnc1

ตัวระบุรูปแบบ FNC1 ทำเครื่องหมายจุดเริ่มต้นของฟิลด์ข้อมูลใหม่ จำเป็นสำหรับสัญลักษณ์ DotCode ที่สอดคล้องกับ GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 เพิ่ม ecicodetext

ECICodetext เข้ารหัสอักขระพิเศษและข้อความระหว่างประเทศ ในตัวอย่างนี้เราจะเข้ารหัส `"犬Right狗"` ด้วย UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 เพิ่ม plain codetext

คุณสามารถเพิ่มข้อความธรรมดาไปยัง DotCode Extended Code Text ได้เช่นกัน ที่นี่เราเพิ่ม `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 เพิ่มตัวคั่นสัญลักษณ์ fnc3

ตัวคั่นสัญลักษณ์ FNC3 แยกส่วนต่าง ๆ ของโค้ด, ทำให้เครื่องสแกนอ่านได้ง่ายขึ้น.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 เพิ่มการเริ่มต้นอ่าน fnc3

ขั้นตอนนี้เพิ่มข้อมูลการเริ่มต้นอ่าน FNC3, ซึ่งบอกเครื่องสแกนวิธีการตีความข้อมูลต่อไป.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 สร้าง codetext

ตอนนี้สร้าง DotCode Extended Codetext โดยเรียกเมธอด `GetExtendedCodetext` บนวัตถุ `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## ขั้นตอนที่ 3: สร้างภาพ dotcode

เรนเดอร์ภาพบาร์โค้ดจาก extended codetext.

#### 3.1 เริ่มต้น barcode generator

คลาส `BarcodeGenerator` เป็นวัตถุหลักของ Aspose.BarCode สำหรับสร้างบาร์โค้ดใด ๆ คุณจะสร้างอินสแตนซ์โดยระบุสัญลักษณ์ที่ต้องการ (`EncodeTypes.DotCode`) และ extended codetext ที่คุณสร้างไว้

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

สุดท้ายเรียก `Save` เพื่อเขียนไฟล์ PNG ลงดิสก์ ภาพพร้อมสำหรับฝังในรายงาน, แอปมือถือ, หรือป้ายพิมพ์.

## ปัญหาทั่วไปและวิธีแก้

- **Incorrect encoding** – ตรวจสอบว่าคุณใช้ `ECIEncodings.UTF8` เมื่อต้องการเพิ่มข้อความหลายภาษา; มิฉะนั้นอักขระอาจแสดงเป็นอักษรผิด.  
- **File‑access errors** – ยืนยันว่าแอปพลิเคชันมีสิทธิ์เขียนไปยังไดเรกทอรีเป้าหมาย.  
- **Quiet zone missing** – ตั้งค่า `gen.Parameters.Barcode.Margin` หากเครื่องสแกนต้องการพื้นที่สีขาวเพิ่มเติมรอบสัญลักษณ์.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้บาร์โค้ดที่สร้างในแอปมือถือได้หรือไม่?**  
A: ใช่. ภาพ PNG ที่สร้างโดย generator สามารถฝังใน iOS, Android, หรือแอปพลิเคชันข้ามแพลตฟอร์มใดก็ได้.

**Q: ถ้าฉันต้องการเข้ารหัสข้อมูลไบนารีแทนข้อความจะทำอย่างไร?**  
A: ใช้เมธอด `AddECICodetext` พร้อม `ECIEncodings` ที่เหมาะสม (เช่น `ECIEncodings.Base64`) เพื่อฝัง payload ไบนารี.

**Q: ฉันจะปรับขนาดบาร์โค้ดโดยไม่กระทบต่อการอ่านได้อย่างไร?**  
A: ปรับคุณสมบัติ `XDimension.Pixels`; ค่าที่สูงขึ้นทำให้โมดูลใหญ่ขึ้น, ค่าที่ต่ำลงทำให้บาร์โค้ดกระชับขึ้น.

**Q: มีวิธีเพิ่ม quiet zone รอบบาร์โค้ดหรือไม่?**  
A: มี. ตั้งค่า `gen.Parameters.Barcode.Margin` เพื่อกำหนด quiet zone ที่ต้องการเป็นพิกเซล.

**Q: ไลบรารีรองรับ .NET 8 หรือไม่?**  
A: รุ่นล่าสุดของ Aspose.BarCode เข้ากันได้กับ .NET 8; เพียงอ้างอิงเวอร์ชัน NuGet package ที่เหมาะสม.

หากคุณต้องการคำแนะนำเพิ่มเติมหรือมีคำถาม, อย่าลังเลที่จะเยี่ยมชม [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) หรือเข้าร่วมกับชุมชนใน [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

---

**อัปเดตล่าสุด:** 2026-09-28  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง DotCode Barcode .NET (โหมดอัตโนมัติ) ด้วย Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [วิธีสร้าง DataMatrix Barcodes ด้วย Aspose.BarCode สำหรับ .NET – คู่มือขั้นตอนโดยละเอียด](/barcode/net/datamatrix-barcode-configuration/)
- [วิธีสร้าง Aztec barcode ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}