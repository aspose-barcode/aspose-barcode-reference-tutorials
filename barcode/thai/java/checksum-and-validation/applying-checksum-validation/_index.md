---
date: 2025-12-19
description: เรียนรู้วิธีปิดการตรวจสอบ checksum ใน Java ด้วย Aspose.BarCode คู่มือแบบขั้นตอนนี้จะแสดงวิธีอ่านบาร์โค้ด
  ปิดการตรวจสอบ checksum และทำให้การจัดการข้อมูลเป็นไปอย่างเชื่อถือได้
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: วิธีปิดการตรวจสอบ Checksum ใน Java
url: /th/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปิดการตรวจสอบ Checksum ใน Java

ในแอปพลิเคชันการจัดการสินค้าคงคลังและโลจิสติกส์สมัยใหม่, **วิธีปิดการตรวจสอบ checksum** สามารถเป็นกุญแจสำคัญในการอ่านบาร์โค้ดรุ่นเก่าที่ไม่มีเลข checksum. Aspose.BarCode for Java ทำให้การปิดการตรวจสอบ checksum เป็นเรื่องง่ายโดยยังคงสามารถดึงข้อมูลที่เข้ารหัสได้. บทแนะนำนี้จะพาคุณผ่านกระบวนการทั้งหมด — ตั้งแต่การตั้งค่าโปรเจกต์จนถึงการอ่านบาร์โค้ด ONE‑CODE โดยไม่ตรวจสอบ checksum.

## คำตอบสั้น
- **การปิดการตรวจสอบ checksum ทำอะไร?** มันบอกให้ตัวอ่านละเลยฟิลด์ checksum, ทำให้บาร์โค้ดที่ไม่มี checksum ที่ถูกต้องสามารถประมวลผลได้.  
- **เมื่อใดที่ควรปิดการตรวจสอบ checksum?** เมื่อทำงานกับระบบรุ่นเก่าหรือบาร์โค้ดที่ไม่เป็นมาตรฐานซึ่งละเว้นหรือทำให้ checksum เสียหาย.  
- **คลาสใดที่ควบคุมการตรวจสอบ checksum?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **การปิดการตรวจสอบ checksum ปลอดภัยหรือไม่?** ปลอดภัยเฉพาะเมื่อคุณเชื่อถือแหล่งที่มาของบาร์โค้ด; มิฉะนั้นการตรวจสอบช่วยจับข้อผิดพลาด.  
- **การตั้งค่านี้ส่งผลต่อประเภทบาร์โค้ดอื่นหรือไม่?** การตั้งค่านี้ใช้กับอินสแตนซ์ `BarCodeReader` ปัจจุบันเท่านั้น.

## Checksum Validation คืออะไร?
Checksum validation คือการตรวจสอบความสมบูรณ์ของข้อมูลที่คำนวณค่าขนาดเล็กจากเนื้อหาของบาร์โค้ดและเปรียบเทียบกับ checksum ที่ฝังอยู่. หากค่าไม่ตรงกัน, บาร์โค้ดจะถือว่าอ่านไม่ได้. การปิดการตรวจสอบนี้บอกให้ Aspose.BarCode ข้ามการเปรียบเทียบ.

## ทำไมต้องปิด Checksum กับ Aspose.BarCode?
- **การสนับสนุนรุ่นเก่า:** สแกนเนอร์รุ่นเก่ามักสร้างบาร์โค้ดโดยไม่มี checksum.  
- **ประสิทธิภาพ:** การข้ามการคำนวณสามารถเร่งการอ่านเป็นชุดใหญ่ได้.  
- **ความยืดหยุ่น:** คุณสามารถกำหนดแต่ละอินสแตนซ์ของตัวอ่านว่าจะบังคับใช้การตรวจสอบหรือไม่.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** ตรวจสอบว่าคุณได้ติดตั้ง JDK เวอร์ชันล่าสุด.  
- **Aspose.BarCode Library:** ดาวน์โหลดไลบรารีจากเว็บไซต์ทางการ [ที่นี่](https://releases.aspose.com/barcode/java/).  

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ, ให้นำเข้าคลาสของ Aspose.BarCode ที่จำเป็นสำหรับการจดจำบาร์โค้ด.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ Java ใหม่ (IDE ที่คุณเลือก) และเพิ่มไฟล์ JAR ของ Aspose.BarCode ไปยัง classpath ของโปรเจกต์.

### ขั้นตอนที่ 2: เริ่มต้น `BarCodeReader`
โหลดภาพที่มีบาร์โค้ด ONE‑CODE ที่คุณต้องการอ่าน.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### ขั้นตอนที่ 3: วิธีปิด Checksum
บอกให้ตัวอ่านละเลยการตรวจสอบ checksum โดยตั้งค่าคุณสมบัติเป็น `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### ขั้นตอนที่ 4: อ่านบาร์โค้ด
วนลูปผลลัพธ์และพิมพ์ข้อความที่ถอดรหัสและประเภทสัญลักษณ์.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**ผลลัพธ์:** ข้อความบาร์โค้ดจะแสดงแม้ว่าภาพต้นฉบับจะไม่มี checksum ที่ถูกต้อง.

## ปัญหาและเคล็ดลับทั่วไป
- **เส้นทางไฟล์ไม่ถูกต้อง:** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้อง; ใช้เส้นทางแบบเต็มสำหรับการทดสอบ.  
- **ประเภทบาร์โค้ดที่ไม่รองรับ:** ตรวจสอบว่า `DecodeType` ตรงกับบาร์โค้ดที่คุณกำลังอ่าน.  
- **ประสิทธิภาพ:** การปิด checksum ในชุดข้อมูลขนาดใหญ่สามารถเพิ่มอัตราการประมวลผล, แต่ควรเปิดใช้งานใหม่สำหรับข้อมูลสำคัญ.

## คำถามที่พบบ่อย

### Aspose.BarCode รองรับประเภทบาร์โค้ดต่าง ๆ หรือไม่?
ใช่, Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลากหลายประเภท, ตั้งแต่ QR และ DataMatrix ไปจนถึงโค้ดเชิงเส้นแบบดั้งเดิม.

### ฉันสามารถใช้ Aspose.BarCode เพื่อการค้าได้หรือไม่?
แน่นอน. มีใบอนุญาตเชิงพาณิชย์สำหรับธุรกิจที่ต้องการฟีเจอร์พร้อมใช้งานในผลิตภัณฑ์.

### ฉันจะรับการสนับสนุนสำหรับ Aspose.BarCode อย่างไร?
เยี่ยมชม [ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือจากทีมผลิตภัณฑ์.

### มีการทดลองใช้ฟรีหรือไม่?
ใช่, คุณสามารถสำรวจฟีเจอร์ทั้งหมดโดยดาวน์โหลด [การทดลองใช้ฟรี](https://releases.aspose.com/).

### ฉันจะหาเอกสารรายละเอียดได้จากที่ไหน?
ดูที่ [เอกสารประกอบ](https://reference.aspose.com/barcode/java/) สำหรับรายละเอียด API, ตัวอย่างโค้ด, และแนวทางปฏิบัติที่ดีที่สุด.

---

**อัปเดตล่าสุด:** 2025-12-19  
**ทดสอบด้วย:** Aspose.BarCode for Java (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}