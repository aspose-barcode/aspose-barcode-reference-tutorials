---
category: general
date: 2026-10-18
description: สร้างบาร์โค้ด Databar Expanded ด้วย Java และ Aspose.BarCode. เรียนรู้วิธีสร้าง
  Databar, ตั้งค่าแถว, และส่งออกภาพบาร์โค้ดเป็น PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: th
lastmod: 2026-10-18
og_description: สร้างบาร์โค้ด Databar Expanded ใน Java. ทำตามคู่มือนี้เพื่อเรียนรู้วิธีสร้าง
  Databar, ตั้งค่าแถว, และส่งออกภาพบาร์โค้ดเป็น PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: สร้างบาร์โค้ด Databar Expanded ด้วย Java – คู่มือทีละขั้นตอน
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: สร้างบาร์โค้ด Databar Expanded ใน Java – คู่มือเต็ม
url: /th/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด Databar Expanded ใน Java – คู่มือเต็ม

หากคุณต้องการ **สร้างบาร์โค้ด databar expanded** ใน Java คู่มือนี้จะแสดงให้คุณเห็น **วิธีสร้างภาพ databar** ด้วยไลบรารี Aspose.BarCode คุณจะได้เรียนรู้วิธีกำหนด **แถวของตัวสร้างบาร์โค้ด** และ **ส่งออกไฟล์ภาพบาร์โค้ด** ในรูปแบบ PNG

ในส่วนต่อไปนี้คุณจะพบโปรแกรมที่ทำงานได้เต็มรูปแบบ คำอธิบายทีละขั้นตอนของทุกการเรียก API และเคล็ดลับการจัดการกรณีขอบที่พบบ่อย เช่น ตัวอักษรที่ไม่รองรับหรือขนาดเลย์เอาต์ที่กำหนดเอง เมื่ออ่านจบคู่มือนี้คุณจะสามารถสร้างบาร์โค้ด Databar Expanded ทั้งแบบ 4‑คอลัมน์และ 3‑แถวและบันทึกไว้ตามที่ต้องการ

## ข้อกำหนดเบื้องต้น

* Java 17 หรือใหม่กว่า (โค้ดสามารถคอมไพล์กับ JDK 11+ ใดก็ได้)
* Maven หรือ Gradle สำหรับจัดการ dependencies
* Aspose.BarCode for Java – เพิ่มเวอร์ชันล่าสุดลงใน `pom.xml` หรือ `build.gradle`
* ความคุ้นเคยพื้นฐานกับเมธอด `main` ของ Java และแนวคิดเชิงวัตถุ

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **เคล็ดลับ:** ไลเซนส์ประเมินผลฟรีใช้ได้สำหรับการพัฒนา; ให้เปลี่ยนเป็นไลเซนส์ที่ซื้อไว้ก่อนนำไปใช้งานจริง

## สร้างบาร์โค้ด databar expanded – การตั้งค่าเริ่มต้น

ขั้นตอนแรกคือการสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภท `EncodeTypes.DatabarExpandedStacked` และ payload ตัวอย่าง Payload นี้สามารถเป็นสตริงอัลฟานูเมอริกใดก็ได้ที่สอดคล้องกับสเปคของ Databar

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*ทำไมจึงสำคัญ*: `EncodeTypes.DatabarExpandedStacked` บอกไลบรารีให้ใช้สัญลักษณ์ Databar Expanded Stacked ซึ่งรองรับสตริงข้อมูลที่ยาวกว่าสัญลักษณ์ Databar ปกติ

## วิธีสร้าง databar ด้วยคอลัมน์ที่กำหนดเอง

Databar Expanded ให้คุณควบคุมจำนวนคอลัมน์ในเลย์เอาต์แบบ stacked การกำหนดคอลัมน์เป็นประโยชน์เมื่อคุณต้องการบาร์โค้ดที่กระชับแต่ยังคงใส่ข้อมูลที่ต้องการได้ครบ

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*คำอธิบาย*: `setColumns(4)` บังคับให้ตัวสร้างแยกบาร์โค้ดออกเป็นสี่ส่วนแนวตั้ง ไลบรารีจะปรับความกว้างของโมดูลโดยอัตโนมัติเพื่อให้ขนาดโดยรวมอยู่ในระดับที่เหมาะสม

## ส่งออกภาพบาร์โค้ดเป็น PNG – เวอร์ชัน 4‑คอลัมน์

