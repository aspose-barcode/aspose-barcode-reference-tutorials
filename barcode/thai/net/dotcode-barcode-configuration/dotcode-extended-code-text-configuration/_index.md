---
title: การกำหนดค่าข้อความโค้ดขยาย DotCode ด้วย Aspose.BarCode สำหรับ .NET
linktitle: การกำหนดค่าข้อความโค้ดขยาย DotCode
second_title: Aspose.BarCode .NET API
description: สร้างการกำหนดค่าข้อความโค้ดขยาย DotCode ได้อย่างง่ายดายโดยใช้ Aspose.BarCode สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อสร้างบาร์โค้ดที่มีประสิทธิภาพ
weight: 13
url: /th/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่าข้อความโค้ดขยาย DotCode ด้วย Aspose.BarCode สำหรับ .NET

## การแนะนำ

ในขอบเขตของการสร้างและการจัดการบาร์โค้ด Aspose.BarCode สำหรับ .NET มีความโดดเด่นในฐานะโซลูชันที่หลากหลายและมีประสิทธิภาพ ไม่ว่าคุณจะต้องการสร้างบาร์โค้ดสำหรับผลิตภัณฑ์ สินค้าคงคลัง หรือแอปพลิเคชันอื่นๆ Aspose.BarCode สำหรับ .NET ก็พร้อมช่วยคุณ ในบทช่วยสอนที่ครอบคลุมนี้ เราจะเน้นที่การสร้างการกำหนดค่าข้อความ DotCode Extended Code โดยใช้ Aspose.BarCode สำหรับ .NET DotCode เป็นบาร์โค้ดเมทริกซ์สองมิติที่สามารถเข้ารหัสทั้งข้อมูลที่เป็นข้อความและข้อมูลไบนารี ทำให้เป็นเครื่องมือที่มีคุณค่าในอุตสาหกรรมต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกคำแนะนำทีละขั้นตอน มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมีเพื่อปฏิบัติตามอย่างมีประสิทธิภาพ:

