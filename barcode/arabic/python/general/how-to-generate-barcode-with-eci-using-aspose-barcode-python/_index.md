---
category: general
date: 2026-08-19
description: كيفية إنشاء الباركود باستخدام ECI مع Aspose.Barcode للبايثون. تعلّم كيفية
  إضافة بيانات ECI، دمج النص العادي، وحفظ الصورة في دليل واضح واحد.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: ar
lastmod: 2026-08-19
og_description: كيفية إنشاء الباركود مع ECI باستخدام Aspose.Barcode للبايثون. اتبع
  هذا الدليل لتعلم كيفية إضافة بيانات ECI، تخصيص المظهر، وحفظ النتيجة.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: كيفية إنشاء باركود باستخدام ECI باستخدام Aspose.Barcode Python – خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: كيفية إنشاء الباركود مع ECI باستخدام Aspose.Barcode Python
url: /ar/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود باستخدام ECI مع Aspose.Barcode Python

إذا كنت بحاجة إلى معرفة **كيفية إنشاء باركود** يحتوي على كل من الأحرف العادية والبيانات المشفرة بـ ECI، يوضح هذا الدليل العملية بالكامل. سترى بالضبط **كيفية إضافة أقسام eci**، وضبط الحجم، وكتابة الصورة إلى القرص باستخدام برنامج نصي واحد قابل للتنفيذ.

يغطي الدرس:

* استرجاع نسخة مكتبة Aspose.Barcode (اختياري لكنه مفيد للتصحيح).  
* بناء سلسلة codetext موسعة تمزج بين الأحرف العادية والـ ECI‑encoded.  
* إنشاء مولد باركود لرمز يدعم codetext الموسع.  
* تخصيص أبعاد الباركود وحفظ ملف PNG النهائي.

لا حاجة إلى أي وثائق خارجية؛ انسخ الكود، شغّله، وستحصل على صورة باركود تتضمن أحرف صينية مشفرة بـ ECI 26 (UTF‑8).

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود:

* Python 3.8 أو أحدث مثبت.  
* حزمة `aspose-barcode` مثبتة (`pip install aspose-barcode`).  
* صلاحية كتابة في المجلد الذي تنوي حفظ ملف PNG فيه.

إذا كنت تستخدم بيئة افتراضية، فعّلها أولاً للحفاظ على عزل الاعتمادات.

## الخطوة 1: التحقق من إصدار Aspose.Barcode (اختياري)

معرفة الإصدار الدقيق للمكتبة يساعد عندما تحتاج إلى الإبلاغ عن أخطاء أو مقارنة الميزات بين الإصدارات.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*لماذا هذا مهم*: يثبت إخراج الإصدار أن وقت التشغيل يتطابق مع الوثائق التي تتبعها. قد تدعم الإصدارات المختلفة قيم ECI مختلفة، لذا فهذه فحص سريع للمنطقية.

## الخطوة 2: بناء codetext موسع مع أجزاء عادية وECI‑encoded

توفر Aspose.Barcode الفئة `ExtCodetextBuilder` لدمج البيانات العادية والقطاعات المشفرة بـ ECI. في هذا المثال نمزج سلسلة رقمية مع أحرف صينية.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*شرح*:  
* `add_plain_codetext` يضيف بيانات يتعامل معها رمز الباركود كأحرف عادية.  
* `add_eci_codetext` يخبر المولد بإضافة مؤشر ECI (هنا **26**، الذي يطابق UTF‑8) قبل النص المقدم. هذا هو بالضبط **كيفية إضافة eci** إلى الباركود.

يمكنك استدعاء `add_eci_codetext` عدة مرات لتضمين عدة كتل لغات مختلفة. يتعامل المُنشئ مع تسلسلات الهروب المطلوبة تلقائيًا.

## الخطوة 3: اختيار رمزية تدعم codetext الموسع

ليس كل نوع باركود يمكنه تخزين قطاعات ECI. Code 128، QR، وData Matrix هي خيارات شائعة. يستخدم المثال Code 128 لأنه مدعوم على نطاق واسع ويعمل جيدًا للبيانات المختلطة أبجديًا رقمية.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*لماذا Code 128؟*: يقبل النطاق الكامل لـ ASCII وتسلسلات الهروب الخاصة بـ ECI التي ينتجها المُنشئ، مما يجعله مثاليًا لسيناريو “كيفية إنشاء باركود” الذي يخلط بين النص العادي والمشفّر.

## الخطوة 4: ضبط مظهر الباركود

يمكنك التحكم في الحجم، الارتفاع، الهوامش، والعديد من الجوانب البصرية الأخرى عبر كائن `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*نصيحة*: إذا كنت تخطط لطباعة الباركود، قم بزيادة `x_dimension` و `bar_height` بشكل متناسب للحفاظ على قابلية القراءة عند DPI المستهدف.

## الخطوة 5: حفظ صورة الباركود

أخيرًا، اكتب الصورة المُولدة إلى ملف. تدعم Aspose.Barcode صيغ PNG، JPEG، BMP، والعديد من الصيغ الأخرى.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

تأكد من وجود مجلد `output` أو أنشئه باستخدام `os.makedirs("output", exist_ok=True)` قبل استدعاء `save`.

### النتيجة المتوقعة

عند فتح `extended_codetext.png`، يجب أن ترى باركود Code 128 يشفّر السلسلة الرقمية `1234567890` متبوعة بالأحرف الصينية “特殊字符”. مسح الباركود باستخدام ماسح حديث يدعم ECI سيعيد السلسلة المختلطة الأصلية.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="باركود تم إنشاؤه باستخدام مثال كيفية إنشاء باركود"}

## الأسئلة الشائعة والحالات الخاصة

### ماذا لو احتجت إلى مجموعة أحرف مختلفة؟

اختر قيمة ECI المناسبة من جدول ISO/IEC 18004. على سبيل المثال، تمثل ECI 27 مجموعة ISO‑8859‑1 (Latin‑1). استبدل المعرف الرقمي في `add_eci_codetext` وفقًا لذلك.

### هل يمكنني تضمين أكثر من كتلة ECI واحدة؟

نعم. استدعِ `add_eci_codetext` عدة مرات. يضيف المُنشئ رموز التحويل اللازمة بين الكتل، محافظًا على الترتيب الذي تضيفه به.

### هل يدعم المولد رموز QR مع ECI؟

بالطبع. استبدل `barcode.Symbology.CODE_128` بـ `barcode.Symbology.QR` واضبط أي معلمات خاصة بـ QR (مثل مستوى تصحيح الأخطاء) عبر `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### كيف أتعامل مع سلاسل بيانات طويلة جدًا؟

بالنسبة للباركودات الخطية مثل Code 128، الحد الأقصى للطول هو حوالي 80 حرفًا عند استخدام codetext الموسع. إذا تجاوزت ذلك، فكر في التحول إلى رمزية ثنائية الأبعاد مثل QR أو Data Matrix، التي يمكنها تخزين آلاف الأحرف.

## البرنامج الكامل القابل للتنفيذ

فيما يلي البرنامج الكامل الذي يمكنك نسخه‑لصقه في ملف باسم `generate_extended_barcode.py` وتشغيله مباشرة.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك الخاصة.

- [كيفية إنشاء صورة باركود مع تخصيص مساحة إضافية باستخدام Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [كيفية إنشاء صورة باركود في Java باستخدام Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [كيفية إنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}