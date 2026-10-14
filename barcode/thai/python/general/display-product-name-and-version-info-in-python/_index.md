---
category: general
date: 2026-09-29
description: แสดงชื่อผลิตภัณฑ์ใน Python ขณะพิมพ์วันที่ออกและดึงรายละเอียดเวอร์ชันจากไลบรารี
  barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: th
lastmod: 2026-09-29
og_description: แสดงชื่อผลิตภัณฑ์ใน Python และเรียนรู้วิธีพิมพ์วันที่ปล่อย, ดึงเวอร์ชัน,
  และแสดงเวอร์ชันย่อยด้วยไม่กี่บรรทัดของโค้ด
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: แสดงชื่อผลิตภัณฑ์และข้อมูลเวอร์ชันใน Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: แสดงชื่อผลิตภัณฑ์และข้อมูลเวอร์ชันใน Python
url: /th/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แสดงชื่อผลิตภัณฑ์และข้อมูลเวอร์ชันใน Python

หากคุณต้องการ **display product name** จากไลบรารี คู่มือนี้จะแสดงวิธีทำอย่างละเอียด คุณจะได้เรียนรู้วิธี **print release date**, **how to get version**, และ **show minor version** ด้วยโค้ด Python ที่กระชับ

หลาย ๆ นักพัฒนานำคุณสมบัติการสแกนหรือสร้างบาร์โค้ดมาใช้และต้องแสดงเมตาดาต้าของไลบรารีให้ผู้ใช้หรือบันทึก การสอนนี้ครอบคลุมทุกอย่างที่จำเป็นเพื่อดึงและนำเสนอข้อมูลนั้นอย่างเชื่อถือได้

## สิ่งที่คุณจะได้เรียนรู้

* ดึงข้อมูลเวอร์ชันจากไลบรารี `barcode`  
* **Display product name** พร้อมกับหมายเลขเวอร์ชันหลักและรอง  
* **Print release date** ในรูปแบบที่อ่านง่ายสำหรับมนุษย์  
* จัดการกับแอตทริบิวต์ที่หายไปอย่างราบรื่น  

**ข้อกำหนดเบื้องต้น**  
* Python 3.8 หรือใหม่กว่า  
* เข้าถึงแพ็กเกจ `barcode` (ติดตั้งด้วย `pip install python-barcode` หรือไลบรารีที่ให้ `BuildVersionInfo`)  

---

## วิธีแสดงชื่อผลิตภัณฑ์และข้อมูลเวอร์ชันใน Python

ขั้นตอนแรกคือการนำเข้าไลบรารีและเรียกเมธอดที่คืนค่าอ็อบเจ็กต์ version‑info อ็อบเจ็กต์นี้มีแอตทริบิวต์เช่น `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` และ `RELEASE_DATE`

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**ทำไมวิธีนี้ถึงได้ผล**  
`BuildVersionInfo()` คืนค่าอ็อบเจ็กต์ขนาดเล็กที่แอตทริบิวต์ถูกกำหนดค่าในขณะนำเข้า การเข้าถึงแอตทริบิวต์โดยตรงช่วยหลีกเลี่ยง I/O เพิ่มเติมและรับประกันว่าข้อมูลที่แสดงตรงกับเวอร์ชันของไลบรารีที่โค้ดของคุณกำลังใช้จริง

### Expected output

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

ค่าที่แสดงจะขึ้นอยู่กับเวอร์ชันของไลบรารี barcode ที่ติดตั้งอยู่

---

## วิธีดึงเวอร์ชันจากไลบรารี barcode

หากคุณต้องการเพียงหมายเลขเวอร์ชันเท่านั้น สามารถข้ามการพิมพ์ชื่อผลิตภัณฑ์และโฟกัสที่ฟิลด์ตัวเลขได้

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*The `PRODUCT_MAJOR` and `PRODUCT_MINOR` attributes follow semantic versioning, letting you compare versions programmatically.*

---

## วิธีพิมพ์วันที่ปล่อย

วันที่ปล่อยถูกเก็บเป็นสตริงในรูปแบบ `YYYY‑MM‑DD` เพื่อแสดงในภาษาท้องถิ่นอื่น ให้แปลงเป็นอ็อบเจ็กต์ `datetime` ก่อน

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tip:** ตรวจสอบสตริงวันที่ก่อนทำการแปลงเสมอเพื่อหลีกเลี่ยง `ValueError` เมื่อไลบรารีเปลี่ยนรูปแบบ

