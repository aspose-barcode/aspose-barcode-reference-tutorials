---
date: 2026-04-08
description: เรียนรู้วิธีอ่านบาร์โค้ดและจัดเรียงตามลำดับที่ต้องการโดยใช้ Aspose.BarCode
  สำหรับ Java คู่มือขั้นตอนนี้แสดงวิธีใช้ Aspose, ตัวอ่านบาร์โค้ด Java, และถอดรหัสบาร์โค้ด
  Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: การอ่านและจัดเรียงบาร์โค้ดตามลำดับที่กำหนด
second_title: Aspose.BarCode Java API
title: วิธีอ่านบาร์โค้ดตามลำดับที่กำหนดโดยใช้ Java
url: /th/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านบาร์โค้ดตามลำดับที่กำหนดโดยใช้ Java

## บทนำ

หากคุณต้องการ **วิธีอ่านบาร์โค้ด** แล้วจัดเรียงตามลำดับที่ต้องการ Aspose.BarCode for Java จะมอบวิธีที่สะอาดและมีประสิทธิภาพสูงให้คุณ ในหลายแอปพลิเคชัน Java—ระบบสินค้าคงคลัง, โซลูชันการจัดส่ง, หรือเครื่องจุดขาย—การอ่านบาร์โค้ดหลายรายการและจัดเรียงตามค่าข้อความเป็นความต้องการที่พบบ่อย คู่มือฉบับนี้จะพาคุณผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการแสดงผลลัพธ์ที่จัดเรียงแล้ว เพื่อให้คุณสามารถรวมการจัดการบาร์โค้ดได้อย่างรวดเร็วและมั่นใจ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดที่จัดการการอ่านบาร์โค้ด?** Aspose.BarCode for Java  
- **ประเภทบาร์โค้ดใดที่ใช้ในตัวอย่าง?** CODE_128  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** ใบอนุญาตชั่วคราวทำงานสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการผลิต  
- **ฉันสามารถจัดเรียงตามเกณฑ์อื่นได้หรือไม่?** ได้—ปรับ comparator เพื่อจัดเรียงตามตำแหน่ง, ความมั่นใจ ฯลฯ  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือใหม่กว่า (JDK ใดก็ได้ที่รองรับไลบรารี Aspose)

## “การอ่านบาร์โค้ด” คืออะไรใน Java?

การอ่านบาร์โค้ดหมายถึงการถอดรหัสรูปแบบภาพให้เป็นสตริงข้อมูลต้นฉบับ Aspose.BarCode มีคลาส `BarCodeReader` ที่ทำหน้าที่แยกการประมวลผลภาพระดับต่ำออกไป ให้คุณมุ่งเน้นที่ตรรกะธุรกิจ เช่น การจัดเรียงหรือการตรวจสอบความถูกต้อง

## ทำไมต้องใช้ Aspose.BarCode สำหรับ Java?

- **การถอดรหัสที่มั่นคง** – รองรับสัญลักษณ์มากกว่า 50 แบบ รวมถึง Code 128, QR, DataMatrix และอื่น ๆ  
- **ความแม่นยำสูง** – อัลกอริทึมที่ปรับแต่งลดการอ่านผิดพลาด แม้บนภาพความละเอียดต่ำ  
- **API ที่เรียบง่าย** – เพียงไม่กี่บรรทัดของโค้ดคุณก็จะได้จากภาพเป็นข้อความ  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Java runtime ใด ๆ ตั้งแต่เดสก์ท็อปจนถึงเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น

ก่อนจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- Java Development Kit (JDK): Aspose.BarCode for Java ต้องการ JDK ที่ทำงานได้ คุณสามารถดาวน์โหลดเวอร์ชันล่าสุด [ที่นี่](https://www.oracle.com/java/technologies/javase-downloads.html)。

- Aspose.BarCode Library: ตรวจสอบว่าคุณมีไลบรารี Aspose.BarCode อยู่แล้ว คุณสามารถรับได้จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/barcode/java/)。

## นำเข้าแพ็กเกจ

เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ แพ็กเกจเหล่านี้ให้คลาสและเมธอดสำคัญสำหรับการทำงานกับบาร์โค้ด

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

ตอนนี้เราจะอธิบายโค้ดเป็นขั้นตอนต่อไป:

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงของไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: ระบุเส้นทางรูปภาพบาร์โค้ดและเริ่มต้น Reader

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## ขั้นตอนที่ 3: อ่านบาร์โค้ดและเก็บผลลัพธ์

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## ขั้นตอนที่ 4: กำหนด Comparator สำหรับการจัดเรียง

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## ขั้นตอนที่ 5: จัดเรียงบาร์โค้ด

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## ขั้นตอนที่ 6: แสดงบาร์โค้ดที่จัดเรียงแล้ว

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **เส้นทางรูปภาพไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) เพื่อให้เส้นทางเต็มทำงานได้อย่างถูกต้อง  
- **ประเภทบาร์โค้ดที่ไม่รองรับ** – หากต้องการถอดรหัสสัญลักษณ์อื่น ให้เปลี่ยน `DecodeType.CODE_128` เป็นค่า enum ที่เหมาะสม (เช่น `DecodeType.QR`)  
- **การจัดเรียงตามค่าตัวเลข** – Comparator เริ่มต้นจัดเรียงแบบอักษร หากต้องการจัดเรียงเชิงตัวเลข ให้แปลง `CodeText` เป็นจำนวนเต็มภายใน Comparator  
- **การทำความสะอาดทรัพยากร** – `BarCodeReader` implements `Closeable` ในโค้ดการผลิต ควรใช้ try‑with‑resources เพื่อให้สตรีมพื้นฐานถูกปล่อยออกอย่างถูกต้อง

## คำถามที่พบบ่อย

### Q: ฉันสามารถหาเอกสาร Aspose.BarCode สำหรับ Java ได้ที่ไหน?
เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/barcode/java/)  

### Q: ฉันจะดาวน์โหลด Aspose.BarCode สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลดได้จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/barcode/java/)  

### Q: มีการทดลองใช้ฟรีหรือไม่?
มี, คุณสามารถสำรวจการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/)  

### Q: ฉันจะรับข้อมูลใบอนุญาตชั่วคราวได้จากที่ไหน?
ใบอนุญาตชั่วคราวสามารถรับได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### Q: ฉันจะหาการสนับสนุนหรือถามคำถามได้จากที่ไหน?
เยี่ยมชมฟอรั่มสนับสนุน [ที่นี่](https://forum.aspose.com/c/barcode/13)  

---

**อัปเดตล่าสุด:** 2026-04-08  
**ทดสอบกับ:** Aspose.BarCode 24.10 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}