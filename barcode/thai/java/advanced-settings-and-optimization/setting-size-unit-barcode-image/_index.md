---
date: 2025-12-08
description: เรียนรู้วิธีสร้างบาร์โค้ด code128 ด้วย Java และสร้างภาพบาร์โค้ดด้วย Java
  โดยใช้ Aspose.BarCode ตั้งค่าหน่วยขนาดที่แม่นยำสำหรับภาพบาร์โค้ดด้วยโค้ดที่เรียบง่ายและนำกลับมาใช้ใหม่ได้
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: สร้างบาร์โค้ด code128 ด้วย Java และ Aspose.BarCode
url: /th/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง code128 barcode java และตั้งหน่วยขนาดด้วย Aspose.BarCode

## บทนำ

ในคู่มือแบบขั้นตอนนี้ คุณจะ **create code128 barcode java** โค้ดที่สร้างภาพบาร์โค้ดและให้คุณควบคุมหน่วยขนาดของผลลัพธ์ ไม่ว่าคุณจะกำลังสร้างระบบสินค้าคงคลัง, ตัวสร้างป้ายจัดส่ง, หรือแอปพลิเคชัน Java ใด ๆ ที่ต้องการบาร์โค้ดที่เชื่อถือได้ Aspose.BarCode for Java ทำให้กระบวนการง่ายและปรับแต่งได้อย่างสูง

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.BarCode for Java.  
- **ประเภทบาร์โค้ดที่ครอบคลุมคืออะไร?** CODE_128 (create code128 barcode java).  
- **จะตั้งหน่วยขนาดอย่างไร?** ใช้คุณสมบHeight` กับ `.setPoint()`.  
- **สามารถสร้าง barcode image java ในรูปแบบอื่นได้หรือไม่?** ได้ – PNG, JPEG, BMP, เป็นต้น.  
- **ข้อกำหนดเบื้องต้นคืออะไร?** ติดตั้ง JDK, ไลบรารี Aspose.BarCode, และ IDE สำหรับ Java.

## อะไรคือ **create code128 barcode java**?

การสร้าง CODE_128 barcode ใน Java หมายถึงการสร้างอินสแตนซ์ของคลาส `BarcodeGenerator` ด้วยค่า enum `EncodeTypes.CODE_128` และให้สตริงข้อมูลที่ต้องการเข้ารหัส สัญลักษณ์นี้ใช้กันอย่างแพร่หลายในโลจิสติกส์เพราะรองรับชุดอักขระ ASCII เต็มรูปแบบและให้ความหนาแน่นของข้อมูลสูง

## ทำไมต้องใช้ Aspose.BarCode เพื่อ **generate barcode image java**?

- **ควบคุมขนาดได้เต็มที่** – สามารถตั้งความสูงของบาร์, ขนาดโมดูล, และความละเอียดของภาพ  
- **ไม่มีการพึ่งพาภายนอก** – Java แท้, ทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ JDK  
- **ปรับแต่งได้หลากหลาย** – สี, ฟอนต์, ระยะขอบ, และแม้กระทั่ง QR code ก็รองรับ  
- **ประสิทธิภาพสูง** – สร้างภาพในระดับมิลลิวินาที, เหมาะกับการประมวลผลเป็นชุด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ  
2. **Aspose.BarCode for Java library** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์ Aspose (รุ่นทดลองหรือแบบลิขสิทธิ์)  
3. **IDE สำหรับ Java** – เช่น IntelliJ IDEA, Eclipse, หรือ VS Code พร้อมส่วนขยาย Java  

## นำเข้าชื่อเนมสเปซ

เพิ่มการนำเข้าที่จำเป็นที่ส่วนหัวของคลาส Java ของคุณเพื่อให้เข้าถึง API ของ Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## วิธี **generate barcode image java** ด้วย Aspose.BarCode?

ด้านล่างเป็นขั้นตอนการทำงานทั้งหมด แต่ละขั้นจะอธิบายด้วยภาษาง่าย ๆ และบล็อกโค้ดต้นฉบับจะคงไว้โดยไม่เปลี่ยนแปลง

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีทรัพยากร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยพาธเต็มที่คุณต้องการให้บันทึกภาพบาร์โค้ด

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ Barcode

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

ที่นี่เราจะ **create code128 barcode java** โดยส่งค่า `EncodeTypes.CODE_128` และสตริงข้อมูล `"1234567"`

### ขั้นตอนที่ 3: ตั้งความสูงของบาร์ (หน่วยขนาด)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

เมธอด `setPoint()` กำหนดความสูงเป็นหน่วย point (1 point = 1/72 นิ้ว) ปรับค่าตามความต้องการของเลย์เอาต์ของคุณ

### ขั้นตอนที่ 4: บันทึกภาพ

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

คำสั่ง `save()` จะเขียนบาร์โค้ดที่สร้างขึ้นไปยังโฟลเดอร์ที่คุณระบุ รูปแบบภาพจะถูกกำหนดจากส่วนขยายไฟล์ (ในกรณีนี้คือ JPEG)

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **Image not created** | พาธ `dataDir` ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่าโฟลเดอร์มีอยู่และแอปพลิเคชันของคุณมีสิทธิ์เขียน |
| **Barcode appears too small** | ความสูงบาร์ที่ตั้งเป็น point ต่ำเกินไปสำหรับ DPI ที่เลือก | เพิ่มค่าที่ส่งให้ `setPoint()` หรือปรับ DPI ของภาพผ่าน `bb.getParameters().getImage().setResolution()` |
| **Unsupported characters** | CODE_128 รองรับเฉพาะ ASCII; คุณส่งค่า Unicode | ใช้สัญลักษณ์อื่น (เช่น QR_CODE) สำหรับข้อมูลที่ไม่ใช่ ASCII |

## คำถามที่พบบ่อย

**Q: Aspose.BarCode for Java เหมาะกับการสร้างและการอ่านบาร์โค้ดหรือไม่?**  
A: ใช่, ไลบรารีนี้รองรับทั้งการสร้างและการอ่านของสัญลักษณ์หลากหลายประเภท

**Q: สามารถปรับแต่งลักษณะของภาพบาร์โค้ดที่สร้างได้หรือไม่?**  
A: แน่นอน. คุณสามารถเปลี่ยนสี, เพิ่มคำบรรยาย, ปรับระยะขอบ, และแม้กระทั่งฝังโลโก้โดยใช้ API `Parameters` ที่ครอบคลุม

**Q: จะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode for Java ได้อย่างไร?**  
A: เยี่ยมชม [here](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราวสำหรับการประเมิน

**Q: จะหาการสนับสนุนสำหรับ Aspose.BarCode for Java ได้จากที่ไหน?**  
A: ฟอรั่มชุมชน Aspose.BarCode เป็นแหล่งที่ดีที่สุดสำหรับความช่วยเหลือ ตรวจสอบ [forum](https://forum.aspose.com/c/barcode/13) เพื่อดูคำตอบและตั้งคำถามใหม่

**Q: สัญลักษณ์บาร์โค้ดที่รองรับใน Aspose.BarCode for Java มีอะไรบ้าง?**  
A: ไลบรารีรองรับสัญลักษณ์หลายสิบประเภท รวมถึง CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, และอื่น ๆ อีกมากมาย

---

**อัปเดตล่าสุด:** 2025-12-08  
**ทดสอบด้วย:** Aspose.BarCode for Java 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}