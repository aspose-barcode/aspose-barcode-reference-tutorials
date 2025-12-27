---
date: 2025-12-27
description: เรียนรู้วิธีสร้างบาร์โค้ด Data Matrix และวิธีตั้งตำแหน่งข้อความบาร์โค้ดใน
  Java ด้วย Aspose.BarCode. ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการปรับแต่งเต็มรูปแบบ.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: สร้างบาร์โค้ด Data Matrix และกำหนดตำแหน่งข้อความโค้ดใน Java
url: /th/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด Data Matrix และกำหนดตำแหน่งข้อความโค้ดใน Java

## บทนำ

การสร้างบาร์โค้ดเป็นความต้องการทั่วไปสำหรับการจัดการสินค้าคงคลัง, การจัดส่ง, และแอปพลิเคชันอื่น ๆ ที่ใช้ Java. ด้วย **Aspose.BarCode for Java** คุณสามารถ **สร้างบาร์โค้ด Data Matrix** ได้อย่างรวดเร็วและควบคุมทุกแง่มุมของภาพ, รวมถึงตำแหน่งที่ข้อความที่มนุษย์อ่านได้ปรากฏ. ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อ **สร้างบาร์โค้ด Data Matrix** และสาธิต **วิธีกำหนดตำแหน่งข้อความบาร์โค้ด** ด้านบนสัญลักษณ์เพื่อให้ตรงกับข้อกำหนดการออกแบบของคุณ.

## คำตอบสั้น
- **ไลบรารีที่ใช้คืออะไร?** Aspose.BarCode for Java  
- **ประเภทบาร์โค้ดที่แสดงคืออะไร?** Data Matrix  
- **คุณกำหนดตำแหน่งข้อความโค้ดอย่างไร?** ใช้ `CodeLocation.ABOVE`  
- **ต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์  
- **โค้ดสามารถทำงานบน Java 8+ ได้หรือไม่?** แน่นอน, รองรับ Java 8 และรุ่นต่อ ๆ ไป  

## Data Matrix barcode คืออะไร?
Data Matrix barcode คือสัญลักษณ์สองมิติ (2‑D) ที่เก็บข้อมูลจำนวนมากในรูปแบบสี่เหลี่ยมจัตุรัสหรือสี่เหลี่ยมผืนผ้าขนาดกะทัดรัด. มันถูกใช้กันอย่างกว้างขวางในการทำเครื่องหมายสินค้าขนาดเล็ก, อิเล็กทรอนิกส์, และอุปกรณ์ทางการแพทย์ เนื่องจากสามารถเข้ารหัสได้สูงสุดถึง 2,335 ตัวอักษรอัลฟานูเมอริก.

