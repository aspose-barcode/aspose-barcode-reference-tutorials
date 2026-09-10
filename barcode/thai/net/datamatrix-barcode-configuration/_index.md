---
date: 2026-06-09
description: เรียนรู้วิธีสร้าง datamatrix barcode ด้วย Aspose.BarCode สำหรับ .NET,
  ปรับแต่ง aspect ratios, ECC modes, และ datamatrix c40 encoding เพื่อการสร้าง barcode
  ที่มีประสิทธิภาพ
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: การกำหนดค่า DataMatrix Barcode
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: สร้าง DataMatrix Barcode – คู่มือระดับมืออาชีพกับ Aspose.BarCode
url: /th/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างบาร์โค้ด DataMatrix – คู่มือระดับมืออาชีพกับ Aspose.BarCode

ยินดีต้อนรับสู่ชุดบทเรียนที่ครอบคลุมของเราสำหรับ **generate datamatrix barcode** ด้วย Aspose.BarCode สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์และปรับแต่งผลลัพธ์ของบาร์โค้ดหรือเป็นผู้ใหม่ที่ต้องการเข้าใจพื้นฐาน คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การกำหนดค่าเบื้องต้นจนถึงเทคนิคการเข้ารหัสขั้นสูง—เพื่อให้คุณสามารถสร้างบาร์โค้ดที่เชื่อถือได้และพร้อมสแกนในแอปพลิเคชัน .NET ใด ๆ

## คำตอบเร็ว
- **วัตถุประสงค์หลักคืออะไร?** เพื่อสร้างและปรับแต่งบาร์โค้ด DataMatrix อย่างโปรแกรมเมติก  
- **ใช้ไลบรารีอะไร?** Aspose.BarCode for .NET.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รุ่น .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันสามารถปรับอัตราส่วนภาพได้หรือไม่?** ได้ – ดูส่วน “How to customize DataMatrix aspect ratio”.

## generate datamatrix barcode คืออะไร?
DataMatrix barcode คือเมทริกซ์สองมิติที่ประกอบด้วยเซลล์สีดำและสีขาว สามารถเก็บข้อมูลได้สูงสุด 2 300 ตัวอักษรอัลฟานูเมอริก โดยใช้ Aspose.BarCode คุณสามารถ **generate datamatrix barcode** เป็นรูปภาพ, PDF หรือ SVG ได้โดยตรงจากโค้ด .NET ของคุณ โดยควบคุมขนาด, ระดับการแก้ไขข้อผิดพลาด, และโหมดการเข้ารหัสเพื่อให้สอดคล้องกับมาตรฐานอุตสาหกรรมใด ๆ

## ทำไมต้องใช้ Aspose.BarCode สำหรับ DataMatrix?
Aspose.BarCode แสดงสัญลักษณ์ DataMatrix ที่ความละเอียดสูงสุดถึง **600 dpi** โดยไม่มีการพิกเซลลิ่ง ทำให้การสแกนคมชัดบนเครื่องพิมพ์ความละเอียดสูง รองรับ **ทั้งหมด 50+ โหมด ECC และ macro** — รวมถึง ECC 000‑140, ECC 200, และ Macro 05/06 — เพื่อให้คุณเลือกระดับการแก้ไขข้อผิดพลาดที่เหมาะสมกับขนาดข้อมูลของคุณ API มีตัวเลือกการเข้ารหัส **ASCII, C40, Text, X12, และ Bytes** ช่วยให้คุณบรรจุข้อมูลได้อย่างมีประสิทธิภาพ การผสานรวมต้องใช้เพียงแพ็กเกจ NuGet เดียวและไม่มีไลบรารีเนทีฟภายนอก

## วิธีปรับอัตราส่วนภาพ DataMatrix
คุณสมบัติ `AspectRatio` ของ `BarCodeGenerator` ควบคุมอัตราส่วนความกว้างต่อความสูงของสัญลักษณ์ DataMatrix ที่สร้าง `BarCodeGenerator` เป็นคลาสหลักใน Aspose.BarCode ที่ใช้สร้างภาพบาร์โค้ด  

