---
category: general
date: 2026-10-24
description: เรียนรู้วิธีสร้างบาร์โค้ด GS1 ใน ASP.NET ด้วย Aspose.BarCode คู่มือแบบขั้นตอนต่อขั้นตอนในการสร้างบาร์โค้ดจากสตริงและแสดงผลเป็น
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: th
lastmod: 2026-10-24
og_description: วิธีสร้างบาร์โค้ด GS1 ใน ASP.NET ด้วย Aspose.BarCode. ทำตามบทแนะนำนี้เพื่อสร้างบาร์โค้ดจากสตริง,
  กำหนดการตั้งค่าการแสดงผล, และบันทึกไฟล์ PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: วิธีสร้างบาร์โค้ด GS1 ใน ASP.NET – คู่มือ Aspose ฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: วิธีสร้างบาร์โค้ด GS1 ใน ASP.NET ด้วย Aspose.BarCode
url: /th/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด GS1 ใน ASP.NET ด้วย Aspose.BarCode

หากคุณต้องการ **วิธีสร้างบาร์โค้ด GS1** ในแอปพลิเคชัน ASP.NET คู่มือนี้จะแสดงขั้นตอนที่ชัดเจน คุณจะได้เห็นวิธีสร้างบาร์โค้ดจากสตริง, กำหนดลักษณะการแสดงผล, และบันทึกผลลัพธ์เป็นไฟล์ PNG

การสร้างบาร์โค้ด GS1 ไม่ต้องการตรรกะการเข้ารหัสแบบกำหนดเอง โดยการใช้ Aspose.BarCode คุณจะได้โซลูชันที่เชื่อถือได้และสอดคล้องมาตรฐาน ซึ่งทำงานบน .NET 6+ และเฟรมเวิร์กรุ่นก่อนหน้า บทแนะนำนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าโปรเจกต์จนถึงการตรวจสอบผลลัพธ์ เพื่อให้คุณสามารถคัดลอกโค้ดไปใช้ในโปรเจกต์เว็บของคุณได้โดยตรง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้แน่ใจว่าคุณมี:

* Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)
* .NET 6 SDK (หรือ .NET Framework 4.7.2 ขึ้นไป)
* ความรู้พื้นฐานเกี่ยวกับ ASP.NET Core หรือ ASP.NET Framework
* ไลเซนส์ Aspose.BarCode (รุ่นประเมินฟรีใช้สำหรับการทดสอบ)

ไม่จำเป็นต้องใช้ไลบรารีของบุคคลที่สามเพิ่มเติม เนื่องจาก Aspose.BarCode จัดการการเข้ารหัสและการเรนเดอร์ทั้งหมดภายใน

## ขั้นตอนที่ 1: สร้างโปรเจกต์ ASP.NET ใหม่

เปิด Visual Studio แล้วสร้าง **ASP.NET Core Web App** (เลือกเทมเพลต *Empty*) สำหรับโปรเจกต์ Web Forms แบบคลาสสิก โค้ดเดียวกันนี้ทำงานได้ในไฟล์ code‑behind

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

การรันโปรเจกต์ควรแสดงข้อความ *GS1 barcode generator is ready.* ในเบราว์เซอร์ ซึ่งเป็นการยืนยันว่าเว็บโฮสต์ทำงานได้

## ขั้นตอนที่ 2: ติดตั้ง Aspose.BarCode ผ่าน NuGet

เปิด **Package Manager Console** แล้วรันคำสั่ง:

```powershell
Install-Package Aspose.BarCode
```

แพ็กเกจจะเพิ่มเนมสเปซ `Aspose.BarCode.Generation` ซึ่งมีคลาส `BarcodeGenerator` ที่คุณจะใช้เพื่อ **generate barcode from string** คำสั่ง NuGet ยังอัปเดตไฟล์โปรเจกต์ด้วยการอ้างอิงที่จำเป็นอีกด้วย

## ขั้นตอนที่ 3: สร้างบาร์โค้ดอย่างง่ายจากสตริง

เพื่อแสดงการใช้งานพื้นฐาน ให้สร้างเมธอดช่วยเหลือที่คืนค่าอาร์เรย์ไบต์ PNG เมธอดนี้สามารถเรียกจากคอนโทรลเลอร์, หน้า Razor หรือ endpoint ใดก็ได้

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

ตอนนี้คุณสามารถเรียก `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` จาก endpoint ใดก็ได้และเขียนไบต์ผลลัพธ์ไปยัง HTTP response ได้ ซึ่งเป็นการสาธิตรูปแบบ **barcode generator asp.net** สำหรับสตริงใด ๆ

## ขั้นตอนที่ 4: วิธีสร้างบาร์โค้ด GS1 – ตัวอย่าง Micro PDF417

บาร์โค้ด GS1 ฝังตัวระบุแอปพลิเคชัน (AI) ที่บ่งบอกข้อมูลสินค้า Aspose.BarCode รองรับรูปแบบ GS1‑compatible ของ Micro PDF417 ซึ่งเหมาะสำหรับการแทนข้อมูลแบบกะทัดรัด

### 4.1 เตรียมสตริงข้อมูล GS1

ข้อมูล GS1 ต้องอยู่ในวงเล็บพร้อมรหัส AI ตัวอย่างสำหรับตัวระบุสินค้า (01) และหมายเลขล็อต (10) จะเป็นดังนี้:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

วงเล็บเป็นส่วนหนึ่งของมาตรฐาน Aspose.BarCode จะทำการพาร์สอัตโนมัติ

