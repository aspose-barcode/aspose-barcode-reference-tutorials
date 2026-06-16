---
date: 2026-05-04
description: เรียนรู้วิธีเพิ่มคำบรรยายให้กับภาพบาร์โค้ดใน Java ด้วย Aspose.Barcode
  Java ตัวอย่างการสร้างบาร์โค้ดด้วย Java นี้แสดงวิธีสร้างภาพบาร์โค้ดใน Java อย่างง่ายดาย
keywords:
- aspose barcode java
- how to add caption
- barcode generator java
- save barcode image
linktitle: เพิ่มคำบรรยายให้บาร์โค้ด
second_title: Aspose.BarCode Java API
title: วิธีเพิ่มคำบรรยายให้กับบาร์โค้ดใน Java ด้วย Aspose.Barcode Java
url: /th/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มคำบรรยายให้กับบาร์โค้ดใน Java ด้วย Aspose.Barcode Java

## บทนำ

หากคุณต้องการ **วิธีเพิ่มคำบรรยาย** ให้กับบาร์โค้ดเพื่อเพิ่มความอ่านง่ายและการสร้างแบรนด์ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่แน่นอนในการเพิ่มคำบรรยายเหนือและใต้ภาพบาร์โค้ดโดยใช้ **Aspose.Barcode Java** เมื่อเสร็จสิ้นคุณจะได้บาร์โค้ดที่มีสไตล์เต็มรูปแบบซึ่งไม่เพียงแต่เข้ารหัสข้อมูลเท่านั้น แต่ยังแสดงข้อความที่เป็นประโยชน์—เหมาะสำหรับป้ายสินค้า ระบบสินค้าคงคลัง หรือสถานการณ์ใด ๆ ที่ผู้ใช้ได้รับประโยชน์จากบริบทเพิ่มเติม

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Barcode Java.  
- **ฉันสามารถเปลี่ยนฟอนต์และสีได้หรือไม่?** ได้—ทั้งฟอนต์ของคำบรรยายและสีข้อความสามารถปรับแต่งได้.  
- **บาร์โค้ดประเภทใดทำงานได้?** ทุกสัญลักษณ์ที่ Aspose.Barcode รองรับ (เช่น CODE_128, QR, DataMatrix).  
- **ต้องมีลิขสิทธิ์สำหรับการทดสอบหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **การดำเนินการใช้เวลานานแค่ไหน?** ปกติใช้เวลาน้อยกว่า 10 นาทีหลังจากเพิ่มไลบรารีแล้ว.

## คำบรรยายในบาร์โค้ดคืออะไร?
คำบรรยายคือข้อความธรรมดาที่ปรากฏเหนือหรือใต้กราฟิกบาร์โค้ด สามารถบอกชื่อสินค้า, ราคา หรือข้อมูลอื่น ๆ ที่เสริมข้อมูลที่เข้ารหัสไว้