**คำตอบโดยตรง:** ตั้งค่า `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (หรือค่าระหว่าง 0.5 ถึง 2.0) ก่อนเรียก `GenerateBarCodeImage()` ไลบรารีจะคำนวณขนาดโมดูลใหม่โดยอัตโนมัติเพื่อรักษาความน่าเชื่อถือของการสแกนพร้อมรักษาอัตราส่วนที่กำหนด

### ขั้นตอนทีละขั้นตอน
1. **Instantiate** `BarCodeGenerator` ด้วย `EncodeTypes.DataMatrix`.  
2. **Adjust** `AspectRatio` ให้เป็นค่าที่คุณต้องการ.  
3. **Generate** ภาพและตรวจสอบด้วยสแกนเนอร์หรือเครื่องอ่านในตัวของ Aspose.

## วิธีสร้าง DataMatrix ECC 000‑140 barcode
ECC 000‑140 เหมาะสำหรับสตริงข้อมูลสั้นที่ต้องการสัญลักษณ์กะทัดรัด ให้การแก้ไขข้อผิดพลาดสูงสุด 140 codewords `DataMatrixEccMode.Ecc000140` เลือกโหมดการแก้ไขข้อผิดพลาด ECC 000‑140 สำหรับ DataMatrix  

**คำตอบโดยตรง:** ใช้ `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` ก่อนการเรนเดอร์ นี้จะสลับตัวเข้ารหัสไปยังอัลกอริทึม ECC 000‑140 ทำให้ได้เมทริกซ์ที่เล็กที่สุดสำหรับข้อมูลที่กำหนดพร้อมยังคงการแก้ไขข้อผิดพลาดที่แข็งแรง

### เคล็ดลับปฏิบัติ
เมื่อเข้ารหัสข้อมูลตัวเลขที่มีความยาวน้อยกว่า 20 ตัวอักษร ECC 000‑140 มักให้เมทริกซ์ขนาด 10 × 10 ซึ่งช่วยประหยัดพื้นที่บนฉลาก

## วิธีสร้าง DataMatrix ECC 200 barcode
ECC 200 เป็นโหมด DataMatrix ที่ได้รับการยอมรับอย่างกว้างขวางที่สุด รองรับข้อมูลอัลฟานูเมอริกได้สูงสุด 2 335 ตัวอักษรและให้การแก้ไขข้อผิดพลาดที่เหนือกว่า `DataMatrixEccMode.Ecc200` เลือกโหมดการแก้ไขข้อผิดพลาด ECC 200 สำหรับ DataMatrix  

**คำตอบโดยตรง:** ตั้งค่า `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` แล้วใส่ข้อมูลของคุณผ่าน `CodeText` ไลบรารีจะเลือกขนาดเมทริกซ์ที่เหมาะสมโดยอัตโนมัติ

### เมื่อควรเลือก ECC 200
ใช้ ECC 200 สำหรับสตริงที่ยาวกว่า, ข้อมูลแบบผสม, หรือเมื่อคุณต้องการความทนทานสูงสุดต่อความเสียหาย — สามารถกู้คืนได้สูงสุด **30 %** ของสัญลักษณ์

## วิธีเชี่ยวชาญการเข้ารหัส DataMatrix ใน ASCII
โหมด ASCII เข้ารหัสอักขระโดยใช้หนึ่งไบต์ต่ออักขระ ทำให้เป็นโหมดที่ใช้พื้นที่น้อยที่สุดสำหรับข้อความธรรมดา `DataMatrixEncodeMode.Ascii` บอกให้ตัวสร้างใช้การเข้ารหัส ASCII สำหรับสัญลักษณ์ DataMatrix  

**คำตอบโดยตรง:** กำหนด `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` แล้วตั้งค่า `CodeText` เป็นสตริง ASCII ของคุณ ตัวเอนจินจะบรรจุข้อมูลโดยไม่มีค่าโอเวอร์เฮด ทำให้ได้เมทริกซ์ที่เล็กที่สุดสำหรับเนื้อหา ASCII เท่านั้น

### ตัวอย่างสถานการณ์
SKU ของคลังสินค้าที่ประกอบด้วยตัวอักษรพิมพ์ใหญ่และตัวเลข (เช่น “AB1234”) เหมาะอย่างยิ่งกับโหมด ASCII มักให้เมทริกซ์ขนาด 12 × 12

## วิธีสร้าง DataMatrix Mode (Auto)
โหมด Auto ให้ Aspose.BarCode วิเคราะห์อินพุตและเลือกโหมดการเข้ารหัสที่มีประสิทธิภาพที่สุดโดยอัตโนมัติ (ASCII, C40, Text, X12, หรือ Bytes) `DataMatrixEncodeMode.Auto` เปิดใช้งานคุณลักษณะการเลือกอัตโนมัตินี้  

**คำตอบโดยตรง:** ตั้งค่า `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto` ไลบรารีจะประเมิน payload, เลือกโหมดที่เหมาะสมที่สุด, และเรนเดอร์บาร์โค้ดในขั้นตอนเดียว

### ประโยชน์
โหมด Auto ลดความพยายามในการพัฒนาและรับประกันสัญลักษณ์ที่เล็กที่สุดสำหรับข้อมูลแบบผสม‑ประเภท เพิ่มความเร็วในการสแกน

## วิธีใช้ DataMatrix encoding mode (Bytes)
โหมด Bytes ถูกออกแบบมาสำหรับข้อมูลไบนารี เช่น payload ที่เข้ารหัสหรือไฟล์ที่บีบอัด `DataMatrixEncodeMode.Bytes` บอกให้ตัวสร้างถือแต่ละไบต์เป็นข้อมูลดิบ  

**คำตอบโดยตรง:** ใช้ `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` แล้วใส่สตริง Base64‑encoded เป็น `CodeText` ตัวเข้ารหัสจะถือแต่ละไบต์เป็นข้อมูลดิบโดยตรง รักษาการแสดงผลไบต์ที่แม่นยำ

### กรณีใช้งาน
ฝัง GUID 128‑บิตหรือโทเค็นที่เข้ารหัสขนาดเล็กโดยตรงลงในสัญลักษณ์ DataMatrix

## วิธีเชี่ยวชาญ DataMatrix encoding mode (C40)
โหมด C40 บีบอัดข้อมูลอัลฟานูเมอริกพิมพ์ใหญ่ ทำให้ขนาดลดลงได้สูงสุด **40 %** เมื่อเทียบกับ ASCII `DataMatrixEncodeMode.C40` เปิดใช้งานอัลกอริทึมบีบอัดนี้  

**คำตอบโดยตรง:** ตั้งค่า `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` แล้วใส่สตริงพิมพ์ใหญ่ (เช่น “HELLO WORLD”) ตัวเอนจินจะบรรจุสามอักขระเป็นสอง codewords ทำให้เมทริกซ์สุดท้ายเล็กลง

### เคล็ดลับระดับมืออาชีพ
C40 ทำงานได้ดีที่สุดเมื่อ payload ประกอบด้วยตัวอักษรพิมพ์ใหญ่, ตัวเลข, และช่องว่างเป็นหลัก สำหรับข้อมูลแบบผสม‑เคส ให้พิจารณาใช้โหมด Auto

## วิธีกำหนดค่า DataMatrix code text
คุณสมบัติ `CodeText` กำหนดข้อมูลที่เก็บในบาร์โค้ดอย่างแม่นยำ สามารถเป็นข้อความธรรมดา, สตริงตัวเลข, หรือแม้แต่ payload XML `CodeText` เป็นคุณสมบัติสตริงหลักของ `BarCodeGenerator` ที่เก็บ payload ของบาร์โค้ด  

**คำตอบโดยตรง:** กำหนด `generator.Parameters.Barcode.CodeText = "YourDataHere"` ก่อนการเรนเดอร์ คุณสมบัตินี้รับสตริง UTF‑8 ใด ๆ ที่มีความยาวสูงสุดตามขีดจำกัดของโหมด ECC ที่เลือก

### เคล็ดลับขั้นสูง
ผสาน `CodeText` กับ `ExtendedDataMatrix` เพื่อฝังเมตาดาต้าเพิ่มเติมโดยไม่เพิ่มขนาดเมทริกซ์ที่มองเห็นได้

## วิธีเชี่ยวชาญการกำหนดค่า DataMatrix macro
โหมด Macro (Macro 05 และ Macro 06) ให้คุณฝังสัญลักษณ์ DataMatrix รองลงในสัญลักษณ์หลัก ซึ่งมีประโยชน์สำหรับการเชื่อมโยงกับแหล่งข้อมูลภายนอก `DataMatrixMacroMode.Macro05` และ `DataMatrixMacroMode.Macro06` เปิดใช้งานคุณลักษณะ macro เหล่านี้  

**คำตอบโดยตรง:** เปิดใช้งาน macro mode ด้วย `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (หรือ `Macro06`) แล้วตั้งค่า `MacroPdf417` สำหรับ payload รอง ไลบรารีจะสร้างสัญลักษณ์คอมโพสิตที่สแกนเนอร์สามารถตีความเป็นสองโค้ดที่เชื่อมโยงกัน

