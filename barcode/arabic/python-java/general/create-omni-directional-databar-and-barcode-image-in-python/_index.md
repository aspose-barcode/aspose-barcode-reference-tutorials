---
category: general
date: 2026-08-12
description: أنشئ شريط بيانات متعدد الاتجاهات باستخدام بايثون وتعلم كيفية إنشاء صورة
  باركود بايثون باستخدام Aspose.BarCode. اتبع الدليل خطوة بخطوة للحصول على حل كامل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: ar
lastmod: 2026-08-12
og_description: أنشئ شريط بيانات متعدد الاتجاهات باستخدام بايثون وقم بإنشاء صورة باركود
  بايثون في دقائق. يوضح هذا الدرس مثالًا كاملاً قابلاً للتنفيذ.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: إنشاء شريط بيانات متعدد الاتجاهات – دليل بايثون كامل
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: إنشاء صورة شريط بيانات وشيفرة شريطية متعددة الاتجاهات في بايثون
url: /ar/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء Omni-directional Databar وصورة الباركود في Python

إذا كنت بحاجة إلى **create omni directional databar** في مشروع Python، يوضح لك هذا الدليل كيفية القيام بذلك وأيضًا كيفية **create barcode image python** باستخدام مكتبة Aspose.BarCode. ستحصل على برنامج جاهز للتنفيذ ينتج ملفين PNG بأبعاد نسبية مختلفة.

إنشاء DataBar يتبع مواصفات Omni‑directional هو طلب شائع لتطبيقات التجزئة واللوجستيات. يغطي الدرس التثبيت، تكوين X‑dimension، ضبط نسبة العرض إلى الارتفاع، وحفظ الصور النهائية. لا توجد خدمات خارجية مطلوبة؛ كل شيء يعمل محليًا.

## ما ستحتاجه

قبل أن تبدأ، تأكد من أن لديك:

* Python 3.8 أو أحدث مثبت على جهازك.
* الوصول إلى الطرفية أو موجه الأوامر.
* صلاحية كتابة في المجلد الذي سيتم حفظ صور الباركود فيه.

الاعتماد الوحيد من طرف ثالث هو **Aspose.BarCode for Python via .NET**, الذي يدعم نوع Omni‑directional DataBar مباشرةً.

## الخطوة 1: تثبيت Aspose.BarCode للـ Python

توفر Aspose.BarCode الفئة `BarcodeGenerator` المستخدمة في مثال الشيفرة. قم بتثبيت الحزمة باستخدام `pip`:

```bash
pip install aspose-barcode
```

تتضمن الحزمة الروابط اللازمة لوقت تشغيل .NET، لذا لا تحتاج إلى تثبيت .NET SDK بشكل منفصل.

## الخطوة 2: استيراد المكتبة وإنشاء المولد

السطر الأول من البرنامج ينشئ مولدًا لـ stacked Omni‑directional DataBar. يتم استخدام قيمة GTIN‑14 `(01)12345678901231` كبيانات تجريبية.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*لماذا هذه الخطوة مهمة*: الثابت `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` يخبر المكتبة بترميز القيمة كـ Omni‑directional DataBar، وهو التنسيق المطلوب من قبل العديد من ماسحات نقاط البيع.

## الخطوة 3: ضبط X‑dimension (عرض الوحدة)

تحدد X‑dimension عرض أصغر وحدة شريط. قيمة `2` بكسل تنتج باركود واضحًا وقابلًا للقراءة دون حجم ملف مفرط.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*لماذا هذه الخطوة مهمة*: ضبط X‑dimension يتيح لك موازنة قابلية القراءة وأبعاد الصورة. قد يؤدي X‑dimension صغير جدًا إلى ظهور ضعيف على الطابعات منخفضة الدقة.

## الخطوة 4: تكوين نسبة العرض إلى الارتفاع وحفظ الصورة الأولى

