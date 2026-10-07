---
category: general
date: 2026-09-23
description: تعلم كيفية إنشاء باركود Code 128 وحفظ صورة الباركود باستخدام Aspose.BarCode
  في بايثون – دليل خطوة بخطوة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: ar
lastmod: 2026-09-23
og_description: إنشاء رمز شريطي Code 128 وحفظ صورة الرمز الشريطي باستخدام Aspose.BarCode
  في بايثون. اتبع هذا المثال الكامل لإنشاء وتخصيص وتصدير الرمز الشريطي كملف PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: إنشاء باركود Code 128 وحفظ صورة الباركود – دليل بايثون
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: كيفية إنشاء باركود Code 128 وحفظ صورة الباركود باستخدام Aspose.BarCode
url: /ar/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود Code 128 وحفظ صورة الباركود باستخدام Aspose.BarCode

إذا كنت بحاجة إلى **إنشاء باركود Code 128** و**حفظ صورة الباركود** في مشروع Python، يوضح هذا الدرس الخطوات الدقيقة. باستخدام `ExtCodetextBuilder` من Aspose.BarCode يمكنك دمج نص عادي وقطاعات Unicode في حمولة واحدة، ثم تصيير النتيجة كملف PNG.

سترى سكريبت كامل قابل للتنفيذ، شرحًا لكل سطر، ونصائح للتعامل مع المشكلات الشائعة مثل معالجة ترميز ECI أو اختيار المجلد الصحيح للإخراج. لا تحتاج إلى وثائق خارجية—فقط انسخ، الصق، وشغّل.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* Python 3.8+ مثبت.
* حزمة `aspose.barcode` (قم بالتثبيت عبر `pip install aspose-barcode`).
* صلاحية كتابة في الدليل الذي سيُحفظ فيه ملف PNG.

يعمل الكود مع أي رموز مدعومة من Aspose.BarCode، لكن المثال يركز على **Code 128** لأنه يشفّر البيانات الأبجدية الرقمية بكفاءة ويدعم مجموعات الأحرف الموسعة.

## الخطوة 1: استيراد الفئات المطلوبة

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*لماذا هذه الخطوة؟* يتيح لك استيراد الفئات الوصول إلى الباني للرموز الموسعة، والكاتب الذي ينشئ الصورة، ومساعد الإصدار الذي يمكن أن يكون مفيدًا لتصحيح تحديثات المكتبة.

## الخطوة 2: بناء النص الموسع للرمز

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

يسمح لك `ExtCodetextBuilder` بخلط بيانات ASCII العادية وUnicode في حمولة باركود واحدة. البايت ECI (Extended Channel Interpretation) `0x03` يخبر القارئ أن البايتات التالية مُشفّرة بـ UTF‑8، وهو أمر أساسي للغات مثل الروسية، الصينية، أو العربية.

## الخطوة 3: تكوين كاتب الباركود لـ Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

تعيين `encode_type` إلى `CODE_128` يوجه الكاتب لتصنيع **باركود Code 128**. خاصية `code_text` تستقبل السلسلة الموسعة التي تم بناؤها في الخطوة السابقة.

## الخطوة 4: حفظ صورة الباركود كملف PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

طريقة `save` تكتب الباركود إلى ملف. استخدام `BarCodeImageFormat.PNG` يضمن ضغطًا بدون فقدان وتوافقًا واسعًا مع تطبيقات الويب والهواتف المحمولة.

## الخطوة 5 (اختياري): التحقق من إصدار مكتبة Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

معرفة الإصدار الدقيق للمكتبة يساعد عندما تحتاج إلى الإبلاغ عن أخطاء أو مقارنة السلوك بين الإصدارات.

## النتيجة المتوقعة

تشغيل السكريبت ينتج مخرجات في وحدة التحكم مشابهة لـ:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

ملف PNG المُولَّد (`extended_codetext.png`) يبدو هكذا:

![باركود Code 128 تم إنشاؤه باستخدام Python وحُفظ كصورة PNG](images/code128_extended.png)

*الصورة تُظهر باركود Code 128 يشفّر كلًا من سلسلة ASCII `ABC123` والكلمة الروسية “Пример”.*

## الأسئلة الشائعة ومعالجة الحالات الخاصة

| السؤال | الجواب |
|----------|--------|
| **هل يمكنني استخدام رموز أخرى؟** | نعم. استبدل `BarCodeEncodeMode.CODE_128` بأي وضع مدعوم آخر مثل `QR` أو `EAN_13` أو `PDF_417`. |
| **ماذا لو احتوى نص Unicode على رموز تعبيرية (إيموجي)؟** | الرموز التعبيرية هي أيضًا أحرف UTF‑8، لذا نفس استدعاء `add_eci_codetext` يعمل. تأكد من أن القارئ المستهدف يدعم الـ ECI الذي تستخدمه. |
| **كيف أغيّر حجم الصورة؟** | اضبط `writer.x_dimension` و `writer.bar_height` قبل استدعاء `save`. |
| **أي مجلد يجب أن أستخدمه لـ `output_path`؟** | أي مجلد يمكن لعملية Python الكتابة فيه. استخدم `os.makedirs` مع `exist_ok=True` لإنشائه تلقائيًا. |

## نصائح احترافية

* **تجنّب كتابة المسارات صراحةً.** استخدم `os.path.join` و `Path` من وحدة `pathlib` لضمان التوافق عبر الأنظمة.
* **تحقق من صحة الباركود.** بعد الحفظ، يمكنك قراءة الصورة مرة أخرى باستخدام `barcode.BarCodeReader` للتأكد من أن النص المشفر يطابق `extended_codetext`.
* **نصيحة الأداء.** إذا كنت تُنشئ العديد من الباركودات داخل حلقة، أعد استخدام كائن `BarCodeWriter` واحد وقم فقط بتحديث `code_text` في كل تكرار.

## الخلاصة

أصبحت الآن تعرف كيفية **إنشاء باركود Code 128** ببيانات ASCII وUnicode مختلطة و**حفظ صورة الباركود** كملف PNG باستخدام Aspose.BarCode في Python. يغطي السكريبت الكامل بناء النص الموسع، تكوين الكاتب، تصدير الصورة، والتحقق من إصدارات المكتبة.

من هنا يمكنك استكشاف:

* إضافة ألوان الخلفية/المقدمة (`writer.back_color`، `writer.fore_color`).
* تضمين الباركود في ملفات PDF باستخدام `Aspose.PDF`.
* استخدام فئة `BarCodeReader` لفك تشفير الصورة المحفوظة والتحقق من المحتوى تلقائيًا.

برمجة سعيدة، ولا تتردد في تجربة رموز أخرى وصيغ صور مختلفة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}