---
date: 2026-06-09
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix และบันทึกเป็น PNG ด้วยการเข้ารหัส
  C40 โดยใช้ Aspose.BarCode – คู่มือเต็มสำหรับการสร้างบาร์โค้ดใน .NET Core
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: โหมดการเข้ารหัส DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: วิธีสร้าง DataMatrix PNG ด้วย C40 โดยใช้ Aspose.BarCode
url: /th/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# โหมดการเข้ารหัส Master DataMatrix (C40) ด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้าง datamatrix** บาร์โค้ดและบันทึกเป็นไฟล์ PNG โดยใช้โหมดการเข้ารหัส C40 กับ Aspose.BarCode สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างระบบสินค้าคงคลัง, ตัวสร้างป้ายจัดส่ง, หรือโซลูชันใด ๆ ที่ต้องการสัญลักษณ์ที่กะทัดรัดและความหนาแน่นสูง การเชี่ยวชาญ C40 จะทำให้สัญลักษณ์ของคุณเล็กลงโดยไม่สูญเสียความอ่านได้ เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการสร้างไฟล์ PNG สุดท้าย—เพื่อให้คุณสามารถนำโค้ดไปใช้ในโครงการของคุณได้ทันที

## คำตอบอย่างรวดเร็ว
- **“how to generate datamatrix” หมายถึงอะไร?** การสร้างภาพบาร์โค้ด DataMatrix ด้วยโปรแกรม  
- **โหมดการเข้ารหัสใดที่ครอบคลุม?** DataMatrix C40, โหมดอักษร-ตัวเลขที่มีประสิทธิภาพ  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการผลิต  
- **ฉันสามารถรันบน .NET Core ได้หรือไม่?** ได้, Aspose.BarCode รองรับ .NET Core, .NET 5, .NET 6 และรุ่นต่อไปอย่างเต็มที่  
- **รูปแบบไฟล์ที่สร้างคืออะไร?** PNG – รูปแบบภาพที่ไม่มีการสูญเสียคุณภาพและเป็นมิตรกับเว็บ  

## วิธีสร้าง DataMatrix ด้วยการเข้ารหัส C40

โหลดข้อมูลของคุณ, กำหนดค่าตัวสร้าง, และเรียก `Save` – นั่นคือขั้นตอนทำงานครบถ้วนในสามขั้นตอนสั้น ๆ คลาส `BarcodeGenerator` จะจัดการการสร้างสัญลักษณ์, ขณะที่ enum `BarCodeImageFormat.Png` บอก Aspose.BarCode ให้เขียนผลลัพธ์เป็นไฟล์ PNG `Save` จะเขียนภาพบาร์โค้ดที่สร้างลงในเส้นทางไฟล์ที่ระบุในรูปแบบที่เลือก ย่อหน้าตอบโดยตรงนี้ให้คุณเห็นวิธีแก้ปัญหาแบบต้นถึงปลายก่อนที่เราจะเจาะลึกแต่ละบรรทัดของโค้ด

## DataMatrix Encoding Mode (C40) คืออะไร?

`DataMatrixEncodeMode` เป็น enumeration ที่ระบุว่า Aspose.BarCode ควรใช้โหมดการเข้ารหัสใดสำหรับสัญลักษณ์ DataMatrix ตัวเลือก `DataMatrixEncodeMode.C40` จะเลือกการเข้ารหัสอักษร-ตัวเลข C40 ซึ่งบรรจุตัวอักษร, ตัวเลข, และเครื่องหมายวรรคตอนบางส่วนลงในโมดูลน้อยลง, ลดขนาดสัญลักษณ์โดยยังคงความอ่านได้สำหรับข้อความสินค้าทั่วไป โครงสร้างที่มีประสิทธิภาพนี้เหมาะเมื่อคุณต้องการเข้ารหัสข้อมูลอักษร-ตัวเลขในรูปแบบกะทัดรัด

## ทำไมต้องใช้ Aspose.BarCode สำหรับ .NET?

