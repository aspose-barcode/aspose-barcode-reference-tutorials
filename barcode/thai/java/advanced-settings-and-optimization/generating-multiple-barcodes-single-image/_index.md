---
date: 2026-10-19
description: เรียนรู้วิธีสร้าง QR code java และสร้างบาร์โค้ดหลายรายการในภาพเดียวโดยใช้
  Aspose.BarCode for Java รวมถึงการตั้งค่า, code, และ troubleshooting
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: การสร้างบาร์โค้ดหลายรายการในภาพเดียว
og_description: สร้าง QR code java และรวมหลายประเภทของบาร์โค้ดเป็นภาพเดียวด้วย Aspose.BarCode
  for Java ทำตาม step‑by‑step guide, ดู code snippets, และเรียนรู้ troubleshooting
  tips
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: สร้าง QR code java – สร้างบาร์โค้ดหลายรายการในภาพเดียว
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: สร้าง QR code java – สร้างบาร์โค้ดหลายรายการในภาพเดียว
url: /th/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง QR code java – สร้างบาร์โค้ดหลายรายการในภาพเดียว

## บทนำ

ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีสร้าง QR code java** และรวมบาร์โค้ดหลายประเภทลงบนแคนวาสเดียวโดยใช้ **Aspose.BarCode for Java** ไม่ว่าคุณต้องการป้าย QR ขนาดกะทัดรัด, บาร์โค้ดสินค้า, หรือการผสมผสานของสัญลักษณ์ 2‑D และเชิงเส้น คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่าโครงการจนถึงการบันทึกภาพรวมสุดท้าย—เพื่อให้คุณเริ่มผสานการสร้างบาร์โค้ดเข้าสู่แอปพลิเคชัน Java ของคุณได้ทันที

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.BarCode for Java ให้ชุดสัญลักษณ์ที่ครบถ้วนที่สุด.  
- **ฉันสามารถสร้างบาร์โค้ดหลายประเภทพร้อมกันได้หรือไม่?** ใช่, คุณสามารถผสม CODE_39, QR, AZTEC และอื่น ๆ บนแคนวาสเดียวได้.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการผลิต.  
- **เวอร์ชัน Java ไหนที่รองรับ?** Java 8 และใหม่กว่าเข้ากันได้เต็มที่.  
- **รูปแบบผลลัพธ์สามารถกำหนดค่าได้หรือไม่?** คุณสามารถส่งออกภาพที่รวมเป็น PNG, JPEG, BMP หรือ TIFF.

## create QR code java คืออะไร?

`create QR code java` หมายถึงกระบวนการแปลงสตริงข้อความเป็นเมทริกซ์สองมิติที่สามารถสแกนโดยสมาร์ทโฟนหรือเครื่องอ่านบาร์โค้ดได้ Aspose.BarCode for Java ทำการเข้ารหัสและการเรนเดอร์ให้คุณจึงสามารถมุ่งเน้นที่ตรรกะธุรกิจแทนการจัดการภาพระดับพิกเซล.

## ทำไมต้องใช้ Aspose.BarCode Java สำหรับการสร้างบาร์โค้ด java?

Aspose.BarCode รองรับ **มากกว่า 50 สัญลักษณ์บาร์โค้ด**—รวมถึง QR, Data Matrix, Code 128, AZTEC และโค้ดเชิงเส้นแบบดั้งเดิม—ทำให้เป็นไลบรารีบาร์โค้ด Java ที่หลากหลายที่สุด มันเรนเดอร์ **ภาพที่มีการ anti‑alias ที่ความละเอียดสูงสุด 1200 dpi** เพื่อรับประกันการสแกนที่คมชัดบนหน้าจอและการพิมพ์ API ต้องการเพียง JVM เท่านั้นและให้โมเดลการกำหนดค่าที่ไหลลื่นเพื่อปรับขนาด สี ระยะขอบ และการแก้ไขข้อผิดพลาดในไม่กี่บรรทัดของโค้ด.

## ข้อกำหนดเบื้องต้น

- ความเข้าใจพื้นฐานของ Java อย่างมั่นคง  
- ติดตั้ง JDK 8 หรือใหม่กว่าและกำหนดค่าใน PATH ของคุณ  
- ไฟล์ JAR ของ Aspose.BarCode for Java (ดาวน์โหลดจากหน้า Aspose.BarCode for Java อย่างเป็นทางการ)  
- IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับแก้ไขและรันตัวอย่าง  

