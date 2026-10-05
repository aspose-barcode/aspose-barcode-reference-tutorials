---
category: general
date: 2026-09-10
description: ترميز الأحرف غير ASCII في رمز QR وحفظ صورة رمز QR باستخدام أداة بناء
  بسيطة بلغة بايثون. اتبع دليلًا خطوة بخطوة باستخدام ExtCodetextBuilder وBarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: ar
lastmod: 2026-09-10
og_description: ترميز الأحرف غير ASCII في رمز QR وحفظ صورة رمز QR باستخدام بايثون.
  يوضح هذا الدرس كيفية إنشاء نص مشفر موسع، توليد رمز QR، وتخزين الصورة.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: ترميز الأحرف غير ASCII في رمز QR وحفظ صورة رمز QR – دليل بايثون خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: ترميز الأحرف غير ASCII في رمز QR وحفظ صورة الرمز QR
url: /ar/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ترميز الأحرف غير ASCII في رمز QR وحفظ صورة رمز QR

إذا كنت بحاجة إلى **ترميز الأحرف غير ASCII** في رمز QR، فإن هذا الدليل يوضح لك بالضبط كيفية القيام بذلك ثم **حفظ صورة رمز QR** على القرص. سواء كنت تتعامل مع بيانات روسية أو صينية أو إيموجي، يتيح لك ExtCodetextBuilder خلط النص العادي والقطاعات المشفرة بـ ECI دون الحاجة إلى تعديل البايتات يدويًا.

سوف تتعلم كيفية إنشاء سلسلة codetext موسعة، وتوليد رمز QR يفهم تلك السلسلة، وأخيرًا كتابة صورة الباركود إلى ملف. يفترض الدليل معرفة أساسية بـ Python وأن لديك حزمة `barcode` SDK مثبتة.

## المتطلبات المسبقة

* تثبيت Python 3.8+.
* حزمة Python `barcode` (أو SDK المناسب) التي توفر `ExtCodetextBuilder` و `CodetextEncodingType` و `BarcodeGenerator`.
* صلاحية كتابة إلى الدليل الذي تريد **حفظ صورة رمز QR** فيه.

يمكنك تثبيت SDK باستخدام pip (استبدل `barcode-sdk` باسم الحزمة الفعلي):

```bash
pip install barcode-sdk
```

## الخطوة 1: إنشاء مُنشئ codetext موسع

الخطوة الأولى هي إنشاء كائن `ExtCodetextBuilder`. يجمع هذا الكائن عدة قطاعات نصية وينتج سلسلة واحدة يمكن لرموز QR تفسيرها.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*لماذا هذا مهم*: تدعم رموز QR **codetext موسع**، مما يعني أنه يمكنك دمج عدة أوضاع ترميز (نص عادي، ECI، إلخ) في باركود واحد. يقوم المُنشئ بتجريد التنسيق منخفض المستوى المطلوب وفقًا لمواصفات QR.

## الخطوة 2: إضافة قطاع نص عادي

النص العادي هو الوضع الافتراضي ويعمل مع أحرف ASCII. إضافته أولاً يوفر نسخة احتياطية قابلة للقراءة للماسحات التي تتجاهل ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

إذا تخطيت هذه الخطوة، سيحتوي رمز QR فقط على قطاع ECI، وقد لا يتمكن بعض القارئات القديمة من فك تشفيره بشكل صحيح.

## الخطوة 3: إضافة قطاع مشفر بـ ECI للأحرف غير ASCII

لإدراج أحرف خارج نطاق ASCII—مثل السيريالية أو الصينية أو الإيموجي—يجب تحديد ترميز ECI (Extended Channel Interpretation). هنا نستخدم UTF‑8 للكلمة الروسية “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*لماذا هذا يعمل*: تحدد مواصفات QR قيم ECI التي تخبر الماسح أي مجموعة أحرف يجب استخدامها. بدون علامة ECI، سيتم تفسير البايتات الخام كـ ISO‑8859‑1، مما ينتج مخرجات مشوهة.

## الخطوة 4: استرجاع سلسلة codetext الموسعة المدمجة

