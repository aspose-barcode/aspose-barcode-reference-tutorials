---
date: 2026-01-17
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ด้วยอักขระแมโครโดยใช้ Aspose.BarCode
  สำหรับ .NET และค้นพบวิธีใช้ DataMatrix ในแอปพลิเคชันของคุณ
linktitle: DataMatrix Macro Configuration
second_title: Aspose.BarCode .NET API
title: วิธีสร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่า Macro DataMatrix Master ด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

ในแอปพลิเคชัน .NET สมัยใหม่ การ **สร้างบาร์โค้ด DataMatrix** เป็นวิธีที่เชื่อถือได้ในการเข้ารหัสข้อมูลจำนวนมากในพื้นที่จำกัด บทแนะนำนี้จะพาคุณผ่านขั้นตอนการ **สร้างบาร์โค้ด DataMatrix** พร้อมอักขระ macro, อธิบาย *วิธีใช้ DataMatrix* อย่างมีประสิทธิภาพ, และแสดงวิธีตรวจสอบผลลัพธ์ด้วย Aspose.BarCode สำหรับ .NET. เมื่อเสร็จสิ้นคุณจะสามารถสร้าง, ปรับแต่ง, และอ่านบาร์โค้ด DataMatrix ได้อย่างมั่นใจ

## คำตอบสั้น ๆ
- **ไลบรารีหลักคืออะไร?** Aspose.BarCode สำหรับ .NET  
- **ฉันสามารถสร้างบาร์โค้ด DataMatrix พร้อมอักขระ macro ได้หรือไม่?** ได้, ใช้คุณสมบัติ `MacroCharacters`  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ต้องมีลิขสิทธิ์ Aspose ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **มีรุ่นทดลองฟรีหรือไม่?** มี – ดาวน์โหลดได้จากเว็บไซต์ทางการของ Aspose

## ข้อกำหนดเบื้องต้น

ก่อนจะเริ่มตั้งค่า macro, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

1. **Visual Studio** – รุ่นใดก็ได้ที่ทันสมัย  
2. **Aspose.BarCode สำหรับ .NET** – ดาวน์โหลดจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/barcode/net/)  
3. **ความรู้พื้นฐานของ .NET** – คุ้นเคยกับ C# และระบบนิเวศของ .NET

## นำเข้า Namespaces

เราจะเริ่มโดยการเรียกใช้ namespaces ที่จำเป็นสำหรับการสร้างและอ่านบาร์โค้ด

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## “generate DataMatrix barcode” กับอักขระ macro คืออะไร?

DataMatrix ที่เปิดใช้งาน macro สามารถบรรจุข้อมูลเพิ่มเติม (เช่น การอ้างอิงไปยังบาร์โค้ดอื่น) ด้วยอักขระ macro พิเศษ (Macro05, Macro06 ฯลฯ) ซึ่งมีประโยชน์ในโลจิสติกส์และการผลิตที่สัญลักษณ์เดียวอาจต้องเชื่อมต่อกับชุดข้อมูลขนาดใหญ่

## ทำไมต้องใช้ Aspose.BarCode เพื่อ generate DataMatrix barcode?

- **ควบคุมเต็มรูปแบบ** เกี่ยวกับขนาด, การแก้ไขข้อผิดพลาด, และการตั้งค่า macro  
- **รองรับหลายแพลตฟอร์ม** สำหรับ .NET Framework, .NET Core, และ .NET 5/6  
- **มีฟังก์ชันการอ่านในตัว** ช่วยให้คุณตรวจสอบบาร์โค้ดได้ทันทีหลังจากสร้าง

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ

สร้าง Console Application (หรือโปรเจกต์ .NET ใดก็ได้) ใน Visual Studio แล้วเพิ่มการอ้างอิงไปยังไฟล์ DLL ของ Aspose.BarCode ที่คุณดาวน์โหลดมา

### ขั้นตอนที่ 2: การกำหนดค่า DataMatrix Macro

ส่วนสำคัญของบทแนะนำ – ที่นี่เราจะ **generate DataMatrix barcode** พร้อมอักขระ macro

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

> **เคล็ดลับ:** แทนที่ `"ASPOSE"` ด้วยสตริงที่คุณต้องการเข้ารหัส. อักขระ macro (`Macro05`) จะบอกสแกนเนอร์ว่าบาร์โค้ดนี้เป็นส่วนหนึ่งของลำดับ macro

