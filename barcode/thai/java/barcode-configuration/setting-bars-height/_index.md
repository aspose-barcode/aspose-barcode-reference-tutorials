---
date: 2026-02-15
description: เรียนรู้วิธีสร้างบาร์โค้ด code128 ด้วย Java และ Aspose.BarCode ปรับขนาดบาร์โค้ด
  ปรับมิติของบาร์โค้ด และสร้างภาพบาร์โค้ดด้วย Java อย่างมีประสิทธิภาพ
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: วิธีสร้างบาร์โค้ด Code128 ด้วย Java และตั้งความสูงของบาร์
url: /th/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าความสูงของบาร์ใน Java

## บทนำ

หากคุณต้องการ **สร้างรหัสบาร์โค้ด code128 ด้วย Java** สำหรับการพิมพ์ฉลาก ใบแจ้งหนี้ หรือแอปมือถือ คุณจะต้องการควบคุมมิติภาพอย่างเต็มที่ Aspose.BarCode for Java ให้คุณ **ปรับขนาดบาร์โค้ด** ตั้งค่าความสูงของบาร์อย่างแม่นยำ และสร้างภาพบาร์โค้ดที่ตรงตามความต้องการของการออกแบบได้ทันที ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมดของการสร้างบาร์โค้ด CODE_128 ปรับความสูงของมัน และบันทึกภาพ—เพื่อให้คุณผลิตบาร์โค้ดที่มีขนาดพอดีทุกครั้ง

## คำตอบสั้น
- **เมธอดหลักทำอะไร?** มันสร้างบาร์โค้ด CODE_128 และให้คุณตั้งค่าความสูงของบาร์  
- **ใช้คลาสใด?** `BarcodeGenerator` จากไลบรารี Aspose.BarCode  
- **ต้องใช้ไลเซนส์สำหรับการทดสอบหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **สามารถเปลี่ยนมิติอื่นได้หรือไม่?** ได้, คุณสามารถปรับความกว้าง, ระยะขอบ, และพารามิเตอร์ขนาดอื่น ๆ  
- **รูปแบบของภาพผลลัพธ์คืออะไร?** ใด ๆ ที่รองรับโดย Aspose.BarCode (เช่น JPEG, PNG)  

## CODE_128 คืออะไรและทำไมต้องตั้งความสูง?
CODE_128 เป็นบาร์โค้ดเชิงเส้นความหนาแน่นสูงที่เข้ารหัสชุด ASCII ทั้งหมด การปรับความสูงของบาร์เป็นสิ่งสำคัญเมื่อบาร์โค้ดต้องสอดคล้องกับมิติของฉลากจริงหรือพอดีกับส่วนประกอบ UI ความสูงที่เหมาะสมช่วยให้สแกนเนอร์อ่านได้ง่ายในขณะที่รักษาการจัดวางภาพให้สมดุล

## ทำไมต้องใช้ Aspose.BarCode for Java?
- **ควบคุมได้เต็มที่** เกี่ยวกับมิติของบาร์โค้ด (ความสูง, ความกว้าง, ระยะขอบ)  
- **รองรับรูปแบบหลากหลาย** – สร้าง PNG, JPEG, BMP และอื่น ๆ  
- **ไม่มีการพึ่งพาภายนอก** – ไลบรารี Java แท้ ๆ, ติดตั้งง่าย  
- **API ครบถ้วน** – ปรับสี, ข้อความ, และการแก้ไขข้อผิดพลาดได้อย่างง่ายดาย  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำให้แน่ใจว่าคุณมี:

