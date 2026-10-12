---
category: general
date: 2026-09-29
description: คู่มือการสร้างบาร์โค้ด C# แสดงวิธีสร้างบาร์โค้ด MicroPdf417 ปรับมิติ
  ตั้งค่าคอลัมน์ และปรับขนาดบาร์โค้ดเพียงไม่กี่บรรทัด.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: th
lastmod: 2026-09-29
og_description: คู่มือการสร้างบาร์โค้ดด้วย C# แสดงวิธีสร้างบาร์โค้ด MicroPdf417 ปรับขนาด
  เปลี่ยนมิติ ตั้งค่าคอลัมน์ และปรับขนาดบาร์โค้ดได้เพียงไม่กี่บรรทัด
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: คู่มือสร้าง Barcode ด้วย C# – สร้างและปรับแต่ง MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'คู่มือสร้าง Barcode Generator ด้วย C#: สร้าง MicroPdf417'
url: /th/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คู่มือสร้าง Barcode generator C#: สร้าง MicroPdf417

หากคุณต้องการ **barcode generator C#** สำหรับโครงการ .NET ของคุณ บทแนะนำนี้จะพาคุณผ่านขั้นตอนการสร้าง MicroPdf417 barcode ตั้งแต่เริ่มต้น คุณจะได้เรียนรู้ **วิธีสร้าง barcode**, การเปลี่ยนขนาด, การกำหนดคอลัมน์, และ **การปรับขนาด barcode** อย่างง่ายดาย

MicroPdf417 เป็น symbology แบบ 2‑D ขนาดกะทัดรัดที่เหมาะสำหรับการติดฉลากชิ้นส่วนขนาดเล็ก, ตั๋ว, หรือแท็กสินค้าคงคลัง เมื่อจบคู่มือนี้คุณจะมีแอปพลิเคชันคอนโซลที่ทำงานได้เต็มรูปแบบซึ่งสร้างภาพ PNG ของ barcode และคุณจะเข้าใจว่าพารามิเตอร์แต่ละตัวมีผลต่อขนาดสุดท้ายอย่างไร

## สิ่งที่ต้องเตรียม

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

* .NET 6.0 SDK หรือรุ่นที่ใหม่กว่า (โค้ดนี้ยังทำงานกับ .NET Framework 4.7+ ได้เช่นกัน)
* IDE ที่รองรับ C# (Visual Studio, VS Code, Rider ฯลฯ)
* แพคเกจ NuGet **GroupDocs.Barcode** – ติดตั้งโดยใช้  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

ไม่จำเป็นต้องใช้เครื่องมือภายนอกเพิ่มเติม; ไลบรารีจะจัดการการเข้ารหัส, การเรนเดอร์, และการบันทึกไฟล์ให้เอง

