---
date: 2026-05-30
description: تعرف على كيفية إنشاء باركود PNG بنسبة أبعاد مخصصة لـ DataMatrix باستخدام
  Aspose.BarCode لـ .NET. دليل خطوة بخطوة لتوليد الباركود وتخصيص الحجم.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: تخصيص نسبة أبعاد DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: إنشاء باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode
url: /ar/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode

إنشاء **barcode PNG** بنسبة أبعاد DataMatrix مخصصة هو طلب شائع عندما تحتاج إلى **إنشاء ملفات barcode PNG** تتناسب مع قيود تخطيط معينة. في هذا الدرس سنستعرض الخطوات الدقيقة **لإنشاء ملفات barcode PNG** باستخدام Aspose.BarCode لـ .NET، ونشرح لماذا قد ترغب في تعديل نسبة الأبعاد، ونظهر لك كيفية ضبط المخرجات لتناسب تطبيقك.

## إجابات سريعة
- **ما الذي تتحكم فيه “aspect ratio”?** إنها تحدد نسبة العرض إلى الارتفاع لوحدات DataMatrix.  
- **هل يمكنني إخراج PNG أو JPEG أو SVG؟** نعم – تدعم طريقة `Save` الصيغ PNG و JPEG و BMP و GIF و TIFF و SVG و PDF.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** الإصدار التجريبي المجاني يكفي للتطوير؛ يتطلب الترخيص الكامل للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.x، .NET Core 3.1+، .NET 5/6/7.  
- **كم عدد قيم aspect‑ratio الصالحة؟** أي قيمة عائمة موجبة؛ القيم الشائعة تتراوح بين 0.5 و 2.0.

## ما هو باركود DataMatrix ولماذا تعديل نسبة أبعاده؟
باركود DataMatrix هو رمز مصفوفة ثنائي الأبعاد يخزن كميات كبيرة من البيانات في مربع مدمج. تعديل **aspect ratio** يتيح لك تمديد أو ضغط الوحدات أفقياً، وهو مفيد عندما تحتاج إلى وضع الباركود في أعمدة ضيقة أو ملصقات عريضة دون الإضرار بموثوقية القراءة.

## لماذا تستخدم Aspose.BarCode لإنشاء barcode PNG؟
يدعم Aspose.BarCode **7 صيغ صور** — PNG و JPEG و BMP و GIF و TIFF و SVG و PDF — ويمكنه معالجة **أكثر من 50 صيغة إدخال وإخراج** في الذاكرة، مع التعامل مع مستندات مئات الصفحات دون تحميل الملف بالكامل. توفر المكتبة API سهل الاستخدام يتيح لك إنشاء باركود DataMatrix بسطر واحد من الشيفرة، مما يضمن عرضًا دقيقًا للبيكسل وتوافقًا كاملًا مع .NET.

## المتطلبات المسبقة

قبل أن نبدأ بتخصيص نسب أبعاد DataMatrix، تأكد من توفر المتطلبات التالية:

