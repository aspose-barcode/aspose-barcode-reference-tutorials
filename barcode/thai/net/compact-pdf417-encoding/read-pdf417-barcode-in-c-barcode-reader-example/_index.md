---
category: general
date: 2026-10-14
description: สร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C# ที่อ่านบาร์โค้ด PDF417 จัดการ macro
  PDF417 และถอดรหัสบาร์โค้ดหลายรายการจากภาพเดียว
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: สร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C# เพื่ออ่านบาร์โค้ด PDF417 และ macro
  PDF417 อย่างรวดเร็วจากภาพ คู่มือขั้นตอนต่อขั้นตอนแสดงวิธีถอดรหัสบาร์โค้ดหลายรายการในรูปเดียว
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: สร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C# – คู่มือฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: สร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C# – ตัวอย่างการอ่านบาร์โค้ด PDF417
url: /th/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C# – ตัวอย่างการอ่านบาร์โค้ด PDF417

`BarCodeReader` เป็นคลาสหลักของ Aspose.BarCode ที่ถอดรหัสบาร์โค้ดจากภาพและส่งคืนเมตาดาต้าโดยละเอียด หากคุณต้องการอ่านข้อมูลบาร์โค้ด PDF417 จากภาพ คู่มือนี้จะแสดงวิธีทำด้วยคลาส **BarCodeReader** ใน C# คุณจะได้เรียนรู้ตัวอย่าง **สร้างเครื่องสแกนบาร์โค้ดคอนโซล** ที่รองรับ macro PDF417 และสามารถอ่านบาร์โค้ดหลายรายการในภาพเดียว

การทำงานกับบาร์โค้ดมักต้องจัดการกับแหล่งภาพที่หลากหลาย สภาพแสงที่เปลี่ยนแปลง และบางครั้งข้อมูลเชิงรวมเช่นส่วนของ macro PDF417 บทเรียนนี้ครอบคลุมทุกสิ่งที่คุณต้องการเพื่อถอดรหัสบาร์โค้ด PDF417 ดึงฟิลด์ขยายของมัน และประมวลผลบาร์โค้ดหลายรายการจากภาพเดียว เมื่อเสร็จสิ้นคุณจะมีโปรแกรมคอนโซลที่สามารถรันได้ซึ่งอ่านบาร์โค้ดจากไฟล์ภาพและพิมพ์ข้อมูลโดยละเอียดไปยังคอนโซล

## คำตอบอย่างรวดเร็ว
- **ตัวอย่างทำอะไร?** มันสร้างเครื่องสแกนบาร์โค้ดคอนโซลที่อ่านบาร์โค้ด PDF417 และ macro PDF417 จากภาพและพิมพ์ฟิลด์ที่ถอดรหัสทั้งหมด  
- **ต้องใช้ไลบรารีอะไร?** Aspose.BarCode for .NET (NuGet)  
- **สามารถอ่านบาร์โค้ดหลายรายการพร้อมกันได้หรือไม่?** ใช่ – ตัวอ่านจะวนลูปผ่านบาร์โค้ดทุกรายการที่พบในภาพ  
- **ต้องการการเชื่อมต่ออินเทอร์เน็ตหรือไม่?** ไม่จำเป็น ไลบรารีทำงานแบบออฟไลน์ทั้งหมด  
- **รองรับเวอร์ชัน .NET ใด?** .NET 6.0 หรือใหม่กว่า  

## สิ่งที่คุณต้องเตรียม

ก่อนเริ่มต้น โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือใหม่กว่า ติดตั้งแล้ว  
* เวอร์ชันล่าสุดของแพ็กเกจ NuGet **Aspose.BarCode for .NET** (หรือไลบรารีที่เข้ากันได้ที่ให้ `BarCodeReader` และ `DecodeType.MacroPdf417`)  
* ไฟล์ภาพที่มีบาร์โค้ด PDF417 หรือ macro PDF417 (ตัวอย่างใช้ `ExtPDF417Meta.png`)  
* โปรแกรมแก้ไขโค้ดหรือ IDE เช่น Visual Studio 2022  

