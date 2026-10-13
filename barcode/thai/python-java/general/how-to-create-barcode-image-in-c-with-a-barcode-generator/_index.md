---
category: general
date: 2026-10-02
description: สร้างภาพบาร์โค้ดใน C# ด้วยตัวสร้างบาร์โค้ด ควบคุมขนาดพิกเซลของบาร์โค้ดและปรับความสูงของบาร์โค้ดเพื่อกำหนดมิติที่ต้องการ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: th
lastmod: 2026-10-02
og_description: สร้างภาพบาร์โค้ดใน C# ด้วยเครื่องสร้างบาร์โค้ด เรียนรู้การตั้งค่าขนาดพิกเซลของบาร์โค้ด
  ปรับความสูงของบาร์โค้ด และกำหนดมิติที่กำหนดเองของบาร์โค้ด
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: สร้างภาพบาร์โค้ดใน C# – คู่มือการสร้างบาร์โค้ดและกำหนดขนาดตามต้องการ
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: วิธีสร้างภาพบาร์โค้ดใน C# ด้วยเครื่องสร้างบาร์โค้ด
url: /th/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดใน C# ด้วยตัวสร้างบาร์โค้ด

หากคุณต้องการ **สร้างภาพบาร์โค้ด** อย่างอัตโนมัติ คู่มือนี้จะแสดงวิธีแก้ไขที่สมบูรณ์พร้อมรันใน C# โดยใช้ตัวสร้างบาร์โค้ดคุณสามารถควบคุม **ขนาดพิกเซลของบาร์โค้ด**, **ปรับความสูงของบาร์โค้ด**, และกำหนด **ขนาดบาร์โค้ดแบบกำหนดเอง** โดยไม่ต้องออกจาก IDE ของคุณ

คุณจะได้เรียนรู้วิธีสร้างไฟล์ PNG สองไฟล์—หนึ่งไฟล์ที่มีความสูงของบาร์ 30 px และอีกไฟล์ที่มี 60 px—โดยคงความกว้างของโมดูลคงที่ ขั้นตอนเหล่านี้ทำงานกับบาร์โค้ดประเภทใดก็ได้ที่ไลบรารีสนับสนุน ดังนั้นคุณสามารถปรับใช้กับ QR code, Code 128 หรือสัญลักษณ์อื่น ๆ

## สิ่งที่คุณต้องการ

- .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังคอมไพล์ได้กับ .NET Framework 4.8)
- การอ้างอิงไปยังไลบรารีบาร์โค้ด (เช่น Aspose.BarCode for .NET หรือคลาส `BarcodeGenerator` ที่เข้ากันได้)
- ความรู้พื้นฐานของ C#
- สิทธิ์การเขียนไปยังโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้างบาร์โค้ดเพื่อ **สร้างภาพบาร์โค้ด**

แรกสุด ให้นำเข้า namespace ที่จำเป็นและสร้างอินสแตนซ์ของ `BarcodeGenerator` ตัวสร้างรับประเภทบาร์โค้ด (`EncodeTypes.DatabarOmniDirectional`) และสตริงข้อมูลที่คุณต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

การสร้างตัวสร้างเป็นพื้นฐานสำหรับ workflow **barcode generator c#** ใด ๆ มันจัดสรรแคนวาสการวาดภายในและเตรียมข้อมูลสำหรับการเรนเดอร์

## ขั้นตอนที่ 2: กำหนด **ขนาดพิกเซลของบาร์โค้ด** และความสูงบาร์เริ่มต้น

คุณภาพภาพสุดท้ายขึ้นอยู่กับสองพารามิเตอร์:

| พารามิเตอร์ | ความหมาย |
|-----------|---------|
| `XDimension.Pixels` | ความกว้างของโมดูลเดียว (องค์ประกอบสีดำ/ขาวที่เล็กที่สุด). |
| `BarHeight.Pixels` | ความสูงของบาร์สำหรับภาพปัจจุบัน. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

การคง **ขนาดพิกเซลของบาร์โค้ด** คงที่ขณะเปลี่ยนความสูงทำให้คุณสร้าง **ขนาดบาร์โค้ดแบบกำหนดเอง** ที่ตรงกับแนวทางแบรนด์หรือข้อกำหนดการสแกน

## ขั้นตอนที่ 3: บันทึกไฟล์ PNG แรก (ความสูง 30 px)

ตอนนี้ให้เขียนภาพลงดิสก์ เมธอด `Save` รับพาธไฟล์และรูปแบบภาพที่ต้องการ

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

ไฟล์ที่ได้เป็น **ภาพบาร์โค้ด** ที่มีความสูงบาร์ 30 px และความกว้างโมดูล 2 px เหมาะสำหรับป้ายเล็ก

## ขั้นตอนที่ 4: **ปรับความสูงของบาร์โค้ด** สำหรับเวอร์ชันขนาดใหญ่ขึ้น

เพื่อสร้างภาพที่สองที่มีขนาดภาพแตกต่าง เพียงแค่เปลี่ยนคุณสมบัติ `BarHeight.Pixels` เท่านั้น นี่แสดงให้เห็นว่าการ **ปรับความสูงของบาร์โค้ด** ทำได้ง่ายแค่ไหนโดยไม่ต้องสร้างตัวสร้างใหม่

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

