---
category: general
date: 2026-07-18
description: استخدم extcodetextbuilder من Aspose لإنشاء رموز QR تجمع بين نص ASCII
  عادي ونص روسي بترميز UTF‑8. تعلّم توليد رموز QR باستخدام Aspose.Barcode في بايثون.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: ar
lastmod: 2026-07-18
og_description: يتيح لك extcodetextbuilder من Aspose دمج مقاطع نصية عادية ومشفرة بـ
  UTF‑8 في رمز QR. اتبع هذا الدليل خطوة بخطوة لـ Aspose.Barcode في بايثون.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: استخدم extcodetextbuilder aspose – إنشاء رموز QR بنص ECI مختلط
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'استخدام ExtCodeTextBuilder من Aspose: إنشاء رموز QR بنص ECI مختلط'
url: /ar/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخدم extcodetextbuilder aspose – إنشاء رموز QR بنص ECI مختلط

هل تساءلت يوماً كيف **تستخدم extcodetextbuilder aspose** لتضمين كل من النص الإنجليزي العادي وحروف السيريليك في رمز QR واحد؟ لست وحدك. يواجه العديد من المطورين صعوبة عندما يحتاجون إلى خلط بيانات ASCII وغير‑ASCII، خاصة عندما يتوقع الماسح الضوئي المستهدف وجود علامات ECI (Extended Channel Interpretation) صحيحة.  

في هذا الدليل سنستعرض الخطوات الدقيقة لإنشاء رمز QR يحمل “HELLO123” **و** الكلمة الروسية “Привет”، باستخدام واجهة برمجة تطبيقات Aspose.Barcode للغة Python. في النهاية ستحصل على سكريبت جاهز للتنفيذ، وتفهم سبب أهمية كل استدعاء، وتعرف كيف تعدل العملية للغات أو صيغ بيانات أخرى.

## ما ستتعلمه

- كيفية **تهيئة ExtCodetextBuilder** وإضافة مقاطع نصية عادية ومشفّرة بـ ECI.  
- لماذا قيمة ترميز ECI `3` تمثل UTF‑8 وكيف يؤثر ذلك على عملية المسح.  
- التسلسل الدقيق لإعداد **مولّد رمز QR** باستخدام Aspose.Barcode.  
- كيفية حفظ الصورة الناتجة والتحقق من المحتوى المختلط.  

**المتطلبات المسبقة** – تحتاج إلى Python 3.8+، وحزمة `aspose-barcode` مثبتة (`pip install aspose-barcode`)، ومجلد يمكنك كتابة الصور إليه. لا شيء آخر.

---

## use extcodetextbuilder aspose to build mixed codetext

أول شيء نحتاجه هو كائن `ExtCodetextBuilder`. فكر فيه كأنماط Builder التي تُلحم قطع نصية مختلفة مع إدراج علامات ECI المناسبة تلقائياً خلف الكواليس.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**لماذا هذا مهم:**  
- `add_plain_codetext` يحتفظ بالبيانات كما هي، وهو مثالي للأرقام أو الأحرف الإنجليزية.  
- `add_eci_codetext` يضيف مقطع ECI (`[ECI:3]`) قبل السلسلة المقدمة، مُخبرًا أي قارئ متوافق أن البايتات التالية هي UTF‑8. بدون ذلك، سيفسر الماسح الضوئي بايتات السيريليك كـ “نفاية”.

> **نصيحة احترافية:** إذا كنت بحاجة إلى مجموعة أحرف مختلفة، غيّر قيمة `eci_encoding` وفقًا لجدول ECI (مثلاً، `26` لـ ISO‑8859‑1).  

---

## Initialise QR Code generation with Aspose.Barcode

الآن بعد أن أصبح لدينا `extended_codetext` مُنسّق بشكل صحيح، يمكننا تمريره إلى مولّد رمز QR. Aspose.Barcode يُبسط إنشاء مصفوفة QR منخفضة المستوى، مما يتيح لك التركيز على البيانات.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**ماذا يحدث هنا؟**  
- `BarcodeGenerator()` ينشئ كائن مولّد جديد بإعدادات افتراضية (الحجم، الدقة، إلخ).  
- `set_symbology` يُخبر المحرك أننا نريد رمز QR بدلاً من، على سبيل المثال، Code128.  

