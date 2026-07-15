---
date: 2026-02-22
description: เรียนรู้วิธีสร้างความสูงบาร์โค้ดแบบกำหนดเองใน .NET ด้วย Aspose.BarCode
  ปรับความสูงของบาร์โค้ดมิติเดียวได้อย่างรวดเร็วและแม่นยำ.
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: สร้างบาร์โค้ดความสูงที่กำหนดเอง – บาร์โค้ดมิติเดียว
url: /th/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างความสูงบาร์โค้ดแบบกำหนดเอง – บาร์โค้ดแบบมิติเดียว

เมื่อคุณต้องการ **create barcode custom height** ในแอปพลิเคชัน .NET, Aspose.BarCode for .NET จะให้คุณควบคุมลักษณะการแสดงผลของบาร์โค้ดแบบมิติเดียวได้อย่างเต็มที่ ไม่ว่าคุณจะสร้างป้ายสินค้าคงคลัง, ใบเสร็จจุดขาย, หรือแท็กการจัดส่ง การปรับความสูงของบาร์โค้ดให้เหมาะสมจะช่วยให้การสแกนทำงานได้อย่างดีที่สุดและดูเป็นมืออาชีพ ในคู่มือขั้นตอนนี้ เราจะพาคุณผ่านทุกสิ่งที่ต้องรู้เพื่อปรับความสูงของบาร์โค้ดแบบมิติเดียวโดยใช้ Aspose.BarCode for .NET.

## คำตอบด่วน
- **What does “barcode custom height” mean?** เป็นขนาดแนวตั้งที่กำหนดเป็นพิกเซลของสัญลักษณ์บาร์โค้ด 1‑D.  
- **Which property controls height?** `Parameters.Barcode.BarHeight.Pixels`.  
- **Can I generate multiple heights in one run?** ได้ – เพียงเปลี่ยนค่าคุณสมบัติและเรียก `Save()` อีกครั้ง.  
- **Supported image formats?** PNG, JPEG, TIFF, BMP, GIF, และอื่น ๆ  
- **Do I need a license for height adjustment?** ไม่จำเป็น, ฟีเจอร์นี้ทำงานได้ในรุ่นทดลองฟรี; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์.  

## “create barcode custom height” คืออะไร

การสร้างบาร์โค้ดด้วยความสูงที่กำหนดเองหมายถึงการระบุค่าพิกเซลที่แน่นอนสำหรับมิติแนวตั้งของแถบบาร์โค้ด ซึ่งเป็นประโยชน์เมื่อคุณมีข้อกำหนดการจัดวางที่เคร่งครัด, ต้องการให้ตรงกับวัสดุพิมพ์ที่มีอยู่, หรืออยากปรับปรุงความอ่านของสแกนเนอร์บนสื่อที่ต่างกัน.

## ทำไมต้องใช้ Aspose.BarCode for .NET?

