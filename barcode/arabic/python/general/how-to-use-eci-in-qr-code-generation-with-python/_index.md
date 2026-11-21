---
category: general
date: 2026-11-20
description: تعرّف على كيفية استخدام ECI، وإنشاء QR من النص، ومسح المُنشئ، وحفظ صورة
  QR باستخدام مكتبة الباركود للبايثون.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: ar
lastmod: 2026-11-20
og_description: كيفية استخدام ECI لإنشاء QR من النص، مسح مُنشئ QR، وحفظ صورة QR –
  دليل كامل خطوة بخطوة.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: كيفية استخدام ECI في توليد رموز QR باستخدام بايثون
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: كيفية استخدام ECI في توليد رموز QR باستخدام بايثون
url: /ar/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام ECI في إنشاء رموز QR باستخدام Python

إذا كنت تحتاج إلى **how to use eci** عند إنشاء رموز QR، فإن هذا الدليل يوضح الخطوات الدقيقة. ستتعرف على كيفية إنشاء QR من نص، مسح الـ builder، وأخيرًا حفظ صورة QR—كل ذلك ببضع أسطر من Python.

عادةً ما تتطلب رموز QR التي تحتوي على بيانات متعددة اللغات مقطع Extended Channel Interpretation (ECI) حتى يعرف القارئ أي مجموعة أحرف يجب تطبيقها. يشرح هذا البرنامج التعليمي كيفية بناء codetext ممتد، مسح الـ builder عند إعادة استخدامه، وحفظ النتيجة كملف PNG.

## المتطلبات المسبقة

- تثبيت Python 3.8+.
- حزمة Aspose.BarCode for Python via .NET (أو أي مكتبة `barcode` متوافقة توفر `ExtCodetextBuilder` و `BarcodeGenerator`).
- إلمام أساسي بمفاهيم رموز QR.

قم بتثبيت المكتبة باستخدام pip:

```bash
pip install aspose-barcode
```

> **نصيحة احترافية:** استخدم بيئة افتراضية لتجنب تعارض الإصدارات.

## الخطوة 1: استيراد الفئات المطلوبة

الفئات الأساسية التي ستعمل معها هي `ExtCodetextBuilder` لإنشاء codetext ممتد و `BarcodeGenerator` لتوليد رمز QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

تتيح لك هذه الاستيرادات الوصول إلى طرق الـ builder (`add_plain_codetext`، `add_eci_codetext`، إلخ) ووظائف الـ generator مثل `set_code_text`، `set_symbology`، و `save`.

## الخطوة 2: إنشاء وتكوين ExtCodetextBuilder

إنشاء نسخة جديدة من الـ builder هو المثال الأول الواضح على **how to use eci**. يمكنك أيضًا مسح الـ builder لاحقًا إذا احتجت إلى إعادة استخدامه.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

استدعاء `clear()` يضمن أن يبدأ الـ builder بحالة نظيفة، وهو أمر أساسي عند توليد عدة رموز QR داخل حلقة.

## الخطوة 3: إضافة نص عادي (بدون ECI) codetext

النص العادي لا يحتاج إلى مقطع ECI. استخدم `add_plain_codetext` للسلاسل المتوافقة مع ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

الـ builder الآن يحتوي على المقطع العادي `"HelloWorld"`.

## الخطوة 4: إضافة مقطع مشفر بـ ECI

هذا هو جوهر **how to use eci**: تحدد قيمة ECI (26 لـ UTF‑8) وتزود السلسلة Unicode التي تريد ترميزها. هذا يسمح لرمز QR بحمل اللغة الروسية أو الصينية أو أي لغة أخرى غير مغطاة بمجموعة ISO‑8859‑1 الافتراضية.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **لماذا هذا مهم:** بدون مؤشر ECI، سيقوم القارئ بتفسير البايتات باستخدام مجموعة الأحرف الافتراضية وسيظهر نصًا مشوشًا للنص غير ASCII.

