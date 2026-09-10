---
date: 2026-04-03
description: เรียนรู้วิธีสร้าง QR code ด้วย Java และสร้างบาร์โค้ดหลายรายการบนภาพเดียวโดยใช้
  Aspose.BarCode for Java รวมถึงการตั้งค่า โค้ด และการแก้ไขปัญหา
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: การสร้างบาร์โค้ดหลายรายการบนภาพเดียว
second_title: Aspose.BarCode Java API
title: สร้าง QR Code ด้วย Java – สร้างบาร์โค้ดหลายรายการบนภาพเดียว
url: /th/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง QR Code ด้วย Java – การสร้างบาร์โค้ดหลายประเภทในภาพเดียว

## บทนำ

ในบทเรียนนี้ คุณจะได้เรียนรู้ **วิธีสร้าง QR code java** และรวมหลายประเภทบาร์โค้ดลงในภาพเดียวโดยใช้ **Aspose.BarCode for Java** ไม่ว่าคุณต้องการป้าย QR ขนาดกะทัดรัด, บาร์โค้ดสินค้า, หรือการผสมผสานของสัญลักษณ์ 2‑D และเชิงเส้น คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่าโปรเจกต์จนถึงการบันทึกภาพรวมสุดท้าย—เพื่อให้คุณเริ่มรวมการสร้างบาร์โค้ดเข้าไปในแอปพลิเคชัน Java ของคุณได้ทันที

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.BarCode for Java มีชุดสัญลักษณ์ที่ครบถ้วนที่สุด.  
- **ฉันสามารถสร้างบาร์โค้ดหลายประเภทพร้อมกันได้หรือไม่?** ได้, คุณสามารถผสม CODE_39, QR, AZTEC และอื่น ๆ บนแคนวาสเดียว.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ใดที่รองรับ?** Java 8 และใหม่กว่าเข้ากันได้เต็มที่.  
- **รูปแบบผลลัพธ์สามารถกำหนดค่าได้หรือไม่?** คุณสามารถส่งออกภาพที่รวมเป็น PNG, JPEG, BMP ฯลฯ.  

## create QR code java คืออะไร?

การสร้าง QR code ใน Java หมายถึงการแปลงข้อความเป็นเมทริกซ์สองมิติที่สามารถสแกนโดยสมาร์ทโฟนหรือเครื่องอ่านบาร์โค้ดได้ **Aspose.BarCode for Java** จัดการการเข้ารหัสและการแสดงผล ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจแทนการประมวลผลภาพระดับต่ำ.

## ทำไมต้องใช้ Aspose.BarCode Java สำหรับการสร้างบาร์โค้ดใน Java?

- **การสนับสนุนสัญลักษณ์ที่หลากหลาย** – จากโค้ดเชิงเส้นคลาสสิกถึงเมทริกซ์ 2‑D สมัยใหม่.  
- **การเรนเดอร์คุณภาพสูง** – ผลลัพธ์ anti‑aliased ที่ทำงานบนอุปกรณ์ใดก็ได้.  
- **API ที่เรียบง่าย** – สร้าง, ปรับแต่ง, และรวมบาร์โค้ดด้วยการเรียกเมธอดเพียงไม่กี่ครั้ง.  
- **ไม่มีการพึ่งพาภายนอก** – ทุกอย่างทำงานบน JVM โดยไม่ต้องใช้ไลบรารีเนทีฟ.  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามบทเรียนนี้, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:

- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ.  
- ไลบรารี Aspose.BarCode for Java ที่ดาวน์โหลดและตั้งค่าแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/barcode/java/).  
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Eclipse หรือ IntelliJ IDEA.

## นำเข้า Namespaces

ในโปรเจกต์ Java ของคุณ, ให้นำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.BarCode. เพิ่มคำสั่ง import ต่อไปนี้ที่ส่วนต้นของคลาส Java ของคุณ:

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

กำหนดเส้นทางไปยังไดเรกทอรีทรัพยากรที่บาร์โค้ดที่สร้างจะถูกบันทึก ไดเรกทอรีนี้สำคัญสำหรับการจัดระเบียบและจัดการภาพบาร์โค้ดของคุณ.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## ขั้นตอนที่ 2: สร้างคอลเลกชันของบาร์โค้ด

เริ่มต้น `HashMap` เพื่อเก็บข้อมูลบาร์โค้ด แต่ละรายการในคอลเลกชันจะแสดงบาร์โค้ดพร้อมประเภทการเข้ารหัสที่สอดคล้อง.

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

