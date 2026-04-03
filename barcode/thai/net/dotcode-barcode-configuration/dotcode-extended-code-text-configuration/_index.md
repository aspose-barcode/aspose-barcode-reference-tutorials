---
date: 2026-01-27
description: เรียนรู้วิธีสร้างข้อความโค้ดขยายของ DotCode ด้วย Aspose.BarCode สำหรับ
  .NET – คู่มือขั้นตอนต่อขั้นตอนสำหรับการสร้างบาร์โค้ด DotCode พร้อมข้อความโค้ดขยาย
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: วิธีสร้างข้อความโค้ดขยายของ DotCode ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง dotcode extended codetext ด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

ในโลกของการสร้างและจัดการบาร์โค้ด Aspose.BarCode สำหรับ .NET โดดเด่นในฐานะโซลูชันที่หลากหลายและมีประสิทธิภาพ ไม่ว่าคุณจะต้องการสร้างบาร์โค้ดสำหรับสินค้า, คลังสินค้า หรือแอปพลิเคชันอื่น ๆ Aspose.BarCode สำหรับ .NET มีทุกอย่างให้คุณ ในบทเรียนฉบับนี้ เราจะ **สร้าง dotcode extended codetext** และสำรวจว่าความสามารถนี้สำคัญต่อสภาพแวดล้อมที่มีข้อมูลอุดมสมบูรณ์ในยุคปัจจุบันอย่างไร DotCode เป็นบาร์โค้ดเมทริกซ์สองมิติที่สามารถเข้ารหัสข้อมูลข้อความและไบนารีได้ ทำให้เป็นเครื่องมือที่มีคุณค่าในหลายอุตสาหกรรม

## คำตอบสั้น

- **What does “create dotcode extended codetext” mean?** หมายความว่าเป็นการสร้างบาร์โค้ด DotCode ที่รวม FNC1, ECICodetext, plain text และสัญลักษณ์ตัวคั่นไว้ใน payload ที่ขยายเดียวกัน  
- **Which library is required?** Aspose.BarCode for .NET.  
- **Do I need a license?** ต้องการไลเซนส์ชั่วคราวสำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **How long does implementation take?** ใช้เวลาประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน  

## วิธีสร้าง dotcode extended codetext

ด้านล่างเป็นขั้นตอนสั้น ๆ ที่แสดงอย่างชัดเจนว่าการสร้าง extended code text และการเรนเดอร์ภาพบาร์โค้ดทำอย่างไร

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในคู่มือแบบขั้นตอน มีข้อกำหนดบางอย่างที่คุณต้องเตรียมไว้เพื่อให้ทำตามได้อย่างมีประสิทธิภาพ:

1. Aspose.BarCode for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.BarCode for .NET แล้วพร้อมใช้งาน หากยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

2. Development Environment: คุณควรมีสภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ เช่น Visual Studio ติดตั้งอยู่บนระบบของคุณ

เมื่อข้อกำหนดเหล่านี้พร้อม เราสามารถดำเนินการสร้าง DotCode Extended Code Text ได้ต่อ

## นำเข้า Namespaces

ก่อนอื่นคุณต้องนำเข้า namespaces ที่จำเป็นในโปรเจกต์ .NET ของคุณเพื่อเข้าถึงฟังก์ชันที่ต้องการจากไลบรารี Aspose.BarCode วิธีทำดังนี้:

```csharp
using Aspose.BarCode.Generation;
```

ตอนนี้เรามีข้อกำหนดครบแล้ว ให้เราลงรายละเอียดกระบวนการสร้าง DotCode Extended Code Text ทีละขั้นตอน

## ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรี

ในขั้นตอนนี้คุณต้องระบุเส้นทางไดเรกทอรีที่ต้องการบันทึกรูปภาพ DotCode Extended Code Text ที่สร้างขึ้น

```csharp
string path = "Your Directory Path";
```

แทนที่ `"Your Directory Path"` ด้วยเส้นทางจริงบนระบบของคุณ

## ขั้นตอนที่ 2: สร้าง DotCode Extended Code Text

เพื่อสร้าง DotCode Extended Code Text ให้ทำตามขั้นตอนย่อยต่อไปนี้:

### 2.1 เพิ่ม FNC1 Format Identifier

FNC1 Format Identifier ใช้เพื่อระบุจุดเริ่มต้นของฟิลด์ข้อมูลใหม่ เป็นส่วนสำคัญของ DotCode Extended Code Text

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 เพิ่ม ECICodetext

ECICodetext คือที่คุณสามารถเข้ารหัสอักขระพิเศษและข้อความสากล ในตัวอย่างนี้เราได้เข้ารหัส `"犬Right狗"` ด้วยการเข้ารหัส UTF‑8

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 เพิ่ม Plain Codetext

คุณยังสามารถเพิ่มข้อความธรรมดาไปยัง DotCode Extended Code Text ได้ ที่นี้เราได้เพิ่ม `"Plain text"`

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 เพิ่ม FNC3 Symbol Separator

