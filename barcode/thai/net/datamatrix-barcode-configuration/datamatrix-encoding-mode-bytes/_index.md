---
date: 2026-05-30
description: เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ในโหมด Bytes และอ่านบาร์โค้ด DataMatrix
  ด้วย Aspose.BarCode สำหรับ .NET – คู่มือบาร์โค้ดแบบทีละขั้นตอน
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: โหมดการเข้ารหัส DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้างบาร์โค้ด DataMatrix ในโหมด Bytes ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด DataMatrix ในโหมด Bytes ด้วย Aspose.BarCode สำหรับ .NET

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **สร้างบาร์โค้ด DataMatrix** โดยใช้โหมดการเข้ารหัส Bytes และจากนั้น **อ่านบาร์โค้ด DataMatrix** กลับด้วย Aspose.BarCode สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างระบบจัดการคลังสินค้า หรือแอปพลิเคชันจองตั๋วบนมือถือ คู่มือบาร์โค้ดแบบขั้นตอนต่อขั้นตอนด้านล่างจะแสดงให้คุณเห็นอย่างชัดเจนว่าตั้งค่าการสร้างบาร์โค้ดอย่างไร ผลิตภาพคุณภาพสูง และถอดรหัสอีกครั้ง—ทั้งหมดในเพียงไม่กี่บรรทัดของ C#.

## คำตอบด่วน
- **ฉันสามารถสร้างบาร์โค้ด DataMatrix ใน .NET ได้หรือไม่?** ใช่, ใช้ `BarcodeGenerator` กับ `EncodeTypes.DataMatrix` และตั้งค่า `DataMatrixEncodeMode.Bytes`.
- **เมธอดใดที่ใช้ในการอ่านบาร์โค้ด?** `BarCodeReader` อ่านภาพและคืนข้อความที่เข้ารหัส.
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้.
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **ฉันสามารถเข้ารหัสได้กี่ไบต์?** สูงสุด 1,555 ไบต์ในสัญลักษณ์ DataMatrix เดียว.

## การสร้างบาร์โค้ด DataMatrix คืออะไร?
**Generate DataMatrix barcode** หมายถึงการสร้างบาร์โค้ดสองมิติรูปสี่เหลี่ยมจัตุรัสที่สามารถเก็บข้อมูลไบนารีได้ Aspose.BarCode แสดงสัญลักษณ์เป็นภาพ PNG, JPG หรือ SVG ที่เครื่องสแกนใดก็สามารถถอดรหัสได้ มันถูกใช้กันอย่างแพร่หลายสำหรับการติดตามสินค้าคงคลัง การจัดการเอกสาร และการตรวจสอบความถูกต้อง เนื่องจากให้ความหนาแน่นของข้อมูลสูงและความสามารถในการแก้ไขข้อผิดพลาด ทำให้เชื่อถือได้แม้ในการพิมพ์คุณภาพต่ำ.

