---
category: general
date: 2026-09-10
description: สร้างบาร์โค้ด PDF417 ด้วย C# อย่างรวดเร็ว เรียนรู้วิธีเปิดใช้งานโหมดคอมแพคต์
  ตั้งค่าคอลัมน์ และสร้างไฟล์ PNG ด้วย BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: th
lastmod: 2026-09-10
og_description: สร้างบาร์โค้ด PDF417 ด้วย C# โดยเปิดใช้งานโหมดคอมแพคท์ ตั้งค่าคอลัมน์
  และบันทึกเป็น PNG. ทำตามคู่มือขั้นตอนโดยละเอียด.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: สร้างบาร์โค้ด PDF417 ด้วย C# – บทแนะนำโหมดคอมแพคท์
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยโหมดบีบอัด
url: /th/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด PDF417 ใน C# ด้วยโหมดคอมแพคท์

หากคุณต้องการ **สร้างบาร์โค้ด PDF417** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงให้คุณเห็นขั้นตอนอย่างละเอียด คุณจะได้เรียนรู้วิธี **เปิดใช้งานโหมดคอมแพคท์**, ตั้งค่าจำนวนคอลัมน์, และบันทึกผลลัพธ์เป็นภาพ PNG ด้วยไลบรารี BarcodeGenerator C#.

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับการติดตามสินค้าคงคลัง, ระบบตั๋ว, และแอปสแกนบนมือถือ เมื่อจบบทเรียนนี้คุณจะมีตัวอย่างที่ทำงานได้เองซึ่งสร้างบาร์โค้ด PDF417 แบบคอมแพคท์พร้อมใช้งานในขั้นตอนการผลิต.

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+)
* เวอร์ชันล่าสุดของไลบรารี **BarcodeGenerator** (เช่น Aspose.BarCode for .NET)
* IDE หรือโปรแกรมแก้ไข เช่น Visual Studio 2022 หรือ VS Code
* สิทธิ์การเขียนไปยังโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก

ไม่จำเป็นต้องติดตั้งแพคเกจ NuGet เพิ่มเติมนอกจากไลบรารีบาร์โค้ดเอง.

## ขั้นตอนที่ 1: สร้างตัวสร้างบาร์โค้ด PDF417

ขั้นตอนแรกคือการสร้างอ็อบเจกต์ `BarcodeGenerator` ด้วยค่า enum `EncodeTypes.Pdf417` และข้อความที่คุณต้องการเข้ารหัส อ็อบเจกต์นี้จะเป็นตัวควบคุมกระบวนการสร้างทั้งหมด.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*ทำไมส่วนนี้สำคัญ*: ค่า `EncodeTypes.Pdf417` บอกไลบรารีให้ใช้สัญลักษณ์ PDF417, ส่วนอาร์กิวเมนต์ที่สองเป็นข้อมูลที่ต้องเข้ารหัส คุณสามารถเปลี่ยน `"Compact mode"` เป็นสตริงอัลฟานูเมอริกใดก็ได้ที่ต้องการเข้ารหัส.

## ขั้นตอนที่ 2: ตั้งค่ามิติ X (ความกว้างโมดูล)

มิติ X ควบคุมความกว้างของสี่เหลี่ยมจัตุรัสขนาดเล็ก (โมดูล) ในบาร์โค้ด ค่าที่เล็กลงจะทำให้ภาพกระชับขึ้น ซึ่งมีประโยชน์เมื่อพื้นที่จำกัด.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

ค่าที่ `2` พิกเซลเป็นการสมดุลที่ดีระหว่างความอ่านง่ายและความกระชับสำหรับสแกนเนอร์ที่ใช้หน้าจอส่วนใหญ่.

## ขั้นตอนที่ 3: กำหนดจำนวนคอลัมน์

PDF417 สามารถจัดข้อมูลในรูปแบบตารางของแถวและคอลัมน์ การปรับจำนวนคอลัมน์จะเปลี่ยนอัตราส่วนของบาร์โค้ด.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

การตั้งค่า **how to set columns** เป็น `3` จะให้บาร์โค้ดสั้นและกว้างที่เหมาะกับป้ายสติ๊กเกอร์ คุณสามารถทดลองค่าตั้งแต่ `1` ถึง `30` ขึ้นอยู่กับปริมาณข้อมูลและสแกนเนอร์เป้าหมาย.

## ขั้นตอนที่ 4: เปิดใช้งานโหมดคอมแพคท์

โหมดคอมแพคท์จะลบแถวเติมที่ไม่จำเป็น ทำให้บาร์โค้ดเล็กลงโดยไม่สูญเสียความสมบูรณ์ของข้อมูล นี่คือขั้นตอนสำคัญสำหรับ **PDF417 แบบคอมแพคท์**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

เมื่อ `Truncate` เป็น `true` ไลบรารีจะคำนวณจำนวนแถวขั้นต่ำที่ต้องการเก็บข้อมูลโดยอัตโนมัติ ซึ่งทำให้ภาพสุดท้ายดู “กระชับ”.

## ขั้นตอนที่ 5: บันทึกบาร์โค้ดที่สร้างเป็นภาพ PNG

สุดท้ายให้เขียนบาร์โค้ดลงไฟล์ PNG ซึ่ง PNG จะรักษาความคมของขอบที่จำเป็นสำหรับการสแกนที่เชื่อถือได้.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางแบบ absolute หรือ relative ที่แอปพลิเคชันของคุณสามารถเขียนได้ หลังจากรันแล้วคุณจะพบไฟล์ `CompactPdf417.png` ที่มีบาร์โค้ดอยู่.

### โค้ดเต็ม

