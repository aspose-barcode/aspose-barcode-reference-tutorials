---
date: 2026-04-05
description: เรียนรู้วิธีสร้างภาพบาร์โค้ด Codabar ด้วย Java พร้อมเช็คซัมและดูตัวอย่างเครื่องอ่านบาร์โค้ด
  Java โดยใช้ Aspose.BarCode ทำตามคู่มือขั้นตอนนี้เพื่อสร้างและจดจำบาร์โค้ด
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: การประยุกต์ใช้ Checksum สำหรับ CodaBar
second_title: Aspose.BarCode Java API
title: วิธีสร้างภาพบาร์โค้ด Codabar ด้วย Java พร้อมตรวจสอบผลรวม
url: /th/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ด codabar ด้วย Java พร้อมเช็คซัม

## บทนำ

ในบทเรียนนี้ คุณจะ **สร้างภาพบาร์โค้ด codabar ด้วย Java** พร้อมเช็คซัม Mod 10 โดยใช้ Aspose.BarCode for Java เราจะอธิบายขั้นตอนการสร้างบาร์โค้ด CodaBar, เปิดใช้งานเช็คซัม, และจากนั้นตรวจสอบด้วย **ตัวอย่างตัวอ่านบาร์โค้ด Java** เมื่อเสร็จคุณจะได้โค้ดสั้นที่พร้อมใช้งานซึ่งสามารถนำไปใส่ในโปรเจกต์ Java ใดก็ได้ ไม่ว่าจะเป็นระบบห้องสมุด, เครื่องพิมพ์ฉลากห้องปฏิบัติการการแพทย์, หรือโซลูชันการชำระเงินในร้านค้าปลีก

## คำตอบสั้น
- **เช็คซัมทำหน้าที่อะไร?** มันตรวจสอบความสมบูรณ์ของข้อมูลบาร์โค้ดระหว่างการสแกน.  
- **ต้องใช้ไลบรารีอะไร?** Aspose.BarCode for Java.  
- **ต้องใช้ลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ลิขสิทธิ์ชั่วคราวใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.  
- **สามารถปรับแต่งลักษณะของบาร์โค้ดได้หรือไม่?** ได้ – สามารถเปลี่ยนสี, ขนาด, และฟอนต์ผ่านพารามิเตอร์ของตัวสร้าง.  
- **รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?** ไลบรารีรองรับ Java 8 และใหม่กว่า.

## วิธีสร้างบาร์โค้ด codabar ด้วย Java

ด้านล่างนี้คุณจะพบคู่มือสั้น ๆ ที่อธิบาย **ทำไมแต่ละบรรทัดถึงสำคัญ** เพื่อให้คุณปรับโค้ดให้เข้ากับโปรเจกต์ของคุณได้อย่างมั่นใจ

### CodaBar barcode คืออะไร?

CodaBar เป็นสัญลักษณ์เชิงเส้น (มิติเดียว) ที่ใช้กันอย่างแพร่หลายในห้องสมุด, ธนาคารเลือด, และการค้าปลีก มันเข้ารหัสข้อมูลตัวเลขและอักขระพิเศษบางตัว ทำให้เหมาะสำหรับแท็กที่อ่านโดยเครื่องได้ง่าย การเพิ่มเช็คซัม (Mod 10) ช่วยเพิ่มความแม่นยำในการอ่าน โดยเฉพาะบนการพิมพ์คุณภาพต่ำ

### ทำไมต้องใช้ Aspose.BarCode สำหรับ Java?

Aspose.BarCode มี **ตัวอย่างตัวอ่านบาร์โค้ด Java** ที่ทำให้ซับซ้อนของการสร้างและการจดจำบาร์โค้ดระดับล่างถูกซ่อนอยู่ มันให้:

* การควบคุมเต็มรูปแบบของโหมดเช็คซัม  
* การรวมเข้ากับ IDE ของ Java อย่างไร้รอยต่อ  
* เอกสารที่ครอบคลุมและการสนับสนุนที่ตอบสนองเร็ว  

### ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมี:

- Java Development Kit (JDK) 8 หรือใหม่กว่า ติดตั้งแล้ว  
- ไลบรารี Aspose.BarCode for Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/barcode/java/)  
- ความคุ้นเคยพื้นฐานกับแนวคิดการเขียนโปรแกรม Java  