FNC3 Symbol Separator ใช้เพื่อแยกส่วนต่าง ๆ ของโค้ด

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 เพิ่ม FNC3 Reader Initialization

ขั้นตอนนี้จะเพิ่มข้อมูลการเริ่มต้นอ่าน FNC3

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 สร้าง Codetext

ตอนนี้ให้สร้าง DotCode Extended Codetext โดยเรียกเมธอด `GetExtendedCodetext` บนวัตถุ `textBuilder`

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## ขั้นตอนที่ 3: สร้างภาพ DotCode

เพื่อสร้าง DotCode Extended Code Text เป็นภาพ ให้ทำตามขั้นตอนย่อยต่อไปนี้:

#### 4.1 เริ่มต้น Barcode Generator

เริ่มต้น `BarcodeGenerator` ด้วยพารามิเตอร์ที่เหมาะสม ในกรณีนี้เราใช้ `EncodeTypes.DotCode` และ codetext ที่สร้างขึ้น

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

และเรียบร้อย! คุณได้สร้าง DotCode Extended Code Text ด้วย Aspose.BarCode สำหรับ .NET อย่างสำเร็จ

## สรุป

Aspose.BarCode สำหรับ .NET เป็นเครื่องมือที่ทรงพลังที่ทำให้การสร้างบาร์โค้ดง่ายขึ้น ในบทเรียนนี้ เราเน้นวิธี **สร้าง dotcode extended codetext** ซึ่งจำเป็นในหลายอุตสาหกรรม โดยเฉพาะเมื่อจำเป็นต้องเข้ารหัสหลายภาษาหรืออักขระพิเศษตามความต้องการของคุณ

หากต้องการคำแนะนำเพิ่มเติมหรือมีคำถาม อย่าลังเลที่จะเยี่ยมชม [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) หรือเข้าร่วมชุมชนใน [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## คำถามที่พบบ่อย

### Q1: DotCode ใช้ทำอะไร?

A1: DotCode ใช้สำหรับเข้ารหัสข้อมูลทั้งข้อความและไบนารี และมักนำไปใช้ในอุตสาหกรรมเช่น การดูแลสุขภาพและโลจิสติกส์เพื่อการติดตามและการเข้ารหัสข้อมูล

### Q2: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ด DotCode ได้หรือไม่?

A2: ได้, Aspose.BarCode สำหรับ .NET มีตัวเลือกให้ปรับแต่งลักษณะของบาร์โค้ด DotCode รวมถึงขนาดและโหมดการเข้ารหัส

### Q3: Aspose.BarCode for .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่าง ๆ หรือไม่?

A3: ได้, Aspose.BarCode for .NET รองรับเฟรมเวิร์ก .NET ช่วงกว้าง ทำให้ยืดหยุ่นและง่ายต่อการรวมเข้ากับระบบ

### Q4: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.BarCode for .NET ได้อย่างไร?

A4: คุณสามารถขอรับไลเซนส์ชั่วคราวจาก [Aspose's website](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินและทดสอบ

### Q5: Aspose.BarCode for .NET เหมาะสำหรับการสร้างบาร์โค้ดระดับองค์กรหรือไม่?

A5: แน่นอน, Aspose.BarCode for .NET ถูกออกแบบมาเพื่อรองรับความต้องการทั้งในระดับเล็กและระดับองค์กร พร้อมความสามารถในการขยายและความน่าเชื่อถือ

## คำถามที่พบบ่อย

**Q: สามารถใช้บาร์โค้ดที่สร้างขึ้นในแอปมือถือได้หรือไม่?**  
A: ได้. ภาพ PNG ที่สร้างโดยตัวสร้างสามารถฝังลงใน iOS, Android หรือแอปพลิเคชันข้ามแพลตฟอร์มอื่น ๆ

**Q: หากต้องการเข้ารหัสข้อมูลไบนารีแทนข้อความจะทำอย่างไร?**  
A: ใช้เมธอด `AddECICodetext` พร้อม `ECIEncodings` ที่เหมาะสม (เช่น `ECIEncodings.Base64`) เพื่อฝังข้อมูลไบนารี

**Q: จะปรับขนาดบาร์โค้ดโดยไม่กระทบต่อความอ่านได้อย่างไร?**  
A: ปรับคุณสมบัติ `XDimension.Pixels`; ค่าที่สูงขึ้นจะเพิ่มขนาดโมดูล ส่วนค่าที่ต่ำลงจะทำให้บาร์โค้ดกระชับขึ้น

**Q: มีวิธีเพิ่ม quiet zone รอบบาร์โค้ดหรือไม่?**  
A: มี. ตั้งค่า `gen.Parameters.Barcode.Margin` เพื่อกำหนด quiet zone ที่ต้องการเป็นพิกเซล

**Q: ไลบรารีรองรับ .NET 8 หรือไม่?**  
A: รุ่นล่าสุดของ Aspose.BarCode รองรับ .NET 8; เพียงอ้างอิงเวอร์ชัน NuGet ที่เหมาะสม

---

**อัปเดตล่าสุด:** 2026-01-27  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}