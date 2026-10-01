---
category: general
date: 2026-07-30
description: إنشاء رمز شريطي Databar Stacked Omnidirectional باستخدام بايثون. اتبع
  هذا الدليل خطوة بخطوة لتكوين نسبة العرض إلى الارتفاع، XDimension، وتصدير PNG باستخدام
  مولد رموز شريطية بايثون.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: ar
lastmod: 2026-07-30
og_description: إنشاء باركود Databar Stacked Omnidirectional باستخدام بايثون. يوضح
  هذا الدرس كيفية ضبط XDimension، تعديل نسبة أبعاد DataBar، وحفظه كملف PNG باستخدام
  BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: إنشاء باركود داتابار مكدس متعدد الاتجاهات – دليل بايثون
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: إنشاء باركود داتابار مكدس متعدد الاتجاهات باستخدام بايثون
url: /ar/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رمز شريطي Databar مكدس متعدد الاتجاهات في بايثون

هل احتجت يوماً إلى **إنشاء رمز شريطي databar مكدس متعدد الاتجاهات** في بايثون لكنك لم تكن متأكدًا من أين تبدأ؟ لست وحدك—العديد من المطورين يواجهون هذه الصعوبة عندما يتعاملون لأول مرة مع الفئة `BarcodeGenerator`. الخبر السار هو أن العملية بأكملها بسيطة إلى حد كبير بمجرد أن تفهم الخصائص الأساسية.

في هذا الدليل سنستعرض مثالًا كاملاً قابلاً للتنفيذ يستخدم **مولد رموز شريطية بايثون** لتعيين XDimension، وضبط نسبة أبعاد DataBar، وأخيرًا تصدير ملفي PNG. في النهاية ستحصل على فهم قوي لكيفية توليد رموز مكدسة متعددة الاتجاهات عالية الجودة لأي مشروع جرد أو لوجستيات.

## ما ستتعلمه

- كيفية إنشاء مولد **databar stacked omnidirectional** مع حمولة GTIN‑14.  
- لماذا حجم بكسل **XDimension** مهم لموثوقية القراءة.  
- تأثير **نسبة أبعاد DataBar** على عرض الصف مقابل ارتفاعه.  
- كيفية حفظ النتيجة كملف **BarCodeImageFormat PNG**.  
- نصائح لإعادة استخدام نفس كائن المولد لإنتاج متغيرات متعددة دون استهلاك إضافي للذاكرة.

### المتطلبات المسبقة

- Python 3.8+ (المكتبة التي نستخدمها هي بايثون صافية، لا تحتاج إلى حزم مترجمة).  
- حزمة `barcode-generator` (تثبيت عبر `pip install barcode-generator`).  
- مجلد يمكنك الكتابة فيه – سيقوم السكربت بحفظ ملفي PNG هناك.

إذا كنت مرتاحًا مع استيراد الوحدات الأساسية في بايثون والبرمجة الكائنية، فأنت جاهز للبدء.

## إنشاء رمز شريطي Databar مكدس متعدد الاتجاهات – نظرة عامة على الخطوات

فيما يلي نقسم سير العمل إلى ست خطوات صغيرة. كل خطوة عبارة عن قطعة شفرة مستقلة يمكنك نسخها ولصقها في REPL أو ملف سكربت. لا تتردد في التجربة—تغيير نسبة الأبعاد أو XDimension سيعطيك نمطًا بصريًا مختلفًا على الفور.

---

## الخطوة 1: إنشاء مولد Databar مكدس متعدد الاتجاهات

أول ما نقوم به هو **إنشاء مولد databar stacked omnidirectional**، مع تمرير تعداد `EncodeTypes` المناسب وسلسلة البيانات.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **لماذا هذا مهم:** علم `EncodeTypes.DatabarStackedOmniDirectional` يخبر المكتبة بإنتاج رمز مكدس متعدد الاتجاهات، وهو النوع الوحيد من DataBar الذي يمكنه ترميز ما يصل إلى 14 رقمًا مع إمكانية القراءة من أي زاوية.

---

## ضبط حجم بكسل XDimension