بعد إضافة جميع القطاعات المطلوبة، استدعِ `get_extended_codetext()` للحصول على السلسلة النهائية التي يتوقعها مُولد الباركود.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

القيمة المطبوعة تبدو كسلسلة من أحرف التحكم متبوعة بالنص الفعلي، لكنك لا تحتاج إلى تحليلها يدويًا.

## الخطوة 5: توليد رمز QR باستخدام codetext الموسع

الآن أنشئ كائن `BarcodeGenerator`، واضبط الترميز إلى QR (الترميز الثنائي الأبعاد الشائع الوحيد الذي يدعم codetext الموسع)، ومرر السلسلة المدمجة.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*نصيحة*: إذا جربت نفس العملية مع Code‑128 أو DataMatrix، سيُطلق SDK استثناءً لأن هذه الصيغ لا يمكنها تفسير علامات ECI.

## الخطوة 6: حفظ صورة رمز QR

أخيرًا، اكتب الباركود إلى ملف PNG. هنا تقوم **بحفظ صورة رمز QR** للاستخدام لاحقًا.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

تأكد من وجود مجلد `output` أو أنشئه باستخدام `os.makedirs('output', exist_ok=True)` قبل استدعاء `save`.

### مثال كامل قابل للتنفيذ

جمع جميع الخطوات معًا يمنحك سكريبتًا مستقلًا يمكنك تشغيله فورًا:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**الناتج المتوقع** (الكونسول):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

فتح `qr_extended.png` بأي ماسح QR سيعرض `HelloWorldПривет`. الماسحات التي تدعم ECI ستظهر الأحرف السيريالية بشكل صحيح؛ أما غيرها فستظهر الجزء ASCII فقط.

## الأسئلة الشائعة والحالات الخاصة

| السؤال | الجواب |
|----------|--------|
| *هل يمكنني استخدام ترميزات أخرى مثل Shift‑JIS؟* | نعم. استبدل `CodetextEncodingType.UTF_8` بـ `CodetextEncodingType.SHIFT_JIS` وقدم النص المناسب. |
| *ماذا لو تجاوزت البيانات المدمجة سعة QR؟* | لرموز QR حدود على الإصدارات (حتى 177 × 177 وحدة). إذا ألقى المُنشئ استثناءً بسبب الحجم، إما أن تزيد مستوى تصحيح الأخطاء أو تقسم البيانات عبر عدة رموز QR. |
| *هل أحتاج لتحديد إصدار QR معين؟* | يقوم SDK تلقائيًا باختيار أصغر إصدار يتناسب مع البيانات. يمكنك فرض إصدار معين باستخدام `qr_generator.set_qr_version(10)` إذا لزم الأمر. |
| *هل ستكون الصورة شفافة؟* | بشكل افتراضي يكتب SDK ملف PNG بخلفية بيضاء. استخدم `qr_generator.set_background_color(Color.Transparent)` قبل `save` إذا كنت بحاجة إلى الشفافية. |

## الخلاصة

في هذا الدليل تعلمت كيفية **ترميز الأحرف غير ASCII** في رمز QR باستخدام `ExtCodetextBuilder` ثم **حفظ صورة رمز QR** باستخدام `BarcodeGenerator`. تتضمن العملية بناء سلسلة codetext موسعة، إضافة كل من القطاعات النصية العادية والقطاعات المشفرة بـ ECI، توليد ترميز QR، وأخيرًا كتابة ملف الصورة.

من هنا يمكنك استكشاف:

* إضافة المزيد من قطاعات ECI (لغات مختلفة أو إيموجي).
* ضبط مستويات تصحيح الأخطاء في QR لمزيد من الموثوقية.
* تضمين ملف PNG المُولد في ملفات PDF أو صفحات الويب.

برمجة سعيدة، واستمتع بإنشاء رموز QR متعددة اللغات!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شاملة من الكود مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية توليد صورة رمز QR في Python باستخدام Aspose.Barcode – دليل كامل](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [توليد باركود Code128 باستخدام Aspose.Barcode Python – دليل كامل](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [عرض اسم المنتج باستخدام مكتبة الباركود Python – دليل خطوة بخطوة](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}