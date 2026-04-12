---
date: 2026-04-12
description: เรียนรู้วิธีการตรวจจับบาร์โค้ดจากเอกสาร Word โดยใช้ Aspose.BarCode for
  Java คู่มือนี้ยังแสดงวิธีการเพิ่มบาร์โค้ดลงใน Word และสกัดภาพจาก Word
keywords:
- how to recognize barcode
- add barcode to word
- read barcode from image
- extract images from word
- barcode detection java
linktitle: การจดจำบาร์โค้ดจากเอกสาร Word
second_title: Aspose.BarCode Java API
title: วิธีจดจำบาร์โค้ดจากเอกสาร Word – คู่มือ Java
url: /th/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการจดจำบาร์โค้ดจากเอกสาร Word – คู่มือ Java

## บทนำ

หากคุณต้องการ **วิธีการจดจำบาร์โค้ด** ที่ฝังอยู่ในไฟล์ Microsoft Word คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านตัวอย่างครบวงจรตั้งแต่ต้นจนจบที่ใช้ Aspose.BarCode for Java เพื่อสร้างบาร์โค้ด, แทรกลงในเอกสาร Word, ดึงภาพออกมาอีกครั้ง, และสุดท้ายอ่านข้อมูลบาร์โค้ด เมื่อเสร็จคุณจะได้เห็นวิธี **เพิ่มบาร์โค้ดลงใน Word**, **ดึงรูปภาพจาก Word**, และทำการ **การตรวจจับบาร์โค้ดด้วย Java** — ทั้งหมดด้วยเพียงไม่กี่บรรทัดของโค้ด

## คำตอบสั้น
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.BarCode for Java (plus Aspose.Words for handling .docx files).  
- **ฉันสามารถอ่านบาร์โค้ดจากภาพได้หรือไม่?** ใช่ – `BarCodeReader` สามารถถอดรหัสภาพที่ดึงจาก Word ได้.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** ทุกเวอร์ชัน JDK 8 + ทำงานได้.  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับต้นแบบพื้นฐาน.

## การจดจำบาร์โค้ดจากเอกสาร Word คืออะไร?

การจดจำบาร์โค้ดหมายถึงการสแกนภาพที่อยู่ภายในไฟล์ Word และแปลงรูปแบบภาพกลับเป็นสตริงข้อมูลเดิม (เช่น “test‑123”). Aspose.BarCode ให้เครื่องถอดรหัส, ในขณะที่ Aspose.Words ช่วยให้เราดึงภาพออกจากคอนเทนเนอร์ .doc/.docx

## ทำไมต้องใช้ Aspose.BarCode for Java?

- **ความแม่นยำสูง** ครอบคลุมกว่า 60 สัญลักษณ์ รวมถึง Code 39, QR, DataMatrix ฯลฯ.  
- **ไม่มีการพึ่งพาภายนอก** – Java แท้, ไม่มีไลบรารีเนทีฟ.  
- **การบูรณาการที่ราบรื่น** กับ Aspose.Words ทำให้ง่ายต่อการ **ดึงรูปภาพจาก Word** และจากนั้น **อ่านบาร์โค้ดจากภาพ**.  
- **ไลเซนส์ที่มั่นคง** ทำงานได้ในสภาพแวดล้อมเดสก์ท็อป, เซิร์ฟเวอร์, และคลาวด์.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – แนะนำให้ใช้เวอร์ชันล่าสุด.  
- **Aspose.BarCode for Java** – ดาวน์โหลดและติดตั้งไลบรารีจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/barcode/java/).  
- **IDE** – IntelliJ IDEA, Eclipse หรือโปรแกรมแก้ไขใด ๆ ที่คุณชอบ.

## นำเข้าแพ็กเกจ

ในโปรเจค Java ของคุณ, นำเข้าคลาส Aspose.BarCode และ Aspose.Words ที่จำเป็น:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## ขั้นตอน 1: สร้างภาพบาร์โค้ด

แรกเริ่ม, สร้างภาพบาร์โค้ดที่จะฝังลงในไฟล์ Word ต่อไป.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## ขั้นตอน 2: เพิ่มบาร์โค้ดลงในเอกสาร Word

ตอนนี้เราจะใส่ภาพที่สร้างใหม่ลงในเอกสาร Word ใหม่. นี้เป็นการสาธิตสถานการณ์ **เพิ่มบาร์โค้ดลงใน Word**.

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## ขั้นตอน 3: ดึงรูปภาพและจดจำบาร์โค้ด

เมื่อบันทึกเอกสารแล้ว, เราสามารถดึงรูปภาพทุกภาพ (รวมถึงบาร์โค้ดของเรา) และรัน **การตรวจจับบาร์โค้ดด้วย Java** บนแต่ละภาพ.

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **เคล็ดลับ:** หากคุณต้องการ **อ่านบาร์โค้ดจากภาพ** ที่ไม่ได้อยู่ในเอกสาร Word, เพียงส่งพาธไฟล์ไปยัง `BarCodeReader` – ตรรกะการถอดรหัสเดียวกันจะใช้ได้.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` on `shape.getImageData()` | รูปร่างไม่มีภาพ. | เพิ่มการตรวจสอบ `shape.hasImage()` (ได้แสดงไว้แล้ว). |
| ประเภทบาร์โค้ดที่คืนค่าไม่ถูกต้อง | ใช้ `DecodeType` ผิด. | ให้ตรงกับ `EncodeTypes` ที่ใช้ในการสร้าง (เช่น `CODE_39_STANDARD`). |
| ภาพไม่ถูกบันทึกอย่างถูกต้อง | ไม่มีสิทธิ์เขียนใน `dataDir`. | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และสามารถเขียนได้. |
| ไลเซนส์ไม่ได้ถูกนำไปใช้ | โหมดประเมินจำกัดฟังก์ชันการทำงาน. | โหลดไลเซนส์ Aspose ของคุณเมื่อเริ่มแอปพลิเคชัน: `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` |

## คำถามที่พบบ่อย

### ค: ฉันสามารถใช้ Aspose.BarCode for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?
ตอบ: ใช่, Aspose.BarCode for Java มีให้ใช้ในเชิงพาณิชย์. คุณสามารถดูรายละเอียดไลเซนส์ได้ [ที่นี่](https://purchase.aspose.com/buy).

### ค: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for Java หรือไม่?
ตอบ: มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode for Java โดยดาวน์โหลดรุ่นทดลองฟรี [ที่นี่](https://releases.aspose.com/).

### ค: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.BarCode for Java อย่างไร?
ตอบ: สำหรับความช่วยเหลือหรือคำถามใด ๆ, เยี่ยมชมฟอรั่ม Aspose.BarCode [ที่นี่](https://forum.aspose.com/c/barcode/13).

### ค: มีไลเซนส์ชั่วคราวสำหรับ Aspose.BarCode for Java หรือไม่?
ตอบ: มี, คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

### ค: ฉันจะหาเอกสารสำหรับ Aspose.BarCode for Java ได้จากที่ไหน?
ตอบ: ดูเอกสารที่ครอบคลุม [ที่นี่](https://reference.aspose.com/barcode/java/).

---  

**อัปเดตล่าสุด:** 2026-04-12  
**ทดสอบกับ:** Aspose.BarCode 24.11 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}