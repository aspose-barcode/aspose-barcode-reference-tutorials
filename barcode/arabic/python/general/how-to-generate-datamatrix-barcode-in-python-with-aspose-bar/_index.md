---
category: general
date: 2026-08-22
description: تعلم كيفية إنشاء رمز DataMatrix في بايثون وترميز النص الروسي باستخدام
  Aspose.BarCode – دليل خطوة بخطوة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: ar
lastmod: 2026-08-22
og_description: إنشاء رمز DataMatrix في بايثون وترميز النص الروسي باستخدام Aspose.BarCode.
  اتبع المثال الكامل وشغّله فورًا.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: إنشاء باركود DataMatrix في بايثون – دليل Aspose.BarCode الكامل
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: كيفية إنشاء باركود DataMatrix في بايثون باستخدام Aspose.BarCode
url: /ar/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود DataMatrix في بايثون باستخدام Aspose.BarCode

إذا كنت بحاجة إلى **إنشاء باركود DataMatrix** في بايثون مع **ترميز النص الروسي**، فإن هذا الدليل يوضح لك الخطوات الدقيقة. سترى مثالًا كاملاً قابلًا للتنفيذ يبني نصًا موسعًا، يضبط الباركود، ويحفظ الصورة في سكريبت واحد.

إنشاء باركود يحتوي على أحرف غير ASCII غالبًا ما يثير أسئلة حول مجموعات الأحرف وترميز البيانات. باستخدام `ExtCodetextBuilder` من Aspose.BarCode، يمكنك تضمين نص UTF‑8 مثل الأحرف السيريالية داخل رمز DataMatrix بأمان. النتيجة تعمل مع أي ماسح يدعم معيار DataMatrix.

في هذا الدرس ستقوم بـ:

* تثبيت حزمة Aspose.BarCode المطلوبة.
* بناء نص موسع يجمع بين البيانات العادية والنص الروسي.
* **إنشاء باركود DataMatrix** باستخدام السلسلة الموسعة.
* تعديل معلمات الباركود مثل حجم الوحدة.
* حفظ الباركود كملف PNG.

لا توجد خدمات خارجية مطلوبة؛ كل شيء يعمل محليًا على جهازك.

## المتطلبات المسبقة

قبل البدء، تأكد من أن لديك:

* Python 3.8 أو أحدث مثبت.
* ترخيص فعال لـ Aspose.BarCode للبايثون (إصدار تجريبي مجاني يكفي للتطوير).
* إلمام أساسي ببرمجة بايثون.

يمكنك تثبيت مكتبة Aspose.BarCode عبر pip:

```bash
pip install aspose-barcode
```

## الخطوة 1: بناء سلسلة نص موسع

المهمة الأولى هي إنشاء سلسلة واحدة تحتوي على معرف المنتج العادي والعبارة الروسية. يسمح لك `ExtCodetextBuilder` بدمج أجزاء نصية مختلفة مع الحفاظ على معلومات الترميز الخاصة بها.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**لماذا هذه الخطوة مهمة** – رموز DataMatrix تخزن بايتات خام. عندما تحتاج إلى دمج أبجديات مختلفة، يجب إبلاغ المُشفّر أي مجموعة أحرف تنطبق على كل جزء. تُدخل طريقة `add_eci_codetext` مؤشر ECI قبل النص الروسي، مما يضمن أن الماسحات تفسّر البايتات كـ UTF‑8. بدون ECI، ستظهر الأحرف السيريالية كبيانات مشوشة.

## الخطوة 2: إنشاء مولّد باركود DataMatrix

