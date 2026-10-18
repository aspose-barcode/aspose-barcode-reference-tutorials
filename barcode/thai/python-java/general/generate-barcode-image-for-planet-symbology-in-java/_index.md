---
category: general
date: 2026-10-18
description: สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์ Planet ด้วย Java. เรียนรู้วิธีสร้างบาร์โค้ด
  Planet ด้วยขนาดบาร์โค้ดที่กำหนดเองและบาร์ว่าง.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: th
lastmod: 2026-10-18
og_description: สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์ Planet ใน Java. บทเรียนนี้แสดงวิธีการสร้างบาร์โค้ด
  Planet ด้วยขนาดบาร์โค้ดที่กำหนดเองและเส้นขอบของบาร์.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์ของดาวเคราะห์ – คู่มือ Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์ Planet ใน Java
url: /th/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพบาร์โค้ดสำหรับสัญลักษณ์ Planet ใน Java

หากคุณต้องการ **สร้างภาพบาร์โค้ด** สำหรับสัญลักษณ์ Planet คำแนะนำนี้จะพาคุณผ่านกระบวนการทั้งหมด ไม่ว่าคุณจะกำลังสร้างระบบอัตโนมัติด้านไปรษณีย์หรือโซลูชันการติดตามแบบกำหนดเอง คุณจะได้เรียนรู้วิธี **สร้างบาร์โค้ด Planet** ด้วย **ขนาดบาร์โค้ดที่กำหนดเอง** และบาร์แบบโครง (ว่าง)

ตัวอย่างนี้ใช้ไลบรารี Aspose.BarCode for Java ซึ่งให้ API แบบ fluent สำหรับมาตรฐานบาร์โค้ดหลักทั้งหมด ไม่จำเป็นต้องใช้เครื่องมือประมวลผลภาพเพิ่มเติม และโค้ดสามารถทำงานบน runtime ของ Java 8+ ใดก็ได้

## ข้อกำหนดเบื้องต้น

* ติดตั้ง Java 8 หรือใหม่กว่า (บทแนะนำนี้ทดสอบกับ JDK 17)
* Maven หรือ Gradle เพื่อจัดการ dependencies
* มีความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และแนวคิดของบาร์โค้ด

หากคุณใหม่กับ Maven คุณสามารถสร้างโปรเจกต์ง่าย ๆ ด้วย `mvn archetype:generate` และเพิ่ม dependency ของ Aspose.BarCode ตามที่แสดงด้านล่าง

## เพิ่ม dependency ของ Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **เคล็ดลับ:** ล็อกหมายเลขเวอร์ชันเพื่อหลีกเลี่ยงการเปลี่ยนแปลงที่ทำให้โค้ดเสียเมื่อไลบรารีอัปเดต.

## ขั้นตอนที่ 1: เริ่มต้นตัวสร้างบาร์โค้ดสำหรับสัญลักษณ์ Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**ทำไมขั้นตอนนี้ถึงสำคัญ:**  
`EncodeTypes.PLANET` บอกไลบรารีให้ใช้สเปคบาร์โค้ด Planet ซึ่งมักใช้ในบริการไปรษณีย์ สตริงข้อมูล `"123456"` คือข้อมูลที่จะแสดงในภาพที่สร้างขึ้น

## ขั้นตอนที่ 2: ตั้งค่าขนาดบาร์โค้ดที่กำหนดเอง (มิติ X)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**ทำไมขั้นตอนนี้ถึงสำคัญ:**  
*มิติ X* กำหนดความกว้างของแต่ละบาร์โดยเฉพาะ การตั้งค่าเป็น **4 พิกเซล** จะทำให้ได้บาร์โค้ดที่เครื่องสแกนส่วนใหญ่อ่านได้ง่ายและยังพอดีกับป้ายมาตรฐาน การเปลี่ยนค่าดังกล่าวเป็นวิธีหลักในการทำให้ได้ **ขนาดบาร์โค้ดที่กำหนดเอง**.

## ขั้นตอนที่ 3: ใช้บาร์แบบว่าง (โครง) แทนบาร์แบบเต็ม

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**ทำไมขั้นตอนนี้ถึงสำคัญ:**  
`setFilledBars(false)` บอก renderer ให้วาดเฉพาะโครงของบาร์ ทำให้ส่วนภายในโปร่งใส สไตล์นี้มักจำเป็นสำหรับบาร์โค้ดไปรษณีย์ที่พื้นหลังอาจมีข้อมูลพิมพ์อื่น ๆ อยู่

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ดเป็น PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**ทำไมขั้นตอนนี้ถึงสำคัญ:**  
การเลือก `BarCodeImageFormat.Png` จะให้ภาพ lossless ที่คงความคมของขอบบาร์โครงได้ ไฟล์พาธสามารถเป็นไดเรกทอรีใดก็ได้ที่คุณมีสิทธิ์เขียน; ตัวอย่างใช้โฟลเดอร์ `output` ที่อยู่สัมพันธ์กับรากของโปรเจกต์