ไม่จำเป็นต้องใช้บริการเพิ่มเติมหรือ API ภายนอก

## การตั้งค่าโครงการสำหรับการอ่านบาร์โค้ด

1. **สร้างโปรเจกต์คอนโซลใหม่**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **เพิ่มไลบรารีบาร์โค้ด**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **คัดลอกภาพบาร์โค้ด**  

   วางไฟล์ `ExtPDF417Meta.png` (หรือภาพใด ๆ ที่มีบาร์โค้ด PDF417) ลงในโฟลเดอร์โปรเจกต์  
   สำหรับบทเรียนนี้เราจะสมมติว่าไฟล์อยู่ที่ `YOUR_DIRECTORY/ExtPDF417Meta.png`.

ตอนนี้โปรเจกต์พร้อมสำหรับการคอมไพล์และรันตัวอย่างตัวอ่านบาร์โค้ดแล้ว

## วิธีสร้างเครื่องสแกนบาร์โค้ดคอนโซลใน C#?

`BarCodeReader` เป็นคลาสที่ Aspose.BarCode ให้มาเพื่ออ่านบาร์โค้ดจากภาพและส่งคืนข้อมูลที่ถอดรหัส  
โหลดภาพด้วย `BarCodeReader` ตั้งค่าชนิดการถอดรหัสเป็น `MacroPdf417` และวนลูปผลลัพธ์ – นั่นคือทั้งหมดที่คุณต้องการเพื่อสร้างเครื่องสแกนบาร์โค้ดคอนโซล ตัวอ่านจะปล่อยทรัพยากรเนทีฟโดยอัตโนมัติด้วยคำสั่ง `using` ดังนั้นคุณไม่ต้องจัดการหน่วยความจำด้วยตนเอง วิธีนี้ทำงานกับรูปแบบภาพใด ๆ ที่ .NET รองรับ เช่น PNG, JPEG หรือ BMP

### ขั้นตอนการทำงานแบบละเอียด