## นำเข้าเนมสเปซ

คำสั่ง import นำคลาสของ Aspose.BarCode เช่น `BarcodeGenerator`, `EncodeTypes` และ `BarCodeImageFormat` เข้ามาในสโคป ทำให้คุณสามารถอ้างอิงได้โดยไม่ต้องใช้ชื่อเต็ม  
`BarcodeGenerator` เป็นคลาสหลักที่ใช้กำหนดค่าและสร้างภาพบาร์โค้ด  
`EncodeTypes` เป็น enum ใน Aspose.BarCode ที่ระบุสัญลักษณ์บาร์โค้ดที่จะสร้าง  
`BarCodeImageFormat` กำหนดรูปแบบภาพผลลัพธ์สำหรับบาร์โค้ดที่สร้าง  

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

**ไดเรกทอรีทรัพยากร** คือโฟลเดอร์ในระบบไฟล์ของคุณที่บันทึกภาพบาร์โค้ดที่สร้างทั้งหมด การกำหนดครั้งเดียวทำให้โครงการของคุณเป็นระเบียบและง่ายต่อการทำความสะอาดไฟล์เก่า.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## ขั้นตอนที่ 2: สร้างคอลเลกชันของบาร์โค้ด

`HashMap<String, EncodeTypes>` เก็บสตริงข้อมูลของแต่ละบาร์โค้ดพร้อมกับสัญลักษณ์ที่คุณต้องการใช้ `HashMap` เป็นคอลเลกชันของ Java ที่แมพคีย์กับค่า คอลเลกชันนี้เป็นตัวขับลูปการสร้างต่อไป `EncodeTypes` เป็น enum ที่ระบุประเภทบาร์โค้ดที่จะสร้าง.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ขั้นตอนที่ 3: สร้างภาพบาร์โค้ด

ลูปการสร้างวนซ้ำผ่าน `HashMap` สร้าง `BarcodeGenerator` สำหรับแต่ละรายการและเรียก `generateBarCodeImage()` เพื่อรับ `BufferedImage` `generateBarCodeImage()` สร้าง `BufferedImage` ที่บรรจุบาร์โค้ดที่เรนเดอร์ `BufferedImage` เป็นคลาสของ Java ที่แสดงภาพในหน่วยความจำ ทุกภาพจะถูกเพิ่มเข้า `ArrayList<BufferedImage>` เพื่อใช้ในการรวมภาพภายหลัง `ArrayList` เป็นการทำรายการที่ปรับขนาดได้ใน Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## ขั้นตอนที่ 4: สร้างภาพรวม

ขั้นแรก อัลกอริทึมคำนวณ **ความกว้างสูงสุด** ของภาพบาร์โค้ดทั้งหมดและ **ความสูงรวม** ที่ต้องการเพื่อจัดเรียงเป็นแนวตั้งพร้อมช่องว่างที่เลือก จากนั้นสร้าง `BufferedImage` ขนาดนั้นและวาดบาร์โค้ดแต่ละอันลงบนแคนวาสโดยใช้วัตถุ `Graphics2D` `Graphics2D` เป็นคลาสของ Java ที่ให้ความสามารถในการเรนเดอร์ 2D สำหรับวาดรูปทรงและภาพ.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ขั้นตอนที่ 5: บันทึกผลลัพธ์

สุดท้าย ภาพรวมจะถูกเขียนลงดิสก์ด้วย `ImageIO.write` โดยใช้รูปแบบที่คุณระบุ (PNG, JPEG, BMP หรือ TIFF) `ImageIO.write` เขียน `BufferedImage` ไปยังไฟล์ในรูปแบบที่กำหนด เส้นทางไฟล์เป็นเส้นทางสัมพันธ์กับไดเรกทอรีทรัพยากรที่กำหนดไว้ก่อนหน้า.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## กรณีการใช้งานทั่วไปสำหรับการสร้างบาร์โค้ดหลายรายการ

