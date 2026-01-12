---
date: 2026-01-12
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix, วิธีสร้าง DataMatrix, และสำรวจเทคนิคการสร้างบาร์โค้ดของ
  Aspose สำหรับโครงการ C#
linktitle: DataMatrix ECC 200 Configuration
second_title: Aspose.BarCode .NET API
title: วิธีสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET

## บทนำ

คุณพร้อมที่จะสำรวจ **วิธีการสร้างบาร์โค้ด DataMatrix** ด้วย Aspose.BarCode สำหรับ .NET หรือยัง? ไม่ว่าคุณจะกำลังสร้างระบบจัดการสินค้าคงคลัง, แอปจุดขาย, หรืออัตโนมัติกระบวนการทำงานของเอกสาร คู่มือนี้จะพาคุณผ่านทุกขั้นตอนของ **การสร้างบาร์โค้ดด้วย Aspose** และแสดงวิธีการสร้างบาร์โค้ด DataMatrix ECC 200 ที่เชื่อถือได้ใน C#.

## คำตอบสั้น ๆ
- **ไลบรารีที่ดีที่สุดสำหรับ DataMatrix ใน .NET คืออะไร?** Aspose.BarCode สำหรับ .NET  
- **ECC ระดับใดที่ ECC 200 ให้บริการ?** ให้การแก้ไขข้อผิดพลาดความหนาแน่นสูงสำหรับการสแกนที่มั่นคง  
- **ต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ชั่วคราวใช้สำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **สามารถส่งออกเป็น PNG, JPEG หรือ TIFF ได้หรือไม่?** ได้ – เมธอด `Save` รองรับหลายรูปแบบภาพ

## สิ่งที่ต้องเตรียม

