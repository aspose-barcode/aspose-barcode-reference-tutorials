---
category: general
date: 2026-11-14
description: บทเรียนการสร้างบาร์โค้ดด้วย C# ที่แสดงวิธีสร้างบาร์โค้ด DataBar Omnidirectional
  ตั้งค่า X‑dimension และปรับความสูงของบาร์เป็นพิกเซล
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: th
lastmod: 2026-11-14
og_description: บทแนะนำการสร้างบาร์โค้ดด้วย C# อธิบายขั้นตอนโดยละเอียดว่าต้องสร้างบาร์โค้ด
  DataBar Omnidirectional อย่างไร กำหนด XDimension เป็นพิกเซล และปรับความสูงของบาร์สำหรับการส่งออกเป็น
  PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: บทเรียนการสร้าง Barcode ด้วย C# – สร้างบาร์โค้ด DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'บทเรียนการสร้างบาร์โค้ด C#: DataBar Omnidirectional'
url: /th/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บทเรียนสร้าง Barcode ด้วย C# – สร้าง DataBar Omnidirectional barcode

หากคุณกำลังมองหา **บทเรียนสร้าง barcode ด้วย C#** คุณมาถูกที่แล้ว คู่มือนี้จะพาคุณผ่านขั้นตอนการสร้าง DataBar Omnidirectional barcode การกำหนดค่า XDimension เป็นพิกเซล และการปรับความสูงของบาร์เพื่อสร้างภาพ PNG

คุณจะได้เห็นตัวอย่างที่ทำงานได้เต็มรูปแบบ ตั้งแต่การเริ่มต้น generator จนถึงการบันทึกหลายภาพด้วยความสูงของบาร์ที่ต่างกัน ไม่ต้องอ้างอิงเอกสารภายนอก—แค่คัดลอกโค้ด รันมัน แล้วคุณจะได้ไฟล์ barcode สองไฟล์พร้อมใช้งาน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

* .NET 6.0 หรือใหม่กว่า  
* การอ้างอิงไลบรารี barcode ที่ให้ `BarcodeGenerator`, `EncodeTypes` และ `BarCodeImageFormat` (เช่น Aspose.BarCode for .NET)  
* ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และ Visual Studio หรือ IDE ที่คุณชื่นชอบ  

> **เคล็ดลับ:** หากคุณใช้ Aspose.BarCode ให้เพิ่มแพคเกจ NuGet `Aspose.BarCode` เข้าไปในโปรเจกต์ของคุณ

## บทเรียนสร้าง Barcode ด้วย C# – ขั้นตอนที่ 1: สร้าง generator

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภทการเข้ารหัส `DatabarOmniDirectional` และข้อมูลที่คุณต้องการเข้ารหัส

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*เหตุผลที่สำคัญ:* `EncodeTypes.DatabarOmniDirectional` บอกไลบรารีให้สร้าง barcode ที่สามารถอ่านได้จากทุกทิศทาง ซึ่งเหมาะอย่างยิ่งสำหรับบรรจุภัณฑ์ค้าปลีกและโลจิสติกส์

## กำหนด XDimension เป็นพิกเซลสำหรับ barcode

X‑dimension กำหนดความกว้างของโมดูลที่เล็กที่สุด (หรือ “พิกเซล”) ใน barcode การตั้งค่าเป็นพิกเซลทำให้คุณควบคุมความหนาแน่นของภาพได้อย่างแม่นยำ

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*คำอธิบาย:* ค่า `2` พิกเซลให้ barcode ที่คมชัดพอสำหรับสแกนเนอร์ส่วนใหญ่ พร้อมขนาดไฟล์ภาพที่ไม่ใหญ่เกินไป

## ปรับความสูงของบาร์และบันทึกภาพ

ความสูงของบาร์กำหนดว่าบาร์จะสูงเท่าไหร่ คุณสามารถสร้างภาพหลายภาพด้วยความสูงที่ต่างกันโดยเปลี่ยนค่าคุณสมบัติ `BarHeight.Pixels` แล้วเรียก `Save` อีกครั้ง

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

ค่า `BarCodeImageFormat.Png` ทำให้ผลลัพธ์เป็นไฟล์ PNG แบบ loss‑less ซึ่งเป็นรูปแบบที่แนะนำสำหรับกราฟิก barcode เนื่องจากรักษาขนาดที่แม่นยำไว้ได้

## เปลี่ยนความสูงของบาร์เพื่อสร้างหลายภาพ