แกนหลักของวิธีแก้คือบล็อก `using` ที่สร้างอินสแตนซ์ `BarCodeReader` ระบุ `DecodeType.MacroPdf417` และวนลูปผ่านบาร์โค้ดที่ตรวจจับได้ทั้งหมด โค้ดต่อไปนี้เป็นโปรแกรมที่สมบูรณ์และทำงานอิสระที่คุณสามารถวางลงใน `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**ทำไมวิธีนี้ถึงได้ผล**:  

* `DecodeType.MacroPdf417` บอกตัวอ่านให้มองหาส่วนขยาย macro ของ PDF417 ซึ่งบรรจุเมตาดาต้าเพิ่มเติมเช่นไฟล์ ID, จำนวนส่วน, และเวลา  
* คำสั่ง `using` รับประกันว่าทรัพยากรที่ไม่ได้จัดการ (ไฟล์แฮนด์เลอร์, บัฟเฟอร์การถอดรหัสเนทีฟ) จะถูกปล่อยอย่างทันท่วงที  
* ลูป `foreach` จะประมวลผล **บาร์โค้ดทั้งหมด** ที่ภาพมีโดยอัตโนมัติ ตอบสนองความต้องการ *อ่านบาร์โค้ดหลายรายการ*

เมื่อคุณรันโปรแกรม (`dotnet run`) คุณควรเห็นผลลัพธ์คล้ายกับต่อไปนี้:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

หากภาพมีบาร์โค้ด PDF417 มากกว่าหนึ่งรายการ ลูปจะพิมพ์บล็อกแยกสำหรับแต่ละบาร์โค้ด ซึ่งแสดงให้เห็นวิธี **อ่านบาร์โค้ดหลายรายการ** จากภาพเดียว

## วิธีอ่านบาร์โค้ดหลายรายการจากภาพได้อย่างไร

ใช้อินสแตนซ์ `BarCodeReader` เพียงหนึ่งตัวและตั้งค่าแฟล็ก `DecodeType` ให้รวมรูปแบบทั้งหมดที่คุณต้องการตรวจจับ โดยการรวมแฟล็กด้วยตัวดำเนินการ OR แบบบิต คุณสามารถบอกไลบรารีให้มองหา PDF417, QR, Code‑128 และสัญลักษณ์อื่น ๆ มากมายในหนึ่งรอบ วิธีนี้ลบความจำเป็นของตัวอ่านแยกต่างหากและลดเวลาในการประมวลผล

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* เป็นบิตมาสก์ ดังนั้นคุณสามารถรวมรูปแบบที่รองรับได้หลายจำนวน Aspose.BarCode รองรับ **สัญลักษณ์บาร์โค้ดกว่า 30 ประเภท** รวมถึง QR, DataMatrix, Code‑128, และ UPC‑A ทำให้สแกนเนอร์เดียวสามารถจัดการกับกรณีการใช้งานที่หลากหลาย เช่น การติดฉลากสินค้า, การตรวจสอบตั๋ว, และการยืนยันตัวตน

## macro PDF417 คืออะไรและเข้าถึงฟิลด์ของมันอย่างปลอดภัยได้อย่างไร

Macro PDF417 เป็นส่วนขยายของสัญลักษณ์ PDF417 ที่ทำให้ชุดข้อมูลขนาดใหญ่สามารถแบ่งออกเป็นหลายสัญลักษณ์บาร์โค้ดได้  
Macro PDF417 เพิ่มชุดคุณสมบัติเพิ่มเติมที่หลากหลาย อย่างไรก็ตาม ไม่ใช่บาร์โค้ดทุกอันจะมีทุกฟิลด์ การเข้าถึงคุณสมบัติที่ไม่มีอยู่สามารถทำให้เกิด `NullReferenceException` วิธีที่ปลอดภัยที่สุดคือการตรวจสอบแต่ละคุณสมบัติก่อนพิมพ์ เพื่อให้แอปพลิเคชันของคุณคงเสถียรแม้ไม่มีข้อมูล macro

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*ทำไมเรื่องนี้สำคัญ*: ในการใช้งานจริงคุณอาจได้รับบาร์โค้ด PDF417 ธรรมดาที่ไม่มีข้อมูล macro การตรวจสอบแบบป้องกันทำให้แอปของคุณทำงานต่อได้โดยไม่เกิดการหยุดทำงาน

## ข้อผิดพลาดทั่วไปและแนวทางปฏิบัติที่ดีที่สุด

| ปัญหา | สาเหตุ | วิธีแก้แนะนำ |
|-------|--------|-----------------|
| เส้นทางรูปภาพไม่ถูกต้อง | `BarCodeReader` จะโยนข้อยกเว้นไฟล์ไม่พบก่อนทำการถอดรหัสใด ๆ | ใช้ `Path.Combine` และตรวจสอบว่าไฟล์มีอยู่ด้วย `File.Exists` |
| ภาพความละเอียดต่ำ | ตัวถอดรหัสไม่สามารถหาขอบบาร์โค้ดได้ ส่งผลให้ไม่มีการตรวจจับ | กำหนดความละเอียดขั้นต่ำที่ 300 dpi เพื่อผลลัพธ์ที่เชื่อถือได้ |
| บาร์โค้ดหมุน > 45° |หลายไลบรารีสมมติว่าบาร์โค้ดอยู่ในแนวตั้งตรง | เปิดใช้งาน `reader.RecognitionOptions.RotateImage = true` หากภาพอาจถูกหมุน |
| ฟิลด์ macro ขาดหาย | การพยายามอ่านคุณสมบัติที่เป็น null จะทำให้แอปพัง | ตรวจสอบ `null` เสมอก่อนเข้าถึงคุณสมบัติ macro |
| การประมวลผลเป็นชุดใหญ่ | การสร้างตัวอ่านใหม่สำหรับแต่ละไฟล์เพิ่มภาระ | ใช้อินสแตนซ์ `BarCodeReader` เดียวกับสตรีมต่าง ๆ เมื่อประมวลผลหลายภาพ |

## ทำไมต้องใช้ Aspose.BarCode สำหรับเครื่องสแกนบาร์โค้ดคอนโซล?

Aspose.BarCode สามารถถอดรหัส **บาร์โค้ดกว่า 30 ประเภท** และประมวลผลภาพขนาดสูงสุด **200 MP** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้ได้อัตราผ่านการทำงาน **150 เฟรมต่อวินาที** บน CPU 3.2 GHz ปกติ ความสามารถเชิงปริมาณเหล่านี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับโซลูชันสแกนแบบปริมาณสูงและติดตั้งในสถานที่ซึ่งความหน่วงและความแม่นยำเป็นสิ่งสำคัญ

## สิ่งที่คุณควรเรียนต่อไปคืออะไร

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ

- [วิธีอ่านบาร์โค้ด DataMatrix ด้วย Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [อ่านบาร์โค้ด DataMatrix C# – สร้างโหมด DataMatrix (อัตโนมัติ)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [อ่านบาร์โค้ดจากภาพ – เชี่ยวชาญการสกัดพื้นที่บาร์โค้ดใน Java ด้วย Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้สแกนเนอร์นี้ในสภาพแวดล้อมการผลิตได้หรือไม่?**  
ตอบ: ใช่. ซื้อไลเซนส์ Aspose.BarCode เชิงพาณิชย์เพื่อเอาน้ำลายน้ำการประเมินออกและรับการสนับสนุนเต็มรูปแบบ

**ถาม: ไลบรารีทำงานบน Linux และ macOS หรือไม่?**  
ตอบ: แน่นอน. Aspose.BarCode for .NET เป็นแบบข้ามแพลตฟอร์มและทำงานบน .NET 6+ บน Windows, Linux, และ macOS

**ถาม: จะจัดการกับภาพขนาดใหญ่มากโดยไม่ใช้หน่วยความจำหมดได้อย่างไร?**  
ตอบ: ใช้คอนสตรัคเตอร์ `LoadOptions` เพื่อเปิดโหมดสตรีมมิ่ง ซึ่งจะประมวลผลภาพเป็นชิ้นส่วนแทนการโหลดทั้งหมดเข้าสู่ RAM

**ถาม: สามารถถอดรหัสภาพที่เข้ารหัสหรือป้องกันด้วยรหัสผ่านได้หรือไม่?**  
ตอบ: ตัวอ่านสามารถจัดการกับภาพที่เข้ารหัสด้วยรูปแบบรหัสผ่านมาตรฐานของ PNG/JPEG; เพียงให้รหัสผ่านผ่าน `reader.ImagePassword`

**ถาม: ถ้าบาร์โค้ดของฉันเสียหายบางส่วนจะทำอย่างไร?**  
ตอบ: เปิดใช้งานตัวเลือกการแก้ไขข้อผิดพลาด เช่น `reader.RecognitionOptions.CorrectErrors = true` เพื่อเพิ่มความทนทานต่อความเสียหายหรือสัญญาณรบกวน

---

**อัปเดตล่าสุด:** 2026-10-14  
**ทดสอบกับ:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีอ่าน Pdf417 ใน C ตัวอย่างตัวอ่านบาร์โค้ดเต็มรูปแบบ](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [อ่านหลายบาร์โค้ด C คู่มือเต็มรูปแบบกับ Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [ถอดรหัสบาร์โค้ดจากภาพด้วยตัวอย่าง C Barcode Reader](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}