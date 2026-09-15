---
date: 2026-05-19
description: เรียนรู้วิธีสร้าง Aztec barcode ด้วย Aspose.BarCode สำหรับ .NET, ปรับอัตราส่วน,
  เข้ารหัสไบต์หรือข้อความ, และโหมดสัญลักษณ์หลัก
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: การเข้ารหัส Aztec Barcode
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: วิธีสร้าง Aztec barcode ด้วย Aspose.BarCode สำหรับ .NET
url: /th/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเข้ารหัสบาร์โค้ด Aztec

คุณพร้อมที่จะสำรวจโลกของการเข้ารหัสบาร์โค้ด Aztec และเรียนรู้วิธี **สร้างบาร์โค้ด Aztec** ด้วย Aspose.BarCode for .NET หรือยัง? ไลบรารีนี้ให้คุณควบคุมขนาด การแก้ไขข้อผิดพลาด และการแสดงข้อมูลได้อย่างเต็มที่ ทำให้เหมาะสำหรับทุกอย่างตั้งแต่การออกบัตรบนมือถือจนถึงการติดตามสินค้าคงคลัง

## คำตอบด่วน
- **ไลบรารีใดที่รองรับบาร์โค้ด Aztec?** Aspose.BarCode for .NET  
- **ฉันสามารถเปลี่ยนอัตราส่วนได้หรือไม่?** ได้, ผ่านคุณสมบัติ `AspectRatio`  
- **การเข้ารหัสระดับไบต์เป็นไปได้หรือไม่?** แน่นอน – use the `EncodeBytes` method  
- **ระดับการแก้ไขข้อผิดพลาดมีอะไรบ้าง?** Levels 0 to 4 (higher = more redundancy)  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่, a commercial license removes evaluation limits  

## Aztec barcode คืออะไร?
Aztec barcode เป็นรหัสเมทริกซ์สองมิติที่สามารถเข้ารหัสได้สูงสุด 3,000 ตัวเลขหรือ 2,300 ตัวอักษรอัลฟานูเมอริก มีรูปแบบตัวค้นหากลางที่ช่วยให้สแกนได้อย่างรวดเร็วแม้สัญลักษณ์จะพิมพ์ด้วยความละเอียดต่ำ เนื่องจากรูปแบบอยู่ตรงกลาง โค้ดจึงอ่านได้จากทุกทิศทาง ทำให้มีความน่าเชื่อถือสูงสำหรับการใช้งานบนมือถือและอุตสาหกรรม

## วิธีปรับแต่งอัตราส่วนของบาร์โค้ด Aztec?
`BarcodeGenerator` คือคลาสหลักที่ใช้สร้างบาร์โค้ดใน Aspose.BarCode ตั้งค่าคุณสมบัติ `AspectRatio` บนวัตถุ `BarcodeGenerator` ให้เป็นอัตราส่วนความกว้างต่อความสูงที่ต้องการ แล้วสร้างภาพ การปรับอัตราส่วนช่วยให้บาร์โค้ดพอดีกับพื้นที่ UI หรือเลเบลที่จำกัดโดยไม่เสียความน่าเชื่อถือของการสแกน อีกทั้งยังช่วยให้สอดคล้องกับแนวทางแบรนด์หรือข้อกำหนดของเครื่องพิมพ์เฉพาะ

### ขั้นตอนการปรับแต่งอัตราส่วน
1. **สร้างอินสแตนซ์ `BarcodeGenerator`** with `EncodeTypes.Aztec`.  
2. **กำหนดข้อมูลของคุณ** (text, bytes, or numeric string).  
3. **ตั้งค่า `AspectRatio`** – for example, `1.5` for a wider bar.  
4. **สร้างภาพ** using `Save` or `GetBarCodeImage`.  

## วิธีเข้ารหัสไบต์ดิบเป็นบาร์โค้ด Aztec?
`EncodeBytes` เป็นเมธอดที่รับอาร์เรย์ไบต์และแปลงเป็นเมทริกซ์ Aztec ส่งอาร์เรย์ไบต์ไปยังเมธอด `EncodeBytes` ของ `BarcodeGenerator` API จะทำการแปลงข้อมูลไบนารีเป็นเมทริกซ์ Aztec แบบกะทัดรัดโดยคงบิตทั้งหมดไว้ เหมาะอย่างยิ่งสำหรับฝังข้อมูลที่เข้ารหัส ตัวระบุไบต์ หรือไฟล์บีบอัดโดยตรงลงในบาร์โค้ด