- **Rich API** – ปรับขนาด, สี, ข้อความ, และอื่น ๆ ด้วยการตั้งค่าคุณสมบัติที่ง่าย.  
- **Cross‑platform** – ทำงานกับ .NET Framework, .NET Core, และ .NET 5/6+.  
- **No external dependencies** – สร้างภาพโดยไม่ต้องพึ่งไลบรารีเพิ่มเติม.  
- **High‑quality rendering** – รับประกันบาร์โค้ดที่สแกนได้แม้ในมิติที่กำหนดเอง.  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, ตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมแล้ว:
- สภาพแวดล้อมการพัฒนาที่มี .NET Framework หรือ .NET Core.  
- ติดตั้ง Aspose.BarCode for .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ [here](https://releases.aspose.com/barcode/net/).  
- ตัวแก้ไขโค้ดตามที่คุณเลือก.

เมื่อเรามีข้อกำหนดครบแล้ว, มาเริ่มกระบวนการปรับความสูงของบาร์โค้ดแบบมิติเดียวกันเถอะ.

## นำเข้า Namespaces

ขั้นแรก, คุณต้องนำเข้า namespaces ที่จำเป็นไปยังโปรเจกต์ของคุณ. namespaces เหล่านี้จำเป็นสำหรับการทำงานกับ Aspose.BarCode for .NET. นี่คือตัวอย่างวิธีทำ:

```csharp
using Aspose.BarCode.Generation;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรี

เริ่มโดยกำหนดเส้นทางไดเรกทอรีที่คุณต้องการบันทึกรูปภาพบาร์โค้ดที่สร้างขึ้น. แทนที่ `"Your Directory Path"` ด้วยเส้นทางจริงบนระบบของคุณ.

```csharp
string path = "Your Directory Path";
```

## ขั้นตอนที่ 2: สร้าง Barcode Generator

ต่อไป, สร้างอินสแตนซ์ของคลาส `BarcodeGenerator`. คุณสามารถระบุประเภทบาร์โค้ด (ในกรณีนี้เราจะใช้ `Code128`) และค่าบาร์โค้ด (ในตัวอย่างนี้คือ `"ASPOSE"`).

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## ขั้นตอนที่ 3: ปรับความสูงของบาร์โค้ด

ในขั้นตอนนี้, คุณจะตั้งค่าความสูงของบาร์โค้ดโดยใช้คุณสมบัติ `BarHeight`. เป็นตัวอย่าง, เราจะปรับความสูงเป็น 40 พิกเซลและ 80 พิกเซลและบันทึกรูปบาร์โค้ดสองภาพตามลำดับ. นี้แสดงให้เห็นว่าการ **create barcode custom height** เป็นเรื่องง่ายแค่ไหน.

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| บาร์โค้ดดูบางเกินหลังจากเปลี่ยนความสูง | ความกว้างไม่ได้ปรับสัดส่วนตาม | ใช้ `Parameters.Barcode.XDimension` เพื่อปรับความกว้างของแถบหากจำเป็น. |
| ไม่สามารถบันทึกรูปภาพ | เส้นทางไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่า `path` ลงท้ายด้วยเครื่องหมายแบ็คสแลชและโฟลเดอร์มีอยู่. |
| บาร์โค้ดที่สร้างไม่สามารถสแกนได้ | ความสูงต่ำ/สูงเกินไปสำหรับสแกนเนอร์ | ทดสอบกับสแกนเนอร์ทั่วไป; รักษาความสูงระหว่าง 30‑100 px สำหรับรหัส 1‑D ส่วนใหญ่. |

## คำถามที่พบบ่อย

**Q: Aspose.BarCode for .NET รองรับประเภทบาร์โค้ดใดบ้าง?**  
A: Aspose.BarCode for .NET รองรับประเภทบาร์โค้ดหลากหลาย รวมถึง Code128, QR Code, DataMatrix, และอื่น ๆ อีกมาก คุณสามารถดูรายการเต็มได้ในเอกสาร.

**Q: ฉันสามารถปรับความกว้างของบาร์โค้ดแบบมิติเดียวได้ด้วยหรือไม่?**  
A: ใช่, คุณสามารถปรับความกว้างของบาร์โค้ดแบบมิติเดียวโดยใช้ Aspose.BarCode for .NET. กระบวนการคล้ายกับการปรับความสูง, และคุณมีการควบคุมเต็มที่ต่อมิติของบาร์โค้ด.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.BarCode for .NET หรือไม่?**  
A: มี, คุณสามารถทดลองใช้ Aspose.BarCode for .NET ได้ในรุ่นทดลองฟรี. คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/).

**Q: ฉันสามารถสร้างบาร์โค้ดในรูปแบบภาพต่าง ๆ ได้หรือไม่?**  
A: ได้, Aspose.BarCode for .NET รองรับรูปแบบภาพหลายประเภท รวมถึง PNG, JPEG, และ TIFF. คุณสามารถเลือกรูปแบบที่เหมาะกับความต้องการของแอปพลิเคชันของคุณ.

**Q: ฉันจะหาเอกสารรายละเอียดของ Aspose.BarCode for .NET ได้จากที่ไหน?**  
A: คุณสามารถอ้างอิงเอกสารได้ที่ [here](https://reference.aspose.com/barcode/net/) เพื่อรับข้อมูลเชิงลึกเกี่ยวกับการใช้ Aspose.BarCode ในโปรเจกต์ .NET ของคุณ.

## สรุป

ในบทแนะนำนี้, เราได้อธิบายกระบวนการ **creating barcode custom height** สำหรับบาร์โค้ดแบบมิติเดียวโดยใช้ Aspose.BarCode for .NET. ด้วยการปรับคุณสมบัติ `BarHeight`, คุณสามารถสร้างภาพบาร์โค้ดที่ตรงกับความต้องการการจัดวางของคุณได้อย่างสมบูรณ์ ไม่ว่าจะเป็นป้ายเล็กหรือรหัสขนาดใหญ่ที่มองเห็นได้ชัด.

หากคุณพบปัญหาใด ๆ หรือมีคำถามเพิ่มเติม, อย่าลังเลที่จะติดต่อชุมชน Aspose ผ่าน [support forum](https://forum.aspose.com/c/barcode/13) ของพวกเขา.

---

**อัปเดตล่าสุด:** 2026-02-22  
**ทดสอบด้วย:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}