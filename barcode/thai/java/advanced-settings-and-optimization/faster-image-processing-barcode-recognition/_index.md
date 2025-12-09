---
date: 2025-12-04
description: เรียนรู้วิธีตั้งโหมดประสิทธิภาพสูงและวิธีอ่านบาร์โค้ดอย่างรวดเร็วโดยใช้เครื่องอ่านบาร์โค้ดประสิทธิภาพสูงกับ
  Aspose.BarCode สำหรับ Java.
linktitle: Faster Image Processing for Barcode Recognition
second_title: Aspose.BarCode Java API
title: 'เครื่องอ่านบาร์โค้ดประสิทธิภาพสูง: การประมวลผลภาพที่เร็วขึ้นสำหรับการจดจำบาร์โค้ดใน
  Java ด้วย Aspose.BarCode'
url: /th/java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เครื่องอ่านบาร์โค้ดประสิทธิภาพสูง: การประมวลผลภาพที่เร็วขึ้นสำหรับการจดจำบาร์โค้ดใน Java ด้วย Aspose.BarCode

ในแอปพลิเคชัน Java สมัยใหม่ **high performance barcode reader** มีความสำคัญเพื่อให้ทันกับความต้องการสแกนแบบเรียลไทม์ เมื่อคุณต้องการ **how to read barcode** อย่างรวดเร็วและเชื่อถือได้ Aspose.BarCode สำหรับ Java ให้เครื่องมือในการเร่งการประมวลผลภาพโดยไม่ลดทอนความแม่นยำ ในคู่มือนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อเปิดใช้งานโหมดประสิทธิภาพสูง ปรับแต่งการตั้งค่าคุณภาพ และบรรลุการจดจำบาร์โค้ดที่เร็วขึ้น

## คำตอบอย่างรวดเร็ว
- **What does “high performance barcode reader” mean?** เป็นการตั้งค่าที่เพิ่มความเร็วการสแกนสูงสุดโดยการปรับอัลกอริทึมการประมวลผลภาพ  
- **Which barcode symbology is used in the example?** DataMatrix (ประเภทของบาร์โค้ด 2‑D)  
- **How do I enable high‑performance mode?** เรียก `reader.setQualitySettings(QualitySettings.getHighPerformance())`  
- **Do I need a license for production?** ใช่, จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่รุ่นทดลอง  
- **What Java version is supported?** รองรับ Java 8 หรือสูงกว่าอย่างเต็มที่  

## เครื่องอ่านบาร์โค้ดประสิทธิภาพสูงคืออะไร?
**high performance barcode reader** เป็นอินสแตนซ์ที่ปรับแต่งเป็นพิเศษของเอนจิน Aspose.BarCode ที่ลดภาระการประมวลผล, ใช้การประมวลผลภาพล่วงหน้าอย่างเข้มข้น, และเร่งการวนลูปการถอดรหัส. เหมาะสำหรับสถานการณ์เช่นสถานีสแกนความเร็วสูง, แอปมือถือ, หรือการประมวลผลแบบแบตช์ของชุดภาพขนาดใหญ่

## ทำไมต้องใช้โหมดประสิทธิภาพสูงของ Aspose.BarCode?
- **Speed:** เร็วขึ้นถึง 2‑3× เมื่อเทียบกับการตั้งค่าเริ่มต้น  
- **Scalability:** จัดการภาพหลายพันภาพต่อ นาทีบนฮาร์ดแวร์ระดับกลาง  
- **Accuracy:** รักษาอัตราการจดจำสูงโดยอัตโนมัติใช้การทำให้เรียบแบบมีเดียนและการปรับแต่งอื่น ๆ  
- **Flexibility:** คุณยังสามารถปรับแต่งการตั้งค่าคุณภาพแต่ละอย่างสำหรับกรณีการใช้งานเฉพาะได้  