### ขั้นตอนที่ 3: ปรับแต่งพารามิเตอร์ของบาร์โค้ด

ก่อนบันทึก, คุณสามารถปรับตั้งค่าเพิ่มเติมได้:

- **XDimension** – ควบคุมขนาดของแต่ละโมดูล (พิกเซล)  
- **Margin**, **ErrorCorrection**, และ **EncodingMode** – ทั้งหมดเข้าถึงได้ผ่าน `gen.Parameters.Barcode.DataMatrix`

### ขั้นตอนที่ 4: บันทึกบาร์โค้ด

โค้ดตัวอย่างข้างต้นจะบันทึกภาพเป็น `DataMatrixMacro.png` ในโฟลเดอร์ที่คุณระบุ. PNG เป็นรูปแบบที่ไม่มีการสูญเสียข้อมูล, เหมาะสำหรับการประมวลผลต่อไป

### ขั้นตอนที่ 5: อ่านบาร์โค้ด

โดยใช้ `BarCodeReader` เราจะอ่านภาพที่สร้างขึ้นทันทีเพื่อยืนยันว่าอักขระ macro และข้อมูลถูกต้อง การตรวจสอบแบบรอบนี้มีประโยชน์อย่างยิ่งในการทดสอบอัตโนมัติ

## การใช้ DataMatrix ในสถานการณ์จริง

- **การติดฉลากสินค้า** – ฝังหมายเลขซีเรียล, ID ของล็อต, หรือ URL  
- **การติดตามเอกสาร** – เชื่อมโยงแบบฟอร์มที่พิมพ์กับบันทึกดิจิทัลผ่านลำดับ macro  
- **การดูแลสุขภาพ** – เข้ารหัสข้อมูลผู้ป่วยบนแท็กขนาดกะทัดรัดสำหรับอุปกรณ์

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| บาร์โค้ดไม่สามารถอ่านได้ | ค่า `XDimension` ไม่ถูกต้องหรือความละเอียดภาพต่ำ | เพิ่ม `XDimension.Pixels` เป็น 4‑6 และบันทึกเป็น PNG หรือ TIFF |
| อักขระ macro ถูกละเลย | ตัวอ่านไม่รองรับโหมด macro | ใช้สแกนเนอร์/รีดเดอร์ที่สนับสนุน DataMatrix macro อย่างชัดเจน (เช่น รุ่นใหม่ของ ZXing) |
| ไม่พบพาธ | ตัวแปร `path` ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่หรือใช้ `Path.Combine` กับ `Environment.CurrentDirectory` |

## คำถามที่พบบ่อย

**ถาม: Aspose.BarCode สำหรับ .NET คืออะไร?**  
ตอบ: Aspose.BarCode สำหรับ .NET เป็นไลบรารีที่ทรงพลัง ช่วยให้นักพัฒนา .NET สามารถสร้างและอ่านบาร์โค้ดในรูปแบบต่าง ๆ รวมถึง DataMatrix, QR, และอื่น ๆ

**ถาม: ทำไมต้องใช้บาร์โค้ด DataMatrix?**  
ตอบ: บาร์โค้ด DataMatrix มีขนาดกะทัดรัด, มีความเชื่อถือสูง, และสามารถเก็บข้อมูลจำนวนมาก ทำให้เหมาะกับการผลิต, โลจิสติกส์, และการดูแลสุขภาพ

**ถาม: จะหาเอกสารของ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?**  
ตอบ: คุณสามารถดูเอกสารได้ที่ [เอกสาร Aspose.BarCode สำหรับ .NET](https://reference.aspose.com/barcode/net/)

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode สำหรับ .NET หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [ลิงก์ทดลองฟรี](https://releases.aspose.com/)

**ถาม: จะขอรับการสนับสนุนสำหรับ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?**  
ตอบ: หากมีคำถามหรือจำเป็นต้องการสนับสนุน, คุณสามารถเยี่ยมชมฟอรั่ม Aspose.BarCode สำหรับ .NET ได้ที่ [ฟอรั่มสนับสนุน](https://forum.aspose.com/c/barcode/13)

---

**อัปเดตล่าสุด:** 2026-01-17  
**ทดสอบด้วย:** Aspose.BarCode 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}