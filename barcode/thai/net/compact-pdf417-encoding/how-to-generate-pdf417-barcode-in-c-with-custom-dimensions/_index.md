---
category: general
date: 2026-09-07
description: สร้างบาร์โค้ด PDF417 ด้วย C# และเรียนรู้วิธีตั้งค่าขนาดบาร์โค้ดเพื่อการควบคุมที่แม่นยำ
  ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างภาพ PNG
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: th
lastmod: 2026-09-07
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# และเรียนรู้วิธีตั้งขนาดบาร์โค้ด บทเรียนนี้แสดงตัวอย่างที่สมบูรณ์และสามารถรันได้
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – คู่มือเต็มพร้อมขนาด
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยขนาดที่กำหนดเอง
url: /th/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยขนาดที่กำหนดเอง

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คู่มือนี้จะแสดงให้คุณเห็นขั้นตอนอย่างละเอียด คุณจะได้เห็นตัวอย่างที่ทำงานได้เต็มรูปแบบซึ่งสร้างภาพ PNG พร้อมให้คุณควบคุมขนาดของบาร์โค้ด

การสร้างบาร์โค้ด PDF417 เป็นความต้องการทั่วไปสำหรับระบบสินค้าคงคลัง, บัตรโดยสาร, และเอกสารที่ต้องการความปลอดภัย ในบทเรียนนี้คุณยังจะได้เรียนรู้ **วิธีตั้งค่าขนาดของบาร์โค้ด** เพื่อให้ผลลัพธ์ตรงกับความต้องการการจัดวางของคุณ

## สิ่งจำเป็นก่อนเริ่ม

