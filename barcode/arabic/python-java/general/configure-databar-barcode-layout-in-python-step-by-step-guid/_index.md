---
category: general
date: 2026-08-12
description: قم بتكوين تخطيط الباركود Databar في بايثون بسرعة. تعلّم كيفية تعيين الأعمدة
  والصفوف وحفظ الصور باستخدام مكتبة مولّد الباركود.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: ar
lastmod: 2026-08-12
og_description: قم بتكوين تخطيط الباركود Databar في بايثون للتحكم في الأعمدة والصفوف
  وإخراج الصورة. اتبع هذا الدليل للحصول على حل جاهز للتنفيذ.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: تكوين تخطيط الباركود Databar في بايثون – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: تكوين تخطيط الباركود Databar في بايثون – دليل خطوة بخطوة
url: /ar/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين تخطيط الباركود Databar في بايثون – دليل خطوة بخطوة

إذا كنت بحاجة إلى **configure Databar barcode layout in Python**، فهذا الدليل يشرح لك العملية بالكامل. ستتعرف على كيفية ضبط عدد الأعمدة أو الصفوف لباركود Databar Expanded Stacked وكيفية حفظ الصورة الناتجة باستدعاء واحد لمكتبة مولد الباركود.

التحكم في التخطيط أمر أساسي عندما تقوم بدمج الباركود على عبوات ضيقة، إيصالات، أو شاشات الهواتف المحمولة. في الأقسام أدناه سنغطي الاستيرادات المطلوبة، خيارَي التخطيط (الأعمدة والصفوف)، وأفضل الممارسات لحفظ صورة PNG نظيفة.

## ما ستحتاجه

* Python 3.8 أو أحدث
* `aspose.barcode` (أو أي حزمة توليد باركود متوافقة) مثبتة  
  ```bash
  pip install aspose-barcode
  ```
* صلاحية كتابة في مجلد سيتم تخزين ملفات PNG فيه

لا توجد أدوات خارجية إضافية مطلوبة—المكتبة تتعامل مع التصيير، التحجيم، وترميز الصورة داخليًا.

## كيفية تكوين تخطيط الباركود Databar في بايثون

جوهر الحل هو الفئة `BarcodeGenerator`. تقبل تعداد `EncodeTypes` الذي يحدد نوع الباركود—في هذه الحالة `EncodeTypes.DatabarExpandedStacked`. بعد إنشاء المولد يمكنك تعديل التخطيط عن طريق ضبط خصائص `columns` أو `rows` في كائن معلمة `data_bar`.

### الخطوة 1: استيراد الفئات المطلوبة

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

هذه الاستيرادات تمنحك الوصول إلى المولد، التعداد لأنواع Databar، وثابت صيغة صورة PNG.

### الخطوة 2: إنشاء مولد باركود لـ Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*لماذا هذه الخطوة؟*  
`EncodeTypes.DatabarExpandedStacked` يخبر المكتبة بإنتاج رموز **Databar Expanded Stacked**، التي تدعم سلاسل رقمية أطول مع الحفاظ على بصمة مدمجة. الوسيط الثاني هو البيانات التي سيتم ترميزها؛ يمكن أن تكون أي سلسلة تفي بمواصفات Databar.

### الخطوة 3: ضبط عدد الأعمدة (تخطيط أفقي)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** هي العبارة المفتاحية لهذه العملية. عندما تزيد عدد الأعمدة، ينتشر الباركود أفقيًا، مما قد يكون مفيدًا للملصقات العريضة. المكتبة تعيد حساب عرض الوحدة تلقائيًا للحفاظ على حجم إجمالي ثابت.

#### نصيحة احترافية
الحد الأقصى لعدد الأعمدة في Databar Expanded Stacked هو 8. ضبط قيمة أعلى من الحد سيقيدها إلى الحد الأقصى، ولكن من الأفضل التحقق من صحة الإدخال مسبقًا.

### الخطوة 4: حفظ صورة الباركود بتخطيط الأعمدة

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** هو الإجراء الذي يكتب الباركود المصدَّر إلى القرص. PNG صيغة غير مضغوطة، مما يحافظ على الحواف الحادة المطلوبة للمسح الموثوق.

