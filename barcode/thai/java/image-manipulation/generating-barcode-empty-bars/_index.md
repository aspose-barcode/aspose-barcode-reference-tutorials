---
date: 2026-04-12
description: เรียนรู้วิธีสร้างบาร์โค้ด Code128 ที่มีบาร์ว่างใน Java ด้วย Aspose.BarCode
  คู่มือนี้จะแสดงวิธีสร้างภาพบาร์โค้ด Java อย่างรวดเร็ว.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: การสร้างบาร์โค้ดที่มีบาร์ว่าง
second_title: Aspose.BarCode Java API
title: วิธีสร้างบาร์โค้ด Code128 พร้อมบาร์ว่างใน Java
url: /th/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด Code128 พร้อมบาร์ว่างใน Java

## บทนำ

การรวมการสร้างบาร์โค้ดเข้ากับแอปพลิเคชัน Java เป็นความต้องการที่พบบ่อย ไม่ว่าจะเป็นระบบจัดการสินค้าคงคลัง แพลตฟอร์มการจำหน่ายตั๋ว หรือโซลูชันจุดขาย (POS) ด้วย **Aspose.BarCode for Java** คุณสามารถ **สร้างภาพบาร์โค้ด Code128** ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนการ **สร้างภาพบาร์โค้ด Java** ที่มีบาร์ว่าง (ไม่เติมสี) เพื่อให้คุณควบคุมสไตล์การแสดงผลของบาร์โค้ดได้อย่างเต็มที่

## คำตอบด่วน
- **ไลบรารีใด?** Aspose.BarCode for Java  
- **กรณีการใช้งานหลัก?** สร้างบาร์โค้ด Code128 พร้อมบาร์ว่างสำหรับการออกแบบ UI แบบกำหนดเอง  
- **ข้อกำหนดเบื้องต้น?** Java JDK 8+, Aspose.BarCode JAR, สิทธิ์การเขียนไปยังโฟลเดอร์สำหรับภาพผลลัพธ์  
- **เวลาในการดำเนินการโดยทั่วไป?** 5‑10 นาทีสำหรับตัวอย่างพื้นฐาน  
- **ฉันสามารถปรับแต่งสีได้หรือไม่?** ใช่ – API มีตัวเลือกการจัดรูปแบบที่ครอบคลุม  

## Code128 คืออะไร?

Code128 เป็นสัญลักษณ์บาร์โค้ดเชิงเส้นความหนาแน่นสูงที่เข้ารหัสชุดอักขระ ASCII ทั้งหมด มักใช้ในโลจิสติกส์ การจัดส่ง และการค้าปลีกเนื่องจากสามารถแสดงข้อมูลอัลฟานูเมอริกได้อย่างกระชับ โดยค่าเริ่มต้น Aspose.BarCode จะเรนเดอร์บาร์ Code128 เป็นสี่เหลี่ยมทึบ; การตั้งค่าคุณสมบัติ **FilledBars** เป็น `false` จะทำให้บาร์เป็นแบบว่าง (โครง) ซึ่งมีประโยชน์สำหรับการสร้างแบรนด์แบบสไตล์

## ทำไมต้องใช้ Aspose.BarCode for Java?

- **ชุดคุณสมบัติที่หลากหลาย** – รองรับประเภทบาร์โค้ดกว่า 50 ประเภท รวมถึง QR, DataMatrix, และ PDF417.  
- **ไม่มีการพึ่งพาภายนอก** – JAR เพียงไฟล์เดียวทำงานบน Java runtime ใดก็ได้.  
- **การควบคุมละเอียด** – คุณสามารถปรับความกว้างของบาร์, สี, ฟอนต์, และคุณสมบัติ `FilledBars`.  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS โดยไม่ต้องใช้ไลบรารีเนทีฟ.  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