نسبة العرض إلى الارتفاع تؤثر على ارتفاع DataBar الكلي بالنسبة لعرضه. نسبة `15` تخلق نمطًا بصريًا مدمجًا.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **نصيحة احترافية**: استخدم `pathlib.Path` لبناء مسار الإخراج، والذي ينشئ المجلدات المفقودة تلقائيًا.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## الخطوة 5: تغيير نسبة العرض إلى الارتفاع لنمط بصري ثانٍ وحفظ صورة أخرى

تغيير نسبة العرض إلى الارتفاع إلى `30` ينتج باركودًا أطول قد يتطلبه بعض أجهزة الماسحات المحددة.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*لماذا هذه الخطوة مهمة*: تجار التجزئة المختلفون وأجهزة المسح لديها قيود حجم مختلفة. توفير كلتا النسبتين في برنامج واحد يتيح لك إنشاء النمط الدقيق الذي تحتاجه دون تكرار الشيفرة.

## البرنامج الكامل – create omni directional databar و create barcode image python

فيما يلي المثال الكامل القابل للتنفيذ الذي يدمج جميع الخطوات السابقة. احفظه باسم `generate_databar.py` وشغّله باستخدام `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### النتيجة المتوقعة

تشغيل البرنامج ينشئ الملفات التالية:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

كلا الصورتين تعرضان Omni‑directional DataBar صالح يمكن مسحه بواسطة معدات التجزئة القياسية.

![مثال على إنشاء شريط بيانات Omni-directional وصورة باركود في Python](example_databar.png "إنشاء شريط بيانات Omni-directional وصورة باركود في Python")

*الصورة أعلاه هي عنصر نائب يوضح ملفي PNG المحفوظين.*

## معالجة المشكلات الشائعة

| المشكلة | السبب | الحل |
|-------|--------|-----|
| `ImportError: No module named aspose` | لم يتم تثبيت Aspose.BarCode أو تم تثبيته في بيئة مختلفة. | فعّل البيئة الافتراضية الصحيحة وشغّل `pip install aspose-barcode`. |
| `PermissionError` when saving | البرنامج يفتقر إلى صلاحية الكتابة للمجلد المستهدف. | اختر دليلًا تملكه أو شغّل البرنامج بصلاحيات مناسبة. |
| Barcode does not scan | X‑dimension منخفض جدًا أو نسبة العرض إلى الارتفاع غير متوافقة مع الماسح. | زد قيمة `x_dimension.pixels` إلى 3 أو 4، واختبر قيمًا مختلفة لـ `aspect_ratio` (مثلاً 20، 25). |
| Missing .NET runtime | Aspose.BarCode يعتمد على وقت تشغيل .NET على Windows/Linux. | ثبّت أحدث وقت تشغيل .NET من موقع Microsoft؛ توثيق الحزمة يوفر إرشادات خاصة بالمنصات. |

## توسيع المثال

يمكنك تعديل البرنامج لتوليد متغيرات DataBar أخرى (مثل `DATABAR_STACKED`، `DATABAR_EXPANDED`). استبدل الثابت `EncodeTypes` وفقًا لذلك:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

إذا كنت بحاجة إلى تضمين الباركود في PDF، يمكن لـ Aspose.PDF للـ Python استيراد ملف PNG مباشرةً أو يمكنك استخدام طريقة `save` مع `BarCodeImageFormat.Pdf`.

## الخلاصة

أظهر هذا الدرس كيفية **create omni directional databar** وكيفية **create barcode image python** باستخدام Aspose.BarCode. لديك الآن برنامج كامل وقابل لإعادة الإنتاج يولد ملفي PNG بأبعاد نسبية مختلفة، ويتعامل مع المشكلات الشائعة، ويمكن توسيعه لتنسيقات باركود أخرى.

بعد ذلك، استكشف إنشاء رموز QR، إضافة الباركود إلى فواتير PDF، أو أتمتة المعالجة الدفعية لكاتالوجات الكبيرة للمنتجات. كل من هذه المواضيع يبني على نمط `BarcodeGenerator` نفسه الموضح هنا. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

- [إنشاء صورة باركود – قسيمة GS1 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [إنشاء صورة باركود DotCode – الصفوف والأعمدة (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [كيفية إنشاء صورة باركود وعرضها في Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}