## ทำไมต้องกำหนดตำแหน่งข้อความบาร์โค้ด?
การวางข้อความที่มนุษย์อ่านได้ **ด้านบน**, **ด้านล่าง**, หรือ **ข้างเคียง** ของบาร์โค้ดช่วยให้ผู้ใช้ตรวจสอบข้อมูลที่เข้ารหัสได้อย่างรวดเร็วโดยไม่ต้องสแกน. การปรับตำแหน่งข้อความช่วยปรับปรุงความสอดคล้องของ UI และสอดคล้องกับแนวทางการสร้างแบรนด์.

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
- ติดตั้ง Java Development Kit (JDK) แล้ว  
- IDE เช่น Eclipse หรือ IntelliJ IDEA  
- ไลบรารี Aspose.BarCode for Java (ดาวน์โหลดได้จาก [here](https://releases.aspose.com/barcode/java/))  

## นำเข้าแพ็กเกจ

First, import the essential Aspose.BarCode classes into your project:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

These imports give you access to the barcode generator and the enumeration that controls text placement.

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรี
ระบุที่ที่คุณต้องการอ่าน/เขียนไฟล์. แทนที่ตัวแปรตำแหน่งที่เก็บด้วยเส้นทางจริงบนเครื่องของคุณ.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ของ BarcodeGenerator
สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภท **Data Matrix** และระบุข้อความโค้ดที่ต้องการเข้ารหัส.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### ขั้นตอนที่ 3: วิธีกำหนดตำแหน่งข้อความบาร์โค้ด
ใช้ enumeration `CodeLocation` เพื่อย้ายข้อความที่มนุษย์อ่านได้. ในตัวอย่างนี้เราวางข้อความ **ด้านบน** ของบาร์โค้ด.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ดที่สร้างขึ้น
สุดท้าย, เขียนภาพบาร์โค้ดลงดิสก์. ไฟล์จะประกอบด้วยสัญลักษณ์ Data Matrix พร้อมข้อความที่วางอยู่ด้านบน.

```java
generator.save(dataDir + "codetextAbove.png");
```

## ปัญหาที่พบบ่อยและวิธีแก้

- **ข้อความไม่แสดง:** ตรวจสอบว่าคุณใช้เวอร์ชันของ Aspose.BarCode ที่รองรับ `CodeLocation`.  
- **ข้อผิดพลาดของเส้นทางไฟล์:** ยืนยันว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) ที่เหมาะสมกับระบบปฏิบัติการของคุณ.  
- **อักขระที่ไม่รองรับ:** Data Matrix สามารถเข้ารหัสได้เพียงชุดอักขระที่จำกัด; หลีกเลี่ยงสัญลักษณ์พิเศษที่ไม่อยู่ในมาตรฐาน ISO/IEC 16022.  

## คำถามที่พบบ่อย (FAQs)

### ถ: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างได้หรือไม่?
A: ใช่, Aspose.BarCode มีตัวเลือกการปรับแต่งอย่างกว้างขวาง, ให้คุณควบคุมสี, ระยะขอบ, และรูปแบบฟอนต์.

### ถ: Aspose.BarCode รองรับ Java 8 และเวอร์ชันต่อ ๆ ไปหรือไม่?
A: แน่นอน, ไลบรารีทำงานกับ Java 8 และรุ่นต่อ ๆ ไปทั้งหมด.

### ถ: ฉันจะรวม Aspose.BarCode เข้ากับโปรเจกต์ Java ที่มีอยู่ของฉันได้อย่างไร?
A: เพิ่มไฟล์ JAR ของ Aspose.BarCode ลงใน classpath ของโปรเจกต์, นำเข้าแพ็กเกจที่จำเป็น, แล้วคุณพร้อมที่จะสร้างบาร์โค้ด.

### ถ: มีเวอร์ชันทดลองของ Aspose.BarCode หรือไม่?
A: มี, คุณสามารถสำรวจความสามารถของ Aspose.BarCode ได้โดยรับเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/).

### ถ: ฉันจะหาความช่วยเหลือหรือการสนับสนุนสำหรับ Aspose.BarCode ได้จากที่ไหน?
A: เยี่ยมชม [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ.

## คำถามเพิ่มเติมที่พบบ่อย

**ถาม: ฉันสามารถสร้างบาร์โค้ดที่มีข้อความวางอยู่ด้านล่างสัญลักษณ์ได้หรือไม่?**  
A: ใช่, ตั้งค่า `CodeLocation.BELOW` ในเมธอด `setLocation` เดียวกัน.

**ถาม: ไลบรารีรองรับบาร์โค้ด 2‑D อื่น ๆ เช่น QR Code หรือไม่?**  
A: แน่นอน, เพียงเปลี่ยน `EncodeTypes.DATA_MATRIX` เป็น `EncodeTypes.QR`.

**ถาม: ฉันจะเปลี่ยนขนาดฟอนต์ของข้อความบาร์โค้ดได้อย่างไร?**  
A: ใช้ `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## สรุป

คุณได้เรียนรู้วิธี **สร้างบาร์โค้ด Data Matrix** ใน Java และควบคุมอย่างแม่นยำ **วิธีกำหนดตำแหน่งข้อความบาร์โค้ด** ด้วย Aspose.BarCode. ทดลองใช้ค่า `CodeLocation` อื่น ๆ และตัวเลือกการจัดรูปแบบเพื่อให้ตรงกับความต้องการการออกแบบของแอปพลิเคชันของคุณ.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}