### ขั้นตอนการเข้ารหัสไบต์
1. **เตรียมอาร์เรย์ไบต์** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **สร้างอินสแตนซ์ `BarcodeGenerator`** with `EncodeTypes.Aztec`.  
3. **เรียก `EncodeBytes(data)`** to load the binary content.  
4. **แสดงบาร์โค้ด** with `Save` or `GetBarCodeImage`.  

## วิธีเข้ารหัสข้อความเป็นบาร์โค้ด Aztec?
`CodeText` เป็นคุณสมบัติที่เก็บข้อมูลข้อความธรรมดาที่จะเข้ารหัส ใช้คุณสมบัติ `CodeText` ของ `BarcodeGenerator` เพื่อใส่ข้อมูลข้อความ ธรรมดา ไลบรารีจะเลือกโหมดการเข้ารหัสที่เหมาะสมโดยอัตโนมัติ (numeric, alphanumeric, or byte) และใช้ระดับการแก้ไขข้อผิดพลาดที่เหมาะสม ทำให้ง่ายต่อการฝัง URL, รหัสสินค้า หรือสตริงที่อ่านได้ใด ๆ

### ขั้นตอนการเข้ารหัสข้อความ
1. **สร้างตัวสร้าง** with `EncodeTypes.Aztec`.  
2. **ตั้งค่า `CodeText`** to the string you want to encode.  
3. **ปรับ `ErrorLevel`** optionally for higher resilience.  
4. **สร้างภาพ** using `Save` or `GetBarCodeImage`.  

## วิธีสร้างบาร์โค้ด Aztec ด้วยระดับการแก้ไขข้อผิดพลาดที่ต่างกัน?
`ErrorLevel` เป็นคุณสมบัติที่ควบคุมปริมาณข้อมูลสำรองที่เพิ่มเข้าไปในบาร์โค้ด ปรับคุณสมบัติ `ErrorLevel` (0‑4) ก่อนการเรนเดอร์ ระดับที่สูงขึ้นจะเพิ่มข้อมูลสำรอง ทำให้บาร์โค้ดอ่านได้แม้ถึง 30 % ของสัญลักษณ์จะเสียหาย สิ่งนี้สำคัญสำหรับสภาพแวดล้อมที่รุนแรง เช่น การติดฉลากอุตสาหกรรมหรือป้ายภายนอก

