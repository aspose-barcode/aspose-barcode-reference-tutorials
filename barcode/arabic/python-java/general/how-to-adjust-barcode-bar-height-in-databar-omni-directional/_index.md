---
category: general
date: 2026-11-27
description: تعلم كيفية ضبط ارتفاع خطوط الباركود في مولد باركود DataBar Omni‑Directional.
  يوضح الكود خطوة بخطوة ضبط الارتفاعات إلى 30 بكسل و60 بكسل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: ar
lastmod: 2026-11-27
og_description: قم بضبط ارتفاع شريط الباركود في مولد باركود DataBar Omni‑Directional
  باستخدام بايثون. اتبع الدليل الكامل لضبط الارتفاعات، البُعد X، وحفظ صور PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: ضبط ارتفاع شريط الباركود في مولد DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: كيفية تعديل ارتفاع شريط الباركود في مولد DataBar Omni‑Directional
url: /ar/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضبط ارتفاع شريط الباركود في مولد DataBar Omni‑Directional

إذا كنت بحاجة إلى **ضبط ارتفاع شريط الباركود** لباركود DataBar Omni‑Directional، فإن هذا الدليل يوضح لك بالضبط كيفية القيام بذلك. سترى مثالًا كاملًا وقابلًا للتنفيذ بلغة Python يغيّر ارتفاع الشريط من 30 بكسل إلى 60 بكسل مع الحفاظ على بُعد X وتنسيق الصورة ثابتين.

تغيير أبعاد الباركود البصرية هو طلب شائع عندما يجب أن يتناسب الباركود مع حجم ملصق محدد أو دليل تصميم. بالإضافة إلى ارتفاع الشريط، قد ترغب أيضًا في تعديل **X‑dimension** (حجم الوحدة) أو اختيار **تنسيق صورة الباركود** مختلف مثل PNG أو JPEG.

في هذا البرنامج التعليمي سوف:

* تثبيت المكتبة المطلوبة (GroupDocs.Barcode for Python)
* إنشاء مولد باركود DataBar Omni‑Directional
* ضبط حجم الوحدة باستخدام `XDimension`
* تعديل خاصية ارتفاع الشريط مرتين
* حفظ الصور الناتجة بالتنسيق المطلوب **BarCodeImageFormat**

لا تحتاج إلى أي خبرة سابقة مع GroupDocs API—فقط معرفة أساسية بلغة Python.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

