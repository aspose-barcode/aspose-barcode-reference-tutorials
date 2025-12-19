---
date: 2025-12-19
description: เรียนรู้วิธีอ่านบาร์โค้ดด้วย Aspose.BarCode สำหรับ Java จัดเรียงตามลำดับที่ต้องการ
  และดูตัวอย่างการตรวจจับบาร์โค้ดด้วย Java อย่างครบถ้วน
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: วิธีอ่านบาร์โค้ดและจัดเรียงตามลำดับที่กำหนดใน Java
url: /th/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านบาร์โค้ดและจัดเรียงตามลำดับที่กำหนดใน Java

## บทนำ

ในแอปพลิเคชัน Java สมัยใหม่ การ **วิธีอ่านบาร์โค้ด** อย่างมีประสิทธิภาพเป็นคำถามที่พบบ่อย ไม่ว่าคุณจะกำลังประมวลผลรายการสินค้าคงคลัง ป้ายจัดส่ง หรือบัตรเข้าร่วมงาน โซลูชันบาร์โค้ดที่เชื่อถือได้สามารถประหยัดเวลาการทำงานด้วยมือหลายชั่วโมงได้ ในบทเรียนนี้เราจะแสดงวิธีอ่านบาร์โค้ดและจัดเรียงตามลำดับที่กำหนดโดยใช้ **Aspose.BarCode for Java** คุณจะได้รับตัวอย่างที่ครบถ้วนพร้อมรันที่แสดงการตรวจจับบาร์โค้ด การสกัดข้อความโค้ด และตรรกะการจัดเรียงแบบกำหนดเอง

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.BarCode for Java
- **ฉันสามารถจัดเรียงบาร์โค้ดหลังจากอ่านได้หรือไม่?** Yes – just store the results and apply a comparator
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** A free trial works for testing; a commercial license is required for production
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 and later
- **นี่คือตัวอย่างการตรวจจับบาร์โค้ดใน Java หรือไม่?** Absolutely – the code reads CODE_128 barcodes and sorts them

## “วิธีอ่านบาร์โค้ด” ใน Java คืออะไร?
การอ่านบาร์โค้ดหมายถึงการถอดรหัสรูปแบบภาพของบาร์โค้ดให้เป็นค่าข้อความที่อยู่เบื้องหลัง Aspose.BarCode ให้เครื่องมือ **barcode reading aspose** ที่มีประสิทธิภาพสูงซึ่งรองรับสัญลักษณ์หลายสิบแบบ รวมถึง CODE_128, QR, DataMatrix และอื่น ๆ

## ทำไมต้องใช้ Aspose.BarCode สำหรับการอ่านบาร์โค้ด aspose?
- **ความแม่นยำสูง** – works even with low‑resolution images
- **API ที่ง่าย** – a few lines of code get you from image to text
- **ข้ามแพลตฟอร์ม** – works on any JVM‑compatible environment
- **รองรับการจัดเรียงในตัว** – you can easily combine reading with Java collections

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกไปในโค้ด โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้ครบถ้วน:

- Java Development Kit (JDK): Aspose.BarCode for Java ต้องการ JDK ที่ทำงานได้ คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้ [ที่นี่](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.BarCode Library: ตรวจสอบว่าคุณมีไลบรารี Aspose.BarCode แล้ว คุณสามารถรับได้จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/barcode/java/).

## นำเข้าแพ็กเกจ

เริ่มต้นโดยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ แพ็กเกจเหล่านี้ให้คลาสและเมธอดที่สำคัญสำหรับการทำงานกับบาร์โค้ด

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

ตอนนี้เราจะอธิบายโค้ดทีละขั้นตอน:

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงของไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: ระบุเส้นทางภาพบาร์โค้ดและเริ่มต้น Reader

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

## ปัญหาทั่วไปและวิธีแก้

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **ไม่พบบาร์โค้ด** | DecodeType ไม่ถูกต้องหรือภาพคุณภาพต่ำ | ตรวจสอบว่าภาพมีบาร์โค้ด CODE_128 และใช้ `DecodeType` ที่เหมาะสม คุณสามารถลอง `DecodeType.ALL` เพื่อการตรวจจับอัตโนมัติได้ |
| **ลำดับการจัดเรียงไม่ถูกต้อง** | Comparator เปรียบเทียบสตริงตามลำดับอักขระ | หากต้องการจัดเรียงเป็นตัวเลข ให้แปลง `CodeText` เป็น `int` ก่อนเปรียบเทียบ |
| **เกิด Null pointer ที่ `BarCodeRegion`** | เส้นทางภาพผิดหรือไม่พบไฟล์ | ตรวจสอบให้ `path` ชี้ไปยังไฟล์ PNG ที่ถูกต้องและไฟล์สามารถอ่านได้โดย JVM |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถหาเอกสาร Aspose.BarCode for Java ได้จากที่ไหน?**  
คำตอบ: เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/barcode/java/).

**ถาม: ฉันจะดาวน์โหลด Aspose.BarCode for Java ได้อย่างไร?**  
คำตอบ: คุณสามารถดาวน์โหลดได้จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/barcode/java/).

**ถาม: มีการทดลองใช้ฟรีหรือไม่?**  
คำตอบ: มี คุณสามารถสำรวจการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/).

**ถาม: ฉันจะรับข้อมูลการออกใบอนุญาตชั่วคราวได้อย่างไร?**  
คำตอบ: ใบอนุญาตชั่วคราวสามารถรับได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

**ถาม: ฉันจะหาการสนับสนุนหรือถามคำถามได้จากที่ไหน?**  
คำตอบ: เยี่ยมชมฟอรั่มสนับสนุน [ที่นี่](https://forum.aspose.com/c/barcode/13).

## คำถามเพิ่มเติม (AI‑Optimized)

**ถาม: ฉันสามารถใช้โค้ดนี้กับประเภทบาร์โค้ดอื่นได้หรือไม่?**  
คำตอบ: แน่นอน เปลี่ยน `DecodeType.CODE_128` เป็นสัญลักษณ์ที่รองรับอื่น ๆ เช่น `DecodeType.QR` หรือ `DecodeType.DATA_MATRIX`.

**ถาม: Aspose.BarCode รองรับการประมวลผลหลายภาพพร้อมกันหรือไม่?**  
คำตอบ: ใช่ ให้วนลูปผ่านคอลเลกชันของเส้นทางไฟล์และใช้ตรรกะ `BarCodeReader` เดียวกันสำหรับแต่ละภาพ.

**ถาม: ฉันจะปรับปรุงประสิทธิภาพสำหรับชุดภาพขนาดใหญ่ได้อย่างไร?**  
คำตอบ: ใช้ตัวอย่าง `BarCodeReader` ซ้ำเมื่อเป็นไปได้และประมวลผลภาพแบบขนานโดยใช้ `ExecutorService` ของ Java.

## สรุป

ในบทเรียนนี้เราได้สาธิต **วิธีอ่านบาร์โค้ด** ด้วย Aspose.BarCode for Java, เก็บผลลัพธ์แต่ละรายการ, และจัดเรียงรายการตามลำดับที่กำหนดโดยใช้แนวทางขั้นตอนต่อขั้นตอน คุณสามารถผสานรวมการตรวจจับบาร์โค้ดและการจัดเรียงที่แข็งแกร่งเข้าไปในแอปพลิเคชัน Java ใด ๆ ไม่ว่าจะเป็นการจัดการสินค้าคงคลัง, โลจิสติกส์ หรือการออกบัตรเข้าร่วมงาน

---

**อัปเดตล่าสุด:** 2025-12-19  
**ทดสอบด้วย:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}