- สภาพแวดล้อมการพัฒนา Java (JDK 8 หรือสูงกว่า)  
- Aspose.BarCode for Java – ดาวน์โหลดได้จาก [download link](https://releases.aspose.com/barcode/java/)  

## นำเข้าแพ็กเกจ

ในโปรเจกต์ Java ของคุณ ให้นำเข้าคลาสหลักที่ให้ความสามารถในการสร้างบาร์โค้ด:

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## วิธีสร้าง code128 barcode java และตั้งค่าความสูงของมัน

### ขั้นตอน 1: เริ่มต้นอ็อบเจกต์ Barcode

สร้างอินสแตนซ์ `BarcodeGenerator` สำหรับบาร์โค้ด CODE_128 พร้อมข้อมูลที่คุณต้องการเข้ารหัส (เช่น “12345678”)

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### ขั้นตอน 2: ปรับมิติของบาร์โค้ด – ตั้งค่าความสูงของบาร์

ใช้คุณสมบัติ `BarHeight` เพื่อกำหนดความสูงเป็นมิลลิเมตร นี่เป็นวิธีหลักในการ **ปรับมิติของบาร์โค้ด**

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **เคล็ดลับมืออาชีพ:** คุณยังสามารถแก้ไข `XDimension` เพื่อเปลี่ยนความกว้างของบาร์แต่ละบาร์, ให้คุณควบคุม **customize barcode size** ได้อย่างเต็มที่

### ขั้นตอน 3: บันทึกภาพบาร์โค้ด – generate barcode image java

สุดท้าย, เขียนบาร์โค้ดลงไฟล์ เมธอด `save` จะกำหนดรูปแบบภาพโดยอัตโนมัติตามนามสกุลไฟล์

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **หมายเหตุ:** แทนที่ `dataDir` ด้วยเส้นทางจริงที่คุณต้องการให้ภาพถูกจัดเก็บ

## กรณีการใช้งานทั่วไป

- **บาร์โค้ดสำหรับการพิมพ์ฉลาก** – ทำให้บาร์โค้ดพอดีกับขนาดฉลากที่กำหนดไว้  
- **การสร้างใบแจ้งหนี้** – ฝังบาร์โค้ดขนาดกะทัดรัดที่สอดคล้องกับการจัดวาง PDF ใบแจ้งหนี้ของคุณ  
- **แอปมือถือ** – สร้างบาร์โค้ดแบบไดนามิกด้วยมิติที่แม่นยำสำหรับการสแกนบนหน้าจอ  

## การแก้ไขปัญหา & เคล็ดลับ

| Issue | Solution |
|-------|----------|
| Barcode appears too thin or too thick | Adjust `XDimension` via `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)`. |
| Image is blurry | Increase the DPI by calling `generator.save(..., BarCodeImageFormat.JPEG, 300)`. |
| Scanner cannot read the code | Verify that the bar height meets the scanner’s minimum requirement (usually ≥ 2 mm). |

## คำถามที่พบบ่อย

**Q: สามารถปรับประเภทบาร์โค้ดใน Aspose.BarCode for Java ได้หรือไม่?**  
A: แน่นอน! ไลบรารีรองรับสัญลักษณ์หลายประเภท เช่น QR, DataMatrix, PDF417, และอื่น ๆ — เพียงเปลี่ยน `EncodeTypes` ในคอนสตรัคเตอร์

**Q: Aspose.BarCode รองรับ IDE ของ Java ต่าง ๆ หรือไม่?**  
A: ใช่, ทำงานได้อย่างราบรื่นกับ Eclipse, IntelliJ IDEA, NetBeans, และ IDE ใด ๆ ที่สนับสนุนโปรเจกต์ Java มาตรฐาน

**Q: สามารถสร้างบาร์โค้ดที่มีค่าตัวเลขและอักขระผสมได้หรือไม่?**  
A: ได้, CODE_128 สามารถเข้ารหัสข้อมูลตัวเลขและอักขระผสมได้ ทำให้ใช้งานได้หลากหลาย

**Q: มีรุ่นทดลองของ Aspose.BarCode for Java หรือไม่?**  
A: มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode ได้โดยรับรุ่นทดลองฟรี [here](https://releases.aspose.com/)

**Q: จะหาแหล่งสนับสนุนสำหรับ Aspose.BarCode for Java ได้จากที่ไหน?**  
A: เยี่ยมชมฟอรั่ม Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.BarCode for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}