1. **สภาพแวดล้อมการพัฒนา** – Visual Studio พร้อม .NET framework ที่เหมาะสมติดตั้งแล้ว  
2. **Aspose.BarCode สำหรับ .NET** – ดาวน์โหลดและติดตั้งจากเว็บไซต์, [ที่นี่](https://releases.aspose.com/barcode/net/)  
3. **ไลเซนส์** – รับไลเซนส์ชั่วคราวสำหรับการทดสอบจาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  
4. **พื้นฐาน C#** – ความคุ้นเคยกับไวยากรณ์ C# และโครงสร้างโปรเจกต์

เมื่อเราครอบคลุมพื้นฐานแล้ว, ไปที่การกำหนดค่า DataMatrix ECC 200 กันต่อ

## นำเข้า Namespaces

เพื่อเริ่มต้น, นำเข้า namespace ที่จำเป็นเพื่อให้เข้าถึงคลาสการสร้างบาร์โค้ด:

```csharp
using Aspose.BarCode.Generation;
```

## วิธีการสร้างบาร์โค้ด DataMatrix ECC 200

### ขั้นตอนที่ 1: เริ่มต้น Barcode Generator

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

ในโค้ดสแนปนี้เราสร้างอินสแตนซ์ `BarcodeGenerator`, ระบุว่าเราต้องการบาร์โค้ด **DataMatrix**, และให้ข้อมูลที่ต้องเข้ารหัส. แทนที่ `"Your Directory Path"` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกรูปภาพ.

### ขั้นตอนที่ 2: ตั้งค่า XDimension และประเภท ECC

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

ที่นี่เรากำหนด **XDimension** (ขนาดของแต่ละโมดูล) และเลือก **ECC 200** เพื่อการแก้ไขข้อผิดพลาดที่แข็งแรง. ปรับค่าพิกเซลหากต้องการโมดูลที่ใหญ่หรือเล็กกว่า.

### ขั้นตอนที่ 3: สร้างและบันทึกรูปภาพบาร์โค้ด

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

เมธอด `Save` จะเขียนบาร์โค้ดลงไฟล์ PNG. คุณสามารถเปลี่ยน `BarCodeImageFormat.Png` เป็น `Jpeg` หรือ `Tiff` ตามต้องการ. นี่คือหัวใจของ **generate barcode image C#** ด้วย Aspose.

## ทำไมต้องใช้การสร้างบาร์โค้ดของ Aspose?

- **API ครบวงจร** – รองรับสัญลักษณ์หลายสิบประเภท, รวมถึง QR, PDF417, และ DataMatrix  
- **ไม่มีการพึ่งพาภายนอก** – ไลบรารี .NET แท้, ผสานรวมง่าย  
- **การเรนเดอร์คุณภาพสูง** – ผลลัพธ์เวกเตอร์ที่ปรับขนาดได้และการควบคุมมิติที่แม่นยำ  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core

## ปัญหาที่พบบ่อยและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| บาร์โค้ดดูเบลอ | XDimension ต่ำเกินไป | เพิ่ม `XDimension.Pixels` เป็น 6‑8 |
| การสแกนล้มเหลวบนมือถือ | ระดับ ECC ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่า `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| ไม่พบไฟล์ที่สร้าง | สตริงพาธไม่ถูกต้อง | ใช้พาธแบบเต็มหรือให้แน่ใจว่าโฟลเดอร์มีอยู่ |

## คำถามที่พบบ่อย (FAQ)

### Q1: Aspose.BarCode สำหรับ .NET คืออะไร?

A1: Aspose.BarCode สำหรับ .NET เป็นไลบรารีที่ทรงพลัง ช่วยให้นักพัฒนา .NET สามารถสร้าง, ปรับแต่ง, และทำงานกับบาร์โค้ดในแอปพลิเคชันต่าง ๆ

### Q2: จำเป็นต้องมีไลเซนส์สำหรับ Aspose.BarCode สำหรับ .NET หรือไม่?

A2: ใช่, คุณต้องมีไลเซนส์ที่ถูกต้องเพื่อใช้ Aspose.BarCode สำหรับ .NET ในโครงการของคุณ. คุณสามารถรับไลเซนส์ชั่วคราวเพื่อการทดสอบได้

### Q3: สามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างด้วย Aspose.BarCode ได้หรือไม่?

A3: แน่นอน! คุณสามารถปรับแต่งลักษณะบาร์โค้ด, ขนาด, และคุณสมบัติต่าง ๆ ให้ตรงกับความต้องการของคุณ

### Q4: Aspose.BarCode สำหรับ .NET รองรับประเภทบาร์โค้ดใดบ้าง?

A4: รองรับประเภทบาร์โค้ดหลากหลาย รวมถึง QR Code, DataMatrix, Code 128, และอื่น ๆ อีกมาก

### Q5: จะหาเอกสารอ้างอิงของ Aspose.BarCode สำหรับ .NET ได้จากที่ไหน?

A5: คุณสามารถเข้าถึงเอกสารได้ [ที่นี่](https://reference.aspose.com/barcode/net/)

## คำถามที่พบบ่อยเพิ่มเติม

**Q: สามารถใช้โค้ดนี้ในแอปพลิเคชันคอนโซล .NET Core ได้หรือไม่?**  
A: ได้, API เดียวกันทำงานใน .NET Core, .NET 5, และ .NET 6

**Q: จะเปลี่ยนรูปแบบการส่งออกเป็น JPEG อย่างไร?**  
A: แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` ในการเรียก `Save`

**Q: สามารถฝังบาร์โค้ดลงใน PDF ได้หรือไม่?**  
A: ได้ – สร้างภาพก่อน, แล้วเพิ่มลงใน PDF ด้วย Aspose.PDF หรือไลบรารี PDF ใด ๆ

**Q: หากต้องการเข้ารหัสอักขระ Unicode จะทำอย่างไร?**  
A: DataMatrix รองรับ UTF‑8; เพียงส่งสตริงโดยตรงตามตัวอย่าง

**Q: ไลบรารีรองรับการสร้างบาร์โค้ดหลายรายการพร้อมกันหรือไม่?**  
A: แน่นอน – ใส่โค้ดการสร้างไว้ในลูปและเปลี่ยนข้อมูล/ค่าแต่ละรอบ

## สรุป

ในคู่มือขั้นตอนนี้เราได้อธิบาย **วิธีการสร้างบาร์โค้ด DataMatrix** ECC 200, สำรวจ **การสร้างบาร์โค้ดด้วย Aspose**, และสาธิตวิธี **generate barcode image C#** ที่คุณสามารถนำไปใช้ในโปรเจกต์ .NET ใดก็ได้. ทดลองกับตัวเลือกการกำหนดค่าต่าง ๆ ที่ Aspose มีให้เพื่อปรับบาร์โค้ดให้ตรงกับความต้องการของคุณ

หากพบอุปสรรคใด ๆ ชุมชนพร้อมให้ความช่วยเหลือที่ [ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13). ขอให้สนุกกับการเขียนโค้ด!

---

**อัปเดตล่าสุด:** 2026-01-12  
**ทดสอบกับ:** Aspose.BarCode 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}