1.  Aspose.BarCode สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและพร้อมใช้งานไลบรารี Aspose.BarCode สำหรับ .NET ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[Aspose.BarCode สำหรับเอกสาร .NET](https://reference.aspose.com/barcode/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ โดยเฉพาะ Visual Studio ติดตั้งอยู่ในระบบของคุณ

ด้วยข้อกำหนดเบื้องต้นเหล่านี้ตามลำดับ ตอนนี้เราสามารถดำเนินการสร้างการกำหนดค่าข้อความ DotCode Extended Code ต่อไปได้

## นำเข้าเนมสเปซ

ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ .NET ของคุณเพื่อเข้าถึงฟังก์ชันที่จำเป็นจากไลบรารี Aspose.BarCode ต่อไปนี้คือวิธีที่คุณสามารถทำได้:


```csharp
using Aspose.BarCode.Generation;
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว เรามาแจกแจงกระบวนการสร้างการกำหนดค่าข้อความ DotCode Extended Code ให้เป็นคำแนะนำทีละขั้นตอนกัน



## ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรี

ในขั้นตอนนี้ คุณจะต้องระบุเส้นทางไดเร็กทอรีที่คุณต้องการบันทึกรูปภาพข้อความ DotCode Extended Code ที่สร้างขึ้น

```csharp
string path = "Your Directory Path";
```

 แทนที่`"Your Directory Path"` ด้วยเส้นทางจริงในระบบของคุณ

## ขั้นตอนที่ 2: สร้างข้อความโค้ดขยาย DotCode

เมื่อต้องการสร้างข้อความโค้ดขยาย DotCode ให้ทำตามขั้นตอนย่อยเหล่านี้:

### 2.1 เพิ่มตัวระบุรูปแบบ FNC1

ตัวระบุรูปแบบ FNC1 ใช้เพื่อระบุจุดเริ่มต้นของเขตข้อมูลใหม่ เป็นส่วนสำคัญของ DotCode Extended Code Text

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 เพิ่ม ECICodetext

ECICodetext เป็นที่ที่คุณสามารถเข้ารหัสอักขระพิเศษและข้อความสากลได้ ในตัวอย่างนี้ เราได้เข้ารหัส "犬Right狗" โดยใช้การเข้ารหัส UTF-8

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 เพิ่มข้อความธรรมดา

คุณยังสามารถเพิ่มข้อความธรรมดาลงใน DotCode Extended Code Text ได้ ที่นี่เราได้เพิ่ม "ข้อความธรรมดา"

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 เพิ่มตัวแยกสัญลักษณ์ FNC3

ตัวแยกสัญลักษณ์ FNC3 ใช้เพื่อแยกส่วนต่างๆ ของโค้ด

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 เพิ่มการเริ่มต้นเครื่องอ่าน FNC3

ขั้นตอนนี้จะเพิ่มข้อมูลการเริ่มต้น FNC3 Reader

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 สร้างข้อความรหัส

 ตอนนี้ให้สร้าง DotCode Extended Codetext โดยการเรียกไฟล์`GetExtendedCodetext` วิธีการบน`textBuilder` วัตถุ.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## ขั้นตอนที่ 3: สร้างภาพ DotCode

เมื่อต้องการสร้างข้อความโค้ดขยาย DotCode เป็นรูปภาพ ให้ทำตามขั้นตอนย่อยเหล่านี้:

#### 4.1 เริ่มต้นตัวสร้างบาร์โค้ด

 เริ่มต้น`BarcodeGenerator` ด้วยพารามิเตอร์ที่เหมาะสม ในกรณีนี้เราใช้`EncodeTypes.DotCode` และข้อความโค้ดที่สร้างขึ้น

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // ตั้งค่ามิติ X สำหรับบาร์โค้ด (ปรับเปลี่ยนตามความจำเป็น)
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // ตั้งค่าโหมดการเข้ารหัส DotCode เป็น ExtendedCodetext
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    //บันทึกภาพบาร์โค้ดที่สร้างขึ้น
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

แค่นั้นแหละ! คุณได้สร้าง DotCode Extended Code Text โดยใช้ Aspose.BarCode สำหรับ .NET สำเร็จแล้ว

## บทสรุป

Aspose.BarCode สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ทำให้การสร้างบาร์โค้ดง่ายขึ้น ในบทช่วยสอนนี้ เรามุ่งเน้นไปที่การสร้าง DotCode Extended Code Text ซึ่งจำเป็นในอุตสาหกรรมต่างๆ โดยเฉพาะอย่างยิ่งในกรณีที่ต้องมีการเข้ารหัสอักขระหลายภาษาและเฉพาะทาง ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถสร้าง DotCode Extended Code Text ตามความต้องการเฉพาะของคุณได้อย่างง่ายดาย

 หากคุณต้องการคำแนะนำเพิ่มเติมหรือมีคำถาม อย่าลังเลที่จะเยี่ยมชม[Aspose.BarCode สำหรับเอกสาร .NET](https://reference.aspose.com/barcode/net/) หรือมีส่วนร่วมกับชุมชนบน[ฟอรั่มสนับสนุน Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## คำถามที่พบบ่อย

### คำถามที่ 1: DotCode ใช้ทำอะไร

คำตอบ 1: DotCode ใช้สำหรับการเข้ารหัสทั้งข้อมูลที่เป็นข้อความและข้อมูลไบนารี และมักใช้ในอุตสาหกรรมต่างๆ เช่น การดูแลสุขภาพและโลจิสติกส์ เพื่อวัตถุประสงค์ในการติดตามและการเข้ารหัสข้อมูล

### คำถามที่ 2: ฉันสามารถปรับแต่งรูปลักษณ์ของบาร์โค้ด DotCode ได้หรือไม่

ตอบ 2: ใช่ Aspose.BarCode สำหรับ .NET มีตัวเลือกในการปรับแต่งรูปลักษณ์ของบาร์โค้ด DotCode รวมถึงขนาดและโหมดการเข้ารหัส

### คำถามที่ 3: Aspose.BarCode สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ หรือไม่

A3: ใช่ Aspose.BarCode สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ที่หลากหลาย ทำให้มั่นใจได้ถึงความยืดหยุ่นและความสะดวกในการบูรณาการ

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[เว็บไซต์ของ Aspose](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินและทดสอบ

### คำถามที่ 5: Aspose.BarCode สำหรับ .NET เหมาะสำหรับการสร้างบาร์โค้ดระดับองค์กรหรือไม่

A5: แน่นอนว่า Aspose.BarCode สำหรับ .NET ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของการสร้างบาร์โค้ดทั้งขนาดเล็กและระดับองค์กร โดยให้ความสามารถในการปรับขนาดและความน่าเชื่อถือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