## Barcode generator C#: การเริ่มต้น generator

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` และระบุ symbology (`EncodeTypes.MicroPdf417`) พร้อมกับข้อมูลที่คุณต้องการเข้ารหัส

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**ทำไมจึงสำคัญ:**  
`BarcodeGenerator` เป็นจุดเริ่มต้นสำหรับการทำงานกับ barcode ทั้งหมด ตัวสร้าง (constructor) จะผูก **EncodeTypes** ที่เลือก (MicroPdf417) กับสตริงข้อมูลดิบ ไลบรารีจะจัดการอักขระ Unicode อย่างเช่น “Å” และ “©” โดยอัตโนมัติ ดังนั้นคุณไม่จำเป็นต้องเขียนตรรกะการเข้ารหัสเพิ่มเติม

## วิธีการเปลี่ยนขนาดของ barcode

ความอ่านได้ของ barcode ขึ้นอยู่กับความกว้างของโมดูล (X‑dimension) อย่างมาก การตั้งค่าให้มีจำนวนพิกเซลมากขึ้นจะทำให้บาร์กว้างขึ้นและภาพสแกนง่ายขึ้น โดยเฉพาะบนจอแสดงผลความละเอียดต่ำ

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**คำอธิบาย:**  
`XDimension.Pixels` ควบคุมความกว้างของโมดูล barcode หนึ่งโมดูล ค่าเริ่มต้นคือ 1 pixel ซึ่งอาจดูบางบนจอแสดงผล DPI สูง การเพิ่มเป็น 2 pixel จะทำให้ความกว้างโดยรวมเพิ่มเป็นสองเท่าโดยไม่กระทบต่อข้อมูลที่เข้ารหัส

**เคล็ดลับ:**  
หากคุณวางแผนพิมพ์ barcode ที่ 300 dpi ค่า 3 หรือ 4 pixel มักให้ความสมดุลที่ดีที่สุดระหว่างขนาดและความน่าเชื่อถือในการสแกน

## วิธีการกำหนดคอลัมน์เพื่อควบคุมขนาด

MicroPdf417 ให้คุณระบุจำนวนคอลัมน์ (สูงสุด 4) คอลัมน์น้อยจะทำให้ barcode สูงขึ้น; คอลัมน์มากจะทำให้กว้างแต่สั้นลง การปรับค่าดังกล่าวเป็นวิธีหลักในการ **ปรับขนาด barcode**

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**ทำไมวิธีนี้ถึงได้ผล:**  
คุณสมบัติ `Pdf417.Columns` ใช้ร่วมกันใน symbology ทั้งหมดที่อิง PDF417 รวมถึง MicroPdf417 การตั้งค่าเป็นค่าสูงสุด (4) จะกระจายข้อมูลไปยังเลย์เอาต์ที่กว้างที่สุด ลดความสูงโดยรวม หากต้องการความสูงที่กระชับกว่า ให้ลดจำนวนคอลัมน์ลงเป็น 2 หรือ 3

**กรณีขอบ:**  
เมื่อสตริงข้อมูลยาว ไลบรารีอาจเพิ่มแถวโดยอัตโนมัติเพื่อรองรับเนื้อหาโดยไม่คำนึงถึงจำนวนคอลัมน์ ควรจำกัด payload ไว้ไม่เกิน 50 ตัวอักษรเพื่อให้ได้ขนาดที่คาดเดาได้

## ปรับขนาด barcode สำหรับผลลัพธ์ที่แตกต่าง

นอกเหนือจาก X‑dimension และคอลัมน์แล้ว คุณสามารถมีอิทธิพลต่อขนาดภาพสุดท้ายโดยเลือกรูปแบบภาพและ DPI ที่เหมาะสม PNG เป็นแบบ lossless เหมาะสำหรับการแสดงบนเว็บ ในขณะที่ BMP หรือ TIFF อาจเหมาะกับการพิมพ์คุณภาพสูง

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

หากต้องการ DPI ที่สูงขึ้น คุณสามารถตั้งค่าโดยตรงได้:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**ผลลัพธ์:**  
ไฟล์ PNG ที่บันทึกไว้จะมี MicroPdf417 barcode ที่คมชัดและสอดคล้องกับขนาดที่คุณกำหนด เปิดไฟล์ในโปรแกรมดูภาพใดก็ได้เพื่อยืนยันขนาดที่แสดง

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ชื่อ **MicroPdf417.png** (หรือ **MicroPdf417_300dpi.png** หากคุณตั้งค่า DPI) barcode จะมีลักษณะคล้ายภาพตัวอย่างด้านล่าง:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*ข้อความแทนภาพ:* *ผลลัพธ์ของ Barcode generator C# แสดง MicroPdf417 PNG*

การสแกนภาพด้วยเครื่องอ่าน barcode 2‑D มาตรฐานจะคืนสตริงต้นฉบับ `Åspóse.Barcóde©`

## โค้ดต้นฉบับเต็มสำหรับคัดลอก‑วางอย่างรวดเร็ว

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

คัดลอกโค้ดไปยังโปรเจกต์คอนโซลใหม่, เรียกคืนแพคเกจ NuGet, แล้วรัน `dotnet run`. คอนโซลจะแจ้งตำแหน่งไฟล์ภาพและคุณจะเห็น barcode ที่สร้างขึ้นในโฟลเดอร์โปรเจกต์ของคุณ

## คำถามทั่วไปและการแก้ไขปัญหา

| คำถาม | คำตอบ |
|----------|--------|
| **ถ้า barcode ดูเบลอ?** | เพิ่มค่า `XDimension.Pixels` หรือ DPI (`Parameters.Image.DpiX/Y`). ทั้งสองวิธีจะทำให้โมดูลใหญ่ขึ้นและปรับปรุงความคมชัดของภาพ. |
| **ฉันสามารถใช้รูปแบบภาพอื่นได้ไหม?** | ได้. แทนที่ `BarCodeImageFormat.Png` ด้วย `Jpeg`, `Bmp` หรือ `Tiff`. PNG ยังคงเป็นตัวเลือกที่ปลอดภัยที่สุดสำหรับคุณภาพ lossless. |
| **ข้อมูลของฉันมีอีโมจิ—จะเข้ารหัสได้ไหม?** | MicroPdf417 รองรับ UTF‑8 ดังนั้นอีโมจิส่วนใหญ่จะเข้ารหัสได้อย่างถูกต้อง หากพบข้อผิดพลาด ให้ตรวจสอบว่าสตริงถูกทำให้เป็นรูปแบบมาตรฐาน (`System.Text.Encoding.UTF8`). |
| **ฉันจะสร้าง symbology อื่นได้อย่างไร?** | เปลี่ยน `EncodeTypes.MicroPdf417` เป็นค่าอื่นใดจาก `EncodeTypes` ( |

## สิ่งที่คุณควรเรียนต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจวิธีการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ

- [วิธีสร้างภาพ Barcode ใน C# – คู่มือ MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [วิธีสร้าง PDF417 barcode ใน C# ด้วยขนาดกำหนดเอง](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}