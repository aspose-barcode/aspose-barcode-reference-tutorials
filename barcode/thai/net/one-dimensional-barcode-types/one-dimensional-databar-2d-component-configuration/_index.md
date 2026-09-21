---
date: 2026-02-28
description: เรียนรู้วิธีสร้างเครื่องสร้างบาร์โค้ด Aspose สำหรับบาร์โค้ด One‑Dimensional
  Databar 2D ใน .NET ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการกำหนดค่าและการปรับแต่ง.
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: สร้างเครื่องสร้างบาร์โค้ด Aspose – การกำหนดค่า Databar 2D
url: /th/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่า One-Dimensional Databar 2D Component

ในบทแนะนำนี้คุณจะ **สร้าง barcode generator Aspose** สำหรับ One‑Dimensional Databar 2D component โดยใช้ไลบรารี Aspose.BarCode .NET ไม่ว่าคุณจะสร้างป้ายสินค้า, ป้ายสินค้าคงคลัง, หรือแอปพลิเคชันใดที่ต้องการข้อมูลที่กะทัดรัดและความหนาแน่นสูง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่าโครงการจนถึงการบันทึกรูปภาพ PNG สุดท้าย

## คำตอบด่วน
- **ฟังก์ชันของ 2D component flag คืออะไร?** มันบอกให้ตัวสร้างรู้ว่าจะฝังสัญลักษณ์ 2D composite ภายในบาร์โค้ด Databar หรือไม่  
- **ฉันสามารถเปลี่ยน X‑dimension ได้หรือไม่?** ได้, คุณสมบัติ `XDimension.Pixels` ควบคุมความกว้างของโมดูล  
- **รูปแบบภาพที่ใช้ในตัวอย่างคืออะไร?** PNG, ผ่าน `BarCodeImageFormat.Png`  
- **ฉันต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **โค้ดนี้เข้ากันได้กับ .NET Core หรือไม่?** แน่นอน—Aspose.BarCode รองรับ .NET Framework และ .NET Core  

## One‑Dimensional Databar 2D Component คืออะไร?
Databar 2D component ผสานบาร์โค้ดเชิงเส้นแบบดั้งเดิมกับสัญลักษณ์ 2D composite ขนาดเล็ก ทำให้คุณสามารถเก็บข้อมูลเพิ่มเติม (เช่น URL หรือฟิลด์ข้อมูลอื่น) โดยไม่เพิ่มขนาดโดยรวมของบาร์โค้ด

## ทำไมต้องใช้ Aspose.BarCode สำหรับงานนี้?
- **Full .NET integration** – ทำงานอย่างไร้รอยต่อกับโครงการ C#  
- **Rich configuration API** – ปรับขนาด, เปิด/ปิด 2D component, และเลือกจากหลายรูปแบบการส่งออกได้  
- **No external dependencies** – ไลบรารีเป็นอิสระ ทำให้การปรับใช้ง่ายดาย  

## ข้อกำหนดเบื้องต้น

1. **Installation** – ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Aspose.BarCode for .NET แล้ว ดาวน์โหลดได้จากเว็บไซต์ [here](https://releases.aspose.com/barcode/net/)  
2. **Basic Knowledge** – ความคุ้นเคยกับ C# และการพัฒนา .NET จะช่วยให้คุณทำตามขั้นตอนได้ง่ายขึ้น  
3. **Development Environment** – Visual Studio, Rider, หรือเครื่องมือแก้ไขที่รองรับ C# ใดก็ได้  

เมื่อครอบคลุมพื้นฐานเหล่านี้แล้ว, มาเริ่มกำหนดค่า Databar 2D component กันเถอะ

## นำเข้า Namespaces

สิ่งแรกที่คุณต้องทำคือการนำเข้า namespace ของ Aspose.BarCode เพื่อให้เข้าถึงคลาสต่าง ๆ ได้

```csharp
using Aspose.BarCode;
```

## กำหนดเส้นทาง Output

ระบุที่ที่ภาพบาร์โค้ดที่สร้างขึ้นจะถูกบันทึกบนระบบไฟล์ของคุณ

```csharp
string path = "Your Directory Path";
```

เปลี่ยน `"Your Directory Path"` ให้เป็นเส้นทางโฟลเดอร์จริงบนเครื่องของคุณ

## สร้าง Barcode Generator

สร้างอินสแตนซ์ของ `BarcodeGenerator` ด้วยประเภท Databar Expanded และระบุข้อมูลที่คุณต้องการเข้ารหัส

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

คุณสามารถเปลี่ยนข้อมูลตัวอย่างเป็นตัวระบุแอปพลิเคชัน GS1 ของคุณหรือ payload อื่นได้ตามต้องการ

## วิธีสร้าง barcode generator Aspose สำหรับ One‑Dimensional Databar 2D

ตอนนี้ให้กำหนดคุณสมบัติภาพและ 2D component flag, จากนั้นบันทึกภาพ

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** ควบคุมความกว้างของแต่ละโมดูลของบาร์โค้ด  
- การตั้งค่า `Is2DCompositeComponent` เป็น **false** จะสร้าง Databar แบบเชิงเส้นล้วน  
- การตั้งค่าเป็น **true** จะเพิ่มสัญลักษณ์ 2D composite ซึ่งมีประโยชน์สำหรับการเข้ารหัสข้อมูลเพิ่มเติม  

## ปัญหาทั่วไป & เคล็ดลับ

- **Invalid Path** – ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน  
- **License Exception** – หากพบคำเตือนเรื่องลิขสิทธิ์, ให้ใช้ลิขสิทธิ์ Aspose ของคุณก่อนสร้างบาร์โค้ด  
- **Image Not Visible** – ตรวจสอบว่า `BarCodeImageFormat` ตรงกับนามสกุลไฟล์ที่คุณใช้  

## สรุป

คุณได้เรียนรู้วิธี **สร้าง barcode generator Aspose** สำหรับ One‑Dimensional Databar 2D component แล้ว, การสลับ 2D composite flag และการปรับ X‑dimension วิธีการที่ยืดหยุ่นนี้ทำให้คุณปรับบาร์โค้ดให้เข้ากับสถานการณ์ธุรกิจหลากหลาย สำหรับการปรับแต่งขั้นสูงเพิ่มเติม, สำรวจเอกสาร Aspose.BarCode เต็มรูปแบบ: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/)

