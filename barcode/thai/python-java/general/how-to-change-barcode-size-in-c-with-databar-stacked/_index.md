---
category: general
date: 2026-08-22
description: วิธีเปลี่ยนขนาดบาร์โค้ดใน C# ด้วยตัวสร้าง DataBar Stacked Omni‑Directional.
  เรียนรู้การตั้งค่า X‑dimension และอัตราส่วนภาพสำหรับการส่งออกเป็น PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: th
lastmod: 2026-08-22
og_description: วิธีเปลี่ยนขนาดบาร์โค้ดใน C# ด้วยตัวสร้าง DataBar Stacked Omni‑Directional
  ทำตามคู่มือขั้นตอนเพื่อปรับมิติ X และอัตราส่วนภาพ
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: วิธีเปลี่ยนขนาดบาร์โค้ดใน C# – คู่มือครบถ้วน
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: วิธีเปลี่ยนขนาดบาร์โค้ดใน C# ด้วย DataBar Stacked
url: /th/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการเปลี่ยนขนาดบาร์โค้ดใน C# ด้วย DataBar Stacked

หากคุณต้องการ **วิธีการเปลี่ยนขนาดบาร์โค้ด** ในแอปพลิเคชัน .NET คำแนะนำนี้จะแสดงขั้นตอนที่แน่นอนโดยใช้ตัวสร้างบาร์โค้ด DataBar Stacked Omni‑Directional คุณจะได้เห็นวิธีควบคุมมิติ X ในหน่วยพิกเซล ปรับอัตราส่วนของบาร์โค้ด และบันทึกผลลัพธ์เป็นไฟล์ PNG

การเปลี่ยนขนาดบาร์โค้ดมักจำเป็นเมื่อพื้นที่บนฉลากมีจำกัดหรือเมื่อจำเป็นต้องใช้ภาพความละเอียดสูงสำหรับช่องทางดิจิทัล บทเรียนนี้ครอบคลุมทุกอย่างที่คุณต้องการ ตั้งแต่การเริ่มต้นตัวสร้างจนถึงการสร้างภาพสองภาพที่มีขนาดต่างกัน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นใหม่กว่า  
* การอ้างอิงไปยังแพคเกจ **Aspose.BarCode for .NET** บน NuGet  
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C#  

ไม่ต้องตั้งค่าพิเศษเพิ่มเติม; โค้ดสามารถทำงานได้บน Windows, Linux หรือ macOS

## วิธีการเปลี่ยนขนาดบาร์โค้ดใน C# – ทีละขั้นตอน

ส่วนต่อไปนี้จะแบ่งกระบวนการออกเป็นขั้นตอนย่อยที่สามารถนำกลับมาใช้ใหม่ได้ แต่ละขั้นตอนอธิบาย **ทำไม** จึงต้องใช้โค้ดนั้น ไม่ใช่แค่ **ทำอะไร**

### ขั้นตอน 1: สร้างตัวสร้างบาร์โค้ด DataBar Stacked Omni‑Directional

อ็อบเจ็กต์ตัวสร้างจะเก็บการตั้งค่าบาร์โค้ดทั้งหมด โดยการส่ง `EncodeTypes.DatabarStackedOmniDirectional` และข้อมูลตัวอย่าง คุณจะได้บาร์โค้ดที่ถูกต้องพร้อมสำหรับการปรับแต่งต่อไป

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*ทำไมจึงสำคัญ* – คลาส **C# barcode generator** จัดการอัลกอริทึมการเข้ารหัส การเริ่มต้นด้วยตัวสร้างที่ถูกต้องทำให้การเปลี่ยนขนาดต่อไปส่งผลต่อประเภทบาร์โค้ดที่ต้องการ

### ขั้นตอน 2: ตั้งค่าขนาดโมดูลพื้นฐาน (X‑dimension) เป็นพิกเซล

