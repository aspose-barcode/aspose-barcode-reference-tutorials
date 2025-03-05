---
title: การรับรู้บาร์โค้ดจากเอกสาร Word ได้อย่างง่ายดาย
linktitle: การรับรู้บาร์โค้ดจากเอกสาร Word
second_title: Aspose.BarCode Java API
description: สำรวจการบูรณาการการจดจำบาร์โค้ดเข้ากับแอปพลิเคชัน Java ของคุณด้วย Aspose.BarCode ได้อย่างราบรื่น ทำตามบทช่วยสอนนี้เพื่อจดจำบาร์โค้ดจากเอกสาร Word
type: docs
weight: 12
url: /th/java/document-barcode-recognition/recognizing-barcodes-from-word/
---

## การแนะนำ

ในโลกแบบไดนามิกของการเขียนโปรแกรม Java ความจำเป็นในการทำงานกับบาร์โค้ดอย่างมีประสิทธิภาพมีเพิ่มมากขึ้น การจดจำบาร์โค้ดจากเอกสาร Word เป็นข้อกำหนดทั่วไป และโชคดีที่ Aspose.BarCode สำหรับ Java มอบโซลูชันที่มีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการจดจำบาร์โค้ดจากเอกสาร Word โดยใช้ Aspose.BarCode สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK): Aspose.BarCode สำหรับ Java ต้องการสภาพแวดล้อมการพัฒนา Java ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ล่าสุดบนระบบของคุณ

-  Aspose.BarCode สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.BarCode สำหรับ Java คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/barcode/java/).

- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการ เช่น Eclipse หรือ IntelliJ เพื่อทำตามตัวอย่าง

## แพ็คเกจนำเข้า

ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจ Aspose.BarCode ที่จำเป็นเพื่อเริ่มต้น:

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

## ขั้นตอนที่ 1: สร้างภาพบาร์โค้ด

ขั้นแรก สร้างภาพบาร์โค้ดโดยใช้ Aspose.BarCode ตั้งค่าข้อความโค้ดและบันทึกรูปภาพ:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## ขั้นตอนที่ 2: เพิ่มรูปภาพลงในเอกสาร Word

ตอนนี้ แทรกรูปภาพบาร์โค้ดที่สร้างขึ้นลงในเอกสาร Word โดยใช้ Aspose.Words:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## ขั้นตอนที่ 3: จดจำบาร์โค้ดจากเอกสาร Word

จากนั้น แยกรูปภาพออกจากเอกสาร Word และจดจำบาร์โค้ดโดยใช้ Aspose.BarCode:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // แตกรูปภาพเป็นไฟล์
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // รู้จักบาร์โค้ดจากภาพนี้
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

ทำซ้ำขั้นตอนเหล่านี้ แล้วคุณจะจดจำบาร์โค้ดจากเอกสาร Word ได้สำเร็จโดยใช้ Aspose.BarCode สำหรับ Java

## บทสรุป

โดยสรุป การใช้ Aspose.BarCode สำหรับ Java ช่วยลดความยุ่งยากในกระบวนการจดจำบาร์โค้ดจากเอกสาร Word ทำตามขั้นตอนที่อธิบายไว้ข้างต้น แล้วคุณจะผสานรวมการจดจำบาร์โค้ดเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย (FAQ)

### ถาม: ฉันสามารถใช้ Aspose.BarCode สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ Aspose.BarCode สำหรับ Java พร้อมให้ใช้งานเชิงพาณิชย์แล้ว คุณสามารถค้นหารายละเอียดใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).

### ถาม: Aspose.BarCode สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ได้ คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode สำหรับ Java ได้โดยการดาวน์โหลดรุ่นทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).

### ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.BarCode สำหรับ Java ได้อย่างไร
หากต้องการความช่วยเหลือหรือข้อสงสัยใดๆ โปรดไปที่ฟอรัม Aspose.BarCode[ที่นี่](https://forum.aspose.com/c/barcode/13).

### ถาม: Aspose.BarCode สำหรับ Java มีใบอนุญาตชั่วคราวหรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.BarCode สำหรับ Java ได้ที่ไหน
 โปรดดูเอกสารประกอบที่ครอบคลุม[ที่นี่](https://reference.aspose.com/barcode/java/).
