---
category: general
date: 2026-10-28
description: تعرّف على كيفية إنشاء نص مشفر موسّع في بايثون باستخدام ExtCodetextBuilder.
  يتضمن بيانات عادية ومشفّرة بـ ECI، كود خطوة بخطوة ونصائح لأفضل الممارسات.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: ar
lastmod: 2026-10-28
og_description: إنشاء نص شفري موسع في بايثون باستخدام ExtCodetextBuilder. يوضح هذا
  الدرس التعامل مع البيانات العادية والبيانات المشفرة بـ ECI، ويقدم كودًا قابلاً للتنفيذ
  بالكامل، بالإضافة إلى الأخطاء الشائعة.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: إنشاء نص برمجي موسع في بايثون – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: كيفية إنشاء نص شفرة موسع في بايثون باستخدام ExtCodetextBuilder
url: /ar/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء نص رمزي موسع في بايثون باستخدام ExtCodetextBuilder

إذا كنت بحاجة إلى **create extended codetext** لتطبيقات الباركود أو مصفوفة البيانات، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك في بايثون. ستتعرف على كيفية دمج النص العادي، إضافة أقسام ECI (Extended Channel Interpretation) للأحرف Unicode، واسترجاع سلسلة واحدة مُنسقة بشكل صحيح جاهزة للترميز.

يغطي الدرس كل شيء بدءًا من تثبيت المكتبة المطلوبة إلى التعامل مع الحالات الحدية مثل قيم ECI غير المدعومة. في النهاية ستحصل على نمط قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع يحتاج إلى **create extended codetext**.

## ما ستتعلمه

* دور `ExtCodetextBuilder` عند بناء سلاسل ذات ترميز مختلط.  
* كيفية **add plain codetext** و **add ECI codetext** في نسخة واحدة من الـ builder.  
* كيفية التحقق من المخرجات النهائية ومعالجة المشكلات الشائعة.  
* تنويعات لمجموعات الأحرف الأخرى (مثل ISO‑8859‑1، Shift‑JIS).  

### المتطلبات المسبقة

* Python 3.8 أو أحدث.  
* حزمة `extcodetext` (أو مكتبة مشابهة توفر `ExtCodetextBuilder`). قم بتثبيتها باستخدام:

```bash
pip install extcodetext
```

* إلمام أساسي بـ Unicode وقيم ECI – ECI 3 يطابق UTF‑8، ECI 4 يطابق ISO‑8859‑1، إلخ.

> **Pro tip:** احتفظ بجدول مرجعي لأرقام ECI قريبًا. يساعد ذلك في تجنب التطابقات غير المقصودة بين الترميز المعلن وتسلسل البايتات الفعلي.

## فهم ExtCodetextBuilder

`ExtCodetextBuilder` أداة صغيرة تقوم بدمج عدة شظايا نصية مع إدراج علامات ECI المطلوبة تلقائيًا. علامة ECI تخبر مُرمّز الباركود التالي أي مجموعة أحرف يجب استخدامها للبايتات التالية. بدون هذه العلامة، قد تُفسَّر الأحرف غير الـ ASCII بشكل خاطئ.

يعمل الـ builder في ثلاث مراحل بسيطة:

1. **Create** نسخة الـ builder.  
2. **Append** شظايا نصية عادية أو مُرمَّزة بـ ECI.  
3. **Retrieve** السلسلة النصية الموسعة المتكاملة.

أدناه نستعرض كل مرحلة مع كود عملي.

## الخطوة 1: إنشاء نسخة ExtCodetextBuilder

السطر الأول يُنشئ الكائن الذي سيحفظ جميع الشظايا. لا توجد أي إعدادات مطلوبة في هذه المرحلة.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*لماذا هذا مهم*: إنشاء نسخة الـ builder يخصص مخزنًا داخليًا. جميع استدعاءات `add_*` اللاحقة تعمل على هذا المخزن، مما يضمن الترتيب الذي تحدده.

## الخطوة 2: إلحاق بيانات نصية عادية (غير مُرمَّزة)

البيانات العادية تتكون من أحرف تنتمي إلى مجموعة الأحرف الافتراضية (عادةً ASCII). استخدم `add_plain_codetext` لهذه الشظايا.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*شرح*: السلسلة `"ABC123"` تحتوي على أحرف ASCII فقط، لذا لا حاجة لعلامة ECI. تقوم الطريقة ببساطة بإلحاق البايتات الخام إلى المخزن الداخلي.

## الخطوة 3: إلحاق بيانات يجب أن تسبقها علامة ECI

عند الحاجة إلى تضمين أحرف Unicode—مثل السيريالية أو اليابانية أو الرموز التعبيرية—يجب إخبار المُرمّز أي مجموعة أحرف يستخدمها. يتم ذلك عبر `add_eci_codetext(eci, text)`. الوسيط الأول هو قيمة ECI الرقمية؛ والوسيط الثاني هو النص الفعلي.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*لماذا ECI 3*: وفقًا لمواصفة ISO/IEC 18004، ECI 3 يطابق UTF‑8. بإدراج هذه العلامة، يعرف قارئ الباركود أن يفسّر البايتات التالية كـ UTF‑8، مما يحافظ على الأحرف السيريالية.

### معالجة الترميزات الأخرى

إذا كنت بحاجة إلى ISO‑8859‑1 (الأوروبية الغربية) فستستخدم `add_eci_codetext(4, "¡Hola!")`. بالنسبة لـ Shift‑JIS (اليابانية) قيمة ECI هي 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

