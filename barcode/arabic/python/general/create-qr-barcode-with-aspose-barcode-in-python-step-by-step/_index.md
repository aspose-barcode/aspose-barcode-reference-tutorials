---
category: general
date: 2026-08-09
description: إنشاء رمز QR في بايثون باستخدام Aspose.BarCode. تعلم كيفية بناء نص شفرة
  موسع، وضبط المظهر، وحفظ الصورة—كل ذلك في دليل واحد.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: ar
lastmod: 2026-08-09
og_description: إنشاء رمز QR في بايثون باستخدام Aspose.BarCode. يوضح هذا الدليل كيفية
  بناء نص رمزي موسع، وضبط المعلمات البصرية، وتصدير الصورة.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: إنشاء رمز QR باستخدام Aspose.BarCode في بايثون – مثال كامل للكود
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: إنشاء رمز QR باستخدام Aspose.BarCode في بايثون – دليل خطوة بخطوة
url: /ar/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رمز QR باستخدام Aspose.BarCode في بايثون – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء رمز QR** في بايثون، فإن هذا الدليل سيقودك خلال العملية بالكامل باستخدام مكتبة Aspose.BarCode. سواءً كنت تقوم بترميز معرفات المنتجات، نص متعدد اللغات، أو بيانات مخصصة، ستتعرف على كيفية بناء نص موسع (extended codetext)، تعديل الإعدادات البصرية، وحفظ الصورة النهائية في سكريبت واحد قابل للتنفيذ.

يوضح المثال أيضًا كيفية عرض إصدار المكتبة، ما يساعدك على التحقق من أنك تستخدم نسخة متوافقة. بنهاية هذا الدليل ستحصل على صورة رمز QR جاهزة للاستخدام وفهم واضح لكل خيار من خيارات التكوين.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- Python 3.8+ مثبت.
- حزمة `aspose-barcode` (تثبيت عبر `pip install aspose-barcode`).
- إلمام أساسي بصياغة بايثون.
- صلاحية كتابة إلى دليل الإخراج حيث سيتم حفظ ملف PNG.

> **نصيحة احترافية:** استخدم بيئة افتراضية لتجنب تعارض الإصدارات مع مشاريع أخرى.

## الخطوة 1: التحقق من إصدار مكتبة Aspose.BarCode

عرض إصدار المكتبة يضمن أنك تستخدم نسخة تدعم النص الموسع وترميز QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**لماذا هذا مهم:**  
قد تفتقر الإصدارات القديمة إلى الفئة `ExtCodetextBuilder` المطلوبة للمقاطع المختلطة بين النص العادي وECI. تأكيد الإصدار يمنع حدوث أخطاء وقت التشغيل لاحقًا في سير العمل.

## الخطوة 2: بناء سلسلة نصية موسعة (extended codetext)

النص الموسع يتيح لك دمج بيانات ASCII عادية مع مقاطع Unicode (ECI)، وهو أمر أساسي لأكواد QR متعددة اللغات.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**لماذا هذا مهم:**  
طريقة `add_plain_codetext` تخزن البيانات كـ ASCII قياسي، بينما `add_eci_codetext` تُضيف بادئة كتلة Unicode بالمُعرّف المناسب لـ ECI. يضمن هذا أن قارئات QR تفسر النص الياباني بشكل صحيح، متجنبة الأحرف المشوشة.

### الاختلافات الشائعة

- **عدة مقاطع ECI:** استدعِ `add_eci_codetext` عدة مرات لدمج عدة لغات.  
- **معرفات ECI مختلفة:** استخدم `27` لـ ISO‑8859‑1، `28` لـ ISO‑8859‑2، إلخ، حسب الترميز المستهدف.

## الخطوة 3: إنشاء رمز QR باستخدام النص الموسع

