---
date: 2026-06-09
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode
  สำหรับ .NET คู่มือนี้แสดงวิธีสร้างบาร์โค้ดด้วย C# อย่างรวดเร็ว
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: โหมดการเข้ารหัส DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

พร้อมที่จะ **สร้างบาร์โค้ด DataMatrix** ที่ใช้การเข้ารหัส ASCII ที่มีประสิทธิภาพหรือไม่? ในบทเรียนนี้คุณจะได้เรียนรู้วิธีการสร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode สำหรับ .NET เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าโปรเจกต์จนถึงการบันทึกภาพสุดท้าย—เพื่อให้คุณสามารถเพิ่มการสร้างบาร์โค้ดในแอปพลิเคชัน C# ของคุณได้ภายในไม่กี่นาที.

## คำตอบด่วน
- **ไลบรารีที่ดีที่สุดสำหรับ DataMatrix ใน .NET คืออะไร?** Aspose.BarCode for .NET  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัด?** ประมาณ 5‑7 บรรทัดสำหรับบาร์โค้ด ASCII พื้นฐาน  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **แพลตฟอร์มที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **ฉันสามารถเปลี่ยนขนาดหรือสีได้หรือไม่?** ใช่, Aspose.BarCode เปิดเผยคุณสมบัติสำหรับขนาดและสีพื้นหน้า/พื้นหลัง  

## DataMatrix barcode คืออะไร?
DataMatrix คือบาร์โค้ดสองมิติที่เก็บข้อความและข้อมูลไบนารีในรูปแบบสี่เหลี่ยมกำลังสองที่กะทัดรัด.  
บาร์โค้ด DataMatrix เข้ารหัสข้อมูลในตารางของโมดูลสีดำและสีขาว, สามารถบรรจุอักขระอัลฟานูเมอริกได้สูงสุด 2,335 ตัวในสัญลักษณ์เดียว. มันถูกใช้กันอย่างกว้างขวางในอุตสาหกรรมการผลิต, โลจิสติกส์, และการดูแลสุขภาพ เนื่องจากสามารถพิมพ์ได้ในขนาดเล็กมากในขณะที่ยังคงสแกนได้อย่างง่ายดาย.

## วิธีสร้างบาร์โค้ด DataMatrix ในโหมด ASCII?
โหลดเนมสเปซ Aspose.BarCode, สร้างอินสแตนซ์ของ `BarcodeGenerator`, ตั้งค่า `EncodeMode` เป็น **EncodeMode.ASCII**, กำหนดสตริงข้อมูลของคุณ, แล้วเรียก `Save` เพื่อบันทึกไฟล์ภาพ วิธีนี้จะสร้างบาร์โค้ด DataMatrix ที่สอดคล้องอย่างสมบูรณ์ด้วยการเข้ารหัสเฉพาะ ASCII เพียงไม่กี่บรรทัดของโค้ด C#.

## ทำไมต้องใช้การเข้ารหัส ASCII สำหรับ DataMatrix?
โหมด ASCII เป็นการเข้ารหัสเริ่มต้นและมีประสิทธิภาพสูงสุดสำหรับข้อมูลข้อความธรรมดา, ให้ขนาดสัญลักษณ์ที่เล็กที่สุดสำหรับสตริงอัลฟานูเมอริก. มันรองรับอักขระ ASCII ทั้ง 128 ตัว, ประมวลผลข้อมูลเร็วกว่าโหมดขยาย, และรับประกันความเข้ากันได้สูงสุดกับสแกนเนอร์รุ่นเก่าที่คาดหวังสัญลักษณ์ ASCII มาตรฐาน.

## ข้อกำหนดเบื้องต้น

