---
category: general
date: 2026-10-08
description: สร้างบาร์โค้ด Planet ว่างด้วย C# และเรียนรู้วิธีสร้างบาร์โค้ดไปรษณีย์โดยใช้
  Aspose.BarCode พร้อมโค้ดและเคล็ดลับแบบขั้นตอนต่อขั้นตอน.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: th
lastmod: 2026-10-08
og_description: สร้างบาร์โค้ด Planet ว่างด้วย Aspose.BarCode ใน C# และดูวิธีสร้างภาพบาร์โค้ดไปรษณีย์สำหรับแอปพลิเคชันการส่งจดหมาย
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: สร้างบาร์โค้ด Planet ว่าง – คู่มือบาร์โค้ดไปรษณีย์ C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: สร้างบาร์โค้ดดาวเคราะห์ว่าง, สร้างบาร์โค้ดไปรษณีย์ด้วย C#
url: /th/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Planet barcode แบบว่าง, สร้าง Postal barcode ด้วย C#

หากคุณต้องการ **สร้าง Planet barcode แบบว่าง** สำหรับระบบไปรษณีย์ คู่มือนี้จะแสดงวิธีทำอย่างละเอียดด้วย Aspose.BarCode for .NET คุณยังจะได้เรียนรู้ **วิธีสร้างภาพ Postal barcode** เช่น Planet และ RM4SCC ปรับความกว้างของบาร์, และควบคุมตัวเลือก filled‑bars

การสร้าง Postal barcode ไม่จำเป็นต้องใช้ไลบรารีกราฟิกแยกต่างหาก Aspose.BarCode SDK มี API เพียงหนึ่งเดียวที่จัดการการเข้ารหัส, การเรนเดอร์ภาพ, และการเลือกฟอร์แมตของภาพ เมื่อจบบทเรียนนี้คุณจะมีไฟล์ PNG พร้อมใช้งานสามไฟล์:

* `PostalPlanetEmptyBars.png` – Planet barcode แบบบาร์ว่าง  
* `PostalPlanetFilledBars.png` – Planet barcode แบบบาร์เต็มตามค่าเริ่มต้น  
* `PostalRM4SCCFilledBars.png` – RM4SCC barcode แบบบาร์เต็ม  

คุณสามารถนำไฟล์เหล่านี้ไปใส่ในเทมเพลตป้ายไปรษณีย์ใดก็ได้, พิมพ์บนซองจดหมาย, หรือส่งต่อให้บริการของบุคคลที่สาม

## ข้อกำหนดเบื้องต้น

* .NET 6.0 หรือใหม่กว่า (โค้ดนี้ยังทำงานได้กับ .NET Framework 4.7+)  
* Visual Studio 2022 หรือ IDE สำหรับ C# ใดก็ได้  
* Aspose.BarCode for .NET – ติดตั้งผ่าน NuGet:

```bash
dotnet add package Aspose.BarCode
```

ไม่ต้องมีการพึ่งพาเพิ่มเติมใด ๆ

## สร้าง Planet barcode แบบว่างด้วย Aspose.BarCode

สัญลักษณ์ Planet เป็นส่วนหนึ่งของตระกูล barcode ของ United States Postal Service (USPS) โดยค่าเริ่มต้น SDK จะวาดบาร์ **เต็ม** เพื่อ **สร้าง Planet barcode แบบว่าง** คุณต้องปิดฟลัก `FilledBars`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**เหตุผลที่ทำงานได้:**  
`EncodeTypes.Planet` บอกให้ตัวสร้างใช้สัญลักษณ์ Planet `XDimension.Pixels` ควบคุมความกว้างจริงของแต่ละบาร์ ซึ่งสำคัญสำหรับสแกนเนอร์ไปรษณีย์ที่คาดหวังขนาดโมดูลเฉพาะ การตั้งค่า `FilledBars` เป็น `false` ทำให้เรนเดอร์วาดเพียงโครงร่างของบาร์แต่ละอัน, ให้ผลลัพธ์เป็นลักษณะ *ว่าง* ตามมาตรฐานบางอย่างของการส่งจดหมาย

### ผลลัพธ์ที่คาดหวัง

คุณจะพบไฟล์ `PostalPlanetEmptyBars.png` ในโฟลเดอร์เป้าหมาย ภาพจะแสดง Planet barcode ที่แต่ละบาร์เป็นโครงร่างแทนสี่เหลี่ยมเต็ม

![Empty Planet barcode example](empty-planet.png){: .align-center alt="สร้าง Planet barcode แบบว่าง – ตัวอย่างของ Planet barcode แบบบาร์ว่าง"}

## วิธีสร้างภาพ Postal barcode (เวอร์ชันบาร์เต็ม)

กระบวนการไปรษณีย์ส่วนใหญ่ใช้เวอร์ชันบาร์เต็มโดยค่าเริ่มต้น API เดียวกันสามารถสร้าง Planet barcode แบบบาร์เต็มและ RM4SCC barcode ได้ด้วยไม่กี่บรรทัดโค้ด

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**ทำไมคุณอาจต้องการ RM4SCC:**  
RM4SCC เป็น barcode ของ USPS รุ่นใหม่ที่เข้ารหัสข้อมูลเดียวกับ Planet แต่ความหนาแน่นสูงกว่า ผู้ให้บริการบางรายต้องการ RM4SCC เพื่อรับส่วนลดการส่งจดหมายจำนวนมาก โค้ดข้างต้นแสดง **วิธีสร้าง Postal barcode** สำหรับทั้งสองมาตรฐานโดยไม่ต้องเปลี่ยนแปลงกระบวนการโดยรวม

### ผลลัพธ์ที่คาดหวัง

* `PostalPlanetFilledBars.png` – Planet barcode แบบบาร์เต็มคลาสสิก  
* `PostalRM4SCCFilledBars.png` – RM4SCC barcode แบบบาร์เต็ม, มีลักษณะคล้ายกันแต่ช่องว่างแคบกว่า  

ไฟล์ทั้งสองสามารถเปิดด้วยโปรแกรมดูภาพใดก็ได้เพื่อยืนยันรูปแบบบาร์

## ปรับความกว้างของบาร์สำหรับความละเอียดการพิมพ์ที่ต่างกัน

สแกนเนอร์ไปรษณีย์มักระบุความกว้างโมดูลขั้นต่ำ (เช่น 0.013 นิ้ว) หากเครื่องพิมพ์ของคุณทำงานที่ 300 dpi โมดูล 4 พิกเซลจะเท่ากับ 0.013 นิ้ว ปรับค่า `XDimension.Pixels` ให้ตรงกับฮาร์ดแวร์ของคุณ:

| โมดูลที่ต้องการ (นิ้ว) | DPI | พิกเซลที่ต้องการ (`XDimension`) |
|--------------------------|-----|-----------------------------------|
| 0.013                    | 300 | 4                                 |
| 0.013                    | 600 | 8                                 |
| 0.015                    | 300 | 5                                 |

**เคล็ดลับมืออาชีพ:** ควรทดสอบเสมอ

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีโค้ดตัวอย่างทำงานครบถ้วนพร้อมคำอธิบายขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโครงการของคุณ

- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}