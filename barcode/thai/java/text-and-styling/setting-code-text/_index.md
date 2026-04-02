---
date: 2025-12-30
description: เรียนรู้วิธีสร้างบาร์โค้ดด้วย Java โดยใช้ Aspose.BarCode คู่มือขั้นตอนนี้จะแสดงวิธีตั้งค่าข้อความบาร์โค้ดแบบกำหนดเอง
  ปรับความกว้าง และบันทึกภาพ
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'สร้างบาร์โค้ด Java - ตั้งค่าข้อความโค้ดโดยใช้ Aspose.BarCode'
url: /th/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด Java: ตั้งค่าข้อความโค้ดด้วย Aspose.BarCode

## บทนำ

ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **generate barcode java** ด้วยไลบรารี Aspose.BarCode Java ไม่ว่าคุณจะกำลังสร้างระบบจัดการสินค้าคงคลัง โซลูชันการติดตามเอกสาร หรือแอปพลิเคชันใด ๆ ที่ต้องการบาร์โค้ด คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การสร้างบาร์โค้ด **Code128** ไปจนถึงการปรับแต่งข้อความโค้ดและการปรับความกว้างของบาร์ สุดท้ายคุณจะได้ภาพที่พร้อมใช้งานซึ่งสามารถฝังได้ทุกที่ที่ต้องการ

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.BarCode for Java.
- **ประเภทบาร์โค้ดที่แสดงคืออะไร?** CODE_128.
- **ฉันจะตั้งค่าข้อความบาร์โค้ดแบบกำหนดเองอย่างไร?** Use the `BarcodeGenerator` constructor or `setCodeText` method.
- **ฉันสามารถเปลี่ยนความกว้างของบาร์ได้หรือไม่?** Yes, via `XDimension` in millimeters.
- **ฉันต้องใช้ลิขสิทธิ์สำหรับการผลิตหรือไม่?** Yes, a commercial license is required.

## ข้อกำหนดเบื้องต้น

ก่อนจะดำเนินการตามบทแนะนำ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ถูกติดตั้งแล้ว.  
- ไลบรารี Aspose.BarCode for Java คุณสามารถดาวน์โหลดได้ **[here](https://releases.aspose.com/barcode/java/)**.  
- โปรแกรมแก้ไขโค้ด เช่น IntelliJ IDEA หรือ Eclipse.  

## นำเข้าแพ็กเกจ

เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ แพ็กเกจเหล่านี้จำเป็นสำหรับการทำงานกับ Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

ตอนนี้เรามาสำรวจกระบวนการตั้งค่าข้อความโค้ดโดยใช้ Aspose.BarCode ใน Java กันเถอะ ทำตามขั้นตอนต่อไปนี้:

## บทแนะนำ Barcode Generator: สร้างบาร์โค้ด Code128

### ขั้นตอนที่ 1: สร้างอินสแตนซ์ของ `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

ที่นี่ เราสร้างอินสแตนซ์ `BarcodeGenerator` โดยระบุสัญลักษณ์บาร์โค้ด (**CODE_128**) และ **ข้อความบาร์โค้ดแบบกำหนดเอง** `"12345678"`.

### ขั้นตอนที่ 2: ปรับความกว้างของบาร์โค้ดสำหรับข้อความบาร์โค้ดแบบกำหนดเอง

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

ปรับความกว้างของบาร์ตามที่คุณต้องการ ในตัวอย่างนี้ เรา **ปรับความกว้างของบาร์โค้ด** เป็น `0.5` mm ซึ่งเหมาะกับขนาดป้ายส่วนใหญ่.

### ขั้นตอนที่ 3: บันทึกภาพบาร์โค้ด

```java
generator.save(dataDir + "setCodeText.jpg");
```

บันทึกภาพบาร์โค้ดที่สร้างลงในไดเรกทอรีที่ระบุ ในกรณีนี้ ไฟล์จะถูกบันทึกเป็น **`setCodeText.jpg`** ภายในไดเรกทอรีเอกสารของคุณ.

## ทำไมต้องใช้ Aspose.BarCode สำหรับ Java?

- **Comprehensive API** – รองรับสัญลักษณ์บาร์โค้ดกว่า 60 ชนิด รวมถึง Code128, QR, DataMatrix, และอื่น ๆ.  
- **High‑quality rendering** – สร้างภาพที่คมชัดในรูปแบบ PNG, JPEG, SVG, และ PDF.  
- **Easy customization** – เปลี่ยนข้อความ, ขนาด, สี, และแม้กระทั่งเพิ่มคำบรรยายที่อ่านได้โดยมนุษย์ด้วยไม่กี่บรรทัดของโค้ด.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS กับ Java 8+ runtime ใดก็ได้.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **บาร์โค้ดดูเบลอ** | เพิ่มความละเอียดของภาพหรือส่งออกเป็นรูปแบบเวกเตอร์ (SVG, PDF). |
| **ข้อความถูกตัด** | ตรวจสอบให้แน่ใจว่า `XDimension` (ความกว้างของบาร์) และ `BarHeight` มีขนาดเพียงพอสำหรับสัญลักษณ์ที่เลือก. |
| **ลิขสิทธิ์ไม่ได้ถูกนำมาใช้** | วางไฟล์ลิขสิทธิ์ของคุณ (`Aspose.BarCode.lic`) ไว้ที่โฟลเดอร์รากของโปรเจกต์และโหลดด้วย `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## คำถามที่พบบ่อยเพิ่มเติม

**Q:** *ความแตกต่างระหว่าง `CODE_128` กับรูปแบบ Code128 อื่นคืออะไร?*  
**A:** `CODE_128` คือสัญลักษณ์มาตรฐานที่เลือกการเข้ารหัสที่มีประสิทธิภาพที่สุด (A, B หรือ C) โดยอัตโนมัติตามข้อความที่ป้อน.

**Q:** *ฉันสามารถเปลี่ยนรูปแบบเอาต์พุตเป็น PNG แทน JPEG ได้หรือไม่?*  
**A:** แน่นอน. ใช้ `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *สามารถเพิ่มคำบรรยายที่อ่านได้โดยมนุษย์ใต้บาร์โค้ดได้หรือไม่?*  
**A:** ได้. ตั้งค่า `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` และระบุข้อความคำบรรยาย.

**Q:** *Aspose.BarCode รองรับอักขระ Unicode หรือไม่?*  
**A:** รองรับ. ให้ข้อความในรูปแบบ UTF‑8 และตรวจสอบให้แน่ใจว่าสัญลักษณ์ที่เลือกรองรับชุดอักขระนั้น.

**Q:** *ฉันจะสร้างบาร์โค้ดหลายรายการในลูปได้อย่างไร?*  
**A:** สร้างอินสแตนซ์ `BarcodeGenerator` ใหม่ภายในลูป ตั้งค่าข้อความสำหรับแต่ละรอบ และเรียก `save` ด้วยชื่อไฟล์ที่ไม่ซ้ำกัน.

---

**อัปเดตล่าสุด:** 2025-12-30  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}