## ทำไมต้องใช้โหมดการเข้ารหัส Bytes?
โหมด Bytes ช่วยให้คุณฝังข้อมูลไบนารีดิบ (สูงสุด 1,555 ไบต์) โดยไม่ต้องแปลงเป็นข้อความ ซึ่งเหมาะสำหรับหมายเลขซีเรียล, GUID หรือข้อมูลที่เข้ารหัสลับ Aspose.BarCode รองรับ **30+ รูปแบบบาร์โค้ด** และสามารถประมวลผล **เอกสารหลายร้อยหน้า** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้ประสิทธิภาพเร็วแม้ในสถานการณ์ที่ต้องประมวลผลจำนวนมาก.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกเข้าสู่กระบวนการเข้ารหัส คุณจะต้องมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. Aspose.BarCode for .NET: เพื่อเริ่มต้น คุณต้องมีไลบรารี Aspose.BarCode for .NET ติดตั้งอยู่ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/barcode/net/). คุณยังสามารถค้นหาผลิตภัณฑ์ Aspose อื่น ๆ ได้ที่ [ที่นี่](https://releases.aspose.com/).
2. สภาพแวดล้อมการพัฒนาของคุณ: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาไว้แล้ว รวมถึง Visual Studio หรือ IDE ใด ๆ ที่คุณเลือกใช้.
3. ความรู้พื้นฐานของ C#: บทแนะนำนี้สมมติว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#.

สำหรับความช่วยเหลือ, เยี่ยมชม [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

เมื่อมีข้อกำหนดเหล่านี้พร้อม คุณก็พร้อมที่จะเริ่มเข้ารหัสข้อมูลในรูปแบบ DataMatrix โดยใช้โหมด Bytes.

## นำเข้า Namespaces
เพื่อใช้ Aspose.BarCode สำหรับ .NET ให้นำเข้า Namespaces ที่จำเป็นที่ส่วนบนของไฟล์ C# ของคุณ:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

เมื่อสภาพแวดล้อมพร้อมแล้ว, เรามาเดินผ่านขั้นตอนที่แน่นอนเพื่อ **สร้างบาร์โค้ด DataMatrix** แล้วอ่านกลับ.

## วิธีการสร้างบาร์โค้ด DataMatrix ในโหมด Bytes
โหลด `BarcodeGenerator`, ตั้งค่าโหมดการเข้ารหัสเป็น Bytes, กำหนดข้อความแสดงผลที่เป็นตัวเลือก, บันทึกภาพ, และสุดท้ายใช้ `BarCodeReader` เพื่อตรวจสอบผลลัพธ์—ทั้งหมดในหกขั้นตอนสั้น ๆ วิธีนี้รับประกันบาร์โค้ดที่เชื่อถือได้ซึ่งสอดคล้องกับมาตรฐาน ISO/IEC 16022.

### ขั้นตอนที่ 1: เริ่มต้น BarcodeGenerator
`BarcodeGenerator` คือคลาสหลักที่ใช้สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์และข้อมูลที่กำหนด.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### ขั้นตอนที่ 2: ตั้งค่า DataMatrix Encode Mode เป็น Bytes
`DataMatrixEncodeMode.Bytes` บอกให้ตัวสร้างพิจารณาข้อมูลเข้าเป็นไบต์ไบนารีดิบแทนข้อความ.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### ขั้นตอนที่ 3: ตั้งค่า Display Text
คุณสมบัติ `CodeText` กำหนดข้อความที่มนุษย์สามารถอ่านได้ที่แสดงใต้สัญลักษณ์บาร์โค้ด.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด
เมธอด `Save` เขียนบาร์โค้ดที่สร้างลงในไฟล์ภาพตามรูปแบบที่ระบุ.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### ขั้นตอนที่ 5: พยายามจดจำ
`BarCodeReader` อ่านภาพบาร์โค้ดและดึงข้อมูลที่เข้ารหัสออกมา.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### ขั้นตอนที่ 6: วนลูปและแสดงผลลัพธ์
วนลูปผ่าน `reader.ReadBarCodes()` เพื่อเข้าถึงบาร์โค้ดที่ตรวจพบแต่ละอันและ `CodeText` ของมัน.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

ด้วยขั้นตอนเหล่านี้ คุณได้ **สร้างบาร์โค้ด DataMatrix** ในโหมด Bytes อย่างสำเร็จและตรวจสอบโดยใช้ Aspose.BarCode สำหรับ .NET ไลบรารีนี้แยกรายละเอียดการเข้ารหัสระดับต่ำออกไป ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจแทนคณิตศาสตร์ของบาร์โค้ดได้.

## ปัญหาทั่วไปและวิธีแก้
- **ข้อมูลที่เข้ารหัสถูกตัด** – ตรวจสอบให้แน่ใจว่าอาเรย์ไบต์ไม่เกิน 1,555 ไบต์; หากเกินไลบรารีจะเปลี่ยนเป็นขนาดสัญลักษณ์ที่ใหญ่ขึ้นโดยอัตโนมัติหรือโยนข้อยกเว้น.
- **ภาพดูเบลอ** – บันทึกภาพด้วยความละเอียดที่สูงกว่า (เช่น 300 dpi) โดยตั้งค่า `generator.Parameters.ImageResolution` ก่อนเรียก `Save`.
- **Reader คืนค่า null** – ตรวจสอบให้แน่ใจว่าเส้นทางภาพถูกต้องและไฟล์ไม่เสียหาย; ยืนยันด้วยว่า `BarCodeReader` ถูกสร้างด้วย `DecodeType.DataMatrix`.

## คำถามที่พบบ่อย
**Q: โหมดการเข้ารหัส DataMatrix คืออะไร?**  
A: โหมดการเข้ารหัส DataMatrix กำหนดวิธีที่ข้อมูลอินพุตถูกแปลงเป็นรูปแบบสองมิติ; โหมด Bytes จะเก็บไบต์ไบนารีดิบโดยตรง.

**Q: ฉันจะได้รับรุ่นทดลองฟรีของ Aspose.BarCode สำหรับ .NET ได้อย่างไร?**  
A: คุณสามารถรับรุ่นทดลองฟรีของ Aspose.BarCode สำหรับ .NET ได้จาก [ที่นี่](https://releases.aspose.com/).

**Q: ฉันสามารถค้นหาเอกสารสำหรับ Aspose.BarCode สำหรับ .NET ได้ที่ไหน?**  
A: คุณสามารถค้นหาเอกสารสำหรับ Aspose.BarCode สำหรับ .NET ได้ที่ [ที่นี่](https://reference.aspose.com/barcode/net/).

**Q: Aspose.BarCode สำหรับ .NET เหมาะกับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: ใช่, Aspose.BarCode สำหรับ .NET เหมาะกับการใช้งานเชิงพาณิชย์ คุณสามารถซื้อใบอนุญาตได้จาก [ที่นี่](https://purchase.aspose.com/buy).

**Q: ฉันสามารถใช้ใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้หรือไม่?**  
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-05-30  
**ทดสอบด้วย:** Aspose.BarCode 24.12 สำหรับ .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง
- [การเข้ารหัส DataMatrix ใน ASCII ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [อ่านบาร์โค้ด DataMatrix C# – สร้างโหมด DataMatrix (อัตโนมัติ)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [วิธีการสร้างบาร์โค้ด DataMatrix (ECC 200) ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}