หากคุณต้องการตัวอย่างเพิ่มเติมหรือเจออุปสรรค, ชุมชน Aspose เป็นสถานที่ที่ดีสำหรับการถามคำถาม

## คำถามที่พบบ่อย

### Aspose.BarCode for .NET รองรับประเภทบาร์โค้ดหลายประเภทหรือไม่?
- ใช่, Aspose.BarCode for .NET รองรับประเภทบาร์โค้ดหลากหลาย ทำให้ใช้งานได้อย่างหลากหลายสำหรับแอปพลิเคชันต่าง ๆ  

### ฉันสามารถปรับแต่งลักษณะของบาร์โค้ดที่สร้างขึ้นได้หรือไม่?
- แน่นอน! คุณสามารถปรับขนาด, สี, และคุณสมบัติดูอื่น ๆ ของบาร์โค้ดให้ตรงกับความต้องการของคุณ  

### มีตัวเลือกลิขสิทธิ์สำหรับ Aspose.BarCode for .NET หรือไม่?
- มี, Aspose มีตัวเลือกลิขสิทธิ์หลายแบบเพื่อรองรับความต้องการที่แตกต่างกัน คุณสามารถสำรวจได้บนเว็บไซต์  

### Aspose.BarCode เหมาะสำหรับผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์หรือไม่?
- Aspose.BarCode ถูกออกแบบให้ใช้งานง่าย ทำให้เหมาะกับทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์  

### ฉันจะขอรับการสนับสนุนและความช่วยเหลือสำหรับ Aspose.BarCode for .NET ได้จากที่ไหน?
- คุณสามารถขอความช่วยเหลือและเข้าร่วมชุมชนได้ที่ [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13)  

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างบาร์โค้ดในรูปแบบอื่นนอกจาก PNG ได้หรือไม่?**  
A: ได้, เมธอด `Save` รองรับ BMP, JPEG, GIF, TIFF และรูปแบบอื่น ๆ โดยระบุ `BarCodeImageFormat` ที่เหมาะสม  

**Q: ฉันจะกำหนดสีที่กำหนดเองให้กับบาร์โค้ดได้อย่างไร?**  
A: ใช้ `gen.Parameters.Barcode.ForeColor` และ `gen.Parameters.Barcode.BackColor` เพื่อกำหนดสีพื้นหน้าและพื้นหลัง  

**Q: สามารถฝังโลโก้ลงในภาพบาร์โค้ดได้หรือไม่?**  
A: Aspose.BarCode มีคุณสมบัติ `Image` ที่คุณสามารถวางโลโก้ทับหลังจากบาร์โค้ดถูกสร้างแล้ว  

**Q: .NET เวอร์ชันใดบ้างที่รองรับ?**  
A: ไลบรารีทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, และ .NET 6+  

**Q: จะเพิ่มความน่าเชื่อถือในการสแกนสำหรับการพิมพ์ความละเอียดต่ำได้อย่างไร?**  
A: เพิ่มค่าของ `XDimension` และตรวจสอบให้มีคอนทราสต์เพียงพอระหว่างบาร์โค้ดและพื้นหลัง  

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}