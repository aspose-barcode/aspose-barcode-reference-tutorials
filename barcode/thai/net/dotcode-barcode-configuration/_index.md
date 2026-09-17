---
date: 2026-06-14
description: เรียนรู้วิธีสร้างบาร์โค้ด DotCode ด้วย Aspose.BarCode สำหรับ .NET, ครอบคลุม
  aspect ratio, encoding modes, extended text, และ reader initialization.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: วิธีสร้างบาร์โค้ด DotCode – คู่มือการกำหนดค่า
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: วิธีสร้างบาร์โค้ด DotCode – คู่มือการกำหนดค่า
url: /th/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างบาร์โค้ด DotCode – คู่มือการกำหนดค่า

## บทนำ
**How to generate DotCode** บาร์โค้ดอย่างรวดเร็วและเชื่อถือได้เป็นความต้องการทั่วไปสำหรับนักพัฒนาที่สร้างระบบจัดการสินค้าคงคลัง, การติดตาม, หรือโซลูชันการสแกนบนมือถือ ในบทเรียนนี้เราจะพาคุณผ่านทุกตัวเลือกการกำหนดค่าที่ Aspose.BarCode สำหรับ .NET มีให้สำหรับสัญลักษณ์ DotCode — การปรับอัตราส่วนภาพ, โหมดการเข้ารหัส Auto และ Bytes, การจัดการข้อความโค้ดขยาย, การเริ่มต้นตัวอ่าน, การจัดวางแถว/คอลัมน์, และโหมด structured‑append. เมื่อจบคุณจะสามารถสร้างภาพ DotCode ที่มีขนาดพอดี, ความหนาแน่นสูง ที่ตรงตามมาตรฐานอุตสาหกรรมและผสานรวมได้อย่างราบรื่นกับแอปพลิเคชัน .NET ใด ๆ

## คำตอบอย่างรวดเร็ว
- **คลาสหลักที่ใช้สร้างบาร์โค้ด DotCode คืออะไร?** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **คุณสมบัติใดที่ควบคุมอัตราส่วนภาพ?** `BarCodeImageAspectRatio`.
- **ฉันสามารถสลับระหว่างการเข้ารหัส Auto และ Bytes ได้หรือไม่?** Yes, via `EncodeMode` property.
- **ต้องใช้ตัวอ่านแยกสำหรับ DotCode หรือไม่?** No, the same `BarcodeGenerator` can decode when `ReadBarcode` is called.
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## วิธีสร้างบาร์โค้ด DotCode ด้วย Aspose.BarCode สำหรับ .NET?
`BarcodeGenerator` เป็นคลาสหลักใน Aspose.BarCode สำหรับสร้างภาพบาร์โค้ด โหลด `BarcodeGenerator` ด้วย `EncodeTypes.DotCode`, ตั้งค่าคุณสมบัติที่ต้องการ (อัตราส่วนภาพ, โหมดการเข้ารหัส, แถว/คอลัมน์, ฯลฯ) และเรียก `GenerateBarCodeImage()` — ไลบรารีจะคืนค่า `System.Drawing.Image` ที่พร้อมใช้งานหรืออาร์เรย์ไบต์ กระบวนการขั้นตอนเดียวนี้จัดการรายละเอียดการเข้ารหัสระดับต่ำทั้งหมด, รองรับรูปแบบผลลัพธ์เช่น PNG, JPEG, และ SVG, และสามารถเรนเดอร์ภาพได้ถึง 10 000 × 10 000 px โดยไม่ใช้หน่วยความจำมากเกินไป.

## บาร์โค้ด DotCode คืออะไร?
บาร์โค้ด DotCode เป็นสัญลักษณ์ 2D รูปสี่เหลี่ยมจัตุรัสที่มีความหนาแน่นสูง สามารถเก็บข้อมูลได้สูงสุด 1 200 ตัวเลขหรือ 800 ตัวอักษรอัลฟานูเมอริกในเมทริกซ์จุดที่กะทัดรัด ถูกออกแบบมาสำหรับการติดฉลากบรรจุภัณฑ์ขนาดเล็กและการสแกนบนมือถือ ให้ความเร็วในการอ่านสูงแม้บนกล้องความละเอียดต่ำ.

