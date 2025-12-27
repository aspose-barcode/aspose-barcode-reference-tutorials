---
date: 2025-12-27
description: เรียนรู้วิธีเพิ่มคำบรรยายให้กับภาพบาร์โค้ดใน Java ด้วย Aspose.BarCode
  ตัวอย่างการสร้างบาร์โค้ดด้วย Java นี้แสดงวิธีสร้างภาพบาร์โค้ดใน Java อย่างง่ายดาย
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: วิธีเพิ่มคำบรรยายให้บาร์โค้ดใน Java ด้วย Aspose.BarCode
url: /th/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มคำบรรยายให้กับบาร์โค้ดใน Java โดยใช้ Aspose.BarCode

## บทนำ

หากคุณต้องการ **วิธีเพิ่มคำบรรยาย** ให้กับบาร์โค้ดเพื่อให้อ่านง่ายขึ้นและเพิ่มแบรนด์ของคุณ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนอย่างละเอียดเพื่อเพิ่มคำบรรยายเหนือและใต้ภาพบาร์โค้ดโดยใช้ Aspose.BarCode สำหรับ Java เมื่อเสร็จสิ้น คุณจะได้บาร์โค้ดที่มีสไตล์เต็มรูปแบบซึ่งไม่เพียงแต่เข้ารหัสข้อมูลเท่านั้น แต่ยังแสดงข้อความที่เป็นประโยชน์—เหมาะสำหรับป้ายสินค้า ระบบคลังสินค้า หรือสถานการณ์ใด ๆ ที่ผู้ใช้ได้รับประโยชน์จากข้อมูลเพิ่มเติม

## คำตอบด่วน
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.BarCode for Java.  
- **ฉันสามารถเปลี่ยนแบบอักษรและสีได้หรือไม่?** ใช่—ทั้งฟอนต์ของคำบรรยายและสีข้อความสามารถปรับแต่งได้.  
- **ประเภทบาร์โค้ดใดบ้างที่ทำงานได้?** ทุกสัญลักษณ์ที่ Aspose.BarCode รองรับ (เช่น CODE_128, QR, DataMatrix).  
- **ต้องใช้ลิขสิทธิ์สำหรับการทดสอบหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีหลังจากเพิ่มไลบรารีแล้ว.

## คำบรรยายในบาร์โค้ดคืออะไร?
คำบรรยายคือข้อความธรรมดาที่ปรากฏเหนือหรือใต้กราฟิกบาร์โค้ด สามารถบอกชื่อสินค้า, ราคา หรือข้อมูลอื่นใดที่เสริมข้อมูลที่เข้ารหัสไว้

## ทำไมต้องเพิ่มคำบรรยายด้วย Aspose.BarCode?
- **ประสบการณ์ผู้ใช้ที่ดีขึ้น:** ผู้ใช้สามารถอ่านความหมายของบาร์โค้ดได้ทันทีโดยไม่ต้องสแกน.  
- **ความสอดคล้องของแบรนด์:** คุณสามารถใช้ฟอนต์, สี, และการจัดตำแหน่งของคุณเองให้ตรงกับแนวทางสไตล์ขององค์กร.  
- **การควบคุมเต็มรูปแบบ:** API ของ Aspose.BarCode ให้คุณสลับการมองเห็น, ตั้งค่าการจัดตำแหน่ง, และกำหนดสไตล์ของแต่ละคำบรรยายแยกกัน.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ติดตั้งแล้ว.
- ไลบรารี Aspose.BarCode สำหรับ Java ดาวน์โหลดและเพิ่มในโปรเจคของคุณ คุณสามารถหา link ดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/barcode/java/).
- IDE เช่น IntelliJ IDEA หรือ Eclipse.

## นำเข้าแพ็กเกจ

ในไฟล์ซอร์ส Java ของคุณ ให้นำเข้าคลาส Aspose.BarCode ที่จำเป็นและคลาส AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสารและไดเรกทอรีทรัพยากร

ระบุที่ที่คุณต้องการเก็บภาพบาร์โค้ดที่สร้างขึ้น ปรับเส้นทางให้ตรงกับสภาพแวดล้อมของคุณ.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของ Barcode Generator

สร้างอินสแตนซ์ `BarcodeGenerator` ด้วยสัญลักษณ์ที่ต้องการ (เช่น CODE_128) และข้อความโค้ดที่ต้องการเข้ารหัส.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## ขั้นตอนที่ 3: กำหนดค่าคำบรรยายเหนือบาร์โค้ด

ตั้งค่าคำบรรยายที่ปรากฏเหนือบาร์โค้ด คุณสามารถควบคุมการจัดตำแหน่ง, ข้อความ, การมองเห็น, ฟอนต์, ขนาด, และสี.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## ขั้นตอนที่ 4: กำหนดค่าคำบรรยายใต้บาร์โค้ด

เช่นเดียวกัน กำหนดคำบรรยายใต้บาร์โค้ด หากต้องการสามารถใช้การจัดตำแหน่งหรือสไตล์ที่แตกต่างได้.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## ขั้นตอนที่ 5: บันทึกภาพบาร์โค้ด

สุดท้าย เขียนบาร์โค้ด (พร้อมคำบรรยาย) ลงในไฟล์ภาพ รูปแบบจะถูกกำหนดจากนามสกุลไฟล์.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

คุณสามารถทำซ้ำขั้นตอนข้างต้นเพื่อทดลองฟอนต์, สี, หรือการจัดตำแหน่งต่าง ๆ หรือเพื่อสร้างภาพบาร์โค้ดหลายภาพในลูป.

## ปัญหาทั่วไปและเคล็ดลับ

- **คำบรรยายไม่แสดง?** ตรวจสอบว่าได้เรียก `setVisible(true)` สำหรับคำบรรยายที่ต้องการแสดง.  
- **สีไม่ถูกต้อง?** ใช้ค่าคงที่ `java.awt.Color` หรือสร้างสีกำหนดเองด้วย `new Color(r, g, b)`.  
- **ปัญหาเส้นทาง?** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และสามารถเขียนได้; มิฉะนั้น `bb.save()` จะโยน `IOException`.  
- **เคล็ดลับประสิทธิภาพ:** ใช้อินสแตนซ์ `BarcodeGenerator` เดียวเมื่อสร้างบาร์โค้ดหลาย ๆ ตัว; เพียงเปลี่ยน `EncodeTypes` หรือ `codetext` ตามต้องการ.

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถปรับแต่งสไตล์ฟอนต์ของคำบรรยายบาร์โค้ดได้หรือไม่?
ได้ คุณสามารถปรับแต่งฟอนต์, ขนาด, และสีของคำบรรยายทั้งเหนือและใต้บาร์โค้ด.

### Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลายประเภทหรือไม่?
แน่นอน! Aspose.BarCode รองรับสัญลักษณ์หลากหลาย ทำให้การสร้างบาร์โค้ดมีความยืดหยุ่น.

### ฉันจะรวม Aspose.BarCode เข้าในโปรเจค Java ของฉันอย่างไร?
คุณสามารถทำตามคู่มือการรวมอย่างละเอียดที่มีอยู่ [ที่นี่](https://reference.aspose.com/barcode/java/) สำหรับขั้นตอนทีละขั้นตอน.

### มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for Java หรือไม่?
ใช่ คุณสามารถเข้าถึงรุ่นทดลองฟรี [ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติทั้งหมดก่อนซื้อ.

### ฉันจะหาความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?
ฟอรั่มชุมชน Aspose.BarCode เป็นแหล่งที่ดีสำหรับการสนับสนุนและการสนทนา เยี่ยมชมฟอรั่ม [ที่นี่](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}