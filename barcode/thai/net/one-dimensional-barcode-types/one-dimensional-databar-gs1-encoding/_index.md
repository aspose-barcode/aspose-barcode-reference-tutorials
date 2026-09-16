---
date: 2026-03-07
description: เรียนรู้วิธีสร้างบาร์โค้ด Databar มิติเดียวที่เข้ารหัสแบบ GS1 ใน .NET
  ด้วย Aspose.BarCode คู่มือนี้จะแสดงวิธีตั้งค่า GS1, กำหนดค่าตัวสร้างบาร์โค้ด, และสร้างบาร์โค้ดอย่างรวดเร็ว.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: สร้างการเข้ารหัส Databar มิติเดียว GS1 ด้วย Aspose.BarCode
url: /th/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง One-Dimensional Databar GS1 Encoding ด้วย Aspose.BarCode

ในบทเรียนนี้คุณจะ **สร้าง one-dimensional databar** บาร์โค้ดที่สอดคล้องกับมาตรฐาน GS1 โดยใช้ไลบรารี Aspose.BarCode สำหรับ .NET ไม่ว่าคุณจะต้องการการตรวจสอบ GS1 อย่างเคร่งครัดหรือบาร์โค้ดที่ยืดหยุ่นมากขึ้น เราจะพาคุณผ่านทุกขั้นตอน ตั้งแต่การติดตั้งไลบรารีจนถึงการจัดการข้อยกเว้นการเข้ารหัส เพื่อให้คุณสามารถสร้างบาร์โค้ดที่เชื่อถือได้ในแอปพลิเคชันของคุณ

## คำตอบด่วน
- **What does “create one-dimensional databar” mean?** หมายถึงการสร้างบาร์โค้ดเชิงเส้น (1‑D) ของตระกูล Databar ซึ่งมักใช้ในด้านการค้าปลีกและโลจิสติกส์.  
- **How do I set GS1 validation?** ตั้งค่า `IsAllowOnlyGS1Encoding` เป็น `true` บนพารามิเตอร์ `DataBar`.  
- **Do I need a license?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Where can I download the library?** จากหน้า releases อย่างเป็นทางการของ Aspose (ดูข้อกำหนดเบื้องต้น).

## “create one-dimensional databar” คืออะไร?
One‑dimensional Databar (ที่รู้จักอีกชื่อว่า RSS) เป็นบาร์โค้ดเชิงเส้นแบบกะทัดรัดที่สามารถเข้ารหัสข้อมูลตัวเลข, วันที่ หรือสตริง AI (Application Identifier) ได้ เมื่อผสานกับการเข้ารหัส GS1 บาร์โค้ดจะใช้โครงสร้างข้อมูลที่ได้รับการยอมรับทั่วโลก ทำให้เหมาะสำหรับการค้าปลีก, การดูแลสุขภาพ, และสถานการณ์ห่วงโซ่อุปทาน

## ทำไมต้องใช้ Aspose.BarCode สำหรับ .NET?
Aspose.BarCode มี API ที่ใช้งานง่าย, รองรับ GS1 อย่างเต็มรูปแบบ, และสามารถปรับแต่งทุกแง่มุมของภาพบาร์โค้ดได้อย่างละเอียด มันขจัดความไม่แน่นอนของการเข้ารหัสระดับต่ำและให้คุณมุ่งเน้นที่ตรรกะธุรกิจ

## ข้อกำหนดเบื้องต้น

1. **Aspose.BarCode for .NET** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/barcode/net/).  
2. **Your Directory Path** – แทนที่ `"Your Directory Path"` ในตัวอย่างด้วยโฟลเดอร์ที่คุณมีสิทธิ์เขียน

## การนำเข้า Namespaces

เพิ่มคำสั่ง `using` ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณ:

```csharp
using Aspose.BarCode;
using System;
```

## ขั้นตอนที่ 1: เริ่มต้น Barcode Generator

สร้างอินสแตนซ์ `BarcodeGenerator` และระบุ symbology ของ Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## ขั้นตอนที่ 2: วิธีตั้งค่า GS1 – สร้างบาร์โค้ดด้วยการตรวจสอบ GS1 อย่างเคร่งครัด