## ข้อกำหนดเบื้องต้น
- **Java Development Environment:** JDK 8 หรือใหม่กว่า, IDE ที่คุณเลือก (IntelliJ, Eclipse, ฯลฯ)  
- **Aspose.BarCode for Java:** ดาวน์โหลด JAR ล่าสุดจาก [Aspose.BarCode download page](https://releases.aspose.com/barcode/java/)  

## นำเข้า Namespaces
ก่อนเริ่มต้น ให้นำเข้าคลาสที่คุณต้องการใช้:

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.QualitySettings;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ทรัพยากร
กำหนดโฟลเดอร์ที่มีภาพตัวอย่างของคุณ.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(FasterImageProcessingForBarcodeRecognition.class) + "BarcodeReader/advanced_features/";
```

## ขั้นตอนที่ 2: เลือกภาพที่มีบาร์โค้ด
ชี้ตัวอ่านไปยังภาพที่คุณต้องการถอดรหัส ในตัวอย่างนี้เราใช้ภาพ DataMatrix.

```java
// Read code39 barcode from image
String imageFilePath = dataDir + "datamatrix.bmp";
```

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ BarCodeReader
สร้างอินสแตนซ์ `BarCodeReader` ด้วยเส้นทางภาพและสัญลักษณ์บาร์โค้ดที่คุณคาดหวัง.

```java
// Create an instance of BarCodeReader and set image and symbology type to recognize
BarCodeReader reader = new BarCodeReader(imageFilePath, DecodeType.DATA_MATRIX);
```

## ขั้นตอนที่ 4: ตั้งค่าโหมดประสิทธิภาพสูง
เปิดใช้งานการกำหนดค่าประสิทธิภาพสูงที่มีมาในตัว นี่คือหัวใจของการตั้งค่า **high performance barcode reader**.

```java
// Set high performance mode
reader.setQualitySettings(QualitySettings.getHighPerformance());
```

## ขั้นตอนที่ 5: ปรับแต่งตัวเลือกแยกต่างหาก (ไม่บังคับ)
คุณยังสามารถปรับการตั้งค่าคุณภาพแต่ละอย่างให้เหมาะกับลักษณะของภาพของคุณ การเปิดใช้การทำให้เรียบแบบมีเดียนมักช่วยปรับผลลัพธ์ในภาพที่มีสัญญาณรบกวน.

```java
// Set separate options
reader.getQualitySettings().setAllowMedianSmoothing(true);
reader.getQualitySettings().setMedianSmoothingWindowSize(4);
```

## ขั้นตอนที่ 6: จดจำบาร์โค้ดจากภาพ
เรียกใช้ตัวอ่านและแสดงข้อมูลที่ถอดรหัส นี่คือขั้นตอนสุดท้ายของกระบวนการ **how to read barcode**.

```java
// Try to recognize the barcode from the image
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("BarCode CodeText: " + result.getCodeText());
    System.out.println("BarCode CodeType: " + result.getCodeTypeName());
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณจะได้ **high performance barcode reader** ที่สามารถประมวลผลภาพได้อย่างรวดเร็วและเชื่อถือได้

## ปัญหาทั่วไปและวิธีแก้
- **No barcode detected:** ตรวจสอบว่าเส้นทางภาพถูกต้องและบาร์โค้ดไม่ได้หมุนเกิน 45°. พิจารณาเพิ่มค่า `MedianSmoothingWindowSize`  
- **Slow performance despite high‑performance mode:** ตรวจสอบว่าคุณใช้ JAR ของ Aspose.BarCode เวอร์ชันล่าสุด; เวอร์ชันเก่าอาจไม่มีการปรับปรุงประสิทธิภาพ  
- **Unsupported symbology:** ตรวจสอบว่า `DecodeType` ที่คุณส่งตรงกับบาร์โค้ดในภาพ  

## คำถามที่พบบ่อย

**Q: Aspose.BarCode รองรับสัญลักษณ์บาร์โค้ดหลายประเภทหรือไม่?**  
A: ใช่, รองรับสัญลักษณ์บาร์โค้ด 1‑D และ 2‑D มากมาย รวมถึง Code128, QR Code, DataMatrix, และอื่น ๆ อีกหลายประเภท.

**Q: สามารถใช้ Aspose.BarCode สำหรับการสร้างและการจดจำบาร์โค้ดได้หรือไม่?**  
A: แน่นอน. ไลบรารีนี้มี API ครบชุดสำหรับการสร้างและการอ่านบาร์โค้ดในแอปพลิเคชัน Java.

**Q: มีตัวเลือกการให้ลิขสิทธิ์สำหรับ Aspose.BarCode หรือไม่?**  
A: มี, คุณสามารถสำรวจแผนการให้ลิขสิทธิ์ต่าง ๆ ได้ที่ [Aspose.BarCode purchase page](https://purchase.aspose.com/buy).

**Q: มีเวอร์ชันทดลองฟรีของ Aspose.BarCode สำหรับ Java หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองที่ทำงานเต็มรูปแบบได้จาก [Aspose releases page](https://releases.aspose.com/).

**Q: จะขอรับการสนับสนุนหรือเข้าร่วมชุมชนได้อย่างไร?**  
A: เยี่ยมชม [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) อย่างเป็นทางการเพื่อรับความช่วยเหลือ ตัวอย่าง และการสนทนาของชุมชน.

---

**อัปเดตล่าสุด:** 2025-12-04  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for Java  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}