### 4.2 สร้างตัวสร้าง GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 เปิดให้เข้าถึงตัวสร้างผ่าน endpoint ของ ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

การเยี่ยมชม `https://localhost:5001/gs1barcode` จะสตรีม PNG ที่สร้างขึ้น ภาพตรงตามสเปค GS1 และไฟล์ยังถูกบันทึกลงดิสก์เพื่อใช้งานต่อไป

## ขั้นตอนที่ 5: การเรนเดอร์ประเภทบาร์โค้ดเพิ่มเติม

แนวทาง **create barcode with aspose** เดียวกันทำงานกับสัญลักษณ์อื่น ๆ ตัวอย่างสั้น ๆ ด้านล่างสร้าง QR code จาก URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

คุณสามารถสลับ `EncodeTypes.QR` กับ `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` หรือประเภทที่สนับสนุนอื่น ๆ พารามิเตอร์การแสดงผล (`XDimension`, `Resolution`, `Color`) สามารถกำหนดได้ผ่านอ็อบเจกต์ `Parameters`

## ขั้นตอนที่ 6: ข้อผิดพลาดทั่วไปและเคล็ดลับปฏิบัติที่ดีที่สุด

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **รูปแบบ AI ไม่ถูกต้อง** | การขาดวงเล็บหรือความยาว AI ที่ไม่ถูกต้องทำให้เกิดข้อผิดพลาดในการเข้ารหัส | ควรสร้างสตริง GS1 ให้ตรงตามมาตรฐานเสมอ ใช้วิธีช่วยเหลือในการต่อ AI |
| **คอลัมน์มากเกินไป** | Micro PDF417 รองรับได้เพียง 1‑4 คอลัมน์; การตั้งค่าเป็น 5 จะทำให้เกิดข้อยกเว้น | ตรวจสอบค่าคอลัมน์ก่อนกำหนด: `if (columns < 1 || columns > 4) throw …` |
| **ความละเอียดภาพต่ำ** | ค่าของ `XDimension` ที่เล็กเกินไปอาจทำให้บาร์โค้ดอ่านไม่ได้บนเครื่องพิมพ์ | สำหรับบาร์โค้ดพร้อมพิมพ์ ให้เพิ่ม `Resolution` (เช่น `generator.Parameters.Image.Resolution = 300`). |
| **ปัญหาเส้นทางไฟล์บน Linux** | การกำหนด backslash อย่างตายตัวทำให้เกิดปัญหาในโฮสต์ที่ไม่ใช่ Windows | ใช้ `Path.Combine` เพื่อสร้างเส้นทางไฟล์; มันจัดการตัวคั่นตามระบบปฏิบัติการ |
| **ยังไม่ได้ตั้งค่าไลเซนส์** | รุ่นทดลองฟรีจะใส่ลายน้ำหลังจาก 30 วัน | ตั้งค่าไลเซนส์ตั้งแต่ต้น: `new License().SetLicense("Aspose.BarCode.lic");` |

## ขั้นตอนที่ 7: ตรวจสอบบาร์โค้ดที่สร้างขึ้น

หลังจากรัน endpoint แล้ว เปิด PNG ด้วยโปรแกรมดูภาพใดก็ได้ เพื่อยืนยันว่าข้อมูล GS1 ถูกเข้ารหัสอย่างถูกต้อง คุณสามารถใช้แอปสแกนมือถือฟรีที่รองรับ GS1 Micro PDF417 (หลายแอปสแกนบาร์โค้ดมีสัญลักษณ์นี้) สแกนภาพ; แอปควรแสดงผล:

```
(01)12345678901234
(10)ABCD
```

หากสแกนเนอร์รายงานข้อผิดพลาด ให้ตรวจสอบรูปแบบ AI และจำนวนคอลัมน์อีกครั้ง

## สรุป

คุณได้เรียนรู้ **วิธีสร้างบาร์โค้ด GS1** ในสภาพแวดล้อม ASP.NET ด้วย Aspose.BarCode แล้ว บทแนะนำนี้ครอบคลุม:

* การตั้งค่าโปรเจกต์ ASP.NET และการติดตั้งแพ็กเกจ NuGet Aspose.BarCode  
* การใช้ **generate barcode from string** สำหรับบาร์โค้ดทั่วไป  
* การทำ **create barcode with aspose** เพื่อสร้างภาพ Micro PDF417 ที่สอดคล้องกับ GS1  
* การบันทึกภาพลงดิสก์และสตรีมผ่าน endpoint HTTP  

จากนี้คุณสามารถสำรวจสัญลักษณ์ GS1 อื่น ๆ (เช่น GS1 DataMatrix) หรือรวมตัวสร้างเข้ากับกระบวนการสั่งซื้อที่ใหญ่ขึ้น ทดลองปรับค่า `XDimension`, สี, และระดับการแก้ไขข้อผิดพลาดเพื่อให้ตรงกับแบรนด์และสภาพแวดล้อมการสแกนของคุณ

ขอให้เขียนโค้ดอย่างสนุกและให้แอปพลิเคชันของคุณพูดภาษาสากลของบาร์โค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [วิธีสร้างบาร์โค้ด code 128 ด้วย GS1 โดยใช้ Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [วิธีสร้าง Quiet Zone ของบาร์โค้ดสำหรับ ITF-14 ด้วย Aspose.BarCode สำหรับ .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [วิธีสร้างบาร์โค้ด ITF-14 .NET – บทแนะนำ Aspose.BarCode อย่างครบถ้วน](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}