الآن بعد أن أصبح لدينا سلسلة مُنسقة بشكل صحيح، يمكننا إنشاء رمز QR.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**لماذا هذا مهم:**  
`EncodeTypes.QR` يخبر Aspose.BarCode باستخدام رمزية QR. تمرير `extended_codetext` مباشرة يربط البيانات المختلطة بمصفوفة QR، محافظًا على كل من الجزء العادي والجزء Unicode.

## الخطوة 4: تعديل المظهر البصري (اختياري لكن موصى به)

ضبط المعلمات البصرية للباركود يحسن من موثوقية القراءة ويتماشى مع إرشادات العلامة التجارية.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**لماذا هذا مهم:**  
- **`x_dimension`** يتحكم في حجم كل وحدة QR؛ إذا كان صغيرًا جدًا قد يسبب أخطاء قراءة على الأجهزة منخفضة الدقة.  
- **`border_width`** يضيف منطقة هادئة. بعض القارئات تتطلب على الأقل منطقة هادئة بطول 4 وحدات؛ المكتبة تضيف ذلك تلقائيًا، لكن يمكنك زيادتها لمزيد من الأمان.

### معالجة الحالات الخاصة

- **بيانات عالية الكثافة:** إذا كان حجم البيانات المشفر كبيرًا، قد تحتاج إلى زيادة `x_dimension` أو اختيار مستوى تصحيح أخطاء أعلى (عبر `qr_generator.parameters.qr.error_correction_level`).  
- **خلفية شفافة:** اضبط `qr_generator.parameters.barcode.bg_color = Color.Transparent` للحصول على PNGs ذات قناة ألفا.

## الخطوة 5: حفظ صورة رمز QR

أخيرًا، اكتب الصورة إلى القرص بالتنسيق المفضل لديك.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**لماذا هذا مهم:**  
الحفظ بصيغة PNG يحافظ على جودة غير مضغوطة، وهو مثالي لأكواد QR التي تحتاج إلى حواف واضحة. إذا كنت تحتاج إلى تنسيق مختلف لتطبيق ويب، ما عليك سوى تغيير تعداد `BarCodeImageFormat`.

### التحقق من النتيجة

افتح الملف المحفوظ في أي عارض صور. يجب أن ترى رمز QR، وعند مسحه سيعيد السلسلة المدمجة:

```
ABC12345
こんにちは
```

معظم تطبيقات قارئ QR الحديثة تعرض الجزء العادي أولًا ثم تُظهر التحية اليابانية بشكل صحيح.

---

## البرنامج الكامل القابل للتنفيذ

انسخ الكتلة الكاملة أدناه إلى ملف باسم `create_qr_barcode.py` وشغّله باستخدام `python create_qr_barcode.py`. عدّل `YOUR_DIRECTORY` إلى مجلد قابل للكتابة على جهازك.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

تشغيل هذا السكريبت يطبع الإصدار، النص الموسع، وتأكيد إنشاء ملف PNG.

---

## الخلاصة

أنت الآن تعرف كيف **تنشئ صور رموز QR** في بايثون باستخدام Aspose.BarCode. غطى الدليل:

1. التحقق من إصدار المكتبة.  
2. بناء نص موسع باستخدام مقاطع عادية وECI (Unicode).  
3. إنشاء رمز QR.  
4. تخصيص المعلمات البصرية مثل حجم الوحدة وعرض الحدود.  
5. حفظ الصورة النهائية بصيغة PNG.

من هنا يمكنك استكشاف:

- تغيير مستويات تصحيح الأخطاء (`qr_generator.parameters.qr.error_correction_level`).  
- إضافة شعار أو صورة خلفية (`qr_generator.parameters.qr.logo`).  
- التصدير إلى صيغ أخرى مثل SVG للرسومات القابلة للتوسع على الويب.  
- دمج المولد في نقطة نهاية Flask أو Django لإنشاء رموز QR عند الطلب.

جرّب أحمال بيانات وإعدادات بصرية مختلفة لتتناسب مع هوية علامتك التجارية ومتطلبات القراءة. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شرح خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}