เมื่อกำหนดเลย์เอาต์แล้ว คุณสามารถส่งออกบาร์โค้ดเป็นไฟล์ PNG ซึ่งเป็นรูปแบบที่แนะนำสำหรับการใช้งาน UI ส่วนใหญ่

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

เมธอด `save` จะเขียนภาพลงในไดเรกทอรีที่ระบุ หากไดเรกทอรีไม่มีอยู่ Java จะสร้างให้โดยอัตโนมัติ

## กำหนดแถวของตัวสร้างบาร์โค้ด

นอกจากคอลัมน์แล้ว สัญลักษณ์ Databar Expanded Stacked ยังรองรับเลย์เอาต์แบบแถว การสลับจากคอลัมน์เป็นแถวสามารถช่วยให้การอ่านบนการพิมพ์ความละเอียดสูงดีขึ้น

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*ทำไมต้องใช้แถว?* เลย์เอาต์ 3‑แถวกระจายข้อมูลในแนวตั้ง ซึ่งเป็นประโยชน์สำหรับป้ายที่แคบและมีพื้นที่แนวนอนจำกัด

## ส่งออกภาพบาร์โค้ดเป็น PNG – เวอร์ชัน 3‑แถว

การบันทึกเลย์เอาต์ที่สองทำตามขั้นตอนเดียวกับก่อนหน้า การตั้งชื่อไฟล์ให้แตกต่างกันจะช่วยให้คุณเปรียบเทียบความแตกต่างของภาพได้ง่ายขึ้น

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ PNG สองไฟล์:

| ชื่อไฟล์                     | รายละเอียดเลย์เอาต์                |
|------------------------------|-----------------------------------|
| `DatabarExpandedCols4.png`   | บาร์โค้ด stacked แบบ 4‑คอลัมน์   |
| `DatabarExpandedRows3.png`   | บาร์โค้ด stacked แบบ 3‑แถว       |

ทั้งสองภาพแสดงสตริงที่เข้ารหัสเดียวกัน แต่ความหนาแน่นของภาพจะแตกต่างตามการตั้งค่าคอลัมน์/แถว

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| ปัญหา                              | สาเหตุ                                     | วิธีแก้ |
|------------------------------------|--------------------------------------------|---------|
| บาร์โค้ดดูเบลอ                     | บันทึกที่ DPI ต่ำ                           | ใช้ `generator.getParameters().setResolution(300)` ก่อน `save` |
| ข้อความถูกตัด                     | Payload เกินขีดจำกัดของ Databar           | ลดขนาด payload หรือสลับเป็น `EncodeTypes.DatabarExpanded` (ไม่ stacked) |
| `NullPointerException` ที่ `setRows`| ใช้เวอร์ชัน Aspose.BarCode ก่อน 20.12    | อัปเกรดเป็นเวอร์ชันล่าสุดของไลบรารี |

## ตัวแปรขั้นสูง (ไม่บังคับ)

* **เปลี่ยนสีพื้นหน้า/พื้นหลัง** – เรียก `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` และ `setBackColor(Color.WHITE)`
* **สร้าง SVG แทน PNG** – แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Svg`
* **ฝังบาร์โค้ดใน PDF** – ใช้ Aspose.PDF สร้างเอกสารและเพิ่ม PNG เป็นรูปภาพ

## สรุป

ตอนนี้คุณรู้วิธี **สร้างบาร์โค้ด databar expanded** ใน Java, **วิธีสร้าง databar** ด้วยการกำหนดคอลัมน์และแถว, และ **วิธีส่งออกไฟล์ภาพบาร์โค้ด** ในรูปแบบ PNG โค้ดเต็มพร้อมคัดลอก วาง และรันในโปรเจกต์ Java ใดก็ได้

ลองทดลองกับเลย์เอาต์ สี หรือรูปแบบผลลัพธ์อื่น ๆ หากคุณพบว่าคู่มือนี้เป็นประโยชน์ อย่าลืมสำรวจเอกสาร Aspose.BarCode สำหรับหัวข้อเช่น *micro‑PDF417*, *QR code error correction*, และ *barcode scanning*

ขอให้เขียนโค้ดสนุก!

## สิ่งที่คุณควรเรียนต่อไป

บทเรียนต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการนำไปใช้แบบต่าง ๆ ในโปรเจกต์ของคุณ

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}