---
date: 2025-12-19
description: เรียนรู้วิธีอ่านบาร์โค้ด Java จากเอกสาร Word ด้วย Aspose.BarCode คู่มือนี้ครอบคลุมการสร้างภาพบาร์โค้ด
  การแทรกลงใน Word และการดึงภาพเพื่ออ่านบาร์โค้ด
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: วิธีอ่านบาร์โค้ดด้วย Java จากเอกสาร Word
url: /th/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านบาร์โค้ด Java จากเอกสาร Word

## บทนำ

การทำงานกับบาร์โค้ดในแอปพลิเคชัน Java เป็นความต้องการทั่วไป โดยเฉพาะเมื่อบาร์โค้ดนั้นฝังอยู่ในไฟล์ Microsoft Word ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีอ่านบาร์โค้ด Java** จากเอกสาร Word ด้วย Aspose.BarCode for Java เราจะอธิบายขั้นตอนการสร้างภาพบาร์โค้ด, การเพิ่มบาร์โค้ดลงในไฟล์ Word, การดึงภาพออกจากเอกสาร Word, และสุดท้ายการถอดรหัสบาร์โค้ดด้วยตัวอย่างโปรแกรมอ่านบาร์โค้ด Java

## คำตอบสั้น
- **ใช้ไลบรารีอะไร?** Aspose.BarCode for Java (พร้อม Aspose.Words สำหรับจัดการภาพ)  
- **สามารถเพิ่มบาร์โค้ดลงใน Word ได้หรือไม่?** ได้ – สร้างภาพแล้วแทรกด้วย Aspose.Words  
- **จะดึงภาพจาก Word อย่างไร?** ใช้ `Document.getChildNodes(NodeType.SHAPE, true)`  
- **มีตัวอย่างโปรแกรมอ่านบาร์โค้ด Java หรือไม่?** โค้ดในขั้นตอน 3 แสดงตัวอย่างครบถ้วน  
- **ข้อกำหนดเบื้องต้นคืออะไร?** JDK, Aspose.BarCode for Java, IDE (Eclipse/IntelliJ)

## การจดจำบาร์โค้ดใน Java คืออะไร?
การจดจำบาร์โค้ดใน Java หมายถึงกระบวนการตรวจจับและถอดรหัสสัญลักษณ์บาร์โค้ดจากภาพหรือเอกสารโดยใช้ไลบรารีเช่น Aspose.BarCode ซึ่งช่วยให้แอปพลิเคชันสามารถอ่านรหัสสินค้า, รหัสสินค้าคงคลัง หรือข้อมูลที่เข้ารหัสอื่น ๆ ได้โดยอัตโนมัติโดยไม่ต้องป้อนข้อมูลด้วยมือ

## ทำไมต้องอ่านบาร์โค้ด Java จากเอกสาร Word?
การฝังบาร์โค้ดโดยตรงในไฟล์ Word มีประโยชน์สำหรับสัญญา, ป้ายจัดส่ง, หรือรายงานที่ต้องการแสดงภาพของรหัส การ **ดึงภาพจาก Word** แล้วถอดรหัสโดยอัตโนมัติช่วยลดความจำเป็นในการสแกนด้วยมือและลดข้อผิดพลาด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – ติดตั้ง JDK เวอร์ชันล่าสุดบนเครื่องของคุณ  
- **Aspose.BarCode for Java** – ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/barcode/java/)  
- **Integrated Development Environment (IDE)** – เช่น Eclipse หรือ IntelliJ IDEA สำหรับเขียนและรันโค้ด

## การนำเข้าแพ็กเกจ

ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจ Aspose.BarCode และ Aspose.Words ที่จำเป็น:

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

## ขั้นตอน 1: สร้างภาพบาร์โค้ด (generate barcode image java)

เริ่มต้นด้วยการสร้างภาพบาร์โค้ดโดยใช้ Aspose.BarCode ภาพนี้จะถูก **เพิ่มบาร์โค้ดลงใน Word** ต่อไป:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## ขั้นตอน 2: แทรกภาพบาร์โค้ดลงในเอกสาร Word (insert image into word)