Aspose.BarCode มี **พารามิเตอร์ที่กำหนดค่าได้กว่า 30 รายการ** สำหรับมิติ, ระดับการแก้ไขข้อผิดพลาด, และโหมดการเข้ารหัส, และรองรับ **รูปแบบภาพและบาร์โค้ดกว่า 50 รูปแบบ** ไลบรารีทำงานบน **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, ให้การสร้างบาร์โค้ดที่ไม่มีการพึ่งพาอื่น ๆ ทำงานบนเซิร์ฟเวอร์, เดสก์ท็อป, และอุปกรณ์มือถือได้เช่นกัน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, Rider หรือ IDE ใด ๆ ที่รองรับ C#  
2. **Aspose.BarCode สำหรับ .NET** – ติดตั้งผ่าน NuGet หรือโปรแกรมติดตั้งอย่างเป็นทางการ ดูรายละเอียดใน [documentation](https://reference.aspose.com/barcode/net/)  
3. **ความรู้พื้นฐาน C#** – คุณควรคุ้นเคยกับ namespace, class, และ using statements  
4. **โฟลเดอร์ที่มีสิทธิ์เขียน** – ไดเรกทอรีบนเครื่องของคุณที่ PNG จะถูกบันทึกลงไป  

## การนำเข้า Namespace ที่จำเป็น

คลาส `BarcodeGenerator` เป็นจุดเริ่มต้นสำหรับการสร้างบาร์โค้ดใด ๆ เพิ่ม namespace ที่จำเป็นที่ส่วนบนของไฟล์ C# ของคุณเพื่อให้เข้าถึง API การสร้างได้:

```csharp
using Aspose.BarCode.Generation;
```

## การสร้างบาร์โค้ดแบบขั้นตอนต่อขั้นตอน

ด้านล่างเป็น **ขั้นตอนการสร้างบาร์โค้ด** อย่างละเอียด แต่ละขั้นตอนอธิบายด้วยภาษาง่าย ๆ และ placeholder ดั้งเดิมจะคงไว้เพื่อความสะดวกในการคัดลอก‑วาง

### ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรี
ตั้งค่าโฟลเดอร์ที่ภาพ PNG จะถูกเก็บไว้ แทนที่ placeholder ด้วยเส้นทางจริงบนเครื่องของคุณ

```csharp
string path = "Your Directory Path";
```

### ขั้นตอนที่ 2: ตั้งค่าการสร้างบาร์โค้ด
สร้างอินสแตนซ์ `BarcodeGenerator`, ระบุ `EncodeTypes.DataMatrix`, และใส่ข้อมูลที่ต้องการเข้ารหัส

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### ขั้นตอนที่ 3: ปรับแต่งบาร์โค้ด
กำหนด X‑dimension (ความกว้างพิกเซลของโมดูล) และสลับโหมดการเข้ารหัสเป็น C40

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด
สุดท้ายบันทึกบาร์โค้ดที่สร้างเป็นไฟล์ PNG นี่คือคำตอบที่ชัดเจนสำหรับ **วิธีบันทึก png** ด้วย Aspose.BarCode

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

เมื่อคุณรันโปรแกรม, คุณจะพบไฟล์ `DataMatrixEncodeModeC40.png` ในโฟลเดอร์ที่ระบุ, พร้อมใช้งานในรายงาน, ป้าย, หรือหน้าเว็บ

## ปัญหาที่พบบ่อยและเคล็ดลับ

- **เส้นทางไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน; หากไม่ `gen.Save` จะโยนข้อยกเว้น  
- **โหมดการเข้ารหัสไม่ถูกต้อง** – หากต้องเข้ารหัสอักขระที่อยู่นอกชุด C40, ให้สลับเป็น `DataMatrixEncodeMode.Auto` หรือโหมดอื่นที่เหมาะสม  
- **ขนาดภาพ** – ปรับ `XDimension.Pixels` เพื่อเพิ่มหรือลดขนาดบาร์โค้ดโดยไม่กระทบต่อความอ่านได้  

## คำถามที่พบบ่อย

**Q: DataMatrix Encoding Mode (C40) คืออะไร?**  
A: C40 เป็นโครงสร้างการเข้ารหัสอักษร-ตัวเลขที่กะทัดรัดสำหรับสัญลักษณ์ DataMatrix, เหมาะสำหรับข้อความที่ประกอบด้วยตัวอักษร, ตัวเลข, และชุดอักขระพิเศษจำกัด

**Q: จะหาเอกสาร Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถดูเอกสารได้ที่ [here](https://reference.aspose.com/barcode/net/)

**Q: Aspose.BarCode สำหรับ .NET รองรับทุกเวอร์ชันของ .NET หรือไม่?**  
A: รองรับ, ไลบรารีสนับสนุนช่วงเวอร์ชัน .NET ที่กว้าง, ตั้งแต่ .NET Framework 4.5+ ถึง .NET 6 และรุ่นต่อไป

**Q: สามารถทดลองใช้ Aspose.BarCode สำหรับ .NET ก่อนซื้อได้หรือไม่?**  
A: ได้, คุณสามารถสำรวจเวอร์ชันทดลองฟรีของ Aspose.BarCode สำหรับ .NET ได้โดยเยี่ยมชม [this link](https://releases.aspose.com/)

**Q: จะหาการสนับสนุนสำหรับ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถพบชุมชนที่ให้การสนับสนุนและเข้าถึงการช่วยเหลือสำหรับ Aspose.BarCode สำหรับ .NET ได้ที่ [Aspose forum](https://forum.aspose.com/c/barcode/13)

## สรุป

โดยทำตาม **ขั้นตอนการสร้างบาร์โค้ด** นี้, คุณจะรู้วิธี **สร้าง datamatrix** บาร์โค้ดและบันทึกเป็นไฟล์ PNG ด้วยโหมดการเข้ารหัส C40 บน Aspose.BarCode สำหรับ .NET วิธีนี้ให้คุณควบคุมลักษณะ, ขนาด, และการแสดงผลข้อมูลของบาร์โค้ดได้เต็มที่, ทำให้การฝังบาร์โค้ดคุณภาพสูงลงในแอปพลิเคชัน .NET ใด ๆ เป็นเรื่องง่าย

---

**อัปเดตล่าสุด:** 2026-06-09  
**ทดสอบด้วย:** Aspose.BarCode 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [DataMatrix Encoding in Bytes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}