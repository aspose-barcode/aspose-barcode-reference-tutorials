---
date: 2026-08-12
description: เรียนรู้วิธีปรับปรุงการอ่านบาร์โค้ดโดยการปรับอัตรากว้าง‑แคบของ CODE_128
  ใน Java ด้วย Aspose.BarCode และสร้างภาพ PNG อย่างมีประสิทธิภาพ ตามขั้นตอนการสอนการสร้างบาร์โค้ดใน
  Java ของเรา
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: การกำหนดค่าอัตรากว้าง‑แคบ
og_description: เรียนรู้วิธีปรับปรุงการอ่านบาร์โค้ดโดยการปรับอัตรากว้าง‑แคบของ CODE_128
  ใน Java ด้วย Aspose.BarCode บทเรียนขั้นตอนนี้จะแสดงวิธีสร้างบาร์โค้ด PNG อย่างรวดเร็ว
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: ปรับปรุงการอ่านบาร์โค้ดด้วยอัตรากว้าง‑แคบของ CODE_128 (58 ตัวอักษร)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: ปรับปรุงการอ่านบาร์โค้ดด้วยอัตรากว้าง‑แคบของ CODE_128
url: /th/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับปรุงการอ่านบาร์โค้ดด้วยอัตรากว้าง‑แคบ CODE_128

## บทนำ

หากคุณต้องการ **ปรับปรุงการอ่านบาร์โค้ด** สำหรับป้ายสินค้าคงคลัง, ป้ายจัดส่ง, หรือแอปพลิเคชันใด ๆ ที่ใช้ CODE_128, การปรับอัตรากว้าง‑แคบเป็นเทคนิคที่มีประสิทธิภาพที่สุด ในบทเรียนนี้เราจะพาคุณผ่านกระบวนการสร้าง **บาร์โค้ดแบบขั้นตอน** ด้วย Aspose.BarCode for Java, แสดงวิธีกำหนดค่าอัตรา, **สร้างภาพบาร์โค้ด PNG** และ **บันทึกภาพบาร์โค้ด** ลงดิสก์ คุณจะได้เห็นว่าทำไมอัตรานี้จึงสำคัญต่อประสิทธิภาพของสแกนเนอร์และวิธีปรับให้เหมาะกับสภาพแวดล้อมการพิมพ์ของคุณ