1. **สภาพแวดล้อมการพัฒนา Java** – ติดตั้ง JDK 8 หรือใหม่กว่าและตั้งค่า `JAVA_HOME`.  
2. **Aspose.BarCode for Java** – ดาวน์โหลด JAR เวอร์ชันล่าสุดจาก [download page](https://releases.aspose.com/barcode/java/).  
3. **ไดเรกทอรีเอกสาร** – โฟลเดอร์บนคอมพิวเตอร์ของคุณที่บาร์โค้ดที่สร้างจะถูกบันทึก.  

## นำเข้าแพ็กเกจ

ในโปรเจกต์ Java ของคุณ ให้นำเข้าคลาสที่จำเป็นสำหรับทำงานกับ Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

การนำเข้าต่าง ๆ นี้ทำให้คุณเข้าถึงตัวสร้างบาร์โค้ด, การนับประเภทรูปภาพ, และการจัดการข้อยกเว้น.

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางเต็มไปยังโฟลเดอร์ที่คุณสร้างตามข้อกำหนดเบื้องต้น นี่คือที่ที่ไฟล์ PNG จะถูกเขียน.

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของตัวสร้างบาร์โค้ด Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

ที่นี่เราสร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยสัญลักษณ์ **CODE_128** และข้อความตัวอย่าง `"TEXT"` นี่คือตัวอย่าง **barcode generator Java** ที่คุณสามารถปรับใช้กับสตริงใดก็ได้ที่ต้องการเข้ารหัส.

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติ FilledBars เป็น False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

โดยการตั้งค่า `FilledBars` เป็น `false` บาร์โค้ดที่สร้างจะปรากฏเป็นบาร์ว่างแทนบาร์ทึบ ทำให้ได้เอฟเฟกต์ภาพตามที่ต้องการ.

## ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

เมธอด `save` จะเขียนบาร์โค้ดไปยังไดเรกทอรีที่ระบุในรูปแบบ PNG คุณสามารถเปลี่ยน `BarCodeImageFormat.PNG` เป็น `JPG`, `BMP`, หรือ `TIFF` หากต้องการรูปแบบภาพอื่น.

## กรณีการใช้งานทั่วไป

- **การสร้างแบรนด์แบบกำหนดเอง** – บาร์ว่างสามารถวางซ้อนกับลวดลายหรือสีพื้นหลังได้.  
- **ทรัพยากรพร้อมพิมพ์** – สร้าง PNG ความละเอียดสูงสำหรับใส่ในใบแจ้งหนี้หรือป้ายจัดส่ง.  
- **การสร้างแบบไดนามิก** – สร้างบาร์โค้ดแบบเรียลไทม์ในบริการเว็บหรือแอปพลิเคชันเดสก์ท็อป.  

## เคล็ดลับการแก้ไขปัญหา

- **เส้นทางไม่ถูกต้อง** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) หรือเชื่อมต่อโดยใช้ `File.separator`.  
- **ต้องมีลิขสิทธิ์** – เวอร์ชันทดลองใช้ได้สำหรับการประเมินค่า แต่ต้องมีลิขสิทธิ์เต็มเพื่อการใช้งานจริง.  
- **อักขระที่ไม่รองรับ** – Code128 รองรับชุด ASCII ทั้งหมด; หลีกเลี่ยงอักขระ Unicode เว้นแต่คุณจะเปลี่ยนไปใช้สัญลักษณ์อื่น.  

## สรุป

คุณได้เรียนรู้วิธี **สร้างภาพบาร์โค้ด Code128** พร้อมบาร์ว่างโดยใช้ Aspose.BarCode for Java แล้ว วิธีการที่ง่ายนี้ช่วยให้คุณสร้างกราฟิกบาร์โค้ดที่ปรับแต่งได้อย่างรวดเร็ว ไม่ว่าจะเป็นการสร้างเครื่องมือจัดการสินค้าบนเดสก์ท็อปหรือ API บนคลาวด์

## คำถามที่พบบ่อย

### Aspose.BarCode รองรับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่?
ใช่, Aspose.BarCode ถูกออกแบบให้ผสานรวมได้อย่างราบรื่นกับ IDE หรือระบบการสร้างใด ๆ ของ Java รวมถึง Maven, Gradle, และโปรเจกต์ JAR ธรรมดา

### ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างได้หรือไม่?
แน่นอน! นอกจาก `FilledBars` แล้ว คุณยังสามารถแก้ไขสี, ความกว้างของบาร์, ระยะขอบ, และแม้กระทั่งเพิ่มข้อความที่มนุษย์อ่านได้โดยใช้ API ที่ครอบคลุม

### มีเวอร์ชันทดลองสำหรับ Aspose.BarCode หรือไม่?
ใช่, คุณสามารถสำรวจความสามารถของ Aspose.BarCode ได้โดยรับเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/).

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.BarCode ได้อย่างไร?
หากมีคำถามหรือขอความช่วยเหลือ โปรดเยี่ยมชม [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### ฉันสามารถค้นหาเอกสารรายละเอียดของ Aspose.BarCode ได้ที่ไหน?
เอกสารที่ครอบคลุมพร้อมให้บริการ [here](https://reference.aspose.com/barcode/java/).

**คำถามเพิ่มเติม**

**Q: ฉันจะสร้างภาพบาร์โค้ดในรูปแบบอื่น เช่น JPEG ได้อย่างไร?**  
A: Change the second argument of `save` to `BarCodeImageFormat.JPEG`.

**Q: ฉันสามารถสร้างบาร์โค้ดหลายรายการในลูปได้หรือไม่?**  
A: Yes – instantiate a new `BarcodeGenerator` inside your loop or reuse the same instance with a new `CodeText`.

---

**อัปเดตล่าสุด:** 2026-04-12  
**ทดสอบกับ:** Aspose.BarCode for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}