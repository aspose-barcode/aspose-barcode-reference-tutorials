---
category: general
date: 2026-09-29
description: عرض اسم المنتج في بايثون أثناء طباعة تاريخ الإصدار واسترجاع تفاصيل الإصدار
  من مكتبة الباركود.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: ar
lastmod: 2026-09-29
og_description: اعرض اسم المنتج في بايثون وتعلم كيفية طباعة تاريخ الإصدار، الحصول
  على النسخة، وعرض النسخة الفرعية ببضع أسطر من الشيفرة.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: عرض اسم المنتج ومعلومات الإصدار في بايثون
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
title: عرض اسم المنتج ومعلومات الإصدار في بايثون
url: /ar/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# عرض اسم المنتج ومعلومات الإصدار في بايثون

إذا كنت بحاجة إلى **عرض اسم المنتج** من مكتبة، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك. ستتعلم أيضًا **طباعة تاريخ الإصدار**، **كيفية الحصول على الإصدار**، و**عرض الإصدار الفرعي** باستخدام كود بايثون مختصر.

العديد من المطورين يدمجون ميزات مسح الباركود أو توليده ويحتاجون إلى إظهار بيانات التعريف الخاصة بالمكتبة للمستخدمين أو السجلات. يغطي هذا الدرس كل ما يلزم لاسترجاع وعرض تلك المعلومات بشكل موثوق.

## ما ستتعلمه

* استرجاع معلومات الإصدار من مكتبة `barcode`.  
* **عرض اسم المنتج** مع أرقام الإصدار الرئيسي والفرعي.  
* **طباعة تاريخ الإصدار** بصيغة قابلة للقراءة البشرية.  
* معالجة الخصائص المفقودة بشكل سلس.  

**المتطلبات المسبقة**  
* بايثون 3.8 أو أحدث.  
* الوصول إلى حزمة `barcode` (قم بالتثبيت باستخدام `pip install python-barcode` أو المكتبة التي توفر `BuildVersionInfo`).  

---

## كيفية عرض اسم المنتج ومعلومات الإصدار في بايثون

الخطوة الأولى هي استيراد المكتبة واستدعاء الطريقة التي تُعيد كائن معلومات الإصدار. يحتوي الكائن على خصائص مثل `PRODUCT`، `PRODUCT_MAJOR`، `PRODUCT_MINOR`، و`RELEASE_DATE`.

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

**لماذا يعمل هذا**  
`BuildVersionInfo()` تُعيد كائنًا خفيفًا يتم ملء خصائصه عند وقت الاستيراد. الوصول إلى الخصائص مباشرةً يتجنب عمليات الإدخال/الإخراج الإضافية ويضمن أن البيانات المعروضة تتطابق مع نسخة المكتبة التي يستخدمها الكود فعليًا.

### النتيجة المتوقعة

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

القيم الدقيقة تعتمد على نسخة مكتبة barcode المثبتة.

---

## كيفية الحصول على الإصدار من مكتبة barcode

إذا كنت بحاجة فقط إلى أرقام الإصدار، يمكنك تخطي طباعة اسم المنتج والتركيز على الحقول الرقمية.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*خصائص `PRODUCT_MAJOR` و`PRODUCT_MINOR` تتبع النسخة الدلالية، مما يتيح لك مقارنة الإصدارات برمجيًا.*

---

## كيفية طباعة تاريخ الإصدار

يتم تخزين تاريخ الإصدار كسلسلة نصية بصيغة `YYYY‑MM‑DD`. لعرضه بلغة مختلفة، حوّله أولاً إلى كائن `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**نصيحة:** تحقق دائمًا من صحة سلسلة التاريخ قبل التحليل لتجنب حدوث `ValueError` عندما تغير المكتبة صيغتها.

---

## عرض الإصدار الفرعي بجانب الإصدار الرئيسي

أحيانًا تحتاج إلى عرض الإصدار الفرعي بشكل منفصل، على سبيل المثال عند تسجيل تحذيرات التوافق.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**نصيحة احترافية:** استخدم الإصدار الفرعي لتفعيل أعلام الميزات:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## معالجة الخصائص المفقودة (حالات الحافة)

الإصدارات القديمة من مكتبة barcode قد لا تُظهر جميع الخصائص. غلف الوصول إلى الخصائص باستخدام `getattr` مع قيم افتراضية معقولة.

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

هذا النمط يضمن أن لا يتعطل السكربت بسبب حقل مفقود، مما يجعله قويًا لخطوط أنابيب CI التي قد تعمل على إصدارات مكتبة متعددة.

---

## مثال كامل قابل للتنفيذ

فيما يلي السكربت الكامل الذي يجمع جميع أفضل الممارسات: التحقق من الخصائص، تنسيق التاريخ، وإخراج واضح.

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

تشغيل هذا السكربت على نظام يحتوي على مكتبة barcode المثبتة ينتج مخرجات مشابهة للمثال السابق، لكنه الآن يحمي من الحقول المفقودة ويُنسق التاريخ بشكل جميل.

---

## الخلاصة

أنت الآن تعرف كيفية **عرض اسم المنتج**، **طباعة تاريخ الإصدار**، **كيفية الحصول على الإصدار**، **كيفية طباعة المنتج**، و**عرض الإصدار الفرعي** باستخدام سير عمل بايثون بسيط. يُظهر المثال الكامل الوصول الموثوق إلى الخصائص، معالجة التاريخ، ومقارنة الإصدارات—مهارات يمكنك إعادة استخدامها لأي مكتبة طرف ثالث تُظهر كائنات البيانات الوصفية.

**الخطوات التالية**

* استكشف طرق البيانات الوصفية الأخرى في مكتبة barcode، مثل `BuildCommitInfo()`.  
* دمج المخرجات في إطار تسجيل (مثل `logging.info`).  
* قارن الإصدارات برمجيًا لفرض الحد الأدنى من الإصدارات المطلوبة في تطبيقك.

لا تتردد في تجربة صيغ إخراج مختلفة أو توسيع السكربت لكتابة المعلومات إلى ملف لأغراض التدقيق. برمجة سعيدة!  

![مخرجات الطرفية تُظهر اسم المنتج وتفاصيل الإصدار](image.png "مخرجات الطرفية")

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [عرض اسم المنتج باستخدام مكتبة Python barcode – دليل خطوة بخطوة](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [كيفية طباعة إصدار Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [كيفية توليد باركود باستخدام Aspose.BarCode في Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}