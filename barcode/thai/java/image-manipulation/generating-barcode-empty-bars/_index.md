---
date: 2025-12-22
description: เรียนรู้วิธีสร้างภาพบาร์โค้ดที่มีบาร์ว่างโดยใช้ Aspose.BarCode สำหรับ
  Java ตัวอย่างการสร้างบาร์โค้ดแบบขั้นตอนนี้ช่วยให้คุณสร้างบาร์โค้ดใน Java ได้อย่างรวดเร็ว
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: วิธีสร้างภาพบาร์โค้ดที่มีแถบว่างใน Java
url: /th/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างภาพบาร์โค้ดที่มีบาร์ว่างใน Java

## บทนำ

ในแอปพลิเคชัน Java สมัยใหม่ ความสามารถในการ **create barcode image** ไฟล์แบบทันทีเป็นคุณลักษณะที่มีคุณค่าสำหรับการจัดการสินค้าคงคลัง ระบบตั๋วเข้าชม และสถานการณ์ธุรกิจอื่น ๆ อีกมากมาย Aspose.BarCode for Java ให้ API ที่ทรงพลังและใช้งานง่ายที่ช่วยให้คุณสร้างบาร์โค้ดคุณภาพสูงได้ด้วยเพียงไม่กี่บรรทัดของโค้ด ในบทเรียนนี้เราจะอธิบายกระบวนการสร้างบาร์โค้ดแบบ **step‑by‑step barcode** ที่สร้างบาร์โค้ดที่มีบาร์ว่าง (ไม่ได้เติม) เหมาะสำหรับการออกแบบที่ต้องการลักษณะเป็นรูพรุน

## คำตอบด่วน
- **What does “empty bars” mean?** บาร์จะถูกเรนเดอร์โดยไม่มีการเติมสีเริ่มต้น ทำดูเป็นรูพรุน.  
- **Which barcode type is used?** Code 128 (สัญลักษณ์เชิงเส้นที่ได้รับการสนับสนุนอย่างกว้างขวาง).  
- **Do I need a license to try it?** มีการทดลองใช้ฟรี; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์.  
- **What output formats are supported?** PNG, JPEG, BMP, GIF, TIFF และอื่น ๆ.  
- **Is this compatible with all Java versions?** ใช่, ไลบรารีทำงานกับ Java 8 และรุ่นต่อ ๆ ไป.  

## สร้างภาพบาร์โค้ดคืออะไร?

การสร้างภาพบาร์โค้ดหมายถึงการแปลงสตริงข้อมูลเป็นภาพที่สแกนเนอร์สามารถอ่านได้ ภาพที่ได้สามารถบันทึกเป็น PNG, JPEG หรือรูปแบบทั่วไปอื่น ๆ และฝังลงใน PDF, พิมพ์บนป้าย, หรือแสดงบน UI

## ทำไมต้องใช้ไลบรารี Aspose.BarCode Java?

- **Rich feature set** – รองรับสัญลักษณ์บาร์โค้ดมากกว่า 50 รายการ รวมถึง Code 128, QR, DataMatrix และอื่น ๆ.  
- **Fine‑grained control** – คุณสมบัติต่าง ๆ เช่น `FilledBars`, สี, ระยะขอบ, และขนาดภาพสามารถกำหนดค่าได้ง่าย.  
- **No external dependencies** – ไฟล์ JAR เพียงไฟล์เดียวจัดการทุกอย่าง ทำให้การปรับใช้ง่ายขึ้น.  
- **Comprehensive documentation** – ตัวอย่าง, การอ้างอิง API, และฟอรั่มช่วยให้คุณเริ่มต้นได้อย่างรวดเร็ว.  

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มการสร้างบาร์โค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. **Java Development Environment** – ตรวจสอบว่าคุณได้ติดตั้ง Java 8+ และมี IDE หรือเครื่องมือสร้างที่เข้ากันได้.  
2. **Aspose.BarCode for Java Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.BarCode for Java จาก [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – สร้างไดเรกทอรีบนระบบของคุณเพื่อเก็บภาพบาร์โค้ดที่สร้างขึ้น.  

## นำเข้าแพ็กเกจ

ในโครงการ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นสำหรับการทำงานกับ Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## วิธีสร้างภาพบาร์โค้ดที่มีบาร์ว่าง

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงที่คุณต้องการบันทึกไฟล์ผลลัพธ์.

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ Barcode Generator (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

ที่นี่ เราใช้สัญลักษณ์ **Code 128**—หนึ่งในบาร์โค้ดเชิงเส้นที่ได้รับความนิยมสูงสุด—ทำให้ตัวอย่างนี้เป็น **code128 barcode java** คลาสสิก.

### ขั้นตอนที่ 3: ตั้งค่า Property FilledBars เป็น False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

การตั้งค่า `FilledBars` เป็น `false` บอกให้ Asp.BarCode เรนเดอร์บาร์เป็นรูปทรงว่าง (รูพรุน) แทนบล็อกสีทึบ.

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

ภาพจะถูกบันทึกในรูปแบบ PNG แต่คุณสามารถเปลี่ยน enum `BarCodeImageFormat` เพื่อสร้าง JPEG, BMP หรือประเภทที่รองรับอื่น ๆ.

ทำซ้ำขั้นตอนเหล่านี้ในแอปพลิเคชัน Java ของคุณเพื่อสร้างไฟล์ **create barcode image** ที่มีบาร์ว่างอย่างง่ายดายโดยใช้ Aspose.BarCode for Java.

## สรุป

โดยสรุป บทเรียนนี้ได้พาคุณผ่านกระบวนการสร้างบาร์โค้ดแบบ **step‑by‑step barcode** ที่แสดงวิธี **create barcode image** ไฟล์ที่มีบาร์ว่างใน Java ด้วย API ที่ใช้งานง่ายและตัวเลือกการปรับแต่งที่หลากหลาย Aspose.BarCode ทำให้การรวมบาร์โค้ดเป็นเรื่องง่ายขึ้น ทำให้เป็นทรัพยากรที่มีคุณค่าสำหรับนักพัฒนาที่ต้องการ **java barcode library** ที่เชื่อถือได้.

## คำถามที่พบบ่อย

### Aspose.BarCode รองรับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่?
ใช่, Aspose.BarCode ถูกออกแบบให้ผสานรวมอย่างราบรื่นกับสภาพแวดล้อมการพัฒนา Java ต่าง ๆ.

### ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างได้หรือไม่?
แน่นอน! Aspose.BarCode มีตัวเลือกการปรับแต่งมากมาย ช่วยให้คุณปรับบาร์โค้ดให้ตรงกับความต้องการของคุณ.

### มีเวอร์ชันทดลองสำหรับ Aspose.BarCode หรือไม่?
ใช่, คุณสามารถสำรวจความสามารถของ Aspose.BarCode ได้โดยรับเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.BarCode อย่างไร?
หากมีคำถามหรือขอความช่วยเหลือ โปรดเยี่ยมชม [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### ฉันจะหาเอกสารรายละเอียดของ Aspose.BarCode ได้จากที่ไหน?
เอกสารที่ครอบคลุมสามารถเข้าถึงได้ [here](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-22  
**ทดสอบด้วย:** Aspose.BarCode Java 24.11 (latest)  
**ผู้เขียน:** Aspose  

---