- **ป้ายบรรจุภัณฑ์** – รวมรหัสสินค้า, รหัสล็อต, และรหัสการจัดส่งบนป้ายเดียวเพื่อลดค่าใช้จ่ายการพิมพ์.  
- **บัตรเข้าร่วมงาน** – ฝัง QR, Data Matrix, และรหัส Code 128 สำหรับสถานีสแกนต่าง ๆ ในสถานที่.  
- **การจัดการสินค้าคงคลัง** – แสดง SKU, ข้อมูลแท็ก RFID, และหมายเลขซีเรียลร่วมกันเพื่อการตรวจสอบและการติดตามที่รวดเร็ว.

## การแก้ไขปัญหาและเคล็ดลับ

- **ปัญหาขนาดภาพ** – ปรับตัวแปร `offset` เพื่อเพิ่มหรือลดช่องว่างระหว่างบาร์โค้ด.  
- **สัญลักษณ์ที่ไม่รองรับ** – ตรวจสอบว่าเวอร์ชัน Aspose.BarCode ของคุณรองรับประเภทบาร์โค้ดที่ต้องการหรือไม่; รุ่นใหม่เพิ่มโค้ด 2‑D เพิ่มเติม.  
- **ประสิทธิภาพ** – ใช้วัตถุ `Graphics2D` เดียวซ้ำเมื่อสร้างภาพหลายภาพในลูปเพื่อให้การจัดสรรวัตถุ น้อยที่สุด.  

## คำถามที่พบบ่อย

**Q: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดแต่ละรายการในภาพที่สร้างได้หรือไม่?**  
A: ได้. ใช้คุณสมบัติของ `BarcodeGenerator` เช่น `setBarColor`, `setBackgroundColor`, และ `setXDimension` เพื่อกำหนดสไตล์ให้แต่ละบาร์โค้ดแยกกันก่อนเพิ่มลงบนแคนวาส.

**Q: Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลายประเภทหรือไม่?**  
A: แน่นอน. ไลบรารีรองรับสัญลักษณ์กว่า 50 ประเภท รวมถึง CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, และ AZTEC ตามที่แสดงในบทเรียนนี้.

**Q: ฉันจะรวม Aspose.BarCode เข้าไปในโครงการ Java ของฉันอย่างไร?**  
A: ดาวน์โหลด JAR จากหน้าดาวน์โหลดไลบรารี Aspose.BarCode for Java, เพิ่มเข้าไปใน classpath ของโครงการ, และนำเข้าเนมสเปซที่จำเป็นตามที่แสดงในส่วน “Import namespaces”.

**Q: ฉันสามารถใช้ Aspose.BarCode สำหรับแอปพลิเคชันเชิงพาณิชย์ได้หรือไม่?**  
A: ได้. ซื้อไลเซนส์จากหน้า Aspose.BarCode license purchase เพื่อยกเลิกข้อจำกัดของการทดลองและรับการสนับสนุนเต็มรูปแบบสำหรับการผลิต.

**Q: มีตัวเลือกการทดลองใช้สำหรับ Aspose.BarCode หรือไม่?**  
A: แน่นอน. มีไลเซนส์ทดลองฟรีจากหน้า Aspose.BarCode free trial download ให้คุณเข้าถึง API อย่างเต็มที่สำหรับการประเมิน.

**Q: ฉันจะสร้าง QR code ความละเอียดสูงสำหรับการพิมพ์อย่างไร?**  
A: ตั้งค่าคุณสมบัติ `setResolutionDpi` บน `BarcodeGenerator` ก่อนเรียก `generateBarCodeImage()`, จากนั้นบันทึกผลลัพธ์ในรูปแบบที่ไม่มีการสูญเสียเช่น PNG.

**Q: ควรทำอย่างไรหากภาพรวมดูเหมือนถูกตัด?**  
A: ตรวจสอบว่า `offset` และการคำนวณขนาดแคนวาสคำนึงถึงความสูงของบาร์โค้ดทั้งหมดอย่างถูกต้อง; การเพิ่มความสูงของแคนวาสหรือการลดขนาดบาร์โค้ดแต่ละรายการจะช่วยแก้ปัญหาการตัดส่วนใหญ่.

---

**อัปเดตล่าสุด:** 2026-10-19  
**ทดสอบด้วย:** Aspose.BarCode for Java 24.11  
**ผู้เขียน:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้างภาพบาร์โค้ด Java – เพิ่มขอบด้วย Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [วิธีสร้างบาร์โค้ด Java: บันทึกเป็นสตรีมด้วย Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [วิธีสร้างบาร์โค้ด Java และพิมพ์บาร์โค้ดด้วย Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}