1. **Visual Studio** – أي نسخة حديثة ستفي بالغرض.  
2. **Aspose.BarCode for .NET** – قم بتنزيله [هنا](https://releases.aspose.com/barcode/net/).  
3. يمكنك أيضًا استكشاف إصدارات منتجات Aspose الأخرى [هنا](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – يجب أن يستهدف مشروعك نسخة مدعومة.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحة الأسماء اللازمة في مشروع C# الخاص بك:

`using Aspose.BarCode.Generation;` تستورد مساحة الأسماء التي تحتوي على فئات توليد الباركود.  

```csharp
using Aspose.BarCode.Generation;
```

> **نصيحة احترافية:** احتفظ بعبارة `using` هذه في أعلى ملفك حتى تكون فئة `BarcodeGenerator` متاحة دائمًا.

## كيفية إنشاء barcode PNG بنسبة أبعاد مخصصة؟

حمّل `BarcodeGenerator`، عيّن نوع DataMatrix، اضبط خاصية `AspectRatio`، ثم استدعِ `Save`. هذا النمط ذو السطر الواحد ينشئ barcode PNG يلتزم بنسبة الأبعاد التي تحددها، وتتعامل المكتبة تلقائيًا مع تحجيم الوحدات ومناطق الهدوء.

`BarcodeGenerator` ينشئ صورة باركود من الرموز والبيانات المحددة.  

### الخطوة 1: إعداد مشروعك
أنشئ مشروعًا جديدًا من نوع Console أو Windows Forms في Visual Studio وأضف إشارة إلى مكتبة Aspose.BarCode DLL.

### الخطوة 2: تهيئة مولد الباركود
أنشئ نسخة منه باستخدام رموز DataMatrix والبيانات التي تريد ترميزها:

`BarcodeGenerator` ينشئ صورة باركود من الرموز والبيانات المحددة.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> هذه السطر ينشئ مولدًا جاهزًا لإنتاج باركود DataMatrix يحتوي على النص التجريبي.

### الخطوة 3: تخصيص نسبة الأبعاد وحفظ ملفات PNG
الآن يمكنك تغيير **aspect ratio** وحفظ كل نسخة كصورة PNG:

`AspectRatio` تحدد نسبة العرض إلى الارتفاع لوحدات DataMatrix.  
`Save` تكتب صورة الباركود المولدة إلى ملف بالتنسيق المختار.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- الاستدعاء الأول ينشئ باركود بنسبة مربعة (`AspectRatio = 1`).  
- الاستدعاء الثاني يضغط الباركود أفقياً (`AspectRatio = 0.5`)، مما ينتج مظهرًا أوسع.

الآن لديك ملفان **barcode PNG** بنسب أبعاد مختلفة جاهزان للاستخدام في التقارير أو الملصقات أو عناصر واجهة المستخدم.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **الصورة المولدة غير واضحة** | قم بزيادة معامل `Resolution` قبل الحفظ (`gen.Parameters.ImageResolution = 300`). |
| **الباركود لا يُقرأ** | تأكد من أن نسبة الأبعاد تبقى بين 0.5 و 2.0 واحرص على وجود منطقة هادئة كافية (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **أخطاء مسار الملف** | استخدم `Path.Combine` لإنشاء مسار الإخراج وتحقق من وجود المجلد. |

## الأسئلة المتكررة

**س: هل يمكنني تخصيص نسبة الأبعاد لأنواع أخرى من الباركود باستخدام Aspose.BarCode لـ .NET؟**  
ج: نعم، العديد من الباركودات ثنائية الأبعاد (مثل QR و PDF417) تدعم تعديل نسبة الأبعاد عبر كائنات المعلمات الخاصة بها.

**س: هل يتوفر نسخة تجريبية مجانية لـ Aspose.BarCode لـ .NET؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.BarCode لـ .NET [هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء ترخيص لـ Aspose.BarCode لـ .NET؟**  
ج: يمكنك شراء الترخيص من موقع Aspose [هنا](https://purchase.aspose.com/buy).

**س: هل Aspose.BarCode لـ .NET متوافق مع إصدارات .NET Framework المختلفة؟**  
ج: نعم، يعمل مع .NET Framework 4.x، .NET Core 3.1+، وأحدث إصدارات .NET.

**س: هل يمكنني توليد باركود بصيغ مختلفة باستخدام Aspose.BarCode لـ .NET؟**  
ج: بالتأكيد – PNG و JPEG و BMP و GIF و TIFF و SVG و PDF كلها مدعومة مباشرة.

## الخلاصة

تخصيص **aspect ratio** لباركود DataMatrix و**إنشاء barcode PNG** سهل مع Aspose.BarCode لـ .NET. باتباع الخطوات السابقة، يمكنك توليد باركود بأحجام مثالية تلبي متطلبات التخطيط الدقيقة لمشروعك. استكشف معلمات إضافية مثل `Resolution` و `Margin` و `Color` لتخصيص المخرجات أكثر، وفكر في إمكانيات `generate datamatrix barcode` عند بناء تطبيقات صديقة للقراءة الضوئية في Visual Studio.

لمزيد من الاستكشاف، اطلع على [التوثيق الرسمي](https://reference.aspose.com/barcode/net/) أو انضم إلى المجتمع في [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**آخر تحديث:** 2026-05-30  
**تم الاختبار باستخدام:** Aspose.BarCode 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء باركود DataMatrix – دليل احترافي مع Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [كيفية إنشاء باركود DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [إتقان ترميز DataMatrix في ASCII باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}