* Python 3.8 أو أحدث مثبت
* حزمة `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* صلاحية كتابة في مجلد سيتم حفظ ملفات PNG فيه

إذا لم تكن على دراية بـ **باركود DataBar Omni‑Directional**، فهو يشفّر رقم GTIN مكوّن من 14 رقمًا ويُستخدم على نطاق واسع في التجزئة للمسح من أي اتجاه.

## الخطوة 1: إعداد مولد باركود DataBar Omni‑Directional

أولاً، استورد الفئات الضرورية وأنشئ المولد باستخدام بيانات GTIN التي تريد تشفيرها.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*لماذا هذا مهم:* ثابت `EncodeTypes.DatabarOmniDirectional` يخبر المكتبة بإنتاج الترميز Omni‑Directional. سلسلة البيانات تشمل AI `(01)` الذي يحدد قيمة GTIN‑14.

## الخطوة 2: تعريف X‑dimension (حجم الوحدة)

يُتحكم X‑dimension في عرض أضيق شريط. قيمة شائعة للعرض على الشاشة هي **2 بكسل لكل وحدة**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

استخدام **set XDimension** المتسق يضمن أن يتناسب الباركود بشكل صحيح عبر مختلف الطابعات والماسحات.

## الخطوة 3: ضبط ارتفاع الشريط إلى 30 بكسل وحفظ الصورة

الآن نغيّر خاصية ارتفاع الشريط. الارتفاع الأول الذي سنستخدمه هو **30 بكسل**، وهو مناسب للملصقات الصغيرة.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

الثابت `BarCodeImageFormat.Png` يحدد **تنسيق صورة الباركود** PNG، والذي يحافظ على جودة غير مضغوطة.

### النتيجة المتوقعة

الملف `DatabarBarHeight30Pixels.png` يحتوي على باركود DataBar Omni‑Directional ارتفاع أشرطةه 30 بكسل. أدناه معاينة مؤقتة:

![باركود DataBar بارتفاع شريط 30 بكسل](images/databar_30px.png "باركود DataBar بارتفاع شريط 30 بكسل")

> **نصيحة:** إذا فتحت ملف PNG في محرر صور، سترى ارتفاع الشريط الدقيق. الأشرطة الضيقة عرضها 2 بكسل، كما تم تعريفه سابقًا.

## الخطوة 4: تغيير ارتفاع الشريط إلى 60 بكسل لباركود أعلى

للتطبيقات التي تتطلب مساحة بصرية أكبر—مثل ملصق الشحن—يمكنك زيادة ارتفاع الشريط إلى **60 بكسل**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

فقط خاصية `BarHeight` هي التي تتغير؛ يبقى X‑dimension والترميز كما هما، لذا يظل الباركود قابلًا للمسح.

## الخطوة 5: حفظ صورة الباركود المحدثة

أخيرًا، احفظ الباركود الأعلى في ملف PNG ثاني.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### النتيجة المتوقعة

الملف `DatabarBarHeight60Pixels.png` يُظهر نفس البيانات المشفرة، لكن كل شريط الآن ارتفاعه 60 بكسل. الفرق البصري موضح أدناه:

![باركود DataBar بارتفاع شريط 60 بكسل](images/databar_60px.png "باركود DataBar بارتفاع شريط 60 بكسل")

## مثال كامل وقابل للتنفيذ

بجمع كل ما سبق، إليك السكريبت الكامل الذي يمكنك نسخه‑ولصقه في ملف باسم `adjust_barcode_height.py` وتشغيله مباشرة.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

تشغيل البرنامج النصي:

```bash
python adjust_barcode_height.py
```

يجب أن ترى ملفي PNG في مجلد `output`، كلٌ يعكس ارتفاع الشريط الذي حددته.

## أسئلة شائعة وحالات خاصة

| السؤال | الجواب |
|----------|--------|
| **هل يمكنني استخدام JPEG بدلاً من PNG؟** | نعم. استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg`. JPEG طريقة ضغط فقدان، لذا يُفضَّل PNG للمسح الدقيق. |
| **ماذا لو احتجت إلى ارتفاع شريط ليس مضاعفًا للـ10؟** | خاصية `BarHeight.Pixels` تقبل أي قيمة صحيحة. فقط عيّن عدد البكسلات المطلوب (مثال: `45`). |
| **هل يؤثر تغيير ارتفاع الشريط على البيانات المشفرة؟** | لا. يتغير فقط التمثيل البصري؛ تظل سلسلة البيانات الأساسية هي نفسها. |
| **كيف أغيّر X‑dimension بعد حفظ الصورة الأولى؟** | يمكنك تعديل `gen.parameters.barcode.x_dimension.pixels` في أي وقت قبل استدعاء `save()`. سيُطبق التغيير على الصور اللاحقة. |
| **هل المولد آمن للاستخدام المتعدد الخيوط؟** | لا يُضمن أن كائن `BarcodeGenerator` آمن للاستخدام المتعدد الخيوط. أنشئ نسخة منفصلة لكل خيط إذا كنت تولّد باركودات بشكل متزامن. |

## الخلاصة

أنت الآن تعرف **كيفية ضبط ارتفاع شريط الباركود** في مولد DataBar Omni‑Directional باستخدام Python. غطى الدليل إنشاء المولد، ضبط **X‑dimension**، تعديل خاصية **ارتفاع شريط الباركود**، وحفظ الصور بالتنسيق المطلوب **barcode image format**.

من هنا يمكنك تجربة ارتفاعات أخرى، أحجام وحدات مختلفة، أو التحويل إلى تنسيقات صور بديلة مثل JPEG أو BMP. قد تستكشف أيضًا ميزات إضافية لمولد الباركود في Python مثل إضافة نص قابل للقراءة البشرية أو تغيير مخططات الألوان.

برمجة سعيدة، واحرص على أن تكون باركوداتك واضحة ومقاسة بدقة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية ضبط العرض وتعديل الارتفاع لباركود GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [إنشاء صورة باركود DataBar Omni‑Directional في Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net مولد باركود – تغيير ارتفاع الباركود](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}