## ทำไมต้องใช้ DotCode กับ Aspose.BarCode?
Aspose.BarCode รองรับ **20+** ประเภทบาร์โค้ด 2D รวมถึง DotCode และสามารถประมวลผลไฟล์ที่ใหญ่กว่า **200 MB** โดยไม่ต้องโหลดภาพทั้งหมดเข้าสู่หน่วยความจำ ไลบรารีรับประกันความแม่นยำในการสแกน **99.9 %** บนกล้องสมาร์ทโฟนมาตรฐานและมีระดับการแก้ไขข้อผิดพลาดในตัวเพื่อลดความล้มเหลวในการอ่าน.

## ข้อกำหนดเบื้องต้น
- .NET Framework 4.5 หรือสูงกว่า, หรือ .NET Core 3.1 / .NET 5+.
- Aspose.BarCode for .NET (แนะนำให้ใช้เวอร์ชันล่าสุด).
- คีย์ไลเซนส์ชั่วคราวหรือเต็ม (รุ่นทดลองใช้ได้สำหรับการพัฒนา).

## การปรับอัตราส่วนภาพ DotCode
**aspect‑ratio** กำหนดว่ามาตราส่วนของเมทริกซ์ DotCode จะยืดหรือบีบแค่ไหน ใช้คุณสมบัติ `BarCodeImageAspectRatio` เพื่อตั้งค่าระหว่าง **0.5** (สูงกว่า) ถึง **2.0** (กว้างกว่า) อัตราส่วน **1.0** จะให้สัญลักษณ์สี่เหลี่ยมจัตุรัสที่สมบูรณ์ ซึ่งเป็นค่าเริ่มต้นและทำงานได้ดีที่สุดกับสแกนเนอร์ส่วนใหญ่.

> **เคล็ดลับ:** เมื่อพิมพ์บนป้ายแคบ, อัตราส่วน **0.75** มักช่วยปรับปรุงความอ่านได้โดยไม่ลดความจุของข้อมูล.

## โหมดการเข้ารหัส DotCode (Auto)
ในโหมด **Auto** ไลบรารีจะวิเคราะห์สตริงอินพุตและเลือกการเข้ารหัสที่มีประสิทธิภาพที่สุดโดยอัตโนมัติ (numeric, alphanumeric, หรือ byte) ซึ่งช่วยเพิ่มความหนาแน่นของข้อมูลและลดขนาดสัญลักษณ์โดยรวม.

> **คำตอบโดยตรง:** ตั้งค่า `EncodeMode = EncodeModes.Auto` บน `BarcodeGenerator` เพื่อให้ Aspose.BarCode ตัดสินใจเลือกการเข้ารหัสที่เหมาะสมที่สุดสำหรับข้อมูลของคุณ, ทำให้ได้ DotCode ที่เล็กที่สุดเท่าที่จะเป็นไปได้โดยยังคงรักษาตัวอักษรทั้งหมดไว้.

## โหมดการเข้ารหัส DotCode (Bytes)
เมื่อคุณต้องการเก็บข้อมูลไบนารีหรืออาร์เรย์ไบต์ที่เข้ารหัสล่วงหน้า, เลือกโหมด **Bytes** ซึ่งบังคับให้ตัวสร้างพิจารณาข้อมูลเป็นไบต์ดิบ, ข้ามการตรวจจับชุดอักขระอัตโนมัติ.

> **คำตอบโดยตรง:** ใช้ `EncodeMode = EncodeModes.Bytes` และให้ payload แบบ `byte[]` เพื่อฝังข้อมูลไบนารีเช่นตัวระบุที่เข้ารหัสหรือไฟล์บีบอัดโดยตรงลงในสัญลักษณ์ DotCode.

## การกำหนดค่าข้อความโค้ดขยายของ DotCode
ข้อความโค้ดขยายช่วยให้คุณแนบข้อมูลเสริมที่ไม่ได้เป็นส่วนหนึ่งของ payload หลัก แต่สามารถแสดงพร้อมบาร์โค้ดในรายงานหรือ GUI ตั้งค่าคุณสมบัติ `ExtendedCodeText` เป็นสตริงใดก็ได้ (สูงสุด **256** ตัวอักษร) และเลือกฟอนต์ผ่าน `ExtendedCodeTextFont`.