## คำตอบอย่างรวดเร็ว
- **อัตรากว้าง‑แคบคืออะไร?** มันควบคุมความกว้างสัมพัทธ์ของบาร์กว้างเทียบกับบาร์แคบในบาร์โค้ด.  
- **สัญลักษณ์ใดสนับสนุนการปรับอัตรา?** สัญลักษณ์ 1‑D ส่วนใหญ่ รวมถึง CODE_128, อนุญาตให้คุณตั้งค่าอัตราที่กำหนดเอง.  
- **ต้องการใบอนุญาตหรือไม่?** มีรุ่นทดลองใช้ฟรี, แต่ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **ฉันสามารถสร้างภาพบาร์โค้ดในรูปแบบ PNG ได้หรือไม่?** ใช่—ใช้ `generator.save(...)` เพื่อสร้างภาพบาร์โค้ด PNG.  
- **โค้ดนี้เข้ากันได้กับ Java 8+ หรือไม่?** แน่นอน; Aspose.BarCode ทำงานกับเวอร์ชัน Java สมัยใหม่ทั้งหมด.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.BarCode for Java ดาวน์โหลดจาก [download link](https://releases.aspose.com/barcode/java/).

## นำเข้าแพ็คเกจ

เพื่อเริ่มต้น, ให้นำเข้าคลาส Aspose.BarCode ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ `BarcodeGenerator` คือคลาสหลักที่ใช้สร้างภาพบาร์โค้ดด้วยสัญลักษณ์และตัวเลือกที่กำหนด.  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## อัตรากว้าง‑แคบคืออะไรและทำไมต้องปรับมัน?

อัตรากว้าง‑แคบกำหนดว่าบาร์ “กว้าง” กว้างกว่าบาร์ “แคบ” กี่เท่า การปรับอัตรานี้ช่วยเพิ่มความเข้ากันได้ของสแกนเนอร์ (สแกนเนอร์ส่วนใหญ่อ่านได้ดีที่สุดเมื่ออัตราอยู่ระหว่าง 2.0 และ 3.0), ชดเชยข้อจำกัดของ DPI ของเครื่องพิมพ์, และทำให้คุณสามารถปรับสไตล์ภาพของแบรนด์ได้โดยไม่เสียความน่าเชื่อถือ.

## วิธีปรับปรุงการอ่านบาร์โค้ดโดยการสร้างบาร์โค้ด CODE_128 ด้วยอัตรากว้าง‑แคบใน Java

เริ่มต้นโดยเพิ่มไลบรารี Aspose.BarCode ไปยังโปรเจกต์ Java ของคุณ, จากนั้นสร้างอินสแตนซ์ `BarcodeGenerator` โดยระบุ `EncodeTypes.CODE_128`. ตั้งค่าอัตรากว้าง‑แคบที่ต้องการด้วย `setWideNarrowRatio`, ปรับการตั้งค่าอื่น ๆ ตามต้องการ, และสุดท้ายเรียก `save` เพื่อบันทึกบาร์โค้ดเป็นไฟล์ PNG. กระบวนการสั้น ๆ นี้ทำให้คุณได้คุณภาพบาร์โค้ดที่สม่ำเสมอและเพิ่มอัตราการอ่านของสแกนเนอร์ในอุปกรณ์หลากหลาย.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน; ที่นี่คือที่ไฟล์ **saved barcode image** จะถูกจัดเก็บ.

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์บาร์โค้ด

คลาส `BarcodeGenerator` สร้างภาพบาร์โค้ดตามสัญลักษณ์และตัวเลือกการเข้ารหัสที่ระบุ.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

ที่นี่เรา **สร้างบาร์โค้ด CODE_128** โดยส่ง `EncodeTypes.CODE_128` ไปยังคอนสตรัคเตอร์.

### ขั้นตอนที่ 3: ตั้งค่าอัตรากว้าง‑แคบ

`setWideNarrowRatio` กำหนดสัดส่วนระหว่างบาร์กว้างและบาร์แคบสำหรับบาร์โค้ดที่สร้าง.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

เมธอด `setWideNarrowRatio` ให้คุณปรับระยะห่างภาพอย่างละเอียด ค่า `3.0f` หมายถึงบาร์กว้างกว้างสามเท่าของบาร์แคบ, ซึ่งอยู่ในช่วงที่เหมาะสม 2.0‑3.0 สำหรับสแกนเนอร์ส่วนใหญ่.

### ขั้นตอนที่ 4: บันทึกภาพลงดิสก์

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

การเรียก `save` จะ **สร้างภาพบาร์โค้ด** และเก็บเป็นไฟล์ PNG, เสร็จสิ้นขั้นตอน **save barcode image**.

## ทำไมต้องปรับอัตรากว้าง‑แคบ?

การปรับอัตรากว้าง‑แคบช่วยเพิ่มความเข้ากันได้ของสแกนเนอร์เนื่องจากสแกนเนอร์อุตสาหกรรมส่วนใหญ่อ่านได้ดีที่สุดเมื่ออัตราอยู่ระหว่าง 2.0 ถึง 3.0 นอกจากนี้ยังช่วยปรับคุณภาพการพิมพ์โดยชดเชยความละเอียดของเครื่องพิมพ์ที่ 150–300 dpi, ลดการบิดเบือนของบาร์ อีกทั้งอัตรานี้ยังทำให้บริษัทสามารถปรับสไตล์บาร์โค้ดให้สอดคล้องกับแนวทางแบรนด์โดยไม่กระทบประสิทธิภาพการสแกน.

## ปัญหาที่พบบ่อยและวิธีแก้ไข

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| บาร์โค้ดดูบิดเบี้ยว | อัตราสูง/ต่ำเกินไปสำหรับเครื่องพิมพ์ | ปรับค่าที่ส่งให้ `setWideNarrowRatio` (เช่น 2.0‑2.5). |
| ไฟล์ไม่ถูกสร้าง | พาธ `dataDir` ไม่ถูกต้องหรือสิทธิ์ไม่เพียงพอ | ตรวจสอบพาธไดเรกทอรีและให้แน่ใจว่าแอปพลิเคชันมีสิทธิ์เขียน. |
| สแกนเนอร์ไม่สามารถอ่านบาร์โค้ดได้ | อัตรานอกช่วงที่แนะนำสำหรับสัญลักษณ์ | ใช้ค่าอัตรามาตรฐาน (2.0‑3.0) หรือทดสอบกับสแกนเนอร์เป้าหมาย. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.BarCode กับเฟรมเวิร์ก Java อื่น ๆ ได้หรือไม่?**  
A: ใช่, Aspose.BarCode ทำงานร่วมกับ Spring, Java EE, Android, และสภาพแวดล้อม Java อื่น ๆ อย่างราบรื่น.

**Q: ฉันจะสร้างบาร์โค้ดด้วยสัญลักษณ์ที่ต่างกันได้อย่างไร?**  
A: เปลี่ยนประเภทสัญลักษณ์ในคอนสตรัคเตอร์ `BarcodeGenerator`, ตัวอย่างเช่น `EncodeTypes.QR` สำหรับ QR code.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.BarCode หรือไม่?**  
A: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีได้ที่ [Aspose.BarCode free trial page](https://releases.aspose.com/).

**Q: ฉันจะหาเอกสารรายละเอียดของ Aspose.BarCode ได้จากที่ไหน?**  
A: ดูเอกสารที่ [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).

**Q: จะรับการสนับสนุนสำหรับ Aspose.BarCode อย่างไร?**  
A: เยี่ยมชมฟอรั่มชุมชน Aspose.BarCode ที่ [Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13) เพื่อรับการสนับสนุนและการสนทนาชุมชน.

---

**อัปเดตล่าสุด:** 2026-08-12  
**ทดสอบกับ:** Aspose.BarCode for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างบาร์โค้ด Java – ตั้งค่าความละเอียดภาพด้วย Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [ตรวจจับการวางแนบาร์โค้ดใน Java ด้วย Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [วิธีสร้างภาพบาร์โค้ด code128 ใน Java ด้วย Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}