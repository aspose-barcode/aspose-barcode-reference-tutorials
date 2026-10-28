---
category: general
date: 2026-10-28
description: เรียนรู้วิธีสร้าง extended codetext ใน Python ด้วย ExtCodetextBuilder
  รวมถึงข้อมูลแบบ plain และข้อมูลที่เข้ารหัสด้วย ECI, โค้ดแบบทีละขั้นตอน และเคล็ดลับการปฏิบัติที่ดีที่สุด.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: th
lastmod: 2026-10-28
og_description: สร้างโค้ดเท็กซ์ขยายใน Python ด้วย ExtCodetextBuilder. บทเรียนนี้แสดงการจัดการข้อมูลแบบธรรมดาและแบบเข้ารหัส
  ECI, โค้ดที่สามารถรันได้เต็มรูปแบบ, และข้อผิดพลาดทั่วไป.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: สร้างข้อความโค้ดขยายใน Python – คู่มือฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: วิธีสร้าง extended codetext ใน Python ด้วย ExtCodetextBuilder
url: /th/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง extended codetext ใน Python ด้วย ExtCodetextBuilder

หากคุณต้องการ **สร้าง extended codetext** สำหรับการใช้งาน barcode หรือ data‑matrix คู่มือนี้จะแสดงให้คุณเห็นอย่างละเอียดว่าต้องทำอย่างไรใน Python คุณจะได้เห็นวิธีการรวม plain text, เพิ่มส่วน ECI (Extended Channel Interpretation) สำหรับอักขระ Unicode, และดึงสตริงเดียวที่จัดรูปแบบอย่างถูกต้องพร้อมสำหรับการเข้ารหัส

บทเรียนนี้ครอบคลุมทุกอย่างตั้งแต่การติดตั้งไลบรารีที่จำเป็นจนถึงการจัดการกรณีขอบเช่นค่า ECI ที่ไม่รองรับ เมื่อจบคุณจะมีรูปแบบที่สามารถนำกลับมาใช้ใหม่ได้ซึ่งคุณสามารถใส่ลงในโปรเจกต์ใด ๆ ที่ต้องการ **สร้าง extended codetext**.

## สิ่งที่คุณจะได้เรียนรู้

* บทบาทของ `ExtCodetextBuilder` เมื่อสร้างสตริงที่ผสมการเข้ารหัส  
* วิธี **add plain codetext** และ **add ECI codetext** ในอินสแตนซ์ builder เดียว  
* วิธีตรวจสอบผลลัพธ์สุดท้ายและแก้ไขปัญหาที่พบบ่อย  
* รูปแบบต่าง ๆ สำหรับชุดอักขระอื่น ๆ (เช่น ISO‑8859‑1, Shift‑JIS)  

### ข้อกำหนดเบื้องต้น

* Python 3.8 หรือใหม่กว่า.  
* แพ็กเกจ `extcodetext` (หรือไลบรารีที่คล้ายกันที่ให้ `ExtCodetextBuilder`). ติดตั้งด้วย:

```bash
pip install extcodetext
```

* ความคุ้นเคยพื้นฐานกับ Unicode และค่า ECI – ECI 3 ตรงกับ UTF‑8, ECI 4 ตรงกับ ISO‑8859‑1, เป็นต้น.

> **Pro tip:** เก็บตารางอ้างอิงของหมายเลข ECI ไว้ใกล้มือ จะช่วยป้องกันการไม่ตรงกันโดยบังเอิญระหว่างการเข้ารหัสที่ระบุและลำดับไบต์จริง

## ทำความเข้าใจ ExtCodetextBuilder

`ExtCodetextBuilder` เป็นยูทิลิตี้ขนาดเล็กที่ต่อข้อความหลายส่วนเข้าด้วยกันพร้อมแทรกเครื่องหมาย ECI ที่จำเป็นโดยอัตโนมัติ เครื่องหมาย ECI จะบอกตัวเข้ารหัส barcode ด้านล่างว่าต้องใช้ชุดอักขระใดสำหรับไบต์ต่อไป หากไม่มีเครื่องหมายนี้ ตัวอักษรที่ไม่ใช่ ASCII จะถูกตีความผิด

Builder ทำงานในสามขั้นตอนง่าย ๆ:

1. **Create** อินสแตนซ์ของ builder.  
2. **Append** ส่วนข้อความแบบ plain หรือที่เข้ารหัสด้วย ECI.  
3. **Retrieve** สตริง extended‑codetext ที่รวมกัน.

ด้านล่างเราจะเดินผ่านแต่ละขั้นตอนพร้อมโค้ดตัวอย่าง.

