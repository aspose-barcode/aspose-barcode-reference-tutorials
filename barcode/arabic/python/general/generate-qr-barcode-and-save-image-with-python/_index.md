---
category: general
date: 2026-11-27
description: إنشاء باركود QR في بايثون باستخدام Aspose.Barcode وتعلم كيفية حفظ صورة
  الباركود على القرص بسرعة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: ar
lastmod: 2026-11-27
og_description: إنشاء رمز QR في بايثون باستخدام Aspose.Barcode وحفظ صورة الرمز مباشرةً.
  اتبع المثال الكامل لإنشاء وتخصيص وتخزين رموز QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: إنشاء رمز QR وحفظ الصورة باستخدام بايثون – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: إنشاء رمز QR وحفظ الصورة باستخدام بايثون
url: /ar/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود QR وحفظ الصورة باستخدام Python

إذا كنت بحاجة إلى **إنشاء باركود QR** في تطبيق Python، يوضح لك هذا الدليل كيفية القيام بذلك باستخدام مكتبة Aspose.Barcode. ستتعلم أيضًا الطريقة الصحيحة **لحفظ صورة الباركود** في مجلد محلي، واسترجاع تفاصيل إصدار المكتبة، ومعالجة مقاطع النص الموسعة.

إنشاء رموز QR هو مطلب شائع لأنظمة التذاكر، والمدفوعات المحمولة، وتتبع المنتجات. بنهاية هذا الدرس ستحصل على سكريبت جاهز للتنفيذ ينتج ملف صورة باركود QR ويطبع معلومات الإصدار لأغراض التصحيح أو الامتثال.

## المتطلبات المسبقة

* تثبيت Python 3.8 أو أحدث.
* حزمة `aspose-barcode`. قم بتثبيتها باستخدام `pip install aspose-barcode`.
* صلاحية كتابة إلى الدليل الذي سيتم تخزين صورة الباركود فيه.

لا توجد خدمات خارجية إضافية مطلوبة؛ العملية بالكامل تُنفّذ محليًا.

## الخطوة 1: بناء نص موسع باستخدام `ExtCodetextBuilder`

النص الموسع يتيح لك دمج النص العادي ومقاطع ECI (Extended Channel Interpretation) في رمز QR واحد. هذا مفيد عندما تحتاج إلى تضمين أحرف من مجموعات أحرف مختلفة، مثل علامة اليورو.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**لماذا هذه الخطوة مهمة:**  
`ExtCodetextBuilder` يجمع السلسلة النهائية التي سيعالجها مشفر QR. بدون بناء النص الموسع، سيحتوي الباركود على أحرف ASCII عادية فقط ولا يمكنه تمثيل الرموز الخاصة بالمحلية.

## الخطوة 2: استرجاع سلسلة النص الموسع المدمج

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

يظهر الناتج كما يلي:

```
Extended codetext: ABC123[ECI3]€123
```

المؤشر `[ECI3]` داخل الأقواس يخبر مشفر QR بالتبديل إلى مجموعة الأحرف المحددة للأحرف التالية.

## الخطوة 3: إنشاء باركود QR باستخدام النص الموسع

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**شرح:**  
`BarcodeGenerator` يستقبل معاملين: نوع الباركود (`QR`) والبيانات التي سيتم ترميزها (`extended_codetext`). يقوم المُولد بإعداد جميع الهياكل الداخلية اللازمة للتصوير.

## الخطوة 4: حفظ صورة الباركود المُنشأة

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**لماذا يجب عليك استخدام هذا النهج:**  
استدعاء `save` مباشرة يكتب الصورة إلى القرص باستخدام الصيغة المستنتجة من امتداد الملف. الطريقة تدعم PNG، JPEG، BMP، وTIFF، مما يمنحك مرونة للمستقبلين المختلفين.

### التحقق من الصورة المحفوظة

افتح الملف `output/qr_extended.png` بأي عارض صور. يجب أن ترى رمز QR، عند مسحه، يعيد السلسلة `ABC123€123`. معظم ماسحات QR المحمولة الحديثة تتعامل مع مقطع ECI تلقائيًا.

## الخطوة 5: الاستعلام عن معلومات إصدار Aspose.BarCode (اختياري لكن مفيد)

معرفة الإصدار الدقيق لمكتبة Aspose.BarCode يساعد عندما تحتاج إلى الإبلاغ عن أخطاء أو التحقق من التوافق.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

ناتج نموذجي:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## السكريبت الكامل – نسخ، لصق، وتشغيل

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

تشغيل السكريبت ينتج صورة رمز QR ويطبع كلًا من النص الموسع وتفاصيل الإصدار إلى وحدة التحكم.

## الاختلافات الشائعة والحالات الخاصة

| الحالة | التعديل الموصى به |
|-----------|------------------------|
| **مجموعة أحرف مختلفة** | غيّر معرف ECI الممرّر إلى `add_eci_codetext`. لاستخدام UTF‑8 استخدم `5`. |
| **تصحيح أخطاء أعلى** | عيّن `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` قبل استدعاء `save`. |
| **حجم صورة مخصص** | استخدم `barcode.parameters.image_width` و `barcode.parameters.image_height` للتحكم في أبعاد البكسل. |
| **إخراج غير PNG** | غيّر امتداد الملف في `output_path` إلى `.jpg` أو `.bmp`. المكتبة تختار المشفر الصحيح تلقائيًا. |

## نصائح احترافية

* **إنشاء مجلد الإخراج** برمجيًا إذا كان قد لا يكون موجودًا:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **تحقق من رمز QR** بعد الإنشاء بقراءته مرة أخرى باستخدام `aspose.barcode.BarcodeReader`. هذا يضمن أن البيانات المشفرة تتطابق مع التوقعات، خاصة عند استخدام مقاطع ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **نصيحة أداء** – أعد استخدام كائن `BarcodeGenerator` واحد إذا كنت بحاجة إلى إنشاء العديد من رموز QR في حلقة. أعد ضبط خاصية `code_text` بدلاً من إنشاء كائن جديد في كل تكرار.

## الخلاصة

أنت الآن تعرف كيف **تنشئ باركود QR** في Python باستخدام Aspose.Barcode، وتبني نصًا موسعًا يدمج مقاطع نصية عادية وECI، وتقوم **بحفظ صورة الباركود** بشكل صحيح على القرص. يوضح السكريبت أيضًا كيفية استرجاع معلومات إصدار المكتبة لتصحيح الأخطاء.

الخطوات التالية التي قد تستكشفها تشمل:

* إضافة شعار أو ألوان مخصصة إلى رمز QR.
* تضمين باركود QR مباشرةً في ملفات PDF باستخدام Aspose.PDF.
* أتمتة إنشاء دفعات للبيانات الكبيرة.

لا تتردد في تجربة أحمال بيانات مختلفة، ومستويات تصحيح الأخطاء، وصيغ الصور. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء صورة QR Code في Python باستخدام Aspose.Barcode – الدليل الكامل](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [كيفية إنشاء باركود Code 128 وحفظ صورة الباركود باستخدام Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [كيفية إنشاء باركود DataMatrix في Python باستخدام Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}