---
category: general
date: 2026-11-20
description: สร้างภาพบาร์โค้ดไปรษณีย์ใน C# อย่างรวดเร็ว เรียนรู้วิธีสร้างบาร์โค้ด
  Planet และ RM4SCC พร้อมสไตล์บาร์ที่ปรับแต่งได้
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: th
lastmod: 2026-11-20
og_description: สร้างภาพบาร์โค้ดไปรษณีย์ใน C# ด้วย Aspose.BarCode บทเรียนนี้แสดงวิธีสร้างบาร์โค้ด
  Planet ปรับแต่งสไตล์ของบาร์ และสร้างภาพ RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: สร้างภาพบาร์โค้ดไปรษณีย์ใน C# – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: สร้างภาพบาร์โค้ดไปรษณีย์และสร้างบาร์โค้ดดาวเคราะห์
url: /th/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดไปรษณีย์และสร้างบาร์โค้ด Planet

สร้างภาพบาร์โค้ดไปรษณีย์ใน C# โดยใช้ไลบรารี Aspose.BarCode หากคุณต้องการสร้างบาร์โค้ด Planet หรือบาร์โค้ด RM4SCC สำหรับการใช้งานส่งจดหมาย บทแนะนำนี้ให้โซลูชันที่สมบูรณ์พร้อมใช้งาน

