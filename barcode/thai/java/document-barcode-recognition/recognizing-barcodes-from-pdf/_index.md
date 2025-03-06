---
title: การรับรู้บาร์โค้ดจาก PDF ใน Java
linktitle: การรับรู้บาร์โค้ดจาก PDF
second_title: Aspose.BarCode Java API
description: เรียนรู้วิธีจดจำบาร์โค้ดจาก PDF ใน Java โดยใช้ Aspose.BarCode คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด เพิ่มประสิทธิภาพการจัดการข้อมูลของคุณ!
weight: 11
url: /th/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การรับรู้บาร์โค้ดจาก PDF ใน Java


## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนของเราเกี่ยวกับการจดจำบาร์โค้ดจาก PDF โดยใช้ Aspose.BarCode สำหรับ Java บาร์โค้ดมีบทบาทสำคัญในการจัดการข้อมูลและการจัดระเบียบ และด้วย Aspose.BarCode กระบวนการจะราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทั้งหมด ตั้งแต่การตั้งค่าข้อกำหนดเบื้องต้นที่จำเป็นไปจนถึงการนำโค้ดสำหรับการจดจำบาร์โค้ดไปใช้งานในไฟล์ PDF

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.BarCode สำหรับใบอนุญาต Java: รับและตั้งค่าใบอนุญาตที่ถูกต้องสำหรับ Aspose.BarCode สำหรับ Java คุณสามารถขอรับใบอนุญาตได้จาก[กำหนดให้จัดซื้อ](https://purchase.aspose.com/buy).

2.  ใบอนุญาต Aspose.PDF: นอกจากนี้ ให้ตั้งค่าใบอนุญาตสำหรับ Aspose.PDF ซึ่งจำเป็นสำหรับการทำงานกับไฟล์ PDF คุณสามารถขอใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

3.  ดาวน์โหลด Aspose.BarCode สำหรับ Java: ดาวน์โหลดไลบรารี Aspose.BarCode จาก[ที่นี่](https://releases.aspose.com/barcode/java/).

เมื่อคุณมีข้อกำหนดเบื้องต้นที่จำเป็นแล้ว เรามาดำเนินการนำเข้าแพ็คเกจที่จำเป็นและเริ่มบทช่วยสอนของเรากัน

## แพ็คเกจนำเข้า

ในโปรเจ็กต์ Java ของคุณ ให้รวมแพ็คเกจ Aspose.BarCode และ Aspose.PDF ต่อไปนี้คือตัวอย่างโค้ดสำหรับการเริ่มต้น:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## ขั้นตอนที่ 1: สร้างบาร์โค้ดและเพิ่มลงใน PDF

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## ขั้นตอนที่ 2: สร้าง PDF และเพิ่มรูปภาพบาร์โค้ด

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## ขั้นตอนที่ 3: แยกรูปภาพจาก PDF

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## ขั้นตอนที่ 4: จดจำบาร์โค้ดจากรูปภาพที่แยกออกมา

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

ทำซ้ำขั้นตอนเหล่านี้ตามต้องการ โดยปรับชื่อไฟล์และเส้นทางให้เหมาะสม

## บทสรุป

 ยินดีด้วย! คุณได้เรียนรู้วิธีจดจำบาร์โค้ดจาก PDF โดยใช้ Aspose.BarCode สำหรับ Java เรียบร้อยแล้ว บทช่วยสอนนี้มีวัตถุประสงค์เพื่อให้คำแนะนำที่ครอบคลุมโดยยังคงรักษาความเรียบง่ายและความชัดเจนไว้ รู้สึกอิสระที่จะสำรวจคุณสมบัติและฟังก์ชันการทำงานเพิ่มเติมที่นำเสนอโดย Aspose.BarCode ใน[เอกสารประกอบ](https://reference.aspose.com/barcode/java/).

## คำถามที่พบบ่อย (FAQ)

### ถาม: ฉันสามารถใช้ Aspose.BarCode สำหรับ Java โดยไม่มีใบอนุญาตได้หรือไม่
แม้ว่า Aspose.BarCode จะสามารถใช้งานได้โดยไม่ต้องมีใบอนุญาต แต่ขอแนะนำให้ขอรับใบอนุญาตเพื่อให้มีฟังก์ชันการทำงานเต็มรูปแบบและเพื่อให้เป็นไปตามข้อกำหนดในการอนุญาตให้ใช้สิทธิ

### ถาม: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.BarCode สำหรับ Java ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### ถาม: มีข้อจำกัดเกี่ยวกับประเภทบาร์โค้ดที่ Aspose.BarCode รองรับหรือไม่
Aspose.BarCode รองรับบาร์โค้ดหลายประเภท โปรดดูเอกสารประกอบสำหรับรายการทั้งหมด

### ถาม: Aspose.BarCode สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองได้จาก[ที่นี่](https://releases.aspose.com/).

### ถาม: ฉันจะขอรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.BarCode สำหรับ Java ได้ที่ไหน
 เยี่ยมชม Aspose.BarCode[ฟอรั่ม](https://forum.aspose.com/c/barcode/13) สำหรับการสนับสนุนและการอภิปราย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