---

## แสดงเวอร์ชันรองพร้อมเวอร์ชันหลัก

บางครั้งคุณต้องการแสดงเวอร์ชันรองแยกจากเวอร์ชันหลัก เช่น เมื่อต้องบันทึกคำเตือนความเข้ากันได้

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** ใช้เวอร์ชันรองเพื่อเปิดใช้งานฟีเจอร์ฟลัก:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## การจัดการแอตทริบิวต์ที่หายไป (กรณีขอบ)

รุ่นเก่าของไลบรารี barcode อาจไม่เปิดเผยแอตทริบิวต์ทั้งหมด ให้ห่อการเข้าถึงแอตทริบิวต์ด้วย `getattr` พร้อมค่าเริ่มต้นที่เหมาะสม

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

รูปแบบนี้ทำให้สคริปต์ของคุณไม่เคยพังจากฟิลด์ที่หายไป ทำให้ระบบ CI ของคุณทำงานได้อย่างมั่นคงแม้ต้องรันกับหลายเวอร์ชันของไลบรารี

---

## ตัวอย่างเต็มที่สามารถรันได้

ด้านล่างเป็นสคริปต์สมบูรณ์ที่รวมแนวปฏิบัติที่ดีที่สุดทั้งหมด: การตรวจสอบแอตทริบิวต์, การจัดรูปแบบวันที่, และการแสดงผลที่ชัดเจน

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

การรันสคริปต์นี้บนระบบที่ติดตั้งไลบรารี barcode จะให้ผลลัพธ์คล้ายกับตัวอย่างก่อนหน้า แต่ตอนนี้จะป้องกันฟิลด์ที่หายไปและจัดรูปแบบวันที่อย่างสวยงาม

---

## สรุป

คุณได้เรียนรู้วิธี **display product name**, **print release date**, **how to get version**, **how to print product**, และ **show minor version** ด้วยเวิร์กโฟลว์ Python ที่ตรงไปตรงมา ตัวอย่างเต็มแสดงการเข้าถึงแอตทริบิวต์อย่างเชื่อถือได้, การจัดการวันที่, และการเปรียบเทียบเวอร์ชัน — ทักษะที่คุณสามารถนำไปใช้กับไลบรารีของบุคคลที่สามใด ๆ ที่เปิดเผยอ็อบเจ็กต์เมตาดาต้า

**ขั้นตอนต่อไป**

* สำรวจเมธอดเมตาดาต้าอื่น ๆ ของไลบรารี barcode เช่น `BuildCommitInfo()`  
* ผสานผลลัพธ์เข้ากับเฟรมเวิร์กการบันทึก (เช่น `logging.info`)  
* เปรียบเทียบเวอร์ชันโดยโปรแกรมเพื่อบังคับใช้เวอร์ชันขั้นต่ำที่ต้องการในแอปพลิเคชันของคุณ  

อย่ากลัวที่จะทดลองกับรูปแบบการแสดงผลต่าง ๆ หรือขยายสคริปต์ให้เขียนข้อมูลลงไฟล์เพื่อการตรวจสอบ ใช้ความสนุกกับการเขียนโค้ด!

![ผลลัพธ์ในเทอร์มินัลแสดงชื่อผลิตภัณฑ์และรายละเอียดเวอร์ชัน](image.png "ผลลัพธ์ในเทอร์มินัล")

## คุณควรเรียนรู้อะไรต่อไป?

บทแนะนำต่อไปนี้ครอบคลุมหัวข้อที่เกี่ยวข้องอย่างใกล้ชิดและต่อยอดจากเทคนิคที่แสดงในคู่มือนี้ แต่ละแหล่งรวมตัวอย่างโค้ดทำงานเต็มรูปแบบพร้อมคำอธิบายทีละขั้นตอน เพื่อช่วยคุณเชี่ยวชาญฟีเจอร์ API เพิ่มเติมและสำรวจแนวทางการทำงานทางเลือกในโปรเจกต์ของคุณ

- [แสดงชื่อผลิตภัณฑ์โดยใช้ไลบรารี Python barcode – คู่มือขั้นตอนโดยละเอียด](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [วิธีพิมพ์เวอร์ชันของ Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [วิธีสร้างบาร์โค้ดด้วย Aspose.BarCode ใน Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}