การสร้างบาร์โค้ดสำหรับบริการไปรษณีย์มักต้องการขนาดที่แม่นยำและตัวเลือกในการสลับระหว่างสไตล์บาร์ที่เติมเต็มและบาร์ที่ว่าง คู่มือฉบับนี้จะพาคุณผ่านการตั้งค่าโฟลเดอร์ผลลัพธ์ การสร้างบาร์โค้ด Planet ทั้งแบบเติมเต็มและแบบว่าง และการผลิตบาร์โค้ด RM4SCC ด้วยการตั้งค่าเดียวกัน เมื่อเสร็จสิ้นคุณจะได้ไฟล์ PNG สี่ไฟล์ที่สามารถใช้โดยตรงในกระบวนการส่งจดหมายของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 หรือใหม่กว่า  
* Visual Studio 2022 (หรือ IDE C# ใด ๆ ที่คุณชอบ)  
* แพคเกจ **Aspose.BarCode** NuGet (`Install-Package Aspose.BarCode`)  

ไม่ต้องกำหนดค่าพิเศษเพิ่มเติม; โค้ดใช้เพียงฟอนต์เริ่มต้นและ PNG encoder เท่านั้น

## ภาพรวมการสร้างบาร์โค้ดไปรษณีย์

แกนหลักของกระบวนการคือคลาส `BarcodeGenerator` ซึ่งรับค่าชนิด `EncodeTypes` ที่กำหนดสัญลักษณ์บาร์โค้ด (เช่น `EncodeTypes.Planet` สำหรับบาร์โค้ด Planet) หลังจากตั้งค่า generator แล้ว คุณเรียก `Save` เพื่อบันทึกไฟล์ภาพ

![Create postal barcode image example](/images/postal_barcode_example.png)

*ข้อความแทนภาพ: ตัวอย่างการสร้างภาพบาร์โค้ดไปรษณีย์ที่แสดงบาร์ที่เติมเต็มและบาร์ที่ว่าง*

## Step 1: Set up the output folder

ก่อนอื่นกำหนดโฟลเดอร์ที่ไฟล์ PNG จะถูกบันทึก การใช้พาธแบบ absolute หรือ relative ทำงานได้เช่นกัน; เพียงตรวจสอบให้โฟลเดอร์มีอยู่หรือให้โค้ดสร้างมันขึ้นมา

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

การสร้างโฟลเดอร์โดยโปรแกรมช่วยป้องกัน `DirectoryNotFoundException` เมื่อบทแนะนำทำงานบนเครื่องใหม่

## Step 2: Generate planet barcode with filled bars

บาร์โค้ด Planet แบบบาร์ที่เติมเต็มเป็นสไตล์เริ่มต้น โค้ดต่อไปนี้สร้างบาร์โค้ด ตั้งค่า X‑dimension เป็น 4 pixels (ขนาดที่นิยมใช้ในงานไปรษณีย์) และบันทึกภาพ

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**ทำไมวิธีนี้ถึงได้ผล:**  
* `EncodeTypes.Planet` บอก generator ให้ใช้สัญลักษณ์ Planet ซึ่งจำเป็นสำหรับหลายบริการไปรษณีย์  
* `XDimension.Pixels` ควบคุมความกว้างของแต่ละบาร์; 4 px ให้ภาพที่คมชัดและสแกนได้โดยไม่ทำให้ไฟล์ใหญ่เกินไป  
* เมธอด `Save` จะเลือก PNG encoder อัตโนมัติตามค่าใน enum `BarCodeImageFormat`

## Step 3: Generate planet barcode with empty bars

บางสเปคไปรษณีย์ต้องการบาร์ที่ว่าง (สีขาว) บนพื้นหลังสีเข้ม คุณสามารถทำได้โดยตั้งค่า `FilledBars` เป็น `false`

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**เคล็ดลับ:** เมื่อ `FilledBars` เป็น `false` generator จะวาดบาร์ด้วยสีพื้นหลัง (ค่าเริ่มต้นคือสีขาว) และช่องว่างด้วยสีพื้นหน้า (สีดำ) หากต้องการโทนสีอื่น ให้ปรับ `Parameters.Barcode.ForeColor` และ `BackColor`

## Step 4: Generate RM4SCC barcode with filled bars

RM4SCC เป็นสัญลักษณ์ไปรษณีย์อีกแบบหนึ่งที่ใช้ในสหราชอาณาจักร ขั้นตอนการสร้างคล้ายกับตัวอย่าง Planet; เพียงค่า `EncodeTypes` ที่เปลี่ยนไป

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**สิ่งที่คาดว่าจะได้:** PNG ที่แสดงบาร์โค้ด RM4SCC แบบกะทัดรัดซึ่งสอดคล้องกับแนวทางไปรษณีย์ของสหราชอาณาจักร ขนาดภาพจะคล้ายกับบาร์โค้ด Planet เนื่องจาก X‑dimension เท่ากัน

## Step 5: Verify the generated images

หลังจากรันโปรแกรม เปิดไฟล์สี่ไฟล์ในโฟลเดอร์ `Barcodes` คุณควรเห็น:

* `PostalPlanetFilledBars.png` – บาร์สีเข้มบนพื้นหลังสีอ่อน  
* `PostalPlanetEmptyBars.png` – บาร์สีอ่อนบนพื้นหลังสีเข้ม (แบบกลับสี)  
* `PostalRM4SCCFilledBars.png` – รูปแบบ RM4SCC มาตรฐาน  

หากภาพใดภาพหนึ่งดูบิดเบี้ยว ให้ตรวจสอบสิ่งต่อไปนี้:

* **X‑dimension** – ค่าที่เล็กเกินไป (< 2 px) อาจทำให้ภาพเบลอ; ค่าที่ใหญ่เกินไป (> 10 px) อาจเกินขนาดป้าย  
* **Data string** – ค่า `"123456"` ต้องตรงตามข้อกำหนดความยาวของสัญลักษณ์ที่เลือก (Planet ต้อง 6 หลัก, RM4SCC ก็ต้อง 6 หลักเช่นกัน)  
* **Folder permissions** – ตรวจสอบให้แอปพลิเคชันมีสิทธิ์เขียนในไดเรกทอรีผลลัพธ์

## การปรับเปลี่ยนทั่วไปและกรณีขอบ

| Scenario | Adjustment |
|----------|------------|
| **Different barcode data** | แทนที่ `"123456"` ด้วยสตริงตัวเลขที่ถูกต้องใด ๆ สำหรับ Planet ความยาวต้องเป็น 6 หลัก; RM4SCC ก็ต้อง 6 หลักเช่นกัน |
| **Custom colors** | ตั้งค่า `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` และ `BackColor = System.Drawing.Color.LightYellow;` |
| **Higher resolution** | เพิ่ม `XDimension.Pixels` เป็น 6 หรือ 8 เพื่อพิมพ์ขนาดใหญ่ขึ้น |
| **Other image formats** | ใช้ `BarCodeImageFormat.Jpeg` หรือ `BarCodeImageFormat.Bmp` ในเมธอด `Save` |
| **Batch generation** | วนลูปผ่านคอลเลกชันของสตริงและเรียกใช้ตรรกะ generator เดียวกันภายในลูป โดยใช้เส้นทาง `outputFolder` เดิม |

## ตัวอย่างเต็มที่สามารถรันได้

คัดลอกโค้ดด้านล่างไปยังโปรเจกต์คอนโซล C# ใหม่ โค้ดจะคอมไพล์ด้วย .NET 6.0 และสร้างภาพบาร์โค้ดสี่ภาพโดยอัตโนมัติ



## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการทำงานทางเลือกในโปรเจกต์ของคุณเอง

- [วิธีสร้างภาพบาร์โค้ดไปรษณีย์ด้วยความสูงกำหนดเองใน C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [วิธีสร้างบาร์โค้ด RM4SCC และสร้างบาร์โค้ด Planet ใน C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [สร้างภาพบาร์โค้ดไปรษณีย์ใน C# – คู่มือทีละขั้นตอน](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}