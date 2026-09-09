---
date: 2026-05-24
description: เรียนรู้วิธีสร้างบาร์โค้ด Aztec .NET ด้วย Aspose.BarCode สำหรับ .NET
  โดยครอบคลุมโหมดสัญลักษณ์ Auto, FullRange, Compact และ Rune พร้อมคำแนะนำแบบขั้นตอนต่อขั้นตอน
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: ตัวอย่างโหมดสัญลักษณ์ Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้างบาร์โค้ด Aztec .NET ด้วย Aspose.BarCode
url: /th/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เชี่ยวชาญโหมดสัญลักษณ์ Aztec ด้วย Aspose.BarCode สำหรับ .NET

If you're looking to **create aztec barcode .net** quickly and reliably, Aspose.BarCode for .NET gives you a full‑featured API that works on .NET Framework, .NET Core and .NET 5/6+. In this tutorial we’ll explore the four Aztec Symbol Modes—Auto, FullRange, Compact, and Rune—showing you exactly how to switch between them and save the result as an image. By the end you’ll be able to embed Aztec barcodes in any .NET application with just a few lines of code.

## คำตอบสั้น
- **What library generates Aztec barcodes in .NET?** Aspose.BarCode for .NET.  
- **How many symbol modes does Aztec support?** Four: Auto, FullRange, Compact, and Rune.  
- **Do I need a license for development?** A free trial works for evaluation; a commercial license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, and .NET 6+.  
- **Can I output PNG, JPEG, or SVG?** Yes—any standard image format is supported.

## create aztec barcode .net คืออะไร?
`create aztec barcode .net` refers to the process of generating an Aztec two‑dimensional barcode using the Aspose.BarCode API in a .NET environment. The API handles encoding, symbol‑mode selection, and image rendering automatically, allowing developers to produce high‑quality barcodes without dealing with low‑level details such as error‑correction calculations or pixel manipulation.

## ทำไมต้องใช้ Aspose.BarCode สำหรับบาร์โค้ด Aztec?
Aspose.BarCode supports **30+ barcode symbologies** and can render images up to **10,000 × 10,000 px** without loading the whole file into memory. It processes a 500‑page document in under **2 seconds** on a typical server, making it ideal for high‑throughput enterprise scenarios.

## ข้อกำหนดเบื้องต้น

Before we get started, make sure you have the following prerequisites in place:

- A working knowledge of .NET development.  
- Visual Studio installed on your machine.  
- A copy of Aspose.BarCode for .NET. You can download it [here](https://releases.aspose.com/barcode/net/). You can also explore other Aspose products [here](https://releases.aspose.com/).

Now that you're all set, let's dive into the Aztec Symbol Mode examples.

## การนำเข้า Namespaces

First, you'll need to import the necessary namespaces to work with Aspose.BarCode for .NET. Open your Visual Studio project and add the following using statements at the top of your code file:

```csharp
using Aspose.BarCode.Generation;
```

With the namespaces in place, you can now start using Aspose.BarCode for .NET.

## ฉันจะตั้งค่า Barcode Generator สำหรับบาร์โค้ด Aztec อย่างไร?

The `BarcodeGenerator` class is the core component that creates barcode images based on the selected symbology and configuration options. It provides a simple API to specify the type of barcode, the data to encode, and various rendering parameters before saving the result to an image file.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

In this step, we have set up the generator and provided the code text for encoding.

## วิธีตั้งค่า Aztec Symbol Mode เป็น Auto?

The `AztecSymbolMode` enumeration defines the four possible symbol modes for Aztec barcodes, and the **Auto** option lets the library automatically choose the most compact size while preserving all data and error‑correction requirements. This mode is ideal for most scenarios where you want the smallest possible barcode without manual tuning.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

This step ensures that the Aztec Symbol Mode is automatically determined, and the resulting barcode image is saved.

## วิธีบังคับใช้ FullRange Symbol Mode?

When you need the maximum data capacity, you can select the **FullRange** value of the `AztecSymbolMode` enumeration. This mode disables automatic size reduction, allowing the barcode to store the full range of characters and achieve the highest possible information density, which is useful for large data sets.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

This will create a barcode with the FullRange Aztec Symbol Mode.

## วิธีสร้างบาร์โค้ด Aztec แบบ Compact?

The **Compact** value of the `AztecSymbolMode` enumeration produces a smaller barcode by reducing the number of layers used in the matrix. This results in a more space‑efficient image, making it suitable for applications with limited display area such as mobile screens or small labels.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

This step configures the barcode to be generated with the Compact Aztec Symbol Mode.

## วิธีสร้างบาร์โค้ด Aztec แบบ Rune?

The **Rune** mode is a specialized variant of the Aztec symbology that encodes numeric data using a custom character set, offering a distinct visual style while retaining the same error‑correction strength as other modes. It is useful when you need a barcode that emphasizes numeric information.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

This step changes the code text to "123" and generates a barcode with the Rune Aztec Symbol Mode.

## ปัญหาทั่วไปและวิธีแก้

- **Image not saving** – Ensure the output folder exists and the application has write permissions.  
- **Unexpected symbol size** – Verify that you haven’t overridden `EncodeMode` elsewhere in your code.  
- **License exception** – A trial version adds a watermark; apply a valid license to remove it.

## คำถามที่พบบ่อย

**Q: จุดประสงค์ของ Aztec Symbol Mode ในการสร้างบาร์โค้ดคืออะไร?**  
A: Aztec Symbol Mode determines how the library packs data into layers, affecting size, capacity, and readability.

**Q: ฉันสามารถเปลี่ยนข้อความโค้ดสำหรับบาร์โค้ด Aztec ใน Aspose.BarCode สำหรับ .NET ได้หรือไม่?**  
A: Yes, simply assign a new string to the `CodeText` property before calling `Save`.

**Q: มีเวอร์ชันทดลองฟรีของ Aspose.BarCode สำหรับ .NET หรือไม่?**  
A: Yes, you can download a free trial version of Aspose.BarCode for .NET [here](https://releases.aspose.com/).

**Q: ฉันสามารถหาเอกสารเต็มของ Aspose.BarCode สำหรับ .NET ได้ที่ไหน?**  
A: You can refer to the complete documentation for Aspose.BarCode for .NET [here](https://reference.aspose.com/barcode/net/).

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ .NET ได้อย่างไร?**  
A: You can acquire a temporary license for Aspose.BarCode for .NET by visiting [this link](https://purchase.aspose.com/temporary-license/).

## สรุป

In this tutorial we explored how to **create aztec barcode .net** using Aspose.BarCode, covering the Auto, FullRange, Compact, and Rune symbol modes. You now have a solid foundation to embed versatile Aztec barcodes into any .NET application, whether it runs on a desktop, web server, or cloud service.

If you have any questions or need further assistance, don't hesitate to reach out to the Aspose.BarCode community on their [support forum](https://forum.aspose.com/c/barcode/13).

---

**อัปเดตล่าสุด:** 2026-05-24  
**ทดสอบกับ:** Aspose.BarCode 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [การเข้ารหัสข้อความโค้ด Aztec ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [การเข้ารหัสไบต์ Aztec ด้วย barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [วิธีสร้างบาร์โค้ด Aztec พร้อมการแก้ไขข้อผิดพลาดใน .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}