تحقق دائمًا من أن مكتبة الباركود المستهدفة تدعم قيمة ECI المختارة؛ القيم غير المدعومة ستؤدي إلى فشل الترميز.

## الخطوة 4: استرجاع السلسلة النصية الموسعة المتكاملة

بعد إلحاق جميع الشظايا، استدعِ `get_extended_codetext()` للحصول على السلسلة النهائية. تتضمن هذه السلسلة أي تسلسلات هروب ECI ضرورية.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Expected output** (displayed as a Python `repr` for clarity):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*تحليل*:

* `ABC123` – جزء ASCII عادي.  
* `\x1B\x1D\x03` – تسلسل هروب ECI لـ UTF‑8 (ESC GS 0x03).  
* `Привет` – الكلمة السيريالية المشفرة بـ UTF‑8.

قد تختلف بايتات الهروب الدقيقة حسب تنفيذ المكتبة، لكن الترتيب المنطقي سيكون دائمًا *عادي → علامة ECI → نص Unicode*.

## مثال كامل قابل للتنفيذ

لنجمع كل شيء معًا، إليك سكريبت مستقل يمكنك نسخه إلى ملف باسم `create_extended_codetext.py` وتشغيله فورًا.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

تشغيل السكريبت يطبع السلسلة المتكاملة، جاهزة لأي مُرمّز باركود يقبل إدخال extended‑codetext.

## المشكلات الشائعة وكيفية تجنّبها

| العَرَض | السبب المحتمل | الحل |
|---|---|---|
| `UnicodeEncodeError` عند استدعاء `add_eci_codetext` | تمرير سلسلة تحتوي على أحرف غير قابلة للتمثيل في الـ ECI المختار | تحقق من أن الـ ECI يطابق الترميز الفعلي للسلسلة (مثلاً استخدم ECI 3 لأي نص UTF‑8). |
| عدم وجود علامة ECI في المخرجات النهائية | استخدام `add_plain_codetext` عن طريق الخطأ لبيانات غير ASCII | استبدلها بـ `add_eci_codetext` لأي حرف خارج نطاق ASCII. |
| قارئ الباركود يظهر أحرفًا مشوهة | القارئ لا يدعم قيمة الـ ECI المختارة | اختر ECI مدعوم عالميًا (UTF‑8 مدعوم على نطاق واسع) أو عُد إلى ISO‑8859‑1 إذا كان ذلك مناسبًا للغة المستهدفة. |
| `get_extended_codetext` تُعيد سلسلة فارغة | لم يتم إضافة أي شظايا قبل استدعاء الطريقة | تأكد من تنفيذ استدعاء واحد على الأقل من `add_*`. |

### حالة الحد: السلاسل الفارغة

استدعاء `add_plain_codetext("")` أو `add_eci_codetext(3, "")` لا يسبب أي ضرر؛ يتجاهل الـ builder الشظية الفارغة. ومع ذلك، قد تؤدي الاستدعاءات المتكررة الفارغة إلى علامات ECI غير ضرورية. احرص على التحقق من طول السلسلة قبل الإضافة.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## توسيع النمط للبيانات الديناميكية

في التطبيقات الواقعية غالبًا ما تُنشئ النص الموسع من مدخلات المستخدم أو سجل قاعدة بيانات. يوضح المقتطف التالي حلقة تعالج قائمة من أزواج `(type, value)`، حيث `type` إما `"plain"` أو `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

هذا النهج يتوسع بسهولة: يمكنك قراءة تعريفات الشظايا من JSON أو CSV أو API دون تعديل منطق البناء الأساسي.

## اختبار المخرجات

اختبار وحدة بسيط يضمن سلوك الـ builder كما هو متوقع. باستخدام `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

تشغيل `pytest` يجب أن ينجح، مؤكدًا أن علامة ECI تظهر بالضبط في الموضع الصحيح.

## مفاهيم ذات صلة قد تستكشفها لاحقًا

* **مكتبات ترميز الباركود** – مثل `python-barcode`، ربطات `zxing`، التي تقبل سلسلة extended codetext مباشرة.  
* **مرجع جدول ECI** – قائمة كاملة بالقيم الرقمية للـ ECI تُنشر بواسطة ISO/IEC 18004 ويمكن تخزينها كقاموس Python للبحث.  
* **مستويات تصحيح الأخطاء** – عند إنشاء رموز QR، اجمع النص الموسع مع مستوى تصحيح الأخطاء المناسب (L, M, Q, H) لضمان مسح موثوق.

## الخلاصة

أنت الآن تعرف كيف **create extended codetext** في بايثون باستخدام `ExtCodetextBuilder`. العملية بسيطة:

1. أنشئ نسخة الـ builder.  
2. ألحق شظايا نصية عادية ومُرمَّزة بـ ECI حسب الحاجة.  
3. استرجع السلسلة النهائية ومرّرها إلى مُولّد الباركود الخاص بك.

باتباع النمط أعلاه يمكنك التعامل مع أي مزيج من بيانات ASCII وUnicode، تجنّب الأخطاء الشائعة في الترميز، وإنتاج سلاسل جاهزة للباركود تعمل عبر مجموعة واسعة من القارئات. جرّب قيم ECI مختلفة، دمج الـ builder في خط أنابيب البيانات الخاص بك، وستحصل على أساس صلب لجميع احتياجاتك من النص الرمزي الموسع.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}