การรวมขั้นตอนทั้งหมดเข้าด้วยกันจะได้โปรแกรมเดียวที่พร้อมรัน:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

การรันโปรแกรมนี้จะสร้างไฟล์ `CompactPdf417.png` ในโฟลเดอร์เดียวกับไฟล์ executable เปิดภาพด้วยโปรแกรมดูใดก็ได้ คุณควรเห็นบาร์โค้ด PDF417 ที่หนาแน่นและคอนทราสต์สูงพร้อมสแกน.

## วิธีเปิดใช้งานโหมดคอมแพคท์ในสถานการณ์อื่น

* **การสร้างเป็นชุด** – เมื่อสร้างบาร์โค้ดจำนวนมาก ให้ตั้งค่า `Truncate` ครั้งเดียวบนตัวสร้างและใช้ซ้ำสำหรับ payload ใหม่แต่ละอัน.
* **รูปแบบภาพที่ต่างกัน** – เมธอด `Save` เดียวกันทำงานกับ `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Bmp` หากต้องการไฟล์ประเภทอื่น.
* **จำนวนคอลัมน์แบบไดนามิก** – หากความยาวของสตริงที่เข้ารหัสเปลี่ยนแปลง ให้คำนวณจำนวนคอลัมน์ที่เหมาะสมตามความยาวสตริงและความละเอียดของสแกนเนอร์.

## วิธีตั้งค่าคอลัมน์สำหรับกรณีการใช้งานเฉพาะ

* **การพิมพ์ป้าย** – ใช้จำนวนคอลัมน์ต่ำ (เช่น `2`‑`5`) เพื่อให้บาร์โค้ดสั้นพอที่จะพอดีกับป้ายแคบ.
* **การสแกนบนมือถือ** – จำนวนคอลัมน์สูง (`10`‑`15`) จะทำให้บาร์โค้ดสูงขึ้นซึ่งกล้องโทรศัพท์โฟกัสได้ง่ายขึ้น.
* **การแลกเปลี่ยนการแก้ไขข้อผิดพลาด** – คอลัมน์มากขึ้นจะลดจำนวนแถว ซึ่งอาจส่งผลต่อการแก้ไขข้อผิดพลาดในบาร์โค้ด ทดสอบกับสแกนเนอร์เป้าหมายเพื่อหาจุดที่เหมาะสม.

## ข้อผิดพลาดทั่วไปและเคล็ดลับมืออาชีพ

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| บาร์โค้ดอ่านไม่ออก | มิติ X ต่ำเกินไป (เช่น `1` พิกเซล) | เพิ่ม `XDimension.Pixels` อย่างน้อยเป็น `2` |
| ภาพใหญ่เกินไป | ตั้งค่าคอลัมน์สูงเกินไปสำหรับข้อมูลสั้น | ลด `Pdf417.Columns` หรือเปิดใช้งาน `Truncate` |
| ไฟล์ PNG ว่างเปล่า | โฟลเดอร์ปลายทางไม่มีหรือไม่มีสิทธิ์เขียน | ตรวจสอบให้โฟลเดอร์มีอยู่และกระบวนการมีสิทธิ์เขียน |
| สแกนเนอร์รายงาน “ข้อมูลเสียหาย” | ปิดการใช้งาน Truncate ขณะใช้คอลัมน์จำนวนมาก | เปิดใช้งาน `Truncate` หรือ ลดจำนวนคอลัมน์ |

## การตรวจสอบผลลัพธ์

คุณสามารถตรวจสอบบาร์โค้ดด้วยแอปสแกน PDF417 ใดก็ได้ (มีแอปฟรีหลายตัวบน Android/iOS) เปิดไฟล์ `CompactPdf417.png` ในแอปและยืนยันว่าข้อความที่ถอดรหัสตรงกับข้อมูลต้นฉบับ (“Compact mode”) หากข้อความไม่ตรง ให้ตรวจสอบค่า `Truncate` และการตั้งค่าคอลัมน์อีกครั้ง.

## ขั้นตอนต่อไป

* **ผสานกับ ASP.NET Core** – ส่งคืน PNG โดยตรงจาก action ของ controller แทนการบันทึกลงดิสก์.
* **เพิ่มข้อความที่อ่านได้โดยมนุษย์** – ใช้ `barcodeGenerator.Parameters.Barcode.CodeTextParameters` เพื่อแสดงสตริงที่เข้ารหัสใต้บาร์โค้ด.
* **สำรวจสัญลักษณ์อื่น** – คลาส `BarcodeGenerator` เดียวกันรองรับ QR, Code128, DataMatrix และอื่น ๆ เปลี่ยน `EncodeTypes` เพื่อทดลอง.

---

### สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด PDF417** ใน C# พร้อมกับ **เปิดใช้งานโหมดคอมแพคท์**, ควบคุม **วิธีตั้งค่าคอลัมน์**, และใช้ API **barcode generator C#** เพื่อ **สร้างบาร์โค้ด** ที่ตรงตามข้อจำกัดด้านขนาดในโลกจริง นำขั้นตอนเหล่านี้ไปใช้ในโครงการ .NET ใด ๆ ที่ต้องการบาร์โค้ดคอมแพคท์และความหนาแน่นสูง และขยายรูปแบบนี้ไปยังฟอร์แมตบาร์โค้ดอื่นตามต้องการ ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดที่ทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบอื่นในโครงการของคุณ.

- [สร้างบาร์โค้ด PDF417 ใน C# – คู่มือขั้นตอนเต็ม](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [วิธีตั้งค่าระดับข้อผิดพลาดในบาร์โค้ด PDF417 – คู่มือเต็ม](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [วิธีบันทึกบาร์โค้ดใน C# – สร้างบาร์โค้ด PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}