## الخطوة 5: استرجاع سلسلة codetext الممتدة المدمجة

بعد إضافة جميع المقاطع المطلوبة، احصل على السلسلة النهائية التي سيتم تمريرها إلى مولد QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

القيمة المطبوعة تبدو شيئًا مثل:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

الصيغة الدقيقة تعتمد على المكتبة، لكن الجزء المهم هو أن علامة ECI (`[ECI26]`) تسبق الحمولة UTF‑8.

## الخطوة 6: توليد رمز QR باستخدام النص المدمج

الآن يمكنك **generate QR from text** بتمرير الـ extended codetext إلى `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

عند فتح `qr_extended.png`، سيظهر رمز QR يشفّر كلًا من السلسلة الإنجليزية العادية والتحية الروسية. مسحه باستخدام قارئ QR حديث سيظهر بشكل صحيح “HelloWorld” و “Привет”.

### لماذا يجب استدعاء `clear()` قبل إعادة استخدام الـ builder

إذا قمت بتوليد عدة رموز QR داخل حلقة، فإن نسيان مسح الـ builder سيؤدي إلى دمج المقاطع القديمة مع الجديدة، مما ينتج رمزًا غير صالح. إليك نمطًا سريعًا:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

هذا المقتطف يوضح **how to clear builder** و **how to generate QR from text** بشكل متكرر.

## الحالات الحدية والمشكلات الشائعة

| الحالة | ما الذي يجب مراقبته | كيفية المعالجة |
|-----------|-------------------|---------------|
| **قيمة ECI غير مدعومة** | المكتبة ترمي استثناء `InvalidArgumentException`. | استخدم فقط قيم ECI المذكورة في المواصفات (مثل 26 لـ UTF‑8، 20 لـ Shift‑JIS). |
| **نص مدمج طويل جدًا** | قد يتجاوز إصدار QR السعة القصوى. | زيادة إصدار QR تلقائيًا (`qr_generator.set_qr_version(QRVersion.AUTO)`) أو تقسيم البيانات عبر عدة رموز QR. |
| **أخطاء أذونات نظام الملفات** | `save` يفشل مع `IOError`. | تأكد من وجود الدليل الهدف وأن العملية لديها صلاحية كتابة. |
| **عرض مجموعة أحرف غير صحيحة** | القارئ يعرض أحرفًا مشوشة. | تحقق من أن قيمة ECI الصحيحة تتطابق مع الترميز الفعلي للسلسلة. |

## مثال كامل قابل للتنفيذ

فيما يلي سكريبت مستقل يمكنك نسخه، لصقه، وتشغيله. يتضمن جميع الاستيرادات، معالجة الأخطاء، وتعليقات للتوضيح.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

تشغيل هذا السكريبت ينتج `output/qr_extended.png`، رمز QR يشفّر بشكل صحيح كلًا من النص الإنجليزي والروسي.

## الخلاصة

أنت الآن تعرف **how to use eci** عند بناء رموز QR، وكيفية **clear the QR builder** قبل إعادة الاستخدام، وكيفية **generate QR from text**، والخطوات الدقيقة لـ **save QR image** باستخدام Python. باتباع النمط أعلاه، يمكنك تضمين أي سلسلة Unicode في رمز QR مع الحفاظ على حالة الـ builder متوقعة.

### ما التالي؟

- استكشف قيم ECI أخرى للغات مثل الصينية (ECI 20) أو ISO‑8859‑5.
- ضبط مستويات تصحيح الأخطاء (`qr_generator.set_error_correction_level`) لتحسين موثوقية المسح.
- دمج عدة مقاطع ECI في رمز QR واحد للرسائل متعددة اللغات.

برمجة سعيدة، واستمتع بإنشاء رموز QR متعددة اللغات!

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود مع ECI باستخدام Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [كيفية إنشاء صورة رمز QR في Python باستخدام Aspose.Barcode – دليل كامل](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [كيفية إنشاء باركود في Python – دليل خطوة بخطوة كامل](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}