### ตัวอย่างในโลกจริง
ฝัง URL ในส่วน macro ขณะยังคงเก็บตัวระบุสินค้าในเมทริกซ์หลัก ทำให้การเชื่อมต่อเว็บ‑to‑barcode เป็นไปอย่างราบรื่น

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## การกำหนดค่า DataMatrix Barcode Tutorials
### [ปรับแต่งอัตราส่วนภาพ DataMatrix](./datamatrix-aspect-ratio-customization/)
เรียนรู้วิธีปรับอัตราส่วนภาพของบาร์โค้ด DataMatrix ด้วย Aspose.BarCode สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการสร้างบาร์โค้ด
### [สร้าง DataMatrix ECC 000-140 Barcodes](./datamatrix-ecc-000-140-configuration/)
สร้างบาร์โค้ด DataMatrix ECC 000-140 อย่างง่ายด้วย Aspose.BarCode สำหรับ .NET เพิ่มประสิทธิภาพในการจัดการสินค้าคงคลังและอื่น ๆ
### [สร้าง DataMatrix ECC 200 Barcodes](./datamatrix-ecc-200-configuration/)
เรียนรู้วิธีสร้างบาร์โค้ด DataMatrix ECC 200 ใน .NET ด้วย Aspose.BarCode ปรับกระบวนการทำงานด้วยการสร้างบาร์โค้ดที่มีประสิทธิภาพ
### [เชี่ยวชาญการเข้ารหัส DataMatrix ใน ASCII](./datamatrix-encoding-mode-ascii/)
เรียนรู้การสร้างบาร์โค้ด DataMatrix ในโหมด ASCII ด้วย Aspose.BarCode สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา
### [สร้าง DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
เรียนรู้วิธีสร้าง DataMatrix Mode (Auto) ด้วย Aspose.BarCode สำหรับ .NET คู่มือขั้นตอนเต็มที่ครอบคลุมตั้งแต่ข้อกำหนดเบื้องต้นจนถึงการอ่านบาร์โค้ด
### [DataMatrix Encoding Mode (Bytes)](./datamatrix-encoding-mode-bytes/)
เรียนรู้วิธีเข้ารหัสข้อมูลในรูปแบบ DataMatrix ด้วยโหมด Bytes ด้วย Aspose.BarCode สำหรับ .NET ปฏิบัติตามคำแนะนำขั้นตอนเพื่อการสร้างและการจดจำบาร์โค้ด
### [เชี่ยวชาญ DataMatrix Encoding Mode (C40)](./datamatrix-encoding-mode-c40/)
เรียนรู้ DataMatrix Encoding Mode (C40) ด้วย Aspose.BarCode สำหรับ .NET สร้างบาร์โค้ดที่กำหนดเองอย่างมีประสิทธิภาพ สำรวจคู่มือขั้นตอน
### [กำหนดค่า DataMatrix Code Text](./datamatrix-extended-code-text-configuration/)
เรียนรู้การกำหนดค่า DataMatrix extended code text ด้วย Aspose.BarCode สำหรับ .NET สร้าง, จดจำ, และผสานบาร์โค้ดในแอปพลิเคชัน .NET ของคุณ
### [เชี่ยวชาญการกำหนดค่า DataMatrix Macro](./datamatrix-macro-configuration/)
เรียนรู้วิธีกำหนดค่า DataMatrix Macro barcodes ด้วย Aspose.BarCode สำหรับ .NET สร้าง, ปรับแต่ง, และจดจำบาร์โค้ด DataMatrix ในแอปพลิเคชัน .NET ของคุณ