เปิดใช้งานการเข้ารหัสเฉพาะ GS1, กำหนด codetext ที่สอดคล้องกับ GS1, และบันทึกภาพ:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## ขั้นตอนที่ 3: การสร้างบาร์โค้ดด้วย Aspose – การเข้ารหัสแบบเปลี่ยนแปลง (ไม่มีการตรวจสอบ GS1)

หากคุณต้องการบาร์โค้ดที่ **ไม่** บังคับใช้กฎ GS1 ให้ปิดการตรวจสอบ:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## ขั้นตอนที่ 4: ตรวจสอบ GS1 ของ Barcode generator – การจัดการข้อยกเว้น

เมื่อ `IsAllowOnlyGS1Encoding` เป็น `true` แต่ codetext ไม่สอดคล้องกับ GS1, Aspose จะโยนข้อยกเว้น. ตัวอย่างต่อไปนี้แสดงวิธีดักจับและบันทึกข้อยกเว้น:

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

### ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **Pitfall:** การส่งสตริงที่ไม่เป็น GS1 ขณะเปิดการตรวจสอบ GS1 จะทำให้การสร้างบาร์โค้ดหยุด.  
- **Pro tip:** ตรวจสอบสตริง AI ของคุณก่อนกำหนดให้กับ `CodeText` เพื่อหลีกเลี่ยงข้อผิดพลาดขณะรันไทม์.  
- **Tip:** ใช้เส้นทางแบบ absolute หรือ `Path.Combine` เพื่อสร้างชื่อไฟล์อย่างปลอดภัยบนหลายแพลตฟอร์ม.

## สรุป

ตอนนี้คุณรู้วิธี **สร้าง one-dimensional databar** บาร์โค้ดด้วยการเข้ารหัส GS1, วิธีสลับการตรวจสอบ GS1, และวิธีจัดการข้อยกเว้นที่เกี่ยวข้อง—ทั้งหมดโดยใช้ Aspose.BarCode สำหรับ .NET. คุณสามารถสำรวจตัวเลือกการจัดรูปแบบเพิ่มเติม เช่น ขนาดบาร์โค้ด, สี, และระยะขอบผ่านอ็อบเจ็กต์ `Parameters.Barcode` ได้ตามต้องการ.

หากคุณพบปัญหาใด ๆ เอกสารอย่างเป็นทางการและฟอรั่มชุมชนเป็นแหล่งข้อมูลที่ยอดเยี่ยม:

- [เอกสาร Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [ฟอรั่มสนับสนุน Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## คำถามที่พบบ่อย

### 1. GS1 encoding ในบาร์โค้ดคืออะไร?
GS1 encoding คือวิธีมาตรฐานในการจัดโครงสร้างข้อมูล (เช่น ตัวระบุสินค้า) ภายในบาร์โค้ด เพื่อให้สามารถทำงานร่วมกันได้ระหว่างผู้ค้าปลีก, ผู้ผลิต, และผู้ให้บริการโลจิสติกส์.

### 2. ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างได้หรือไม่?
ได้. Aspose.BarCode ให้คุณปรับขนาด, สี, ระยะขอบ, และแม้กระทั่งเพิ่มข้อความที่มนุษย์อ่านได้ผ่านการตั้งค่า `Parameters.Barcode`.

### 3. ฉันจะหาแหล่งข้อมูลและเอกสารเพิ่มเติมสำหรับ Aspose.BarCode ได้จากที่ไหน?
คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่ [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). เป็นแหล่งข้อมูลที่มีคุณค่าสำหรับการเรียนรู้และแก้ปัญหา.

### 4. มีเวอร์ชันทดลองสำหรับ Aspose.BarCode หรือไม่?
มี, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.BarCode สำหรับ .NET จาก [here](https://releases.aspose.com/).

### 5. ฉันจะซื้อไลเซนส์สำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร?
เพื่อซื้อไลเซนส์สำหรับ Aspose.BarCode สำหรับ .NET, เยี่ยมชม [purchase page](https://purchase.aspose.com/buy) บนเว็บไซต์ของ Aspose.

**อัปเดตล่าสุด:** 2026-03-07  
**ทดสอบด้วย:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}