## ขั้นตอน 1: สร้างอินสแตนซ์ ExtCodetextBuilder

บรรทัดแรกสร้างอ็อบเจกต์ที่จะเก็บส่วนข้อความทั้งหมด ณ จุดนี้ไม่ต้องมีการกำหนดค่าใด ๆ

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*ทำไมเรื่องนี้สำคัญ*: การสร้างอินสแตนซ์ของ builder จะจัดสรรบัฟเฟอร์ภายใน การเรียก `add_*` ต่อ ๆ ไปทั้งหมดทำงานบนบัฟเฟอร์นั้น ทำให้ลำดับที่คุณระบุได้รับการรับประกัน

## ขั้นตอน 2: เพิ่มข้อมูล plain (ไม่ได้เข้ารหัส)

ข้อมูล plain ประกอบด้วยอักขระที่อยู่ในชุดอักขระเริ่มต้น (โดยทั่วไปคือ ASCII) ใช้ `add_plain_codetext` สำหรับส่วนข้อความเหล่านี้

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*คำอธิบาย*: สตริง `"ABC123"` มีเฉพาะอักขระ ASCII จึงไม่ต้องการเครื่องหมาย ECI วิธีนี้เพียงแค่เพิ่มไบต์ดิบลงในบัฟเฟอร์ภายใน

## ขั้นตอน 3: เพิ่มข้อมูลที่ต้องมี ECI นำหน้า

เมื่อคุณต้องฝังอักขระ Unicode—เช่น Cyrillic, Japanese หรือ emoji—คุณต้องบอกตัวเข้ารหัสว่าต้องใช้ชุดอักขระใด วิธีทำคือใช้ `add_eci_codetext(eci, text)` อาร์กิวเมนต์แรกคือค่าตัวเลขของ ECI; อาร์กิวเมนต์ที่สองคือข้อความจริง

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*ทำไมต้องใช้ ECI 3*: ตามสเปค ISO/IEC 18004, ECI 3 ตรงกับ UTF‑8 การแทรกเครื่องหมายนี้ทำให้เครื่องอ่าน barcode รู้ว่าจะต้องถอดรหัสไบต์ต่อไปเป็น UTF‑8 เพื่อรักษาอักขระ Cyrillic

### การจัดการกับการเข้ารหัสอื่น ๆ

หากคุณต้องการ ISO‑8859‑1 (Western European) คุณจะใช้ `add_eci_codetext(4, "¡Hola!")`. สำหรับ Shift‑JIS (Japanese) ค่า ECI คือ 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

ควรตรวจสอบเสมอว่าห้องสมุด barcode ที่ใช้รองรับค่า ECI ที่เลือก; ECI ที่ไม่รองรับจะทำให้การเข้ารหัสล้มเหลว

## ขั้นตอน 4: ดึงสตริง extended‑codetext ที่รวมกัน

หลังจากเพิ่มส่วนข้อความทั้งหมดแล้ว เรียก `get_extended_codetext()` เพื่อรับสตริงสุดท้าย สตริงนี้จะรวมลำดับ escape ของ ECI ที่จำเป็นทั้งหมด

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**ผลลัพธ์ที่คาดหวัง** (แสดงเป็น Python `repr` เพื่อความชัดเจน):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*การแยกส่วน*:

* `ABC123` – ส่วน ASCII แบบ plain.  
* `\x1B\x1D\x03` – ลำดับ escape ของ ECI สำหรับ UTF‑8 (ESC GS 0x03).  
* `Привет` – คำ Cyrillic ที่เข้ารหัสเป็น UTF‑8

ไบต์ escape ที่แท้จริงอาจแตกต่างกันขึ้นอยู่กับการทำงานของไลบรารี แต่ลำดับเชิงตรรกะจะเป็นเสมอว่า *plain → เครื่องหมาย ECI → ข้อความ Unicode*.

## ตัวอย่างที่สามารถรันได้เต็มรูปแบบ

เมื่อรวมทุกอย่างเข้าด้วยกัน นี่คือสคริปต์ที่เป็นอิสระซึ่งคุณสามารถคัดลอก‑วางลงในไฟล์ชื่อ `create_extended_codetext.py` แล้วรันได้ทันที

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

การรันสคริปต์จะแสดงสตริงที่รวมกัน พร้อมใช้กับตัวเข้ารหัส barcode ใด ๆ ที่รับอินพุต extended‑codetext

