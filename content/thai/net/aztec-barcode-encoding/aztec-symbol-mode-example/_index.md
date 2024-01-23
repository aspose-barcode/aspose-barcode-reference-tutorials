---
title: การเรียนรู้โหมดสัญลักษณ์ Aztec ด้วย Aspose.BarCode สำหรับ .NET
linktitle: ตัวอย่างโหมดสัญลักษณ์แอซเท็ก
second_title: Aspose.BarCode .NET API
description: สำรวจโหมดสัญลักษณ์ Aztec ใน Aspose.BarCode สำหรับ .NET และเรียนรู้วิธีสร้างบาร์โค้ดอเนกประสงค์ได้อย่างง่ายดาย ทดลองโหมด Auto, FullRange, Compact และ Rune ในบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 14
url: /th/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---
หากคุณต้องการรวมความสามารถในการสร้างบาร์โค้ดอันทรงพลังเข้ากับแอปพลิเคชัน .NET ของคุณ Aspose.BarCode สำหรับ .NET เป็นโซลูชันที่ยอดเยี่ยม ในบทช่วยสอนนี้ เราจะเจาะลึกโหมดสัญลักษณ์ Aztec และสำรวจตัวเลือกต่างๆ โดยใช้ Aspose.BarCode สำหรับ .NET เราจะครอบคลุมข้อกำหนดเบื้องต้น นำเข้าเนมสเปซ และแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้ด้านการทำงานของการพัฒนา .NET
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  สำเนาของ Aspose.BarCode สำหรับ .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/barcode/net/).

ตอนนี้คุณพร้อมแล้ว เรามาเจาะลึกตัวอย่างโหมดสัญลักษณ์ Aztec กันดีกว่า

## การนำเข้าเนมสเปซ

ขั้นแรก คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.BarCode สำหรับ .NET เปิดโครงการ Visual Studio ของคุณและเพิ่มคำสั่งต่อไปนี้โดยใช้คำสั่งที่ด้านบนของไฟล์โค้ดของคุณ:

```csharp
using Aspose.BarCode.Generation;
```

ด้วยเนมสเปซที่มีอยู่แล้ว คุณสามารถเริ่มใช้ Aspose.BarCode สำหรับ .NET ได้แล้ว

## ขั้นตอนที่ 1: การตั้งค่าเครื่องสร้างบาร์โค้ด

เริ่มต้นด้วยการเริ่มต้นเครื่องสร้างบาร์โค้ดด้วยประเภทการเข้ารหัส Aztec และระบุข้อความโค้ด ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

ในขั้นตอนนี้ เราได้ตั้งค่าตัวสร้างและระบุข้อความโค้ดสำหรับการเข้ารหัส

## ขั้นตอนที่ 2: การตั้งค่าโหมดสัญลักษณ์เป็นอัตโนมัติ

ตอนนี้ มาตั้งค่าโหมดสัญลักษณ์ Aztec เป็น "อัตโนมัติ" แล้วบันทึกภาพบาร์โค้ดเป็นไฟล์ PNG ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

ขั้นตอนนี้ช่วยให้แน่ใจว่าโหมดสัญลักษณ์ Aztec ถูกกำหนดโดยอัตโนมัติ และภาพบาร์โค้ดที่ได้จะถูกบันทึก

## ขั้นตอนที่ 3: การตั้งค่าโหมดสัญลักษณ์เป็น FullRange

หากคุณต้องการระบุโหมดสัญลักษณ์ Aztec เป็น "FullRange" คุณสามารถทำได้โดยใช้โค้ดต่อไปนี้:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

สิ่งนี้จะสร้างบาร์โค้ดด้วยโหมดสัญลักษณ์ FullRange Aztec

## ขั้นตอนที่ 4: การตั้งค่าโหมดสัญลักษณ์เป็นกระชับ

หากต้องการสร้างบาร์โค้ดโดยตั้งค่าโหมดสัญลักษณ์ Aztec เป็น "กะทัดรัด" ให้ใช้รหัสต่อไปนี้:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

ขั้นตอนนี้จะกำหนดค่าบาร์โค้ดที่จะสร้างด้วยโหมดสัญลักษณ์ Compact Aztec

## ขั้นตอนที่ 5: การตั้งค่าโหมดสัญลักษณ์เป็น Rune

สุดท้ายนี้ หากคุณต้องการใช้โหมดสัญลักษณ์ Aztec "Rune" คุณสามารถทำได้โดยตั้งค่าดังนี้:

```csharp
gen.CodeText = "123"; // เปลี่ยนข้อความโค้ดหากจำเป็น
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

ขั้นตอนนี้เปลี่ยนข้อความโค้ดเป็น "123" และสร้างบาร์โค้ดด้วยโหมดสัญลักษณ์ Rune Aztec

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจโหมดสัญลักษณ์ Aztec ใน Aspose.BarCode สำหรับ .NET เราครอบคลุมถึงการตั้งค่าเครื่องสร้างบาร์โค้ด การกำหนดค่าโหมดสัญลักษณ์ Aztec เป็นอัตโนมัติ FullRange กระชับ และ Rune และบันทึกภาพบาร์โค้ดที่สร้างขึ้น ด้วยความรู้นี้ คุณสามารถรวมการสร้างบาร์โค้ดอเนกประสงค์เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย

 หากคุณมีคำถามหรือต้องการความช่วยเหลือเพิ่มเติม อย่าลังเลที่จะติดต่อชุมชน Aspose.BarCode บน[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/barcode/13).

## คำถามที่พบบ่อย

### คำถามที่ 1: จุดประสงค์ของโหมดสัญลักษณ์ Aztec ในการสร้างบาร์โค้ดคืออะไร

ตอบ 1: โหมดสัญลักษณ์ Aztec ช่วยให้คุณสามารถระบุวิธีการเข้ารหัสสำหรับบาร์โค้ด Aztec ได้ โดยให้ความยืดหยุ่นในการสร้างบาร์โค้ด

### คำถามที่ 2: ฉันสามารถเปลี่ยนข้อความโค้ดสำหรับบาร์โค้ด Aztec ใน Aspose.BarCode สำหรับ .NET ได้หรือไม่

ตอบ 2: ได้ คุณสามารถเปลี่ยนข้อความโค้ดได้อย่างง่ายดายตามความต้องการเฉพาะของคุณเมื่อสร้างบาร์โค้ด Aztec

### คำถามที่ 3: มี Aspose.BarCode สำหรับ .NET เวอร์ชันทดลองใช้ฟรีหรือไม่

A3: ได้ คุณสามารถดาวน์โหลด Aspose.BarCode สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะหาเอกสารฉบับเต็มสำหรับ Aspose.BarCode สำหรับ .NET ได้ที่ไหน

 A4: คุณสามารถดูเอกสารประกอบฉบับสมบูรณ์สำหรับ Aspose.BarCode for .NET ได้[ที่นี่](https://reference.aspose.com/barcode/net/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร

 A5: คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้โดยไปที่[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).