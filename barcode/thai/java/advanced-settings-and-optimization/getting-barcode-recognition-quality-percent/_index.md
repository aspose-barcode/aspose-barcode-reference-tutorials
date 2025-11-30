---
date: 2025-11-30
description: เรียนรู้วิธีประเมินคุณภาพการอ่านบาร์โค้ดใน Java ด้วย Aspose.Barcode คู่มือขั้นตอนต่อขั้นตอนเพื่อดึงเปอร์เซ็นต์คุณภาพการจดจำ
language: th
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – การรับคุณภาพการจดจำบาร์โค้ดเป็นเปอร์เซ็นต์
url: /java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – การรับคุณภาพการจดจำบาร์โค้ดเป็นเปอร์เซ็นต์

## Introduction

หากคุณต้องการ **ประเมินคุณภาพการอ่านบาร์โค้ด** ในแอปพลิเคชัน Java, **Aspose.Barcode Java** มี API ที่เรียบง่ายซึ่งคืนค่าคุณภาพการจดจำเป็นเปอร์เซ็นต์ ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนที่จำเป็นเพื่อดึงเปอร์เซ็นต์นั้น, อธิบายว่าทำไมเมตริกนี้สำคัญ, และแสดงวิธีรวมการเรียกนี้เข้าไปในโค้ดของคุณที่มีอยู่แล้ว

## Quick Answers
- **“คุณภาพการอ่าน” หมายถึงอะไร?** เป็นคะแนนความมั่นใจ (0‑100 %) ที่ไลบรารีกำหนดให้กับบาร์โค้ดแต่ละอันที่ถอดรหัสได้  
- **ต้องใช้เวอร์ชันของไลบรารีใด?** ใด ๆ ที่เป็น Aspose.Barcode Java รุ่นล่าสุด (ตัวอย่างใช้ชุด 24.x ล่าสุด)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ชั่วคราวใช้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **สามารถอ่านบาร์โค้ดทุกประเภทได้หรือไม่?** ได้ – ธง `DecodeType.ALL_SUPPORTED_TYPES` เปิดใช้งานรูปแบบทั้งหมดที่ Aspose.Barcode รองรับ  
- **ค่าคุณภาพเชื่อถือได้สำหรับ QR code หรือไม่?** แน่นอน – อัลกอริทึมความมั่นใจเดียวกันใช้กับสัญลักษณ์ 1‑D และ 2‑D ทั้งหมด

## What is Aspose.Barcode Java and How to Assess Barcode Reading Quality?

**Aspose.Barcode Java** เป็นไลบรารีที่จัดการเต็มรูปแบบซึ่งช่วยให้นักพัฒนาสร้าง, อ่าน, และวิเคราะห์บาร์โค้ดโดยไม่ต้องพึ่งพาไลบรารีภายนอก หนึ่งในเครื่องมือวินิจฉัยที่มีประโยชน์ที่สุดคือเมตริก **คุณภาพการอ่าน** ซึ่งบอกระดับความมั่นใจของเอ็นจินในการถอดรหัสสัญลักษณ์ เมตริกนี้สำคัญเมื่อคุณต้องตัดสินใจว่าจะยอมรับการสแกน, ขอให้ผู้ใช้ทำการจับภาพใหม่, หรือเรียกใช้ตรรกะการจัดการข้อผิดพลาด

## Why Use Aspose.Barcode Java for Barcode Reading Quality?

- **คะแนนความมั่นใจสม่ำเสมอ** ในสัญลักษณ์ที่รองรับทั้งหมด  
- **ไม่มี DLL เนทีฟ** – เป็น Java แท้ ๆ ทำงานได้บนแพลตฟอร์มที่รองรับ JVM ใดก็ได้  
- **การควบคุมระดับละเอียด**: คุณสามารถดึงค่าคุณภาพต่อบาร์โค้ดได้ ไม่ใช่แค่ผลลัพธ์แบบผ่าน/ไม่ผ่านทั่ว ๆ ไป  
- **เอ็นจินอ่านที่ปรับประสิทธิภาพ** สามารถขยายจากเดสก์ท็อปถึงบริการคลาวด์ได้

## Prerequisites

ก่อนเริ่มทำงาน, ตรวจสอบว่าคุณมี:

- **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือใหม่กว่า, พร้อม IDE ที่คุณชอบ (IntelliJ, Eclipse, VS Code ฯลฯ)  
- **ไลบรารี Aspose.Barcode Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/)  
- **ภาพบาร์โค้ดตัวอย่าง** – บทแนะนำนี้ใช้ไฟล์ `code39Extended.jpg` ที่อยู่ในโฟลเดอร์ `BarcodeReader/advanced_features/`

เมื่อเตรียมพร้อมแล้ว, เรามาเริ่มเขียนโค้ดกัน

## Import Namespaces