## ข้อผิดพลาดทั่วไปและวิธีหลีกเลี่ยง

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---|---|---|
| `UnicodeEncodeError` เมื่อเรียก `add_eci_codetext` | การส่งสตริงที่มีอักขระที่ไม่สามารถแทนได้ใน ECI ที่เลือก | ตรวจสอบให้แน่ใจว่า ECI ตรงกับการเข้ารหัสจริงของสตริง (เช่น ใช้ ECI 3 สำหรับข้อความ UTF‑8 ใด ๆ) |
| ไม่มีเครื่องหมาย ECI ในผลลัพธ์สุดท้าย | โดยบังเอิญใช้ `add_plain_codetext` กับข้อมูลที่ไม่ใช่ ASCII | เปลี่ยนเป็น `add_eci_codetext` สำหรับอักขระใด ๆ ที่อยู่นอกช่วง ASCII |
| สแกนเนอร์บาร์โค้ดแสดงอักขระผิดรูป | สแกนเนอร์ไม่รองรับค่า ECI ที่เลือก | เลือก ECI ที่รองรับโดยทั่วไป (UTF‑8 รองรับอย่างกว้างขวาง) หรือใช้ ISO‑8859‑1 หากภาษาที่ต้องการอนุญาต |
| `get_extended_codetext` คืนค่าว่าง | ไม่มีส่วนข้อความใดถูกเพิ่มก่อนเรียกเมธอด | ตรวจสอบให้มีการเรียก `add_*` อย่างน้อยหนึ่งครั้ง |

### กรณีขอบ: สตริงว่าง

การเรียก `add_plain_codetext("")` หรือ `add_eci_codetext(3, "")` ไม่เป็นอันตราย; builder จะละเว้นส่วนที่ว่าง อย่างไรก็ตาม การเรียกหลายครั้งที่ว่างอาจทำให้เกิดเครื่องหมาย ECI ที่ไม่จำเป็น ป้องกันโดยตรวจสอบความยาวของสตริงก่อนเพิ่ม

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## การขยายรูปแบบสำหรับข้อมูลแบบไดนามิก

ในแอปพลิเคชันจริงคุณมักสร้าง extended codetext จากข้อมูลผู้ใช้หรือบันทึกในฐานข้อมูล โค้ดต่อไปนี้แสดงลูปที่ประมวลผลรายการของทูเพิล `(type, value)` ซึ่ง `type` จะเป็น `"plain"` หรือ `"eci"`

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

วิธีนี้ขยายได้ดี: คุณสามารถอ่านคำนิยามส่วนข้อความจาก JSON, CSV หรือ API โดยไม่ต้องเปลี่ยนแปลงตรรกะการสร้างหลัก

## การทดสอบผลลัพธ์

การทดสอบหน่วยอย่างรวดเร็วช่วยยืนยันว่า builder ทำงานตามที่คาดหวัง โดยใช้ `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

การรัน `pytest` ควรผ่าน, ยืนยันว่าเครื่องหมาย ECI ปรากฏตรงที่ควรจะเป็น

## แนวคิดที่เกี่ยวข้องที่คุณอาจสนใจต่อไป

* **Barcode encoding libraries** – เช่น `python-barcode`, `zxing` bindings, ที่รับสตริง extended codetext โดยตรง.  
* **ECI table reference** – รายการเต็มของค่าตัวเลข ECI ถูกเผยแพร่โดย ISO/IEC 18004 และสามารถเก็บเป็นพจนานุกรม Python เพื่อค้นหา.  
* **Error correction levels** – เมื่อสร้าง QR code, ผสาน extended codetext กับระดับการแก้ไขข้อผิดพลาดที่เหมาะสม (L, M, Q, H) เพื่อการสแกนที่ทนทาน.

## สรุป

ตอนนี้คุณรู้วิธี **สร้าง extended codetext** ใน Python ด้วย `ExtCodetextBuilder` กระบวนการง่าย ๆ ดังนี้:

1. สร้างอินสแตนซ์ของ builder.  
2. เพิ่มส่วนข้อความแบบ plain และที่เข้ารหัสด้วย ECI ตามต้องการ.  
3. ดึงสตริงสุดท้ายและส่งให้ตัวสร้าง barcode ของคุณ.

โดยทำตามรูปแบบข้างต้น คุณสามารถจัดการกับการผสมผสานของข้อมูล ASCII และ Unicode ใด ๆ ป้องกันข้อผิดพลาดการเข้ารหัสทั่วไป และสร้างสตริงพร้อมใช้กับ barcode ที่ทำงานได้กับสแกนเนอร์หลากหลาย ทดลองใช้ ECI ต่าง ๆ ผสาน builder เข้ากับ pipeline ของข้อมูลของคุณ แล้วคุณจะมีพื้นฐานที่มั่นคงสำหรับความต้องการ extended‑codetext ทั้งหมดของคุณ.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}