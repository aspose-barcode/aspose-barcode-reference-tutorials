---
title: สร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET
linktitle: เวอร์ชัน DataMatrix
second_title: Aspose.BarCode .NET API
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ใน .NET โดยใช้ Aspose.BarCode สำหรับ .NET มิติข้อมูลที่กำหนดเอง การรองรับ ECC และอื่นๆ
weight: 12
url: /th/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET

หากคุณกำลังมองหาโซลูชันที่เชื่อถือได้ในการสร้างบาร์โค้ด DataMatrix ในแอปพลิเคชัน .NET ของคุณ Aspose.BarCode สำหรับ .NET คือคำตอบของคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้ Aspose.BarCode สำหรับ .NET เพื่อสร้างบาร์โค้ด DataMatrix เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถปฏิบัติตามได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนาที่รองรับ .NET
-  สำเนาของ Aspose.BarCode สำหรับ .NET ซึ่งคุณสามารถดาวน์โหลดได้[ลิงค์นี้](https://releases.aspose.com/barcode/net/).
- ความรู้พื้นฐานเกี่ยวกับ C# และกรอบงาน .NET

ตอนนี้ เรามาสำรวจเวอร์ชันของ DataMatrix และวิธีสร้างเวอร์ชันเหล่านี้โดยใช้ Aspose.BarCode สำหรับ .NET กันดีกว่า

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ C# ใดๆ จำเป็นต้องนำเข้าเนมสเปซที่จำเป็น ในกรณีของ Aspose.BarCode คุณจะต้องมีสิ่งต่อไปนี้:

```csharp
using Aspose.BarCode.Generation;
```

 เนมสเปซนี้ให้การเข้าถึง`BarcodeGenerator` ซึ่งมีความสำคัญอย่างยิ่งต่อการสร้างบาร์โค้ด

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีของคุณ

เริ่มต้นด้วยการกำหนดเส้นทางไดเรกทอรีที่คุณต้องการบันทึกบาร์โค้ด DataMatrix ที่สร้างขึ้น

```csharp
string path = "Your Directory Path";
```

 แทนที่`"Your Directory Path"` พร้อมเส้นทางจริงที่คุณต้องการบันทึกภาพบาร์โค้ด

## ขั้นตอนที่ 2: เริ่มต้นตัวสร้างบาร์โค้ด

 สร้างอินสแตนซ์ของ`BarcodeGenerator` และระบุประเภทบาร์โค้ดเป็น`DataMatrix`. คุณยังสามารถให้ข้อมูลที่คุณต้องการเข้ารหัสภายในบาร์โค้ดได้

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // รหัสสำหรับการสร้างบาร์โค้ดอยู่ที่นี่
}
```

## ขั้นตอนที่ 3: กำหนดค่าคุณสมบัติบาร์โค้ด

คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของบาร์โค้ด DataMatrix ได้ เช่น ขนาดและประเภท ECC (รหัสแก้ไขข้อผิดพลาด) นี่คือตัวอย่างการตั้งค่ามิติ X เป็น 4 พิกเซลและเลือก ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## ขั้นตอนที่ 4: ตั้งค่าเวอร์ชัน DataMatrix และบันทึก

คุณสามารถระบุเวอร์ชัน DataMatrix ได้โดยการตั้งค่าจำนวนแถวและคอลัมน์ หลังจากกำหนดค่าเวอร์ชันแล้ว ให้บันทึกภาพบาร์โค้ด

ตัวอย่างเช่น หากต้องการสร้างบาร์โค้ด DataMatrix ที่มี 22 แถว 22 คอลัมน์โดยใช้ ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

ในทำนองเดียวกัน คุณสามารถสร้างบาร์โค้ดที่มีพารามิเตอร์ที่แตกต่างกันได้โดยการเปลี่ยนเวอร์ชันและประเภท ECC ตามต้องการ

## ขั้นตอนที่ 5: ทำซ้ำสำหรับเวอร์ชันอื่น

คุณสามารถทำซ้ำขั้นตอนที่ 4 สำหรับ DataMatrix เวอร์ชันอื่นๆ ได้ ตัวอย่างเช่น หากต้องการสร้างบาร์โค้ดที่มี 12 แถว 64 คอลัมน์โดยใช้ ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## ขั้นตอนที่ 6: สลับประเภท ECC

หากคุณต้องการเปลี่ยนประเภท ECC เป็น Ecc140 คุณสามารถทำได้โดยการอัปเดตคุณสมบัติ ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## ขั้นตอนที่ 7: สร้างบาร์โค้ดด้วยเวอร์ชันและ ECC ที่แตกต่างกัน

ทำซ้ำขั้นตอนที่ 4 สำหรับ DataMatrix และประเภท ECC อื่นๆ โดยบันทึกบาร์โค้ดแต่ละอันด้วยชื่อไฟล์ที่ไม่ซ้ำกัน

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

เมื่อคุณได้เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix โดยใช้ Aspose.BarCode สำหรับ .NET แล้ว คุณก็สามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย

## บทสรุป

Aspose.BarCode สำหรับ .NET ช่วยให้กระบวนการสร้างบาร์โค้ด DataMatrix ในแอปพลิเคชัน .NET ของคุณง่ายขึ้น ด้วยคำแนะนำทีละขั้นตอนนี้ คุณสามารถสร้างบาร์โค้ดที่มีเวอร์ชันและประเภท ECC ที่แตกต่างกันได้ โดยให้ความยืดหยุ่นและการปรับแต่งที่ตรงตามความต้องการเฉพาะของคุณ

 หากคุณมีคำถามหรือต้องการความช่วยเหลือ อย่าลังเลที่จะเยี่ยมชม[Aspose.BarCode สำหรับเอกสาร .NET](https://reference.aspose.com/barcode/net/) หรือตรวจสอบ[ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13) สำหรับการสนับสนุน

## คำถามที่พบบ่อย

### คำถามที่ 1: ECC ในบาร์โค้ด DataMatrix คืออะไร

ตอบ 1: ECC (รหัสแก้ไขข้อผิดพลาด) เป็นองค์ประกอบสำคัญของบาร์โค้ด DataMatrix ที่ช่วยรับประกันความสมบูรณ์ของข้อมูล ระดับ ECC ที่แตกต่างกันจะให้ระดับการแก้ไขข้อผิดพลาดที่แตกต่างกัน

### คำถามที่ 2: ฉันสามารถสร้างบาร์โค้ด DataMatrix ด้วยขนาดที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET ได้หรือไม่

A2: ได้ คุณสามารถปรับแต่งขนาดของบาร์โค้ด DataMatrix ได้โดยการตั้งค่าจำนวนแถวและคอลัมน์ตามที่แสดงในบทช่วยสอน

### คำถามที่ 3: ฉันจะดาวน์โหลด Aspose.BarCode สำหรับ .NET ได้ที่ไหน

 A3: คุณสามารถดาวน์โหลด Aspose.BarCode สำหรับ .NET ได้จาก[ลิงค์นี้](https://releases.aspose.com/barcode/net/).

### คำถามที่ 4: Aspose.BarCode สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ได้ คุณสามารถเข้าถึง Aspose.BarCode สำหรับ .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร

 A5: หากต้องการรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET โปรดไปที่[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
