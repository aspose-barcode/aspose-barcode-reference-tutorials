---
date: 2025-12-27
description: เรียนรู้วิธีตั้งค่าสีข้อความบาร์โค้ดใน Java ด้วย Aspose.BarCode และค้นพบวิธีสร้างบาร์โค้ดที่มีสีสำหรับแอปพลิเคชันใดก็ได้
linktitle: Setting Code Text Foreground Color
second_title: Aspose.BarCode Java API
title: วิธีตั้งค่าสีข้อความของบาร์โค้ดใน Java ด้วย Aspose.BarCode
url: /th/java/text-and-styling/setting-code-text-foreground-color/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีข้อความบาร์โค้ดใน Java ด้วย Aspose.BarCode

## บทนำ
ในแอปพลิเคชัน Java สมัยใหม่ การ **ตั้งค่าสีข้อความบาร์โค้ด** ให้ความยืดหยุ่นในการสอดคล้องกับแนวทางแบรนด์หรือปรับปรุงความอ่านง่ายบนสื่อที่พิมพ์ออกมา Aspose.BarCode for Java ทำให้การปรับแต่งทุกแง่มุมของบาร์โค้ด รวมถึงสีข้อความของโค้ดเป็นเรื่องง่าย ในคู่มือนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อ **ตั้งค่าสีข้อความบาร์โค้ด** และแสดงวิธี **สร้างบาร์โค้ดด้วยสี** ที่ดูดีในทุกสภาพแวดล้อม

