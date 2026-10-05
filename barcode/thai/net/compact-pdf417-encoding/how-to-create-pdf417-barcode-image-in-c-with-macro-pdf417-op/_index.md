---
category: general
date: 2026-09-13
description: เรียนรู้วิธีสร้างภาพบาร์โค้ด PDF417 ด้วย C# โดยใช้ BarcodeGenerator และตัวเลือก
  Macro PDF417 โค้ดทีละขั้นตอน เคล็ดลับ และตัวอย่างเต็มรูปแบบ
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: th
lastmod: 2026-09-13
og_description: สร้างภาพบาร์โค้ด PDF417 ใน C# ด้วย BarcodeGenerator. ทำตามบทแนะนำโดยละเอียดนี้เพื่อกำหนดค่าตัวเลือก
  Macro PDF417 และบันทึกบาร์โค้ดเป็นไฟล์ PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: สร้างภาพบาร์โค้ด PDF417 ด้วย C# – คู่มือฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: วิธีสร้างภาพบาร์โค้ด PDF417 ใน C# ด้วยตัวเลือก Macro PDF417
url: /th/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ด PDF417 ใน C# ด้วยตัวเลือก Macro PDF417

หากคุณต้องการ **สร้างภาพบาร์โค้ด PDF417** ใน C# คู่มือนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าต้องทำอย่างไรโดยใช้ **คลาส BarcodeGenerator** ไม่ว่าคุณจะกำลังสร้างระบบติดตามเอกสารหรือเข้ารหัสไฟล์ขนาดใหญ่ คำแนะนำขั้นตอนต่อขั้นตอนด้านล่างครอบคลุมทุกอย่างตั้งแต่การตั้งค่าตัวเลือก Macro PDF417 จนถึงการบันทึก PNG สุดท้าย

การสร้างบาร์โค้ดเป็นเรื่องง่ายเมื่อคุณเข้าใจพารามิเตอร์สำคัญ ในบทเรียนนี้คุณจะได้เรียนรู้วิธี:

* เริ่มต้น `BarcodeGenerator` สำหรับ **Macro PDF417**.
* ปรับขนาดโมดูลของบาร์โค้ด (`XDimension`).
* กำหนดค่าการตั้งค่าเฉพาะส่วนเช่น file ID, segment ID, และ checksum.
* บันทึกผลลัพธ์เป็น **รูปแบบภาพบาร์โค้ด** (PNG) ที่สามารถแสดงใน UI ใดก็ได้.

ข้อกำหนดเบื้องต้นเพียงอย่างเดียวคือสภาพแวดล้อมการพัฒนา .NET (Visual Studio 2022 หรือใหม่กว่า) และแพคเกจ NuGet Aspose.BarCode for .NET ซึ่งให้ API `BarcodeGenerator` ที่ใช้ในตัวอย่าง

---

## วิธีสร้างภาพบาร์โค้ด PDF417 ใน C# – ภาพรวม

การสร้างภาพบาร์โค้ด PDF417 ประกอบด้วยสี่ขั้นตอนเชิงตรรกะ:

1. **สร้างตัวสร้าง** – สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วย `EncodeTypes.MacroPdf417` และข้อมูลที่คุณต้องการเข้ารหัส.  
2. **กำหนดขนาดโมดูล** – ตั้งค่า `XDimension.Pixels` เพื่อควบคุมความกว้างจริงของแต่ละองค์ประกอบของบาร์โค้ด.  
3. **กำหนดค่าตัวเลือก Macro PDF417** – ระบุจำนวนคอลัมน์, ตัวระบุไฟล์, หมายเลขส่วน, และ checksum ที่เป็นตัวเลือก.  
4. **บันทึกบาร์โค้ด** – เขียนภาพที่สร้างลงดิสก์โดยใช้ **รูปแบบภาพบาร์โค้ด** ที่รองรับ เช่น PNG.  

แต่ละขั้นตอนจะอธิบายอย่างละเอียดด้านล่าง พร้อมโค้ด C# ที่สมบูรณ์และสามารถรันได้

---

## ขั้นตอนที่ 1: เริ่มต้น BarcodeGenerator สำหรับ Macro PDF417

บรรทัดแรกสร้างอ็อบเจ็กต์ `BarcodeGenerator` ที่ทราบว่าต้องสร้างบาร์โค้ด **Macro PDF417** ตัวสร้างรับอาร์กิวเมนต์สองค่า: ประเภทการเข้ารหัสและสตริงข้อมูลดิบ

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**ทำไมจึงสำคัญ:**  
`EncodeTypes.MacroPdf417` บอกไลบรารีให้จัดการบาร์โค้ดเป็นคอนเทนเนอร์หลายส่วน ซึ่งจำเป็นเมื่อคุณต้องแบ่งไฟล์ขนาดใหญ่เป็นหลายสัญลักษณ์ อินสแตนซ์ `BarcodeGenerator` เป็นแบบ disposable ดังนั้นบล็อก `using` จะรับประกันว่าทรัพยากรที่ไม่ได้จัดการทั้งหมดจะถูกปล่อยหลังจากบันทึกภาพ

---

## ขั้นตอนที่ 2: ตั้งค่าขนาดโมดูลของบาร์โค้ด (XDimension)

`XDimension` ควบคุมความกว้างเป็นพิกเซลของโมดูลบาร์โค้ดหนึ่งตัว (แถบสีดำหรือสีขาวที่เล็กที่สุด) ค่า **2 พิกเซล** ให้ภาพที่กระชับแต่ยังอ่านได้

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**เคล็ดลับปฏิบัติ:**  
หากเครื่องพิมพ์เป้าหมายของคุณมี DPI ต่ำ ให้เพิ่มจำนวนพิกเซล (เช่น `3` หรือ `4`) เพื่อหลีกเลี่ยงการเบลอ ในทางกลับกันสำหรับการแสดงบนหน้าจอคุณสามารถลดค่าลงเพื่อให้ไฟล์มีขนาดเล็กลง