ต่อไปเราจะใช้ Aspose.Words เพื่อ **แทรกภาพลงใน Word** และบันทึกเอกสาร:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## ขั้นตอน 3: จดจำบาร์โค้ดจากเอกสาร Word (java barcode reader example)

สุดท้าย ดึงภาพแต่ละภาพจากไฟล์ Word แล้วรัน **ตัวอย่างโปรแกรมอ่านบาร์โค้ด Java** เพื่อถอดรหัสบาร์โค้ด:

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

> **หมายเหตุ:** ลูปด้านบนแสดงการ **ดึงภาพจาก Word**, บันทึกแต่ละภาพ, แล้วถอดรหัสบาร์โค้ดโดยใช้เส้นทางไฟล์ภาพเดียวกัน ปรับค่า `dataDir` ให้ตรงกับสภาพแวดล้อมของคุณตามต้องการ

## ปัญหาที่พบบ่อยและเคล็ดลับ

- **เส้นทางไฟล์ไม่ตรงกัน** – ตรวจสอบให้ `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่ มิฉะนั้นตัวอ่านจะโยน `FileNotFoundException`  
- **ประเภทบาร์โค้ดที่ไม่รองรับ** – ตัวอย่างใช้ `CODE_39_STANDARD` หากต้องการ QR, DataMatrix ฯลฯ ให้เปลี่ยนทั้ง `EncodeTypes` และ `DecodeType` ให้สอดคล้อง  
- **ประสิทธิภาพ** – สำหรับเอกสารขนาดใหญ่ ควรพิจารณาประมวลผลภาพแบบขนาน (parallel streams) เพื่อเร่งการจดจำ

## คำถามที่พบบ่อย (FAQs)

### ถ: สามารถใช้ Aspose.BarCode for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?
ใช่, Aspose.BarCode for Java มีให้ใช้ในโครงการเชิงพาณิชย์ รายละเอียดการให้ลิขสิทธิ์สามารถดูได้ [ที่นี่](https://purchase.aspose.com/buy)

### ถ: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for Java หรือไม่?
มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.BarCode for Java [ที่นี่](https://releases.aspose.com/)

### ถ: จะขอรับการสนับสนุนสำหรับ Aspose.BarCode for Java อย่างไร?
สำหรับการช่วยเหลือหรือคำถามใด ๆ ให้เยี่ยมชมฟอรั่ม Aspose.BarCode [ที่นี่](https://forum.aspose.com/c/barcode/13)

### ถ: มีใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode for Java หรือไม่?
มี, คุณสามารถขอรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ถ: จะหาเอกสารประกอบสำหรับ Aspose.BarCode for Java ได้จากที่ไหน?
ดูเอกสารฉบับสมบูรณ์ได้ [ที่นี่](https://reference.aspose.com/barcode/java/)

## คำถามเพิ่มเติม

**ถาม: สามารถอ่านสัญลักษณ์บาร์โค้ดอื่น ๆ นอกจาก Code 39 ได้หรือไม่?**  
ตอบ: แน่นอน เพียงเปลี่ยน `EncodeTypes` เมื่อสร้างและ `DecodeType` เมื่ออ่านให้ตรงกับสัญลักษณ์ที่ต้องการ (เช่น `EncodeTypes.QR`, `DecodeType.QR`)

**ถาม: วิธีนี้ทำงานกับไฟล์ .docx ได้หรือไม่?**  
ตอบ: ได้ Aspose.Words รองรับทั้งรูปแบบ `.doc` และ `.docx` อย่างโปร่งใส โค้ดเดียวกันทำงานได้กับทั้งสองรูปแบบ

**ถาม: จะปรับปรุงความแม่นยำของการจดจำภาพความละเอียดต่ำอย่างไร?**  
ตอบ: เพิ่ม DPI เมื่อบันทึกภาพบาร์โค้ด (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) หรือใช้รูปแบบภาพคุณภาพสูงเช่น PNG

---

**อัปเดตล่าสุด:** 2025-12-19  
**ทดสอบกับ:** Aspose.BarCode for Java 24.11 และ Aspose.Words for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}