X‑dimension กำหนดความกว้างของโมดูลบาร์โค้ดแต่ละตัว การปรับค่านี้จะทำให้ความกว้างและความสูงโดยรวมเปลี่ยนตามสัดส่วน

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*ทำไมจึงสำคัญ* – X‑dimension ที่ใหญ่ขึ้นทำให้บาร์โค้ดใหญ่ขึ้น ซึ่งเหมาะกับเครื่องพิมพ์ความละเอียดต่ำ ในทางกลับกันค่าที่เล็กลงจะให้บาร์โค้ดกระชับ เหมาะกับฉลากขนาดเล็ก

### ขั้นตอน 3: เปลี่ยนอัตราส่วนของบาร์โค้ดเป็น 15 แล้วบันทึกภาพ

**อัตราส่วนของบาร์โค้ด** ควบคุมความสัมพันธ์ระหว่างความสูงและความกว้าง อัตราส่วน 15 จะให้บาร์โค้ดที่ค่อนข้างสูง

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*ทำไมจึงสำคัญ* – อุปกรณ์สแกนต่าง ๆ มีข้อกำหนดอัตราส่วนที่เหมาะสม การตั้งค่าเป็น 15 แสดงวิธี **วิธีการเปลี่ยนขนาดบาร์โค้ด** โดยการปรับความสูงขณะคงความกว้างตาม X‑dimension

#### ผลลัพธ์ที่คาดหวัง

ไฟล์ `DatabarAspectRatio15.png` แสดงบาร์โค้ด DataBar Stacked Omni‑Directional ที่สูงกว่าค่าปริยาย ความกว้างของบาร์โค้ดสะท้อน X‑dimension 2 พิกเซล และความสูงตามอัตราส่วน 15

### ขั้นตอน 4: เปลี่ยนอัตราส่วนของบาร์โค้ดเป็น 30 แล้วบันทึกภาพใหม่

การเพิ่มอัตราส่วนเป็น 30 ทำให้บาร์โค้ดสูงขึ้นอีก แสดงความยืดหยุ่นของการปรับขนาด

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*ทำไมจึงสำคัญ* – การสลับค่า **barcode aspect ratio** ทำให้คุณเห็นผลของ **วิธีการเปลี่ยนขนาดบาร์โค้ด** ได้ทันทีโดยไม่ต้องสร้างตัวสร้างใหม่ ซึ่งช่วยประหยัดเวลาในกรณีประมวลผลเป็นชุด

#### ผลลัพธ์ที่คาดหวัง

ไฟล์ `DatabarAspectRatio30.png` สูงกว่าไฟล์ก่อนหน้าอย่างชัดเจน ยืนยันว่าอัตราส่วนมีผลโดยตรงต่อความสูงของบาร์โค้ด

### ขั้นตอน 5: ตรวจสอบภาพที่สร้างขึ้น