## คำตอบสั้น
- **วิธีหลักในการเปลี่ยนสีข้อความบาร์โค้ดคืออะไร?** ใช้ `getCodeTextParameters().setColor(Color.YOUR_COLOR)`.
- **ไลบรารีใดให้ความสามารถนี้?** Aspose.BarCode for Java.
- **ต้องมีลิขสิทธิ์เพื่อเปลี่ยนสีหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง.
- **สามารถใช้สี AWT ใดก็ได้หรือไม่?** ใช่, รองรับค่าสี `java.awt.Color` ทั้งคงที่และค่าที่กำหนดเองแบบ RGB.
- **การเปลี่ยนแปลงนี้มีผลกับรูปแบบบาร์โค้ดทั้งหมดหรือไม่?** การตั้งค่าสีข้อความจะใช้กับสัญลักษณ์ที่รองรับทั้งหมด.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK)** – JDK ที่เข้ากันได้ติดตั้งบนเครื่องของคุณ ดาวน์โหลดได้จาก [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- **Aspose.BarCode for Java library** – รับเวอร์ชันล่าสุดจาก [download page](https://releases.aspose.com/barcode/java/). ทำตามคำแนะนำการติดตั้งเพื่อเพิ่ม JAR ลงใน classpath ของโปรเจกต์.
- **IDE ที่คุณชื่นชอบ** – Eclipse, IntelliJ IDEA หรือ NetBeans ทำงานได้เท่าเทียมกัน.

## นำเข้าแพ็กเกจ
เพิ่มการนำเข้าที่จำเป็นในคลาส Java ของคุณเพื่อให้สามารถทำงานกับตัวสร้างบาร์โค้ดและอ็อบเจกต์สีได้

```java
import com.aspose.barcode.generation.BarcodeGenerator;
import java.awt.Color;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: ระบุไดเรกทอรี
กำหนดตำแหน่งที่ภาพบาร์โค้ดที่สร้างจะถูกบันทึก ปรับเส้นทางให้ตรงกับโครงสร้างโปรเจกต์ของคุณ

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ BarcodeGenerator
เลือกสัญลักษณ์บาร์โค้ด (เช่น **CODE_128**) และระบุข้อความโค้ดที่คุณต้องการเข้ารหัส

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

### ขั้นตอนที่ 3: ตั้งค่าสีข้อความโค้ด
นี่คือหัวใจของบทเรียน – เราตั้งค่าสีข้อความโค้ดเป็น **สีแดง** คุณสามารถเปลี่ยน `Color.RED` เป็นค่า `java.awt.Color` ใดก็ได้ เช่น `new Color(0, 128, 255)` สำหรับเฉดสีที่กำหนดเอง

```java
generator.getParameters().getBarcode().getCodeTextParameters().setColor(Color.RED);
```

### ขั้นตอนที่ 4: บันทึกภาพบาร์โค้ด
สุดท้าย เขียนบาร์โค้ดที่ปรับแต่งแล้วลงดิสก์ รูปแบบภาพ (JPEG, PNG ฯลฯ) จะถูกกำหนดตามนามสกุลไฟล์

```java
generator.save(dataDir + "codeTextForegroundColor.jpg");
```

> **เคล็ดลับ:** หากต้องการสร้างบาร์โค้ดที่มีสีพื้นหลังเฉพาะด้วย ให้ใช้เมธอด `generator.getParameters().getBarcode().getBarColor()` และ `setBackColor()`.

## ทำไมต้องตั้งค่าสีข้อความบาร์โค้ด?
การปรับสีข้อความช่วยให้คุณ:

- สอดคล้องบาร์โค้ดกับแบรนด์ขององค์กร
- ปรับปรุงความคอนทราสต์บนพื้นหลังสีเข้มหรือสีอื่น
- สร้างฉลากที่ดูน่าสนใจสำหรับสื่อการตลาด

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **สีข้อความไม่เปลี่ยน** | ตรวจสอบว่าคุณเรียก `setColor` **หลัง** จากการสร้าง `BarcodeGenerator` แต่ **ก่อน** บันทึกภาพ. |
| **สีที่ไม่รองรับ** | ใช้ค่าคงที่ `java.awt.Color` มาตรฐานหรือสร้าง `Color` ใหม่ด้วยค่า RGB. |
| **ไฟล์ไม่ถูกบันทึก** | ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และสามารถเขียนได้. |

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถปรับแต่งส่วนอื่นของบาร์โค้ดด้วย Aspose.BarCode for Java ได้หรือไม่?
ใช่, Aspose.BarCode มีตัวเลือกการปรับแต่งหลากหลาย รวมถึงการเลือกสัญลักษณ์, การปรับขนาด, และการปรับแบบอักษรของข้อความ.

### Aspose.BarCode รองรับ IDE ของ Java ต่าง ๆ หรือไม่?
แน่นอน. Aspose.BarCode ทำงานร่วมกับ IDE ยอดนิยมของ Java เช่น Eclipse, IntelliJ, และ NetBeans อย่างไร้รอยต่อ.

### จะหาการสนับสนุนสำหรับคำถามเกี่ยวกับ Aspose.BarCode ได้จากที่ไหน?
เยี่ยมชม [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) เพื่อขอความช่วยเหลือจากชุมชนและผู้เชี่ยวชาญของ Aspose.

### มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for Java หรือไม่?
มี, คุณสามารถสำรวจความสามารถของ Aspose.BarCode ได้โดยรับรุ่นทดลองฟรีจาก [here](https://releases.aspose.com/).

### จะซื้อไลเซนส์สำหรับ Aspose.BarCode for Java ได้อย่างไร?
ไปที่ [purchase page](https://purchase.aspose.com/buy) เพื่อซื้อไลเซนส์และเปิดใช้งานศักยภาพเต็มของ Aspose.BarCode.

## สรุป
คุณได้เรียนรู้วิธี **ตั้งค่าสีข้อความบาร์โค้ด** ใน Java ด้วย Aspose.BarCode และพบว่าการ **สร้างบาร์โค้ดด้วยสี** ที่ตรงกับความต้องการออกแบบของคุณนั้นง่ายเพียงใด สำหรับการปรับแต่งขั้นสูงเพิ่มเติม เช่น การเปลี่ยนสีของบาร์, การเพิ่มคำบรรยาย, หรือการสร้างเอกสารบาร์โค้ดหลายหน้า โปรดดูที่ [documentation](https://reference.aspose.com/barcode/java/) อย่างเป็นทางการ.

---

**อัปเดตล่าสุด:** 2025-12-27  
**ทดสอบกับ:** Aspose.BarCode 24.12 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}