การเปลี่ยนความสูงขณะคง **ขนาดพิกเซลของบาร์โค้ด** ทำให้บาร์คมชัดและอัตราส่วนโดยรวมคงที่

## ขั้นตอนที่ 5: บันทึกไฟล์ PNG ที่สอง (ความสูง 60 px)

สุดท้าย ให้บันทึกเวอร์ชันที่ใหญ่ขึ้น

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

ตอนนี้คุณมี **ขนาดบาร์โค้ดแบบกำหนดเอง** สองแบบที่บันทึกไว้เคียงกัน:

- `DatabarBarHeight30Pixels.png` – ความสูงบาร์ 30 px
- `DatabarBarHeight60Pixels.png` – ความสูงบาร์ 60 px

ภาพทั้งสองใช้ **ขนาดพิกเซลของบาร์โค้ด** เดียวกันที่ 2 px ทำให้ความสอดคล้องของภาพคงที่ในทุกขนาด

## ทำไมการตั้งค่าเหล่านี้ถึงสำคัญ

- **ขนาดพิกเซลของบาร์โค้ด** (`XDimension`) มีผลต่อความสามารถในการอ่านของสแกนเนอร์ ความกว้าง 2 px เป็นค่าเริ่มต้นทั่วไปที่สมดุลระหว่างขนาดไฟล์และความน่าเชื่อถือของการสแกน
- **ความสูงของบาร์** กำหนดความสูงของบาร์โค้ดบนป้าย บางสแกนเนอร์ในร้านค้าต้องการความสูงขั้นต่ำ; บางกรณีอนุญาตให้บาร์สูงกว่าเพื่อความสวยงาม
- การคงอินสแตนซ์ของตัวสร้างไว้ขณะปรับ `BarHeight` เพียงอย่างเดียวช่วยลดการจัดสรรหน่วยความจำและเร่งการประมวลผลเป็นชุด

## กรณีขอบและเคล็ดลับการปฏิบัติที่ดีที่สุด

| สถานการณ์ | แนวทางแนะนำ |
|-----------|----------------------|
| **รูปแบบภาพที่แตกต่าง** (JPEG, BMP) | เปลี่ยน `BarCodeImageFormat.Jpeg` หรือ `.Bmp` ในการเรียก `Save`. JPEG มีขนาดเล็กกว่าแต่อาจทำให้เกิด artefacts จากการบีบอัด. |
| **ผลลัพธ์ความละเอียดสูง** (เช่น 300 DPI) | เพิ่ม `XDimension.Pixels` อย่างสัดส่วน (เช่น 4 px) และปรับ `BarHeight.Pixels` เพื่อคงขนาดจริงเดียวกัน. |
| **สตริงข้อมูลแบบไดนามิก** | ห่อการสร้างตัวสร้างในเมธอดที่รับสตริงข้อมูลเป็นพารามิเตอร์ แล้วใช้อินสแตนซ์ `barcode` เดียวกันสำหรับการบันทึกหลายครั้ง. |
| **การสร้างเป็นชุดแบบปลอดภัยต่อเธรด** | สร้าง `BarcodeGenerator` แยกต่อเธรดหรือใช้พูลแบบ thread‑local เพื่อหลีกเลี่ยง race condition. |
| **ข้อผิดพลาดสิทธิ์ระบบไฟล์** | ตรวจสอบว่า `outputFolder` มีอยู่และกระบวนการมีสิทธิ์เขียน; จัดการ `IOException` อย่างเหมาะสม. |

## รายการซอร์สโค้ดเต็ม

ด้านล่างเป็นโปรแกรมเต็มรูปแบบที่สามารถคัดลอก วาง และรันได้

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### ผลลัพธ์ที่คาดหวัง

หลังจากรันโปรแกรม โฟลเดอร์ `YOUR_DIRECTORY` จะมีไฟล์ PNG สองไฟล์:

- **DatabarBarHeight30Pixels.png** – บาร์โค้ดขนาดกะทัดรัดเหมาะสำหรับป้ายเล็ก
- **DatabarBarHeight60Pixels.png** – เวอร์ชันขนาดใหญ่เหมาะสำหรับการใช้งานที่ต้องการความมองเห็นสูง

ไฟล์ทั้งสองสามารถเปิดด้วยโปรแกรมดูภาพใดก็ได้ พิมพ์ออก หรือฝังใน PDF

## สรุป

ตอนนี้คุณรู้วิธี **สร้างภาพบาร์โค้ด** ใน C# ด้วย **barcode generator c#**, ควบคุม **ขนาดพิกเซลของบาร์โค้ด**, **ปรับความสูงของบาร์โค้ด**, และสร้าง **ขนาดบาร์โค้ดแบบกำหนดเอง** ที่ตอบสนองความต้องการการสแกนหรือแบรนด์เฉพาะ ตัวอย่างนี้แสดงรูปแบบที่สะอาดและทำซ้ำได้ซึ่งสามารถขยายเป็นการประมวลผลเป็นชุดหรือสัญลักษณ์ต่าง ๆ

### สิ่งที่ควรสำรวจต่อไป

- [How to create barcode image in C# with adjustable height](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}