เปิดไฟล์ PNG ด้วยโปรแกรมดูภาพใดก็ได้ คุณควรเห็นบาร์โค้ดสองตัวที่มีความกว้างเท่ากัน (ควบคุมโดย X‑dimension) แต่ความสูงต่างกัน (ควบคุมโดยอัตราส่วน) หากภาพดูเบลอ ให้เพิ่มพิกเซลของ X‑dimension; หากภาพสูงเกินไป ให้ลดอัตราส่วน

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*ทำไมจึงสำคัญ* – การตรวจสอบแบบโปรแกรมมิ่งรับประกันว่าการเปลี่ยนขนาดถูกนำไปใช้อย่างถูกต้อง ซึ่งสำคัญสำหรับสายงานการสร้างอัตโนมัติ

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับ | เหตุผล |
|-----------|------------|--------|
| **ฉลากขนาดเล็กมาก** | ตั้งค่า `XDimension.Pixels = 1` และ `AspectRatio = 10` | ลดพื้นที่โดยรวมขณะยังคงความอ่านได้ |
| **การพิมพ์ความละเอียดสูง** | ตั้งค่า `XDimension.Pixels = 4` และ `AspectRatio = 20` | เพิ่มความหนาแน่นของพิกเซลเพื่อผลลัพธ์คมชัด |
| **รูปแบบภาพอื่น** | แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Jpeg` | มีประโยชน์เมื่อการสนับสนุน PNG มีข้อจำกัด |
| **ข้อมูลแบบไดนามิก** | ส่งสตริงตัวแปรไปยังคอนสตรัคเตอร์ `BarcodeGenerator` | สร้างบาร์โค้ดอัตโนมัติสำหรับแต่ละสินค้า |

เมื่อคุณต้องสร้างบาร์โค้ดจำนวนมากที่มีขนาดแตกต่างกัน ให้ห่อขั้นตอนเหล่านี้ไว้ในเมธอด:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

การเรียก `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` จะสร้างบาร์โค้ดขนาดกำหนดในบรรทัดเดียวของโค้ด

## เคล็ดลับสำคัญสำหรับการเปลี่ยนขนาดที่เชื่อถือได้

* **ตั้งค่า X‑dimension ก่อนอัตราส่วน** การเปลี่ยนอัตราส่วนก่อนอาจทำให้เกิดการสเกลที่ไม่คาดคิดหาก X‑dimension มีค่าเริ่มต้นที่ไม่เหมาะสม  
* **ใช้โฟลเดอร์ผลลัพธ์ที่สม่ำเสมอ** การกำหนดค่า `"YOUR_DIRECTORY"` เหมาะสำหรับสาธิต แต่ในสภาพแวดล้อมจริงควรใช้ `Path.Combine(Environment.CurrentDirectory, "Barcodes")`  
* **ตรวจสอบขนาดภาพที่สร้าง** การเปลี่ยนแปลงเล็กน้อยใน X‑dimension อาจไม่เห็นชัดบนหน้าจอ; การตรวจสอบขนาดพิกเซลจะยืนยันว่าการเปลี่ยนแปลงมีผล  

## สรุป

คุณได้เรียนรู้ **วิธีการเปลี่ยนขนาดบาร์โค้ด** ใน C# ด้วยตัวสร้าง DataBar Stacked Omni‑Directional โดยการปรับ **พิกเซลของ X‑dimension** และ **อัตราส่วนของบาร์โค้ด** คุณสามารถสร้างภาพ PNG ที่เหมาะกับขนาดหรือความละเอียดของฉลากใด ๆ ตัวอย่างที่ทำงานได้เต็มรูปแบบด้านบนแสดงขั้นตอนทั้งหมดตั้งแต่การสร้างตัวสร้างจนถึงการตรวจสอบขนาด

### สิ่งที่ควรสำรวจต่อไป

* **สีที่กำหนดเอง** – ทดลองใช้ `barcodeGenerator.Parameters.Barcode.ForeColor` และ `BackColor` เพื่อให้สอดคล้องกับแนวทางแบรนด์  
* **ประเภทบาร์โค้ดอื่น** – แทนที่ `EncodeTypes.DatabarStackedOmniDirectional` ด้วย `EncodeTypes.QR` หรือ `EncodeTypes.Code128` เพื่อดูว่าพารามิเตอร์ขนาดทำงานอย่างไรในสัญลักษณ์ต่าง ๆ  
* **การประมวลผลเป็นชุด** – ผสานเมธอด `GenerateDatabar` กับการนำเข้า CSV เพื่อสร้างบาร์โค้ดหลายพันรายการโดยอัตโนมัติ  

ปรับโค้ดส่วนนั้นให้เข้ากับสถาปัตยกรรมของโครงการคุณ และให้การปรับขนาดบาร์โค้ดช่วยเพิ่มความน่าเชื่อถือในการสแกนและการออกแบบที่สวยงาม ขอให้สนุกกับการเขียนโค้ด!

## สิ่งที่คุณควรเรียนต่อไป

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้ในโครงการของคุณเอง

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}