---

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกเฉพาะของ Macro PDF417

Macro PDF417 เพิ่มเมตาดาต้าที่ทำให้สแกนเนอร์สามารถสร้างไฟล์ต้นฉบับจากหลายส่วนของบาร์โค้ด ตัวเลือกที่พบบ่อยที่สุดคือ:

| Property | Meaning |
|----------|---------|
| `Columns` | จำนวนคอลัมน์ในแต่ละสัญลักษณ์ (ส่งผลต่อความกว้าง). |
| `MacroPdf417FileID` | ตัวระบุที่ไม่ซ้ำสำหรับไฟล์ทั้งหมด. |
| `MacroPdf417SegmentID` | ดัชนีของส่วนปัจจุบัน (เริ่มที่ 1). |
| `MacroPdf417SegmentsCount` | จำนวนส่วนทั้งหมดที่ประกอบเป็นไฟล์. |
| `MacroPdf417FileName` | ชื่อไฟล์ต้นฉบับ (เป็นตัวเลือก, เพื่อการแสดงผล). |
| `MacroPdf417Checksum` | Checksum 16‑บิตที่เป็นตัวเลือกสำหรับการตรวจสอบความสมบูรณ์. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**ทำไมการตั้งค่าเหล่านี้จึงสำคัญ:**  
- **Columns** มีผลต่อความอ่านง่ายและมิติของภาพโดยรวม.  
- **FileID** ต้องเหมือนกันในทุกส่วนเพื่อให้ตัวถอดรหัสรู้ว่าพวกมันเป็นส่วนของไฟล์เดียวกัน.  
- **SegmentID** และ **SegmentsCount** ช่วยให้สแกนเนอร์จัดลำดับชิ้นส่วนได้อย่างถูกต้อง.  
- **FileName** และ **Checksum** เป็นตัวเลือกแต่ช่วยปรับปรุงประสบการณ์ผู้ใช้และความสมบูรณ์ของข้อมูล.

**กรณีขอบ:** หากคุณสร้างมากกว่า 999 ส่วน ฟิลด์ `SegmentID` จะ overflow; ให้แบ่งข้อมูลเป็นหลายไฟล์แทน

---

## ขั้นตอนที่ 4: บันทึกบาร์โค้ดที่สร้างเป็นภาพ PNG

ขั้นตอนสุดท้ายเขียนบาร์โค้ดลงดิสก์ `BarCodeImageFormat.Png` สร้างภาพ loss‑less ที่ทำงานได้กับเว็บ, เดสก์ท็อป, และแพลตฟอร์มมือถือ

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**รูปแบบทางเลือก:**  
คุณสามารถแทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp`, หรือ `Gif` หากระบบต่อไปของคุณต้องการรูปแบบเฉพาะ โปรดจำไว้ว่า JPEG จะสร้าง artefacts การบีบอัดที่อาจลดความน่าเชื่อถือของการสแกน

**ผลลัพธ์ที่คาดหวัง:**  
ไฟล์ `MacroPdf417.png` จะมีบาร์โค้ด PDF417 แบบหลายส่วนที่คอนทราสต์สูง เมื่อเปิดดูควรคล้ายกับภาพประกอบด้านล่าง

![ตัวอย่างการสร้างภาพบาร์โค้ด PDF417](image.png){: .align-center alt="ตัวอย่างการสร้างภาพบาร์โค้ด PDF417 ที่สร้างโดยโค้ด C#"}

---

## โค้ดต้นฉบับเต็ม – พร้อมคัดลอกและรัน

ด้านล่างเป็นโปรแกรมที่สมบูรณ์และเป็นอิสระ มันรวมถึง `using` directives ที่จำเป็น, เมธอด `Main`, และคอมเมนต์ที่อธิบายแต่ละบรรทัดที่ไม่ชัดเจน

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**การรันโปรแกรม:**  

1. สร้างโปรเจกต์คอนโซล .NET 6 (หรือใหม่กว่า) ใหม่.  
2. เพิ่มแพคเกจ NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. แทนที่ `Program.cs` ที่สร้างขึ้นด้วยโค้ดด้านบน.  
4. ปรับ `outputPath` ให้เป็นโฟลเดอร์ที่คุณมีสิทธิ์เขียน.  
5. สร้างและรัน – คอนโซลจะยืนยันตำแหน่งของภาพ.

---

## คำถามทั่วไป & การแก้ไขปัญหา

| Question | Answer |
|----------|--------|
| *ถ้าบาร์โค้ดกว้างเกินกว่าสติ๊กเกอร์ของฉันจะทำอย่างไร?* | ลด `Columns` หรือเพิ่ม `XDimension.Pixels` เพื่อปรับสมดุลระหว่างความกว้างและความอ่านง่าย. |
| *ฉันจำเป็นต้องตั้งค่า checksum หรือไม่?* | Checksum เป็นตัวเลือก |

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลรวมถึงตัวอย่างโค้ดที่ทำงานได้เต็มรูปแบบพร้อมคำอธิบายขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้แบบทางเลือกในโครงการของคุณเอง

- [สร้างบาร์โค้ด PDF417 ใน C# – คู่มือขั้นตอนเต็ม](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [สร้างเมตาดาต้าบาร์โค้ด PDF417 ใน C# – คู่มือขั้นตอนเต็ม](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [สร้างบาร์โค้ดพร้อมข้อความ – คู่มือ Macro PDF417 เต็มรูปแบบ](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}