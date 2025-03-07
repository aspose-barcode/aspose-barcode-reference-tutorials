---
title: การสร้างบาร์โค้ดหลายอันบนรูปภาพเดียวใน Java ด้วย Aspose.BarCode
linktitle: การสร้างบาร์โค้ดหลายอันบนภาพเดียว
second_title: Aspose.BarCode Java API
description: สร้างบาร์โค้ดหลายอันบนรูปภาพเดียวได้อย่างง่ายดายโดยใช้ Aspose.BarCode สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 19
url: /th/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างบาร์โค้ดหลายอันบนรูปภาพเดียวใน Java ด้วย Aspose.BarCode

## การแนะนำ

ในโลกแบบไดนามิกของการเขียนโปรแกรม Java การสร้างและการจัดการบาร์โค้ดอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับแอปพลิเคชันต่างๆ Aspose.BarCode สำหรับ Java ช่วยให้กระบวนการนี้ง่ายขึ้น ช่วยให้นักพัฒนาสามารถสร้างบาร์โค้ดหลายอันบนภาพเดียวได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนต่างๆ เพื่อให้บรรลุเป้าหมายนี้โดยใช้ Aspose.BarCode ในสภาพแวดล้อม Java

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.BarCode สำหรับไลบรารี Java ดาวน์โหลดและตั้งค่า คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/barcode/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ IDEA

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.BarCode เพิ่มคำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของคลาส Java ของคุณ:

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

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีทรัพยากร

กำหนดเส้นทางไปยังไดเร็กทอรีทรัพยากรที่จะบันทึกบาร์โค้ดที่สร้างขึ้น ไดเร็กทอรีนี้มีความสำคัญอย่างยิ่งต่อการจัดระเบียบและจัดการภาพบาร์โค้ดของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีทรัพยากร
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ขั้นตอนที่ 2: สร้างคอลเลกชันบาร์โค้ด

เริ่มต้น HashMap เพื่อจัดเก็บข้อมูลบาร์โค้ด แต่ละรายการในคอลเลกชันจะแสดงบาร์โค้ดที่มีประเภทการเข้ารหัสตามลำดับ

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## ขั้นตอนที่ 3: สร้างภาพบาร์โค้ด

วนซ้ำคอลเลกชันและสร้างภาพบาร์โค้ดโดยใช้ไลบรารี Aspose.BarCode เก็บภาพไว้ใน ArrayList เพื่อประมวลผลต่อไป

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ขั้นตอนที่ 4: สร้างภาพที่รวม

กำหนดความกว้างสูงสุดและความสูงรวมของภาพบาร์โค้ด สร้าง BufferedImage เพื่อรวมภาพบาร์โค้ดแต่ละภาพให้เป็นภาพเอาต์พุตเดียว

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
## ขั้นตอนที่ 5: บันทึกผลลัพธ์

บันทึกภาพที่รวมในขั้นสุดท้ายไปยังตำแหน่งไฟล์ที่ระบุ

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## บทสรุป

ยินดีด้วย! คุณสร้างบาร์โค้ดหลายอันบนรูปภาพเดียวได้สำเร็จโดยใช้ Aspose.BarCode สำหรับ Java ไลบรารีอันทรงพลังนี้ทำให้การจัดการบาร์โค้ดง่ายขึ้น ทำให้เป็นเครื่องมืออันล้ำค่าสำหรับนักพัฒนา Java

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของบาร์โค้ดแต่ละอันในรูปภาพที่สร้างขึ้นได้หรือไม่

ตอบ 1: ใช่ Aspose.BarCode มีตัวเลือกการปรับแต่งมากมายสำหรับลักษณะที่ปรากฏของบาร์โค้ด ซึ่งช่วยให้คุณปรับแต่งสไตล์ของบาร์โค้ดแต่ละอันให้ตรงตามความต้องการของคุณได้

### คำถามที่ 2: Aspose.BarCode เข้ากันได้กับสัญลักษณ์บาร์โค้ดต่างๆ หรือไม่

A2: แน่นอน! Aspose.BarCode รองรับสัญลักษณ์ที่หลากหลาย รวมถึง CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 และ AZTEC ดังที่แสดงในบทช่วยสอนนี้

### คำถามที่ 3: ฉันจะรวม Aspose.BarCode เข้ากับโปรเจ็กต์ Java ของฉันได้อย่างไร

 A3: เพียงดาวน์โหลด Aspose.BarCode สำหรับไลบรารี Java จาก[ที่นี่](https://releases.aspose.com/barcode/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

### คำถามที่ 4: ฉันสามารถใช้ Aspose.BarCode สำหรับการใช้งานเชิงพาณิชย์ได้หรือไม่

 A4: ได้ คุณสามารถขอรับใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy) เพื่อใช้ Aspose.BarCode เพื่อวัตถุประสงค์ทางการค้า

### คำถามที่ 5: มีตัวเลือกทดลองใช้งานสำหรับ Aspose.BarCode หรือไม่

 A5: แน่นอน! คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode ได้โดยรับใบอนุญาตทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