### ผลลัพธ์ที่คาดหวัง

การรันโปรแกรมจะสร้างไฟล์ที่คล้ายกับภาพด้านล่าง:

![Generated barcode image for Planet symbology](/images/planet-barcode.png){.align-center alt="ภาพบาร์โค้ดที่สร้างขึ้นแสดงบาร์โค้ด Planet ที่มีบาร์โครงว่าง"}

ภาพแสดง **บาร์โค้ด Planet** ที่มีบาร์บาง ๆ ว่างเปล่า ตรงกับขนาดที่คุณกำหนดเองอย่างแม่นยำ

## ความแปรผันทั่วไปและกรณีขอบ

| สถานการณ์ | การปรับเปลี่ยน |
|-----------|------------|
| **ความยาวข้อมูลที่แตกต่าง** | บาร์โค้ด Planet รองรับตัวเลขได้สูงสุด 12 ตัวอักษร เปลี่ยนอาร์กิวเมนต์ตัวที่สองของคอนสตรัคเตอร์ให้สอดคล้อง |
| **ความละเอียดสูงขึ้น** | เพิ่มมิติ X (`setPixels`) หรือกำหนด `YDimension` เพื่อควบคุมความสูงของบาร์ |
| **บาร์โค้ดสี** | ใช้ `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` เพื่อเปลี่ยนสีของบาร์ |
| **บันทึกเป็น SVG** | แทนที่ `BarCodeImageFormat.Png` ด้วย `BarCodeImageFormat.Svg` เพื่อให้ได้ผลลัพธ์แบบเวกเตอร์ |
| **รันบน Android** | ใช้ Aspose.BarCode for Android ที่เข้ากันได้กับ Android และแทนที่พาธของระบบไฟล์ด้วย `Context.getFilesDir()` |

> **ระวัง:** การตั้งมิติ X ต่ำเกินไป (เช่น 1 พิกเซล) อาจทำให้บาร์โค้ดอ่านไม่ออกบนเครื่องพิมพ์ความละเอียดต่ำ ควรทดสอบด้วยสแกนเนอร์จริงหลังจากปรับขนาด

## โค้ดต้นฉบับเต็มสำหรับคัดลอก‑วางอย่างรวดเร็ว

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

คัดลอกโค้ดไปยังไฟล์ชื่อ `PlanetBarcodeDemo.java` วางไว้ภายใต้ `src/main/java/com/example/barcode/` รัน `mvn compile exec:java` แล้วคุณจะเห็นผลลัพธ์ของ **สร้างภาพบาร์โค้ด** ในโฟลเดอร์ `output`

## สรุป

ตอนนี้คุณรู้วิธี **สร้างภาพบาร์โค้ด** สำหรับสัญลักษณ์ Planet ใน Java วิธี **สร้างบาร์โค้ด Planet** ด้วย **ขนาดบาร์โค้ดที่กำหนดเอง** และวิธีสลับจากบาร์เต็มเป็นบาร์ว่างเพื่อสไตล์ที่ดูสะอาดตา ตัวอย่างเต็มแสดงการเรียก API ที่จำเป็นทั้งหมด ตั้งแต่การเริ่มต้นตัวสร้างจนถึงการบันทึกไฟล์ PNG

**ขั้นตอนต่อไป** – สำรวจประเภทบาร์โค้ดอื่น ๆ (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) และทดลองตัวเลือกภาพเพิ่มเติมเช่นสีพื้นหลัง, ระยะขอบ, และการตั้งค่า DPI หากคุณต้องการฝังบาร์โค้ดใน PDF ให้รวมโค้ดนี้กับ Aspose.PDF for Java เพื่อโซลูชันแบบครบวงจร

ขอให้เขียนโค้ดอย่างสนุก!

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดซึ่งต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งข้อมูลมีตัวอย่างโค้ดทำงานครบถ้วนพร้อมคำอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโครงการของคุณ

- [วิธีสร้างบาร์โค้ด Planet ด้วยบาร์เต็มและบาร์ว่าง](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [สร้างภาพบาร์โค้ด Planet – คู่มือขั้นตอนโดยละเอียด](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [วิธีสร้างบาร์โค้ด Java: สร้างภาพบาร์โค้ดที่แม่นยำ](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}