### الخطوة 5: إنشاء مولد ثانٍ لنفس نوع الباركود (تخطيط صفوف)

إذا كنت تفضل تكدسًا عموديًا، فستعمل مع الصفوف بدلاً من الأعمدة. الكود أدناه يعيد استخدام نفس القيمة لكنه ينشئ نسخة جديدة من `BarcodeGenerator` لتجنب خلط إعدادات الأعمدة والصفوف.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### الخطوة 6: ضبط عدد الصفوف (تخطيط عمودي)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** ترتب وحدات الباركود عموديًا. تخطيط من ثلاثة صفوف يقلل ارتفاع كل مجموعة فردية، مما يجعل الباركود مناسبًا للإيصالات الضيقة أو شاشات الهواتف المحمولة.

#### حالة خاصة
إذا ضبطت `rows` إلى 1، فإن المكتبة تُنشئ Databar صفًا واحدًا (ما يعادل Databar القياسي). القيم الأقل من 1 تُتجاهل وتُعاد إلى الإعداد الافتراضي (صف واحد).

### الخطوة 7: حفظ صورة الباركود بتخطيط الصفوف

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

مرة أخرى، نحن **save barcode image** باستخدام PNG للحفاظ على وضوح النتيجة.

## مثال كامل قابل للتنفيذ

جمع كل الأجزاء معًا يمنحك سكريبت مستقل يمكنك إدراجه في أي مشروع بايثون.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**الناتج المتوقع**

تشغيل السكريبت ينشئ ملفين PNG:

* `output/ExpandedCols4.png` – باركود ممتد عبر أربعة أعمدة
* `output/ExpandedRows3.png` – باركود مضغوط في ثلاثة صفوف

يمكن فتح كلتا الصورتين في أي عارض صور أو استيرادهما مباشرةً إلى فواتير PDF، قوالب الملصقات، أو صفحات الويب.

## الأسئلة الشائعة واستكشاف الأخطاء وإصلاحها

| السؤال | الإجابة |
|----------|--------|
| *ماذا لو كان الباركود غير واضح؟* | زيادة دقة الصورة عن طريق ضبط `barcode_generator.parameters.image_width` و `image_height` قبل استدعاء `save`. |
| *هل يمكنني استخدام صيغ صور أخرى؟* | نعم. استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Gif` حسب الحاجة. |
| *هل هناك حد لطول البيانات؟* | Databar Expanded Stacked يدعم حتى 74 حرفًا رقميًا. تجاوز الحد يرفع استثناء `ArgumentException`. |
| *كيف يمكنني تغيير لون المقدمة؟* | استخدم `barcode_generator.parameters.barcode.color = Color.Blue` (استورد `System.Drawing.Color`). |
| *هل يمكنني دمج الأعمدة والصفوف؟* | لا. الـ API يعامل الأعمدة والصفوف كأنماط تخطيط متعارضة. اختر أحدهما لكل مثال باركود. |

## الخطوات التالية

الآن بعد أن يمكنك **configure Databar barcode layout**، فكر في استكشاف المواضيع ذات الصلة التالية:

* **إضافة تسميات نصية** – استخدم `barcode_generator.parameters.barcode.code_text` لعرض القيمة المشفرة أسفل الصورة.
* **دمج الباركود في PDF** – اجمع PNG المُولد مع `aspose.pdf` لإنشاء مستندات قابلة للطباعة.
* **تحجيم ديناميكي** – احسب عدد الأعمدة أو الصفوف المثالي بناءً على أبعاد الملصق أثناء التشغيل.
* **معالجة دفعات** – كرر عبر ملف CSV لأكواد المنتجات لتوليد مكتبة من صور الباركود تلقائيًا.

جرّب قيمًا مختلفة للأعمدة والصفوف لترى كيف تؤثر على موثوقية المسح على أجهزتك المستهدفة. كلما اختبرت أكثر، كلما فهمت أفضل التوازنات بين حجم الباركود، قابليته للقراءة، وقيود المساحة.

---

*برمجة سعيدة! إذا وجدت هذا الدليل مفيدًا، شاركه مع زملائك أو اترك تعليقًا حول تحديات التخطيط التي واجهتها.*

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}