بعد تجهيز النص الموسع، أنشئ كائن `BarcodeGenerator` مع تحديد النوع `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**لماذا DataMatrix؟** – DataMatrix هو باركود ثنائي الأبعاد يمكنه تخزين ما يصل إلى 2,335 حرفًا أبجديًا رقميًا أو 1,556 بايت. إنه مثالي للأشياء الصغيرة، الأجزاء الصناعية، والحالات التي تحتاج فيها إلى تضمين نص متعدد اللغات.

## الخطوة 3: (اختياري) ضبط معلمات الباركود

يوفر Aspose.BarCode العديد من المعلمات. بالنسبة لمعظم الاستخدامات، الإعدادات الافتراضية تنتج رمزًا قابلًا للقراءة. ومع ذلك، قد ترغب في التحكم في حجم كل وحدة (أصغر مربع في المصفوفة) لتتناسب مع متطلبات الطباعة.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

تشمل المعلمات المفيدة الأخرى مستوى تصحيح الأخطاء، الهامش، ولون الخلفية. قم بضبطها فقط إذا كان بيئة المسح المستهدفة تتطلب تحمّلات محددة.

## الخطوة 4: حفظ صورة الباركود

أخيرًا، احفظ الباركود إلى ملف. تدعم طريقة `save` صيغ PNG، JPEG، BMP، وعدة صيغ متجهية.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

عند فتح `extended_codetext.png`، سترى رمز DataMatrix واضحًا. مسحه باستخدام قارئ DataMatrix قياسي يعيد الجزأين:

1. **ABC123** – المعرف العادي.
2. **Привет** – التحية الروسية، تم فك ترميزها بشكل صحيح كـ UTF‑8.

## مثال كامل قابل للتنفيذ

فيما يلي السكريبت الكامل الذي يمكنك نسخه ولصقه في ملف باسم `generate_datamatrix.py`. استبدل `YOUR_DIRECTORY` بمسار مجلد موجود على نظامك.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Run the script from the command line:

```bash
python generate_datamatrix.py
```

You should see console output similar to:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## التحقق من النتيجة

لتأكيد أن الباركود يرمّز العبارة الروسية بشكل صحيح:

1. افتح ملف PNG في عارض صور.
2. استخدم أي تطبيق مسح DataMatrix (العديد من التطبيقات المحمولة تدعم ذلك) أو ماسحًا ماديًا.
3. يجب أن تعرض السلسلة المفكوكة `ABC123Привет` (أو الجزأين منفصلين حسب واجهة المستخدم في الماسح).

إذا ظهرت الأحرف الروسية كرموز غير مفهومة، تحقق مرة أخرى من أن الماسح يدعم ECI UTF‑8. معظم القارئات الحديثة تدعم ذلك، لكن الأجهزة القديمة قد تحتاج إلى تكوين صريح.

## المشكلات الشائعة وكيفية تجنّبها

| المشكلة | السبب | الحل |
|-------|-------|-----|
| نص سيريالي مشوش | مؤشر ECI مفقود | استخدم `add_eci_codetext` مع `eci_encoding=3`. |
| الباركود صغير جدًا للطابعة | حجم الوحدة الافتراضي دقيق جدًا لدقة DPI منخفضة | زيادة `x_dimension` (مثلاً `3.0` أو `4.0`). |
| الملف غير محفوظ | مسار المجلد غير صالح | تأكد من وجود `YOUR_DIRECTORY` وأنه قابل للكتابة. |
| الماسح لا يستطيع القراءة | كثافة البيانات مفرطة | قلل كمية البيانات المشفرة أو زد مستوى تصحيح الأخطاء (`generator.parameters.barcode.error_correction_level`). |

## توسيع المثال

يمكنك تعديل هذا النمط للغات أو أنواع بيانات أخرى:

* **ترميز النص الياباني أو العربي** – غيّر `eci_encoding` إلى القيمة المناسبة (مثلاً 5 لـ ISO‑8859‑5، 6 لـ ISO‑8859‑7).  
* **إضافة مقاطع ECI متعددة** – استدعِ `add_eci_codetext` عدة مرات، كل مرة بترميز مختلف.  
* **إنشاء رمز QR بدلاً من ذلك** – استبدل `EncodeTypes.DATA_MATRIX` بـ `EncodeTypes.QR`.  

جميع الخطوات الأخرى تبقى كما هي لأن `ExtCodetextBuilder` يختصر التعامل مع البايتات منخفضة المستوى.

## الخلاصة

أنت الآن تعرف كيفية **إنشاء باركود DataMatrix** في بايثون و**ترميز النص الروسي** باستخدام ميزة النص الموسع في Aspose.BarCode. السكريبت الكامل يتعامل مع تفاوض مجموعة الأحرف، إنشاء الباركود، وإخراج الصورة ببضع أسطر من الشيفرة فقط.

بعد ذلك، استكشف رموز باركود أخرى (PDF417، Aztec) أو دمج المولد في خدمة ويب تُعيد صور PNG عند الطلب. نفس المبادئ—بناء نص موسع واختيار `EncodeTypes` المناسب—تنطبق على كامل مجموعة Aspose.BarCode.

برمجة سعيدة، واستمتع بقوة إنشاء باركود متعدد اللغات!

## ما الذي ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET – دليل خطوة بخطوة](/barcode/english/net/datamatrix-barcode-configuration/)
- [إنشاء باركود DataMatrix في وضع ASCII باستخدام Aspose.BarCode لـ .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [كيفية إنشاء باركود DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}