> **เคล็ดลับระดับมืออาชีพ:** ผสานข้อความขยายกับขนาดฟอนต์ที่เล็กลง (เช่น 8 pt) เพื่อให้พื้นที่ภาพต่ำลงในขณะที่ยังคงให้บริบทที่มนุษย์อ่านได้.

## การเริ่มต้นตัวอ่าน DotCode
`BarCodeReader` เป็นคลาสที่ใช้ถอดรหัสบาร์โค้ดจากภาพหรือสตรีม การอ่านภาพ DotCode มีความง่ายเท่ากับการสร้าง ตัวอย่างการใช้งาน: สร้างอินสแตนซ์ `BarCodeReader` ด้วยสตรีมภาพและระบุ `EncodeTypes.DotCode` แล้วเรียก `ReadBarCode()` เพื่อดึงสตริงที่ถอดรหัสได้.

> **คำตอบโดยตรง:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – บล็อกเดียวนี้ทำการถอดรหัสสัญลักษณ์โดยไม่ต้องพึ่งพาไลบรารีภายนอก.

## การกำหนดค่าแถวและคอลัมน์ของ DotCode
DotCode อนุญาตให้ควบคุมจำนวนแถวและคอลัมน์โดยตรง ซึ่งส่งผลต่อขนาดสัญลักษณ์และความสามารถในการแก้ไขข้อผิดพลาด ใช้คุณสมบัติ `Rows` และ `Columns` เพื่อตั้งค่าระหว่าง **10** ถึง **144** เมทริกซ์ที่ใหญ่ขึ้นจะเพิ่มความจุของข้อมูลและความทนทาน.

> **แนวปฏิบัติที่ดีที่สุด:** สำหรับแท็กสินค้าที่ต้องทนต่อการจัดการที่รุนแรง, ตั้งค่า **Rows = 64** และ **Columns = 64** เพื่อเพิ่มความซ้ำซ้อนเพิ่มเติม.

## การกำหนดค่าโหมด Structured Append ของ DotCode
Structured Append ช่วยแบ่ง payload ขนาดใหญ่เป็นหลายสัญลักษณ์ DotCode ที่สามารถอ่านต่อเนื่องกันได้ ตั้งค่า `StructuredAppend = true` และกำหนด `StructuredAppendCount` กับ `StructuredAppendIndex` สำหรับแต่ละส่วน.

> **คำตอบโดยตรง:** เปิดใช้งาน `StructuredAppend` บนแต่ละ `BarcodeGenerator`, กำหนดดัชนีที่ไม่ซ้ำกัน (เริ่มจาก 1) และตั้งค่าจำนวนทั้งหมด; ไลบรารีจะฝังข้อมูลลิงก์ที่จำเป็นโดยอัตโนมัติ.

## ปัญหาและวิธีแก้ไขทั่วไป
- **บาร์โค้ดไม่อ่านได้บนหน้าจอความละเอียดต่ำ:** เพิ่มคุณสมบัติ `Resolution` อย่างน้อย **300 dpi** ก่อนการสร้าง.
- **คำเตือนการตัดข้อมูล:** ตรวจสอบว่าความยาวอินพุตไม่เกินขีดจำกัดสูงสุดสำหรับแถว/คอลัมน์ที่เลือก; ปรับขนาดหรือสลับไปใช้โหมด Bytes หากจำเป็น.
- **ไลเซนส์หมดอายุระหว่างการพัฒนา:** ใช้ไลเซนส์ชั่วคราวที่ได้จากพอร์ทัล Aspose; แทนที่ด้วยคีย์ถาวรก่อนการเปิดใช้งานในสภาพแวดล้อมการผลิต.

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างบาร์โค้ด DotCode ในรูปแบบ SVG ได้หรือไม่?**  
A: ใช่, ตั้งค่า `BarCodeImageFormat = BarCodeImageFormat.Svg` บนตัวสร้างเพื่อรับผลลัพธ์เวกเตอร์ที่ปรับขนาดได้.

**Q: สามารถฝังโลโก้ภายในสัญลักษณ์ DotCode ได้หรือไม่?**  
A: Aspose.BarCode ไม่รองรับการฝังโลโก้โดยตรงสำหรับ DotCode, แต่คุณสามารถวางภาพทับหลังการสร้างโดยใช้ไลบรารีกราฟิกมาตรฐาน.