### นำเข้าแพ็กเกจ

ในโปรเจกต์ Java ของคุณ ให้นำเข้าคลาสที่จำเป็นเพื่อทำงานกับ Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

### คู่มือขั้นตอนต่อขั้นตอน

#### ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม

สร้างโปรเจกต์ Java ใหม่และเพิ่มไฟล์ JAR ของ Aspose.BarCode ไปยังเส้นทางการสร้างของคุณ กำหนดโฟลเดอร์ที่ภาพที่สร้างขึ้นจะถูกบันทึก

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### ขั้นตอนที่ 2: สร้างภาพบาร์โค้ด CodaBar พร้อมเช็คซัม

สร้างอินสแตนซ์ของ `BarcodeGenerator`, เปิดใช้งานเช็คซัม, เลือกโหมด Mod 10, และบันทึกภาพ

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### ขั้นตอนที่ 3: ตัวอย่างตัวอ่านบาร์โค้ด Java – ตรวจจับบาร์โค้ด

ตอนนี้อ่านบาร์โค้ดกลับมาโดยเปิดการตรวจสอบเช็คซัมเพื่อให้แน่ใจว่าข้อมูลถูกต้อง

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

การรันโค้ดจะพิมพ์ข้อความที่ถอดรหัส, ประเภทสัญลักษณ์, และเช็คซัมที่คำนวณได้, ยืนยันว่าบาร์โค้ดถูกสร้างและตรวจสอบอย่างถูกต้อง

### กรณีการใช้งานทั่วไป

- **การจัดการห้องสมุด:** เข้ารหัสรหัสหนังสือสำหรับการสแกนอย่างรวดเร็วที่จุดชำระเงิน.  
- **ป้ายธนาคารเลือด:** รับรองการระบุตัวผู้ป่วยอย่างแม่นยำด้วยการป้องกันเช็คซัม.  
- **ป้ายชั้นวางสินค้าในร้านค้า:** พิมพ์บาร์โค้ดราคาต่ำและความเร็วสูงสำหรับการติดตามสินค้าคงคลัง.  

### ปัญหาและวิธีแก้ไขทั่วไป

| ปัญหา | วิธีแก้ไข |
|-------|----------|
| **การตรวจสอบเช็คซัมล้มเหลว** | ตรวจสอบว่า `EnableChecksum` ถูกตั้งค่าเป็น `YES` และ `CodabarChecksumMode` ตรงกับโหมดที่ใช้ในการสร้าง (Mod 10). |
| **ข้อผิดพลาดไฟล์ไม่พบ** | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และภาพที่สร้าง (`Codabar_Mod10.png`) ถูกบันทึกไว้ที่นั่นก่อนการอ่าน. |
| **เวอร์ชัน Java ไม่รองรับ** | ใช้ Java 8 หรือใหม่กว่า; เวอร์ชันเก่าอาจไม่มี API ที่จำเป็น. |

## คำถามที่พบบ่อย

**คำถาม: Aspose.BarCode รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?**  
ตอบ: Aspose.BarCode ถูกออกแบบให้ทำงานกับ Java 8 และใหม่กว่า ตรวจสอบเอกสารอย่างเป็นทางการสำหรับความเข้ากันได้โดยละเอียด.

**คำถาม: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างได้หรือไม่?**  
ตอบ: ได้, คุณสามารถแก้ไขสี, ฟอนต์, และรูปแบบภาพผ่าน API พารามิเตอร์ของตัวสร้าง.

**คำถาม: มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบหรือไม่?**  
ตอบ: ได้, คุณสามารถรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.BarCode จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).

**คำถาม: ฉันจะหาแหล่งสนับสนุนและทรัพยากรเพิ่มเติมได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [ฟอรั่ม Aspose.BarCode](https://forum.aspose.com/c/barcode/13) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

**คำถาม: มีการทดลองใช้ฟรีหรือไม่?**  
ตอบ: ได้, คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode โดยดาวน์โหลดการทดลองใช้ฟรีจาก [ที่นี่](https://releases.aspose.com/).

---

**Last Updated:** 2026-04-05  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}