วนลูปผ่านคอลเลกชันและสร้างภาพบาร์โค้ดโดยใช้ไลบรารี Aspose.BarCode เก็บภาพไว้ใน `ArrayList` เพื่อการประมวลผลต่อไป.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## ขั้นตอนที่ 4: สร้างภาพรวม

กำหนดความกว้างสูงสุดและความสูงรวมของภาพบาร์โค้ด สร้าง `BufferedImage` เพื่อรวมภาพบาร์โค้ดแต่ละภาพเป็นภาพผลลัพธ์เดียว.

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

บันทึกภาพรวมสุดท้ายไปยังตำแหน่งไฟล์ที่ระบุ.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## กรณีการใช้งานทั่วไปสำหรับการสร้างบาร์โค้ดหลายรายการ

- **ป้ายบรรจุภัณฑ์** – รวมรหัสสินค้า, รหัสล็อต, และรหัสการจัดส่งบนป้ายเดียว.  
- **บัตรเข้าร่วมงาน** – ฝัง QR, Data Matrix, และรหัส Code 128 สำหรับสถานีสแกนต่าง ๆ.  
- **การจัดการสินค้าคงคลัง** – แสดง SKU, ข้อมูลแท็ก RFID, และหมายเลขซีเรียลร่วมกันเพื่อการตรวจสอบอย่างรวดเร็ว.

## การแก้ไขปัญหาและเคล็ดลับ

- **ปัญหาขนาดภาพ** – ปรับตัวแปร `offset` เพื่อเพิ่มหรือ ลดระยะห่างระหว่างบาร์โค้ด.  
- **สัญลักษณ์ที่ไม่รองรับ** – ตรวจสอบว่าเวอร์ชัน Aspose.BarCode ของคุณรองรับประเภทบาร์โค้ดที่ต้องการหรือไม่.  
- **ประสิทธิภาพ** – ใช้ `Graphics` ตัวเดียวซ้ำ หากคุณสร้างภาพหลายภาพในลูป.

## คำถามที่พบบ่อย

**Q1: ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดแต่ละอันในภาพที่สร้างได้หรือไม่?**  
A1: ใช่, Aspose.BarCode มีตัวเลือกการปรับแต่งที่หลากหลายสำหรับลักษณะของบาร์โค้ด, ทำให้คุณสามารถปรับสไตล์ของแต่ละบาร์โค้ดตามความต้องการของคุณ.

**Q2: Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลายประเภทหรือไม่?**  
A2: แน่นอน! Aspose.BarCode รองรับสัญลักษณ์หลากหลาย รวมถึง CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, และ AZTEC ตามที่แสดงในบทเรียนนี้.

**Q3: ฉันจะรวม Aspose.BarCode เข้าในโปรเจกต์ Java ของฉันได้อย่างไร?**  
A3: เพียงดาวน์โหลดไลบรารี Aspose.BarCode for Java จาก [here](https://releases.aspose.com/barcode/java/) และทำตามคำแนะนำการติดตั้งที่ให้ไว้ในเอกสาร.

**Q4: ฉันสามารถใช้ Aspose.BarCode สำหรับการใช้งานเชิงพาณิชย์ได้หรือไม่?**  
A4: ใช่, คุณสามารถรับใบอนุญาตจาก [here](https://purchase.aspose.com/buy) เพื่อใช้ Aspose.BarCode ในการใช้งานเชิงพาณิชย์.

**Q5: มีตัวเลือกการทดลองใช้สำหรับ Aspose.BarCode หรือไม่?**  
A5: แน่นอน! คุณสามารถสำรวจคุณสมบัติของ Aspose.BarCode โดยรับใบอนุญาตทดลองใช้ฟรีจาก [here](https://releases.aspose.com/).

**Q6: ฉันจะสร้าง QR code ความละเอียดสูงสำหรับการพิมพ์ได้อย่างไร?**  
A6: ตั้งค่า DPI ที่ต้องการบน `BarcodeGenerator` ก่อนเรียก `generateBarCodeImage()`, จากนั้นบันทึกภาพในรูปแบบ loss‑less เช่น PNG.

**Q7: ควรทำอย่างไรหากภาพรวมดูเหมือนถูกตัด?**  
A7: ตรวจสอบว่า `offset` และการคำนวณขนาดแคนวาสได้คำนึงถึงความสูงของบาร์โค้ดทั้งหมดอย่างถูกต้อง; การเพิ่มความสูงของแคนวาสหรือการลดขนาดบาร์โค้ดแต่ละอันจะช่วยแก้ปัญหาการตัดส่วนใหญ่.

---

**อัปเดตล่าสุด:** 2026-04-03  
**ทดสอบด้วย:** Aspose.BarCode for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}