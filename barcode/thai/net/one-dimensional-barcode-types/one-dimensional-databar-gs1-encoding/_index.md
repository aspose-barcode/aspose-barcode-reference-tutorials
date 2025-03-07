---
title: การเข้ารหัส Databar GS1 หนึ่งมิติ
linktitle: การเข้ารหัส Databar GS1 หนึ่งมิติ
second_title: Aspose.BarCode .NET API
description: เรียนรู้วิธีสร้างบาร์โค้ดที่เข้ารหัส Databar GS1 ใน .NET โดยใช้ Aspose.BarCode สร้างบาร์โค้ดได้อย่างง่ายดาย ปฏิบัติตามคำแนะนำทีละขั้นตอนของเรา
weight: 18
url: /th/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเข้ารหัส Databar GS1 หนึ่งมิติ


ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างบาร์โค้ดที่เข้ารหัส Databar GS1 หนึ่งมิติโดยใช้ Aspose.BarCode สำหรับไลบรารี .NET ไม่ว่าคุณกำลังมองหาการสร้างบาร์โค้ดที่มีการเข้ารหัส GS1 หรือไม่มีก็ตาม เราก็ช่วยคุณได้ คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณเข้าใจข้อกำหนดเบื้องต้น นำเข้าเนมสเปซ และสาธิตแต่ละตัวอย่างเพื่อสร้างบาร์โค้ดที่เข้ารหัส Databar GS1 ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.BarCode สำหรับ .NET: คุณควรติดตั้ง Aspose.BarCode สำหรับ .NET หากยังไม่มีสามารถ Download ได้จาก[ที่นี่](https://releases.aspose.com/barcode/net/).

2.  เส้นทางไดเรกทอรีของคุณ: แทนที่`"Your Directory Path"` ในตัวอย่างโค้ดที่มีเส้นทางจริงที่คุณต้องการบันทึกภาพบาร์โค้ดที่สร้างขึ้น

ตอนนี้คุณมีข้อกำหนดเบื้องต้นที่จำเป็นพร้อมแล้ว เรามาดำเนินการในส่วนการเขียนโค้ดกันดีกว่า

## การนำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่เกี่ยวข้องสำหรับ Aspose.BarCode เพิ่มบรรทัดโค้ดต่อไปนี้ที่จุดเริ่มต้นของโครงการ .NET ของคุณ:

```csharp
using Aspose.BarCode;
using System;
```

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้างบาร์โค้ด

ขั้นตอนแรกคือการเริ่มต้นออบเจ็กต์ BarcodeGenerator ด้วยประเภทการเข้ารหัสที่ต้องการ ในกรณีนี้ เรากำลังใช้การเข้ารหัส Databar แบบขยาย 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## ขั้นตอนที่ 2: สร้างบาร์โค้ดด้วยการเข้ารหัส GS1

ตอนนี้ เราจะตั้งค่าข้อความโค้ดด้วยการตรวจสอบ GS1Encoding และบันทึกภาพบาร์โค้ดที่สร้างขึ้น 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## ขั้นตอนที่ 3: สร้างบาร์โค้ดเข้ารหัสตัวแปร

ในขั้นตอนนี้ เราจะสร้างบาร์โค้ดที่มีข้อความรหัสตัวแปรโดยไม่มีการตรวจสอบ GS1Encoding

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## ขั้นตอนที่ 4: จัดการข้อยกเว้นสำหรับการตรวจสอบการเข้ารหัส GS1

หากคุณพยายามสร้างบาร์โค้ดที่มีข้อความรหัสตัวแปรโดยเปิดใช้งานการตรวจสอบ GS1Encoding บาร์โค้ดจะเกิดข้อยกเว้น ต่อไปนี้คือวิธีที่คุณสามารถจัดการกับมันได้:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

ตอนนี้ คุณได้สร้างบาร์โค้ดที่เข้ารหัส Databar GS1 หนึ่งมิติด้วย Aspose.BarCode สำหรับ .NET สำเร็จแล้ว คุณสามารถสำรวจและปรับแต่งการสร้างบาร์โค้ดเพิ่มเติมได้ตามความต้องการเฉพาะของคุณ

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการสร้างบาร์โค้ดที่เข้ารหัส Databar GS1 หนึ่งมิติโดยใช้ Aspose.BarCode สำหรับ .NET เราได้กล่าวถึงข้อกำหนดเบื้องต้น นำเข้าเนมสเปซที่จำเป็น และให้คำแนะนำทีละขั้นตอนสำหรับการสร้างทั้งบาร์โค้ดที่เข้ารหัส GS1 และบาร์โค้ดเข้ารหัสตัวแปร

 ด้วย Aspose.BarCode สำหรับ .NET การสร้างบาร์โค้ดจะกลายเป็นงานที่ราบรื่น โดยให้ความยืดหยุ่นและการควบคุมความต้องการในการสร้างบาร์โค้ดของคุณ หากคุณพบปัญหาใด ๆ หรือมีคำถาม อย่าลังเลที่จะเยี่ยมชม[เอกสาร Aspose.BarCode](https://reference.aspose.com/barcode/net/) หรือขอความช่วยเหลือได้ที่[ฟอรั่มสนับสนุน Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## คำถามที่พบบ่อย

### 1. การเข้ารหัส GS1 ในบาร์โค้ดคืออะไร
การเข้ารหัส GS1 เป็นมาตรฐานที่ใช้ในบาร์โค้ดเพื่อให้แน่ใจว่ามีโครงสร้างข้อมูลและการระบุตัวตนที่เหมาะสม โดยทั่วไปจะใช้กับสินค้าในการค้าปลีก การดูแลสุขภาพ และโลจิสติกส์ เพื่ออำนวยความสะดวกในการติดตามและการแลกเปลี่ยนข้อมูลที่แม่นยำ

### 2. ฉันสามารถปรับแต่งรูปลักษณ์ของบาร์โค้ดที่สร้างขึ้นได้หรือไม่?
ได้ คุณสามารถปรับแต่งรูปลักษณ์ของบาร์โค้ดที่สร้างด้วย Aspose.BarCode สำหรับ .NET ได้ คุณสามารถควบคุมพารามิเตอร์ต่างๆ เช่น ขนาด สี และสไตล์ได้

### 3. ฉันจะหาแหล่งข้อมูลเพิ่มเติมและเอกสารประกอบของ Aspose.BarCode ได้ที่ไหน
 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่[เอกสาร Aspose.BarCode](https://reference.aspose.com/barcode/net/). เป็นทรัพยากรที่มีคุณค่าสำหรับการเรียนรู้และการแก้ไขปัญหา

### 4. Aspose.BarCode มีเวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถรับ Aspose.BarCode สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### 5. ฉันจะซื้อใบอนุญาตสำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร
 หากต้องการซื้อใบอนุญาตสำหรับ Aspose.BarCode สำหรับ .NET โปรดไปที่[หน้าซื้อ](https://purchase.aspose.com/buy) บนเว็บไซต์ Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