**Q: การแก้ไขข้อผิดพลาดทำงานอย่างไรสำหรับ DotCode?**  
A: สัญลักษณ์นี้มีการแก้ไขข้อผิดพลาด Reed‑Solomon ในตัว; การเพิ่มแถว/คอลัมน์จะเพิ่มระดับการแก้ไขโดยอัตโนมัติ.

**Q: จำเป็นต้องใช้ไลบรารีแยกเพื่ออ่าน DotCode จาก PDF หรือไม่?**  
A: ไม่, `BarCodeReader` เดียวกันสามารถดึง DotCode จากหน้า PDF, ภาพ, หรือสตรีมได้โดยไม่ต้องใช้เครื่องมือเพิ่มเติม.

**Q: ขนาดข้อมูลสูงสุดสำหรับสัญลักษณ์ DotCode เดียวคือเท่าไหร่?**  
A: สูงสุด **1 200** ตัวเลขหรือ **800** ตัวอักษรอัลฟานูเมอริก, ขึ้นอยู่กับการกำหนดค่าแถว/คอลัมน์ที่เลือก.

**อัปเดตล่าสุด:** 2026-06-14  
**ทดสอบกับ:** Aspose.BarCode 24.11 for .NET  
**ผู้เขียน:** Aspose  

## บทเรียนการกำหนดค่าบาร์โค้ด DotCode
### [ปรับอัตราส่วนภาพ DotCode](./dotcode-aspect-ratio-customization/)
เรียนรู้การปรับอัตราส่วนภาพบาร์โค้ด DotCode ด้วย Aspose.BarCode สำหรับ .NET. สร้างบาร์โค้ดที่ปรับแต่งตามความต้องการของแอปพลิเคชันของคุณได้อย่างง่ายดาย.
### [โหมดการเข้ารหัส DotCode (Auto)](./dotcode-encoding-mode-auto/)
สำรวจโหมดการเข้ารหัส DotCode (Auto) ใน Aspose.BarCode สำหรับ .NET, เครื่องมือที่ทรงพลังสำหรับการสร้างบาร์โค้ด. เรียนรู้วิธีสร้างบาร์โค้ด DotCode ทีละขั้นตอน. ตรวจสอบเอกสาร, ดาวน์โหลดไลบรารี, และรับไลเซนส์ชั่วคราว.
### [โหมดการเข้ารหัส DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
เรียนรู้การเข้ารหัส DotCode ด้วย Aspose.BarCode สำหรับ .NET: คู่มือขั้นตอนต่อขั้นตอนเพื่อสร้างบาร์โค้ด.
### [การกำหนดค่าข้อความโค้ดขยายของ DotCode](./dotcode-extended-code-text-configuration/)
สร้างการกำหนดค่าข้อความโค้ดขยายของ DotCode อย่างง่ายด้วย Aspose.BarCode สำหรับ .NET. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการสร้างบาร์โค้ดที่มีประสิทธิภาพ.
### [การเริ่มต้นตัวอ่าน DotCode](./dotcode-reader-initialization/)
เรียนรู้วิธีเริ่มต้นตัวอ่าน DotCode ด้วย Aspose.BarCode สำหรับ .NET. สร้างบาร์โค้ด DotCode ได้อย่างง่ายดายสำหรับการใช้งานหลากหลาย.
### [การกำหนดค่าแถวและคอลัมน์ของ DotCode](./dotcode-rows-columns-configuration/)
เรียนรู้การกำหนดค่าแถวและคอลัมน์ของ DotCode ด้วย Aspose.BarCode สำหรับ .NET. สร้างบาร์โค้ด 2D ที่แม่นยำและปรับแต่งได้อย่างไม่มีความยากลำบาก.
### [การกำหนดค่าโหมด Structured Append ของ DotCode](./dotcode-structured-append-mode-configuration/)
เรียนรู้การกำหนดค่าโหมด Structured Append ของ DotCode ด้วย Aspose.BarCode สำหรับ .NET และสร้างบาร์โค้ดที่มีประสิทธิภาพ.

## บทเรียนที่เกี่ยวข้อง

- [ปรับอัตราส่วนภาพ DotCode ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [การกำหนดค่าข้อความโค้ดขยายของ DotCode ด้วย Aspose.BarCode สำหรับ .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [โหมดการเข้ารหัส DotCode (Auto) ใน Aspose.BarCode สำหรับ .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}