## คำถามที่พบบ่อย

**Q: ฉันจะตัดสินใจเลือกโหมด ECC ใด?**  
A: เลือก ECC 000‑140 สำหรับชุดข้อมูลขนาดเล็กที่ต้องการการแก้ไขข้อผิดพลาดจำกัด, หรือ ECC 200 สำหรับข้อมูลขนาดใหญ่และความน่าเชื่อถือสูงกว่า โหมด Macro เพิ่มชั้นข้อมูลเพิ่มเติมสำหรับการเชื่อมโยง

**Q: ฉันสามารถฝังข้อความกำหนดเองในบาร์โค้ด DataMatrix ได้หรือไม่?**  
A: ได้, ตั้งค่าคุณสมบัติ `CodeText` เป็นสตริงที่คุณต้องการ, แล้วเลือกโหมดการเข้ารหัสที่เหมาะสม (ASCII, C40, ฯลฯ) เพื่อควบคุมขนาด

**Q: มีวิธีให้ระบบเลือกโหมดการเข้ารหัสที่ดีที่สุดโดยอัตโนมัติหรือไม่?**  
A: ตั้งค่า `EncodeMode` เป็น `Auto`; Aspose.BarCode จะประเมิน payload และเลือกโหมดที่ใช้พื้นที่น้อยที่สุดโดยอัตโนมัติ

**Q: พิจารณาด้านประสิทธิภาพสำหรับการสร้างบาร์โค้ดจำนวนมากมีอะไรบ้าง?**  
A: ใช้ instance ของ `BarCodeGenerator` เดียว, เปิดใช้งาน multi‑threading, และสร้างภาพ PNG เพื่อคุณภาพ lossless หรือ JPEG เพื่อขนาดไฟล์ที่เล็กลง การประมวลผล 10 000 สัญลักษณ์มักเสร็จในเวลาน้อยกว่า 30 วินาทีบนเซิร์ฟเวอร์ 8‑core มาตรฐาน

**Q: Aspose.BarCode รองรับ .NET Core และ .NET 5/6 หรือไม่?**  
A: แน่นอน – ไลบรารีเข้ากันได้เต็มที่กับ .NET Framework, .NET Core, และเวอร์ชัน .NET ล่าสุด พร้อมชุดฟีเจอร์เดียวกันบนทุกแพลตฟอร์ม

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้าง DataMatrix Barcodes (ECC 200) ด้วย Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [เชี่ยวชาญการเข้ารหัส DataMatrix ใน ASCII ด้วย Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [สร้าง Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}