حجم بكسل **XDimension** يتحكم في أصغر وحدة (أرفع شريط أسود). قيمة `2` بكسل تعمل جيدًا لمعظم سيناريوهات العرض على الشاشة.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **نصيحة محترف:** إذا كنت تخطط لطباعة الرمز الشريطي بدقة DPI عالية، قم بزيادة هذه القيمة إلى 3 أو 4 لتجنب الحواف الضبابية.

---

## تعديل نسبة أبعاد DataBar (15)

نسبة **DataBar** تحدد مدى عرض كل صف مقارنة بارتفاعه. نسبة `15` تنتج صفوفًا أوسع، وهو ما يفضله العديد من القارئات لالتقاط الحركة السريعة.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **لماذا 15؟** المواصفة الرسمية لـ GS1 توصي بنسبة بين 10 و20 للرموز المكدسة متعددة الاتجاهات. نختار `15` كقيمة افتراضية متوازنة.

---

## تصدير الرمز الشريطي كـ PNG باستخدام BarCodeImageFormat

بعد ضبط المولد، نقوم بحفظ الصورة. تعداد `BarCodeImageFormat.Png` يضمن إخراجًا بدون فقدان، مثالي للمعالجة اللاحقة.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **ما ستراه:** افتح ملف PNG الناتج؛ ستلاحظ رمزًا شريطيًا نظيفًا وعالي التباين مع صفوف واسعة نسبيًا.

---

## تغيير نسبة أبعاد DataBar إلى 30

أحيانًا تحتاج إلى صفوف أطول بدلاً من أوسع—ربما لتناسب ملصقًا ضيقًا. تغيير **نسبة أبعاد DataBar** إلى `30` يجعل كل صف أطول.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **حالة حافة:** النسب العالية جدًا (مثلاً >40) قد تجعل الرمز الشريطي يتجاوز ارتفاعات الملصقات الشائعة، لذا اختبره على طابعة فعلية قبل الاعتماد النهائي.

---

## تصدير الرمز الشريطي مرة أخرى مع النسبة الجديدة

أخيرًا، نعيد استخدام كائن `barcode_generator` نفسه لكتابة ملف PNG ثاني. لا حاجة لإنشاء مولد جديد—فقط غيّر الخاصية واستدعِ `Save` مرة أخرى.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **النتيجة:** ستحصل الآن على ملفي PNG—أحدهما بصفوف عريضة (`AR15`) والآخر بصفوف طويلة (`AR30`). قارنهما جنبًا إلى جنب لتقرر أيهما الأنسب لإعداد القارئ لديك.

---

## مثال كامل يعمل

نجمع كل ما سبق في سكربت كامل يمكنك تشغيله فورًا. استبدل `YOUR_DIRECTORY` بمسار مطلق على جهازك.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**الناتج المتوقع** (في وحدة التحكم):

```
✅ Two PNG files created – AR15 and AR30
```

وسيظهر ملفا صورة في المجلد المستهدف، جاهزين لاختبارات المسح.

---

## الخلاصة

لقد **أنشأنا رموز شريطية databar stacked omnidirectional** في بايثون، وضبطنا **حجم بكسل XDimension**، وجربنا إعدادين مختلفين لـ **نسبة أبعاد DataBar**، وصدرنا النتائج كملفات **BarCodeImageFormat PNG**. يكتمل سير العمل في بضع أسطر فقط، لكنه يمنحك تحكمًا كاملًا في الخصائص البصرية التي تهم القارئات.

ما الخطوة التالية؟ جرّب تغيير الحمولة إلى GTIN مختلف، أو العب بالألوان بتحويل PNG إلى صورة ذات لوحة ألوان، أو أنشئ تقرير PDF يضم كلا الملفين PNG جنبًا إلى جنب. فئة `BarcodeGenerator` مرنة بما يكفي للتعامل مع جميع هذه السيناريوهات، لذا لا تتردد في التجربة.

هل لديك أسئلة حول حالة استخدام معينة أو صادفت خطأ؟ اترك تعليقًا أدناه، وسأكون سعيدًا بالمساعدة. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف نهج تنفيذ بديلة في مشاريعك.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}