- .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า ติดตั้งแล้ว  
- Visual Studio 2022 (หรือ IDE ที่รองรับ C# ใดก็ได้)  
- แพ็คเกจ NuGet **Aspose.BarCode for .NET** (หรือไลบรารีที่เข้ากันได้ซึ่งสนับสนุน PDF417)  

คุณสามารถเพิ่มแพ็คเกจด้วยคำสั่งต่อไปนี้:

```bash
dotnet add package Aspose.BarCode
```

## ขั้นตอนที่ 1: สร้างตัวสร้างบาร์โค้ด PDF417

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภท `EncodeTypes.Pdf417` และข้อความที่คุณต้องการเข้ารหัส วัตถุตัวสร้างนี้จะเก็บการตั้งค่าทั้งหมดของบาร์โค้ด

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**ทำไมเรื่องนี้ถึงสำคัญ:** enum `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้สัญลักษณ์ PDF417 ซึ่งรองรับข้อมูลขนาดใหญ่และการแก้ไขข้อผิดพลาด สตริงข้อความสามารถมีอักขระ Unicode ได้ ดังนั้นคุณจึงสามารถเข้ารหัสสัญลักษณ์ระหว่างประเทศได้โดยไม่ต้องทำงานเพิ่มเติม

## ขั้นตอนที่ 2: วิธีตั้งค่าขนาดของบาร์โค้ด

การควบคุมขนาดของแต่ละโมดูล (สี่เหลี่ยมสีดำ/สีขาวที่เล็กที่สุด) กำหนดความละเอียดโดยรวมของภาพ คุณสมบัติ `XDimension.Pixels` กำหนดความกว้างเป็นพิกเซลของหนึ่งโมดูล

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**ทำไมเรื่องนี้ถึงสำคัญ:** `XDimension` ที่ใหญ่ขึ้นให้ภาพที่มีความละเอียดสูงกว่า ซึ่งเหมาะสำหรับการพิมพ์หรือสแกนจากระยะไกล ในทางกลับกันค่าที่เล็กลงจะลดขนาดไฟล์สำหรับการใช้งานบนเว็บ

## ขั้นตอนที่ 3: กำหนดรูปแบบ PDF417 (คอลัมน์และแถว)

PDF417 ให้คุณปรับรูปแบบเมทริกซ์โดยระบุจำนวนคอลัมน์และแถว ซึ่งอาจส่งผลต่อความอ่านง่ายและขนาดทางกายภาพของบาร์โค้ด

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**ทำไมเรื่องนี้ถึงสำคัญ:** การปรับคอลัมน์และแถวช่วยให้คุณใส่บาร์โค้ดลงในพื้นที่ที่กำหนดหรือให้ตรงกับข้อกำหนดอัตราส่วนของสแกนเนอร์ ไลบรารีจะเพิ่มพื้นที่ว่างโดยอัตโนมัติหากข้อมูลไม่เต็มเมทริกซ์

## ขั้นตอนที่ 4: บันทึกบาร์โค้ดเป็นภาพ PNG

สุดท้ายให้เขียนบาร์โค้ดที่สร้างขึ้นลงไฟล์ PNG ซึ่งรักษาคุณภาพแบบไม่มีการสูญเสีย ทำให้เหมาะสำหรับการประมวลผลต่อไป

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

เมื่อคุณรันโปรแกรม ไฟล์ `Pdf417Layout.png` จะปรากฏในโฟลเดอร์ผลลัพธ์ของโครงการ ภาพจะมีลักษณะดังนี้:

![ภาพบาร์โค้ด PDF417 ที่สร้างด้วยขนาดที่กำหนดเอง](og_image_placeholder.png)

*ข้อความแทนภาพ: ภาพบาร์โค้ด PDF417 ที่สร้างด้วยขนาดที่กำหนดเอง*  

**ทำไมเรื่องนี้ถึงสำคัญ:** การบันทึกเป็น PNG ทำให้ขนาดโมดูลที่คุณตั้งค่าสามารถคงไว้ได้ ซึ่งสำคัญต่อแอปพลิเคชันสแกนต่อไป

## ตัวอย่างเต็มในบล็อกเดียว

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก วาง และรันได้โดยไม่ต้องแก้ไข (ยกเว้นเส้นทางการบันทึกหากต้องการเปลี่ยน)

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### ผลลัพธ์ที่คาดหวัง

- **ไฟล์:** `Pdf417Layout.png` (PNG, lossless)  
- **ขนาด:** กำหนดโดย `XDimension` (2 px) × เมทริกซ์ (คอลัมน์ × แถว)  
- **เนื้อหา:** บาร์โค้ด PDF417 ที่สแกนได้ซึ่งเข้ารหัสสตริง Unicode `Åspóse.Barcóde©`

## คำถามทั่วไปและกรณีขอบ

### ถ้าฉันต้องการภาพขนาดใหญ่สำหรับการพิมพ์?

เพิ่มค่า `XDimension.Pixels` เป็น 4 หรือ 5 ค่าที่ใหญ่ขึ้นจะสร้างบาร์โค้ดที่มีความละเอียดสูงกว่า แต่ขนาดไฟล์ก็จะเพิ่มขึ้นด้วย

### ฉันสามารถเข้ารหัสข้อมูลมากกว่าตัวอย่างได้หรือไม่?

ได้ PDF417 สามารถบรรจุได้สูงสุด 1,850 ตัวอักษร เพียงเปลี่ยนอาร์กิวเมนต์ข้อความในคอนสตรัคเตอร์ `BarcodeGenerator` หากข้อมูลเกินความจุของเมทริกซ์ ไลบรารีจะเพิ่มแถวโดยอัตโนมัติ

### การแก้ไขข้อผิดพลาดทำงานอย่างไร?

PDF417 มีการแก้ไขข้อผิดพลาดในตัว คุณสามารถปรับระดับได้โดยใช้:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

ระดับที่สูงขึ้นจะเพิ่มความทนทานแต่ทำให้บาร์โค้ดใหญ่ขึ้น

### ถ้าบาร์โค้ดดูเบลอบนหน้าจอ?

ตรวจสอบให้แน่ใจว่า DPI ของภาพที่ส่งออกตรงกับสภาพแวดล้อมการแสดงผล คุณสามารถตั้งค่า DPI เมื่อบันทึกได้:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## เคล็ดลับระดับมืออาชีพ

- **เคล็ดลับ:** ควรทดสอบบาร์โค้ดที่สร้างขึ้นกับสแกนเนอร์จริงที่คุณจะใช้เสมอ เนื่องจากอุปกรณ์ต่าง ๆ มีความทนทานต่อขนาดโมดูลและโซนเงียบที่แตกต่างกัน  
- **ระวัง:** ค่า `XDimension` ที่เล็กมาก (< 1 px) อาจแสดงเป็นเส้นที่มองไม่เห็นบนหน้าจอที่มี DPI สูง  
- **คำแนะนำสำหรับเว็บแอป:** ให้บริการ PNG พร้อมหัวข้อ `Cache-Control: public, max-age=86400` เพื่อลดภาระการสร้างซ้ำหลายครั้ง

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด PDF417** ใน C# และตั้งค่า **ขนาดของบาร์โค้ด** อย่างแม่นยำเพื่อให้ตรงกับความต้องการใด ๆ ตัวอย่างเต็มที่ทำงานได้แสดงการสร้างภาพ PNG ด้วยการจัดคอลัมน์/แถวและขนาดโมดูลที่กำหนดเอง พร้อมสำหรับการพิมพ์หรือการแจกจ่ายดิจิทัล

### ขั้นตอนต่อไป

- สำรวจ **วิธีสร้างบาร์โค้ด PDF417** ด้วยรูปแบบภาพต่าง ๆ (JPEG, BMP)  
- เรียนรู้ **วิธีตั้งค่าขนาดของบาร์โค้ด** อย่างไดนามิกตามข้อมูลที่ผู้ใช้ป้อนหรือ DPI ของอุปกรณ์  
- ผสานการสร้างบาร์โค้ดเข้ากับ ASP.NET Core API เพื่อให้บริการบาร์โค้ดตามความต้องการ  

คุณสามารถทดลองตั้งค่า PDF417 อื่น ๆ เช่น การแก้ไขข้อผิดพลาด, ระยะขอบ, และสีได้ตามต้องการ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งต่อไปที่คุณควรเรียนรู้

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดที่ทำงานได้ครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานแบบอื่นในโปรเจกต์ของคุณ

- [วิธีตั้งค่าระดับข้อผิดพลาดในบาร์โค้ด PDF417 – คู่มือเต็ม](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [วิธีบันทึกบาร์โค้ดใน C# – สร้างบาร์โค้ด PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [สร้างบาร์โค้ด PDF417 ใน C# – คู่มือเต็ม](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}