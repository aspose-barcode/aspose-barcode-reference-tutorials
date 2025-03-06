---
title: การสร้างและบันทึกบาร์โค้ดใน Java
linktitle: การสร้างและการบันทึกบาร์โค้ด
second_title: Aspose.BarCode Java API
description: สร้างและบันทึกบาร์โค้ดได้อย่างง่ายดายใน Java ด้วย Aspose.BarCode ผสานรวมอย่างลงตัว ปรับแต่งรูปลักษณ์ และเพลิดเพลินกับการรองรับบาร์โค้ดที่ครอบคลุม
weight: 12
url: /th/java/symbology-and-format/generating-saving-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างและบันทึกบาร์โค้ดใน Java


## การแนะนำ

คุณกำลังมองหาการผสานรวมการสร้างบาร์โค้ดเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่นหรือไม่? ไม่ต้องมองอีกต่อไป! ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้ Aspose.BarCode สำหรับ Java เพื่อสร้างและบันทึกบาร์โค้ดอย่างมีประสิทธิภาพ Aspose.BarCode เป็นไลบรารี Java อันทรงพลังที่ทำให้การสร้างและการจัดการบาร์โค้ดง่ายขึ้น โดยมอบเครื่องมือที่จำเป็นในการปรับปรุงแอปพลิเคชันของคุณด้วยฟังก์ชันการทำงานของบาร์โค้ด

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนเครื่องของคุณ

- ไลบรารี Aspose.BarCode: ดาวน์โหลดและติดตั้งไลบรารี Aspose.BarCode คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/barcode/java/).

- ฐานข้อมูล MySQL: ตั้งค่าฐานข้อมูล MySQL ที่คุณต้องการจัดเก็บข้อมูลที่เกี่ยวข้องกับบาร์โค้ด

- การเชื่อมต่อฐานข้อมูล: ตรวจสอบให้แน่ใจว่าคุณมีข้อมูลรับรองและการเชื่อมต่อที่จำเป็นเพื่อโต้ตอบกับฐานข้อมูล MySQL

## แพ็คเกจนำเข้า

ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับการเชื่อมต่อ Aspose.BarCode และ MySQL

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## ขั้นตอนที่ 1: สร้างและบันทึกบาร์โค้ด

```java
// ขั้นตอนที่ 1 - สร้างบาร์โค้ดและบันทึกชั่วคราวในไฟล์
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

คำอธิบาย: ขั้นตอนนี้เกี่ยวข้องกับการสร้างบาร์โค้ดด้วย Aspose.BarCode การตั้งค่าข้อความโค้ด และการบันทึกภาพบาร์โค้ดไปยังตำแหน่งที่ระบุ

## ขั้นตอนที่ 2: แทรกบันทึกในฐานข้อมูล MySQL

```java
// ขั้นตอนที่ 2 - แทรกบันทึกใหม่ใน MySQL DB
Connection con = null;

// เปิดการเชื่อมต่อ
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// เตรียมแถลงการณ์
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// กำหนดหมายเลขผลิตภัณฑ์และชื่อผลิตภัณฑ์
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// คอลัมน์ที่ 3 เป็นภาพบาร์โค้ด ประเภท DB คือ BLOB
// ในการบันทึกภาพ เราจำเป็นต้องสร้างสตรีมจากไฟล์ภาพ
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// ดำเนินการคำสั่ง
pre.executeUpdate();
System.out.println("Insertion successful.");

// ปิดการเชื่อมต่อ
pre.close();
con.close();
```

คำอธิบาย: ขั้นตอนนี้เกี่ยวข้องกับการเชื่อมต่อกับฐานข้อมูล MySQL และการแทรกบันทึกใหม่พร้อมข้อมูลผลิตภัณฑ์และภาพบาร์โค้ดที่เกี่ยวข้อง

## บทสรุป

ยินดีด้วย! คุณได้รวม Aspose.BarCode สำหรับ Java เข้ากับแอปพลิเคชันของคุณเพื่อสร้างและบันทึกบาร์โค้ดได้สำเร็จ ไลบรารีอันทรงพลังนี้ทำให้กระบวนการง่ายขึ้น ทำให้การนำบาร์โค้ดไปใช้เป็นเรื่องง่าย

## คำถามที่พบบ่อย

### ถาม: Aspose.BarCode เข้ากันได้กับบาร์โค้ดประเภทต่างๆ หรือไม่
ตอบ: ได้ Aspose.BarCode รองรับบาร์โค้ดหลายประเภท รวมถึง CODE_39_STANDARD, CODE_128, QR และอื่นๆ

### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของบาร์โค้ดที่สร้างขึ้นได้หรือไม่
ตอบ: แน่นอน! Aspose.BarCode มีตัวเลือกการปรับแต่งมากมายสำหรับลักษณะที่ปรากฏของบาร์โค้ด ซึ่งช่วยให้คุณปรับแต่งให้ตรงตามความต้องการเฉพาะของคุณได้

### ถาม: Aspose.BarCode มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).

### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.BarCode ได้ที่ไหน
 ตอบ: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/barcode/java/).

### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.BarCode ได้อย่างไร
 ตอบ: เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/barcode/13) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