การนำเข้าต่อไปนี้ให้คุณเข้าถึงคลาสตัวอ่านและผลลัพธ์ที่จำเป็นสำหรับการดึงคุณภาพ

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Step 1: Set the Resource Directory Path

กำหนดโฟลเดอร์ที่บรรจุภาพตัวอย่าง `Utils.getDataDir` เป็นตัวช่วยที่คำนวณเส้นทางเต็มสำหรับโปรเจกต์ปัจจุบัน

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Step 2: Initialize the BarCodeReader Object

สร้างอินสแตนซ์ `BarCodeReader` โดยชี้ไปที่ไฟล์ภาพและบอกให้พยายามอ่าน **บาร์โค้ดทุกประเภทที่รองรับ**

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Step 3: Read the Barcodes and Retrieve the Quality Percentage

วนลูปผ่านบาร์โค้ดที่ตรวจพบแต่ละอัน, พิมพ์ข้อความ, ประเภท, และเปอร์เซ็นต์ **คุณภาพการอ่าน** ที่คืนจาก `getReadingQuality()`

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**เกิดอะไรขึ้นที่นี่?**  
- `readBarCodes()` คืนคอลเลกชันของอ็อบเจ็กต์ `BarCodeResult`, หนึ่งอ็อบเจ็กต์ต่อบาร์โค้ดที่พบ  
- `getReadingQuality()` ให้ค่า `double` ระหว่าง `0` ถึง `100`, แสดงระดับความมั่นใจ  
- คุณสามารถใช้ค่านี้ตัดสินใจว่าการสแกนนั้นยอมรับได้หรือควรขอให้ผู้ใช้ทำการสแกนใหม่

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Quality always 0** | ภาพความละเอียดต่ำหรือเบลอมาก | ใช้แหล่งภาพความละเอียดสูงกว่า หรือทำการประมวลผลภาพล่วงหน้า (เช่น การเพิ่มความคม) |
| **No barcodes detected** | ธง `DecodeType` ไม่ถูกต้อง | ตรวจสอบให้ใช้ `DecodeType.ALL_SUPPORTED_TYPES` หรือระบุประเภทที่คุณคาดหวังอย่างชัดเจน |
| **Exception on `Utils.getDataDir`** | โครงสร้างโปรเจกต์แตกต่างจากตัวอย่าง | แทนที่การเรียกตัวช่วยด้วยเส้นทางเต็มที่กำหนดเองหรือเส้นทางสัมพันธ์ที่ตรงกับโครงสร้างของคุณ |

## Frequently Asked Questions

### Q1: Aspose.Barcode รองรับบาร์โค้ดทุกประเภทหรือไม่?

A1: Aspose.Barcode รองรับสัญลักษณ์บาร์โค้ดหลากหลายรวมถึง 1‑D (Code‑39, Code‑128, UPC) และ 2‑D (QR, DataMatrix, PDF417) ด้วยมาตรฐานต่าง ๆ

### Q2: สามารถใช้ Aspose.Barcode เพื่อการค้าได้หรือไม่?

A2: ใช่, คุณสามารถใช้ Aspose.Barcode ในโครงการส่วนบุคคลและเชิงพาณิชย์ได้ รายละเอียดลิขสิทธิ์มีให้ดู [ที่นี่](https://purchase.aspose.com/buy)

### Q3: จะขอรับลิขสิทธิ์ชั่วคราวเพื่อการทดสอบได้อย่างไร?

A3: รับลิขสิทธิ์ชั่วคราวจากพอร์ทัล Aspose [ที่นี่](https://purchase.aspose.com/temporary-license/)

### Q4: จะหาแหล่งสนับสนุนและชุมชนเพิ่มเติมได้จากที่ไหน?

A4: เยี่ยมชม [ฟอรั่ม Aspose.Barcode](https://forum.aspose.com/c/barcode/13) เพื่อรับการสนับสนุนจากผู้ใช้และทีมงานอย่างเป็นทางการ

### Q5: มีตัวอย่างโค้ดเพิ่มเติมในเอกสารหรือไม่?

A5: มี, ตัวอย่างโค้ดที่ครอบคลุมให้ในเอกสารอย่างเป็นทางการ [ที่นี่](https://reference.aspose.com/barcode/java/)

## Conclusion

ด้วยการใช้ **Aspose.Barcode Java** คุณสามารถดึง **เปอร์เซ็นต์คุณภาพการอ่านบาร์โค้ด** สำหรับสัญลักษณ์ที่สแกนได้อย่างง่ายดาย เมตริกนี้ช่วยให้คุณสร้างตรรกะการตรวจสอบที่ฉลาดขึ้น, ปรับปรุงประสบการณ์ผู้ใช้, และรักษาความสมบูรณ์ของข้อมูลในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ

---

**Last Updated:** 2025-11-30  
**Tested With:** Aspose.Barcode Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}