1. **สภาพแวดล้อมการพัฒนา** – Visual Studio, Rider หรือ IDE ที่รองรับ C# ใดก็ได้.  
2. **Aspose.BarCode for .NET** – ดาวน์โหลดแพคเกจล่าสุดจาก [here](https://releases.aspose.com/barcode/net/).  
   - เอกสาร: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - ชุมชนช่วยเหลือ: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **ความรู้พื้นฐาน C#** – ความคุ้นเคยกับโครงสร้างโปรเจกต์ .NET จะช่วยให้คุณทำตามขั้นตอนได้อย่างรวดเร็ว.  
4. **ผลิตภัณฑ์ Aspose อื่นๆ** สามารถพบได้ที่ [here](https://releases.aspose.com/).

## นำเข้า Namespaces

เพื่อเริ่มต้น, เพิ่ม `using` directives ที่จำเป็นที่ส่วนบนของไฟล์ C# ของคุณ:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Namespaces เหล่านี้ให้คุณเข้าถึงคลาส `BarcodeGenerator` และประเภทที่เกี่ยวกับภาพที่จำเป็นสำหรับการบันทึกผลลัพธ์.

## ขั้นตอนที่ 1: สร้างไดเรกทอรี

เลือกโฟลเดอร์ที่ภาพบาร์โค้ดที่สร้างขึ้นจะถูกเก็บไว้. แทนที่ `"Your Directory Path"` ด้วยพาธแบบเต็มหรือแบบสัมพันธ์ที่มีอยู่บนเครื่องของคุณ.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

โค้ดนี้จะตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่ก่อนพยายามเขียนไฟล์ใด ๆ, ป้องกันข้อผิดพลาดขณะรัน.

## ขั้นตอนที่ 2: การเข้ารหัสข้อมูลในโหมด ASCII

คลาส `BarcodeGenerator` สร้างและกำหนดค่าภาพบาร์โค้ด. ค่าตัวเลข `DataMatrixEncodeMode` ใช้เลือกอัลกอริทึมการเข้ารหัสสำหรับสัญลักษณ์ DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

หลังจากรันโค้ด, คุณจะพบไฟล์ `datamatrix_ascii.png` ในโฟลเดอร์ที่คุณระบุ. ภาพนี้มีบาร์โค้ด DataMatrix ที่เข้ารหัสสตริง `"1234567890"` ด้วยโหมด ASCII กะทัดรัด.

## ปัญหาทั่วไปและวิธีแก้

- **ข้อผิดพลาดการเข้าถึงไฟล์** – ตรวจสอบให้แน่ใจว่าแอปพลิเคชันมีสิทธิ์เขียนในโฟลเดอร์เป้าหมาย. การรัน Visual Studio ด้วยสิทธิ์ผู้ดูแลระบบสามารถแก้ปัญหาการอนุญาตบน Windows ได้.  
- **ขนาดสัญลักษณ์ไม่ถูกต้อง** – หากบาร์โค้ดแสดงผลใหญ่เกินไปหรือเล็กเกินไป, ปรับค่า `generator.Parameters.Image.Width` และ `Height` หรือให้ Aspose คำนวณขนาดที่เหมาะสมโดยไม่ระบุคุณสมบัติเหล่านั้น.  
- **อักขระที่ไม่รองรับ** – โหมด ASCII ยอมรับอักขระในช่วง 0‑127 เท่านั้น. สำหรับข้อมูล Unicode, ให้เปลี่ยนเป็น `DataMatrixEncodeMode.Base256` หรือโหมดที่เหมาะสมอื่น ๆ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้สิ่งนี้ในแอปพลิเคชันเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, จำเป็นต้องมีไลเซนส์ Aspose ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีสำหรับการประเมินผล.

**Q: ไลบรารีทำงานกับ .NET Core หรือไม่?**  
A: แน่นอน – Aspose.BarCode รองรับ .NET Core 3.1+, .NET 5, .NET 6 และเวอร์ชันต่อ ๆ ไปอย่างเต็มที่.

**Q: ฉันสามารถเข้ารหัสอักขระได้กี่ตัวในโหมด ASCII?**  
A: สูงสุด 2,335 อักขระอัลฟานูเมอริก สามารถใส่ในสัญลักษณ์ DataMatrix เดียวเมื่อใช้การเข้ารหัส ASCII.

**Q: ฉันสามารถเปลี่ยนสีพื้นหน้า หรือสีพื้นหลังของบาร์โค้ดได้หรือไม่?**  
A: ใช่, ปรับ `generator.Parameters.Image.ForeColor` และ `BackColor` ให้เป็นค่า `System.Drawing.Color` ใดก็ได้.

**Q: ฉันจะหา ตัวอย่างขั้นสูงเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารอย่างเป็นทางการมีตัวอย่างหลายสิบตัวอย่างที่ครอบคลุมขนาดที่กำหนดเอง, สี, และระดับการแก้ไขข้อผิดพลาด.

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ Aspose.BarCode สำหรับ .NET กับภาษาโปรแกรมอื่น ๆ นอกจาก C# ได้หรือไม่?
A1: Aspose.BarCode รองรับหลายภาษาโปรแกรม, แต่บทเรียนนี้เน้นที่ C#.

### Q2: โหมดการเข้ารหัสที่แตกต่างกันในบาร์โค้ด DataMatrix มีอะไรบ้าง?
A2: บาร์โค้ด DataMatrix รองรับโหมดการเข้ารหัสหลายแบบ, รวมถึง ASCII, C40, Text, และ Base256. แต่ละโหมดเหมาะกับประเภทข้อมูลที่แตกต่างกัน.

### Q3: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างขึ้น เช่น ขนาดและสีได้หรือไม่?
A3: ใช่, Aspose.BarCode มีพารามิเตอร์หลากหลายสำหรับการปรับแต่งลักษณะของบาร์โค้ด, รวมถึงขนาด, สี, และอื่น ๆ.

### Q4: มีเวอร์ชันทดลองฟรีของ Aspose.BarCode สำหรับ .NET หรือไม่?
A4: ใช่, คุณสามารถสำรวจ Aspose.BarCode สำหรับ .NET ด้วยรุ่นทดลองฟรีจาก [here](https://releases.aspose.com/).

### Q5: ฉันสามารถซื้อไลเซนส์สำหรับ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?
A5: คุณสามารถซื้อไลเซนส์ได้จากเว็บไซต์ Aspose [here](https://purchase.aspose.com/buy).

---

**อัปเดตล่าสุด:** 2026-06-09  
**ทดสอบด้วย:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [การเข้ารหัส DataMatrix เป็นไบต์ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [อ่านบาร์โค้ด DataMatrix C# – สร้างโหมด DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}