## ทำไมต้องเพิ่มคำบรรยายด้วย Aspose.Barcode Java?
- **ปรับปรุงประสบการณ์ผู้ใช้:** ผู้ใช้สามารถอ่านความหมายของบาร์โค้ดได้ทันทีโดยไม่ต้องสแกน.  
- **ความสอดคล้องของแบรนด์:** คุณสามารถใช้ฟอนต์, สีและการจัดตำแหน่งของคุณเองให้ตรงกับแนวทางสไตล์ขององค์กร.  
- **การควบคุมเต็มรูปแบบ:** API ของ Aspose.Barcode ให้คุณสลับการมองเห็น, ตั้งค่าการจัดตำแหน่ง, และสไตล์ของแต่ละคำบรรยายได้อย่างอิสระ.  
- **การผสานรวมที่ราบรื่น:** ทำงานได้อย่างต่อเนื่องกับ **barcode generator java** workflow และให้คุณ **save barcode image** ในรูปแบบที่ต้องการ.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ติดตั้งอยู่.  
- ไลบรารี Aspose.BarCode for Java ดาวน์โหลดและเพิ่มเข้าไปในโปรเจกต์ของคุณ คุณสามารถค้นลิงก์ดาวน์โหลดได้ [here](https://releases.aspose.com/barcode/java/).  
- IDE เช่น IntelliJ IDEA หรือ Eclipse.

## นำเข้าแพ็กเกจ

ในไฟล์ซอร์ส Java ของคุณ ให้นำเข้าคลาส Aspose.BarCode ที่จำเป็นและคลาส AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสารและไดเรกทอรีทรัพยากร

ระบุที่ที่คุณต้องการเก็บภาพบาร์โค้ดที่สร้างขึ้น ปรับเส้นทางให้ตรงกับสภาพแวดล้อมของคุณ

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของ Barcode Generator

สร้างอินสแตนซ์ `BarcodeGenerator` ด้วยสัญลักษณ์ที่ต้องการ (เช่น CODE_128) และข้อความโค้ดที่คุณต้องการเข้ารหัส

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## ขั้นตอนที่ 3: กำหนดค่าคำบรรยายด้านบนของบาร์โค้ด

ตั้งค่าคำบรรยายที่ปรากฏเหนือบาร์โค้ด คุณสามารถควบคุมการจัดตำแหน่ง, ข้อความ, การมองเห็น, ฟอนต์, ขนาดและสีได้

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## ขั้นตอนที่ 4: กำหนดค่าคำบรรยายด้านล่างของบาร์โค้ด

เช่นเดียวกัน ให้กำหนดคำบรรยายด้านล่างบาร์โค้ด หากต้องการสามารถใช้การจัดตำแหน่งหรือสไตล์ที่แตกต่างกันได้

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().setSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## ขั้นตอนที่ 5: บันทึกรูปภาพบาร์โค้ด

สุดท้าย ให้เขียนบาร์โค้ด (พร้อมคำบรรยาย) ลงในไฟล์ภาพ รูปแบบจะถูกกำหนดจากส่วนขยายของไฟล์

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

คุณสามารถทำซ้ำขั้นตอนข้างต้นเพื่อทดลองฟอนต์, สี หรือการจัดตำแหน่งต่าง ๆ หรือเพื่อสร้างภาพบาร์โค้ดหลาย ๆ รูปในลูป

## ปัญหาและเคล็ดลับทั่วไป

- **คำบรรยายไม่ปรากฏ?** ตรวจสอบให้แน่ใจว่าได้เรียก `setVisible(true)` สำหรับคำบรรยายที่ต้องการแสดง.  
- **สีไม่ถูกต้อง?** ใช้ค่าคงที่ `java.awt.Color` หรือสร้างสีกำหนดเองด้วย `new Color(r, g, b)`.  
- **ปัญหาเส้นทาง?** ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่เขียนได้; หากไม่เช่นนั้น `bb.save()` จะโยน `IOException`.  
- **เคล็ดลับประสิทธิภาพ:** ใช้อินสแตนซ์ `BarcodeGenerator` เพียงตัวเดียวเมื่อต้องสร้างบาร์โค้ดหลาย ๆ ตัว; เพียงเปลี่ยน `EncodeTypes` หรือ `codetext` ตามต้องการ.

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถปรับแต่งสไตล์ฟอนต์ของคำบรรยายบาร์โค้ดได้หรือไม่?
ได้ คุณสามารถปรับแต่งฟอนต์, ขนาดและสีของคำบรรยายทั้งด้านบนและด้านล่างของบาร์โค้ดได้

### Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลายประเภทหรือไม่?
แน่นอน! Aspose.BarCode รองรับสัญลักษณ์หลากหลาย ทำให้คุณมีความยืดหยุ่นในการสร้างบาร์โค้ด

### ฉันจะรวม Aspose.BarCode เข้าในโปรเจกต์ Java ของฉันได้อย่างไร?
คุณสามารถทำตามคู่มือการรวมที่ละเอียดได้จาก [here](https://reference.aspose.com/barcode/java/) สำหรับขั้นตอนแบบทีละขั้นตอน

### มีการทดลองใช้ฟรีสำหรับ Aspose.BarCode for Java หรือไม่?
มี คุณสามารถเข้าถึงรุ่นทดลองฟรี [here](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติทั้งหมดก่อนตัดสินใจซื้อ

### ฉันจะขอความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?
ฟอรั่มชุมชน Aspose.BarCode เป็นสถานที่ที่ดีสำหรับการสนับสนุนและการสนทนา เยี่ยมชมฟอรั่มได้ที่ [here](https://forum.aspose.com/c/barcode/13)

---

**อัปเดตล่าสุด:** 2026-05-04  
**ทดสอบด้วย:** Aspose.BarCode for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}