### ขั้นตอนการตั้งค่าการแก้ไขข้อผิดพลาด
1. **สร้างอินสแตนซ์ `BarcodeGenerator`** for Aztec.  
2. **กำหนดข้อมูลของคุณ** (text or bytes).  
3. **ตั้งค่า `ErrorLevel`** – e.g., `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **แสดงบาร์โค้ด** with your preferred output format.  

## โหมดสัญลักษณ์ Aztec มีอะไรบ้างและวิธีใช้
`SymbolMode` เป็นการตั้งค่าที่กำหนดขนาดเมทริกซ์และความจุข้อมูลของ Aztec code ที่สร้างขึ้น โหมดสัญลักษณ์ Aztec กำหนดขนาดเมทริกซ์และความจุข้อมูล ไลบรารีมีสี่โหมด: **Auto**, **FullRange**, **Compact**, และ **Rune**  

- **Auto** – ตัวสร้างเลือกขนาดที่เล็กที่สุดที่เป็นไปได้.  
- **FullRange** – อนุญาตขนาดเมทริกซ์สูงสุดสำหรับชุดข้อมูลขนาดใหญ่มาก.  
- **Compact** – สร้างสัญลักษณ์ที่เล็กกว่าและหนาแน่น เหมาะสำหรับพื้นที่จำกัด.  
- **Rune** – โหมดพิเศษสำหรับการเข้ารหัส Unicode rune.  

เลือกโหมดผ่าน `Generator.Parameters.Barcode.Aztec.SymbolMode` แต่ละโหมดจะสมดุลระหว่างขนาด ความอ่านง่าย และความจุข้อมูล ช่วยให้คุณปรับบาร์โค้ดให้เหมาะกับข้อจำกัดของแอปพลิเคชันของคุณ

## บทแนะนำการเข้ารหัสบาร์โค้ด Aztec
ด้านล่างเป็นคู่มือขั้นตอนที่เจาะลึกในแต่ละหัวข้อที่กล่าวถึงข้างต้น คลิกที่ลิงก์ใดก็ได้เพื่อสำรวจตัวอย่างโค้ดเต็ม, ความต้องการเบื้องต้น, และเคล็ดลับการปฏิบัติที่ดีที่สุด

### [ปรับแต่งอัตราส่วนบาร์โค้ด Aztec](./aztec-aspect-ratio-customization/)
เรียนรู้วิธีปรับแต่งอัตราส่วนบาร์โค้ด Aztec ด้วย Aspose.BarCode for .NET สร้างบาร์โค้ดที่เป็นเอกลักษณ์และยืดหยุ่นสำหรับแอปพลิเคชัน .NET ของคุณ

### [การเข้ารหัสไบต์ Aztec](./aztec-bytes-encoding/)
เรียนรู้วิธีทำการเข้ารหัสไบต์ Aztec ด้วย Aspose.BarCode for .NET คู่มือขั้นตอนพร้อมความต้องการเบื้องต้นและตัวอย่างโค้ด

### [การเข้ารหัสข้อความโค้ด Aztec](./aztec-code-text-encoding/)
ค้นพบพลังของการเข้ารหัสข้อความโค้ด Aztec ด้วย Aspose.BarCode for .NET เรียนรู้วิธีสร้างและอ่านโค้ด Aztec ในแอปพลิเคชัน .NET ของคุณ

### [การสร้างบาร์โค้ด Aztec พร้อมการแก้ไขข้อผิดพลาด](./aztec-error-level-example/)
เรียนรู้วิธีสร้างบาร์โค้ด Aztec พร้อมระดับการแก้ไขข้อผิดพลาดต่าง ๆ ด้วย Aspose.BarCode for .NET คู่มือครบถ้วนสำหรับการสร้างบาร์โค้ด

### [เชี่ยวชาญโหมดสัญลักษณ์ Aztec](./aztec-symbol-mode-example/)
สำรวจโหมดสัญลักษณ์ Aztec ใน Aspose.BarCode for .NET และเรียนรู้วิธีสร้างบาร์โค้ดที่หลากหลายได้อย่างง่ายดาย รับประสบการณ์จริงกับโหมด Auto, FullRange, Compact, และ Rune ในบทแนะนำที่ครอบคลุมนี้

## คำถามที่พบบ่อย

**Q: .NET เวอร์ชันใดที่รองรับการเข้ารหัส Aztec ด้วย Aspose.BarCode?**  
A: ไลบรารีทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 และรุ่นต่อไป

**Q: ฉันสามารถสร้างบาร์โค้ด Aztec ความละเอียดสูงสำหรับการพิมพ์ได้หรือไม่?**  
A: ใช่—ตั้งค่าคุณสมบัติ `Resolution` (เช่น 300 dpi) ก่อนบันทึกภาพเพื่อให้ได้คุณภาพพร้อมพิมพ์

**Q: บาร์โค้ด Aztec สามารถบรรจุข้อมูลได้มากแค่ไหน?**  
A: สูงสุด 3,000 ตัวเลขหรือ 2,300 ตัวอักษรอัลฟานูเมอริก หรือประมาณ 1,800 ไบต์ของข้อมูลดิบในโหมด Compact

**Q: สามารถอ่านบาร์โค้ด Aztec ที่ถูกหมุนได้หรือไม่?**  
A: แน่นอน—ดีโค้ดของ Aspose.BarCode ตรวจจับทิศทางโดยอัตโนมัติและแก้ไขระหว่างการอ่าน

**Q: ฉันต้องการใบอนุญาตสำหรับการพัฒนาและการทดสอบหรือไม่?**  
A: มีใบอนุญาตทดลองฟรีสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์

---

**อัปเดตล่าสุด:** 2026-05-19  
**ทดสอบด้วย:** Aspose.BarCode 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างบาร์โค้ด Aztec ด้วยอัตราส่วนที่กำหนดเองโดยใช้ Aspose.BarCode สำหรับ .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [การเข้ารหัสไบต์ Aztec ด้วยตัวสร้างบาร์โค้ด .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [วิธีสร้างบาร์โค้ด Aztec พร้อมการแก้ไขข้อผิดพลาดใน .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}