إذا كنت بحاجة إلى مستوى تصحيح أخطاء أعلى، يمكنك استدعاء `qr_generator.parameters.barcode.qr_error_level = ...` قبل تعيين النص.

---

## Assign the extended codetext to the QR generator

مع جاهزية المولّد، الخطوة التالية هي ببساطة إمداد المولّد بالسلسلة المختلطة التي بنيناها مسبقًا.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**لماذا لا نستخدم `set_codetext`؟**  
`set_codetext` يتعامل مع الإدخال كنص عادي، ويزيل أي علامات ECI. `set_extended_codetext` يحافظ على البايتات الخام، بما في ذلك مقطع ECI، مما يضمن أن الماسح يرى التحويل اللغوي الصحيح.

---

## Save the QR Code image and verify the result

أخيرًا، نكتب رمز QR إلى القرص. Aspose.Barcode يدعم PNG، JPEG، BMP، وأكثر؛ PNG هو الخيار الآمن لأنه يحافظ على البيانات بدون فقدان.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

يجب الآن أن يكون لديك ملف PNG في الموقع المحدد. افتحه بأي تطبيق ماسح QR يدعم ECI (معظم الهواتف الذكية الحديثة تدعم ذلك). امسح مرة – سترى “HELLO123”. امسح مرة أخرى (أو استخدم ماسحًا يُظهر البيانات الخام) – ستحصل أيضاً على “Привет”. القطعتان تظهران كحمولة واحدة، تمامًا كما بنيناها.

![استخدام extcodetextbuilder aspose مثال رمز QR](YOUR_DIRECTORY/qr_extended.png)

*نص بديل للصورة: مثال رمز QR باستخدام extcodetextbuilder aspose يُظهر نص ECI مختلط*

---

## Full, Ready‑to‑Run Script

بدمج كل شيء، إليك البرنامج الكامل الذي يمكنك نسخه‑ولصقه في ملف باسم `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

شغّله باستخدام:

```bash
python qr_mixed_eci.py
```

ستظهر لك رسالة في وحدة التحكم تؤكد موقع الحفظ، وسيظهر ملف PNG في المكان الذي حددته.

---

## Common Questions & Edge Cases

### ماذا لو لم يتعرف الماسح على الجزء السيريليكي؟
تأكد من أن تطبيق المسح يعلن عن دعم ECI. قد تتجاهل الأجهزة القديمة مقطع ECI وتتعامل مع البايتات كـ ISO‑8859‑1، مما ينتج عنه أحرف مشوشة.

### هل يمكنني إضافة أكثر من مقطعين؟
بالطبع. استدعِ `add_plain_codetext` أو `add_eci_codetext` بقدر ما تحتاج. سيقوم الـ Builder بدمجها بالترتيب الذي تستدعي فيه الطرق.

### كيف أغيّر حجم رمز QR أو لون المقدمة؟
استخدم كائن `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### هل هناك طريقة لتضمين بيانات ثنائية (مثل ملف صغير) إلى جانب النص؟
نعم. استخدم `add_binary_codetext` مع مصفوفة بايت، وقم بزوجها مع ECI مناسب إذا كانت البيانات الثنائية تمثل مجموعة أحرف معينة. سيتعامل الـ Builder مع التحولات اللازمة بين الأنماط.

---

## Conclusion

أنت الآن تعرف **كيفية استخدام extcodetextbuilder aspose** لإنشاء رموز QR تمزج بسلاسة بين النص ASCII العادي والنص الروسي المشفر بـ UTF‑8. من خلال الاستفادة من `ExtCodetextBuilder`، وتعيين **ترميز ECI** الصحيح، وإدخال النتيجة في **مولّد Aspose.Barcode لرموز QR**، تحصل على صورة واحدة متوافقة مع المعايير وتعمل على الماسحات الحديثة.  

من هنا، جرّب استبدال `eci_encoding=3` بمعرفات لغات أخرى، أو جرب إضافة مقاطع نصية عادية إضافية لبناء حمولة متعددة اللغات. يمكنك أيضًا استكشاف خيارات `BarCodeImageFormat` لإخراج SVG أو PDF إذا كنت تحتاج إلى رسومات متجهة.  

برمجة سعيدة، ولا تتردد في ترك تعليق إذا واجهت أي صعوبات—ملاحظاتك تساعد في تحسين هذه الأدلة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف نهج تنفيذ بديلة في مشاريعك.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}