บ่อยครั้งที่คุณต้องการ barcode เดียวกันในขนาดต่างกัน—เช่นหนึ่งสำหรับป้ายเล็กและอีกหนึ่งสำหรับโปสเตอร์ขนาดใหญ่ เปลี่ยนความสูงของบาร์และใช้ generator ตัวเดียวกันต่อ:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*กรณีขอบ:* หากตั้งความสูงของบาร์ต่ำเกินไป (เช่น ต่ำกว่า 10 px) สแกนเนอร์บางรุ่นอาจอ่านไม่ออก ควรทดสอบภาพที่สร้างกับฮาร์ดแวร์สแกนเนอร์ของคุณเสมอ

## โค้ดเต็ม

ด้านล่างเป็นโปรแกรมเต็มที่คุณสามารถคัดลอก‑วางลงในโปรเจกต์คอนโซลใหม่ได้ รวมถึงคำสั่ง `using` ที่จำเป็นทั้งหมดและแสดงการเปลี่ยนแปลงความสูงของบาร์สองแบบ

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

รันโปรแกรม แทนที่ `YOUR_DIRECTORY` ด้วยเส้นทางโฟลเดอร์ที่ใช้งานได้ แล้วคุณจะพบไฟล์ PNG สองไฟล์:

* `DatabarBarHeight30Pixels.png` – บาร์สูง 30 px  
* `DatabarBarHeight60Pixels.png` – บาร์สูง 60 px  

![ผลลัพธ์ของบทเรียนสร้าง barcode ด้วย C#](images/databar-example.png "บทเรียนสร้าง barcode ด้วย C# แสดงภาพ DataBar สองภาพ")

## คำถามที่พบบ่อย

| คำถาม | คำตอบ |
|----------|--------|
| **ฉันสามารถเปลี่ยนรูปแบบภาพได้หรือไม่?** | ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Gif` ตามต้องการ. PNG เป็นรูปแบบที่แนะนำสำหรับคุณภาพ lossless |
| **ถ้าต้องการ XDimension ที่ต่างออกไปล่ะ?** | ปรับ `generator.Parameters.Barcode.XDimension.Pixels` เป็นจำนวนเต็มใดก็ได้. ค่าที่ใหญ่ขึ้นจะทำให้ความกว้างของ barcode เพิ่มขึ้น |
| **DataBar Omnidirectional เหมาะกับการสแกนบนมือถือหรือไม่?** | ใช่, หากขนาดที่พิมพ์ตรงตามขนาดโมดูลขั้นต่ำของสแกนเนอร์ (โดยทั่วไป 0.33 mm). XDimension แบบพิกเซลช่วยให้คุณทำตามข้อกำหนดนี้ |
| **จะฝัง barcode ลงใน PDF ได้อย่างไร?** | หลังจากบันทึก PNG แล้ว ใช้ไลบรารี PDF (เช่น iTextSharp) เพื่อแทรกภาพลงในหน้า PDF |

## สรุป

**บทเรียนสร้าง barcode ด้วย C#** นี้ได้สอนคุณวิธีสร้าง DataBar Omnidirectional barcode ตั้งค่า XDimension เป็นพิกเซล และสร้างไฟล์ PNG ด้วยความสูงของบาร์ที่ต่างกัน ตอนนี้คุณมีโค้ดที่สามารถนำกลับมาใช้ใหม่ได้สำหรับโปรเจกต์ C# ใด ๆ ที่ต้องการสร้าง barcode

### ขั้นตอนต่อไป

* สำรวจ `EncodeTypes` อื่น ๆ เช่น `Code128` หรือ `QR` เพื่อขยายความรู้ด้าน barcode ของคุณ  
* ผสาน PNG ที่สร้างกับไลบรารีสร้าง PDF เพื่อผลิตใบแจ้งหนี้ที่พิมพ์ได้  
* ทดลองใช้ `generator.Parameters.Barcode.Color` เพื่อเพิ่มสีที่กำหนดเองโดยยังคงอยู่ในข้อกำหนดของสแกนเนอร์

ปรับแต่งตัวอย่างตามต้องการ ลองเพิ่มความสูงของบาร์อื่น ๆ หรือเปลี่ยนรูปแบบการส่งออกได้เลย ขอให้สนุกกับการเขียนโค้ด!

## คุณควรเรียนรู้อะไรต่อไป?

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานอื่น ๆ ในโปรเจกต์ของคุณ

- [วิธีตั้งความกว้างและปรับความสูงสำหรับ GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [วิธีตั้งความสูงของ barcode, สร้าง DataBar barcode ด้วย C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [วิธีสร้าง omnidirectional Databar barcode ด้วย C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}