---
category: general
date: 2026-09-29
description: تعلم كيفية إنشاء باركود Databar متعدد الاتجاهات في C# باستخدام Aspose.BarCode.
  اضبط بُعد X، حدد نسبة العرض إلى الارتفاع، واحفظ الصور بصيغة PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: ar
lastmod: 2026-09-29
og_description: إنشاء رمز شريطي Databar متعدد الاتجاهات في C# باستخدام Aspose.BarCode.
  تعلم كيفية ضبط البُعد X، تعديل نسبة العرض إلى الارتفاع، وتصدير ملفات PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: إنشاء باركود Databar متعدد الاتجاهات في C# – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: كيفية إنشاء باركود Databar متعدد الاتجاهات في C#
url: /ar/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود Databar متعدد الاتجاهات في C#

إذا كنت بحاجة إلى **إنشاء باركود Databar متعدد الاتجاهات** في تطبيق .NET، يوضح لك هذا الدليل الخطوات الدقيقة. ستتعرف على كيفية تهيئة باركود DataBar المتراكم متعدد الاتجاهات، ضبط بُعد X، تغيير نسبة العرض إلى الارتفاع، وإنشاء صور PNG باستخدام Aspose.BarCode.

إنشاء **باركود DataBar المتراكم متعدد الاتجاهات** شائع عندما تحتاج إلى ترميز معرفات المنتجات لأجهزة المسح في المتاجر. في هذا البرنامج التعليمي ستتعلم **ضبط نسبة عرض الباركود**، التحكم في حجم الوحدة، وتصدير النتيجة دون مغادرة بيئة التطوير المتكاملة.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- .NET 6.0 أو أحدث مثبت
- Visual Studio 2022 (أو أي بيئة تطوير متوافقة مع C#)
- حزمة **Aspose.BarCode for .NET** عبر NuGet (الإصدار 23.12 أو أحدث)

يمكنك إضافة الحزمة عبر مدير حزم NuGet:

```bash
dotnet add package Aspose.BarCode
```

## الخطوة 1: تهيئة باركود Databar متعدد الاتجاهات

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` يستهدف رموز **DataBar المتراكم متعدد الاتجاهات**. يتلقى المُنشئ نوع الترميز وسلسلة البيانات.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**لماذا هذا مهم:** قيمة `EncodeTypes.DatabarStackedOmniDirectional` تخبر Aspose.BarCode بإنشاء تنسيق Databar متعدد الاتجاهات المحدد، وهو مطلوب للمسح في كلا الاتجاهين.

## الخطوة 2: تعريف بُعد X (حجم الوحدة)

بُعد X يتحكم في عرض وحدة الباركود الواحدة بالبكسل. قيمة `2` بكسل تعمل جيدًا للعرض على الشاشة ومعظم الطابعات.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**لماذا هذا مهم:** بُعد X ثابت يضمن أن الباركود يفي بحدود الحجم الدنيا لأجهزة مسح المتاجر مع الحفاظ على حجم ملف الصورة ضمن نطاق معقول.

## الخطوة 3: ضبط نسبة العرض إلى الارتفاع الأولى وحفظ الصورة

**نسبة العرض إلى الارتفاع** تحدد العلاقة بين الارتفاع والعرض لباركود DataBar. نسبة `15` تنتج باركودًا مدمجًا وطويلاً مثاليًا للمساحات الضيقة على الملصقات.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**لماذا هذا مهم:** تعديل نسبة العرض إلى الارتفاع يتيح لك ملاءمة الباركود في تخطيطات ملصقات مختلفة دون التضحية بالقراءة. يمكن فحص ملف PNG المحفوظ في أي عارض صور.

## الخطوة 4: تغيير نسبة العرض إلى الارتفاع وإنشاء صورة ثانية

أحيانًا يكون الباركود الأوسع مطلوبًا—على سبيل المثال عندما يتوفر مساحة أفقية أكبر على الملصق. تغيير النسبة إلى `30` ينتج مظهرًا أكثر تسطحًا.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**لماذا هذا مهم:** من خلال إتاحة خاصية **set barcode aspect ratio**، يمكنك إنتاج عدة إصدارات من الباركود من قاعدة شفرة واحدة، مما يبسط خطوط أنابيب إنشاء الملصقات الآلية.

## النتيجة المتوقعة

تشغيل البرنامج ينتج ملفي PNG في مجلد الإخراج الخاص بالتطبيق:

| اسم الملف                | نسبة العرض إلى الارتفاع | الوصف البصري |
|--------------------------|--------------------------|--------------|
| `DatabarAspectRatio15.png` | 15                       | باركود طويل وضيق مناسب للملصقات الضيقة |
| `DatabarAspectRatio30.png` | 30                       | باركود أوسع يملأ مساحة أفقية أكبر |

يمكنك تضمين هذه الصور في التقارير، طباعتها على عبوات المنتجات، أو إرسالها إلى خدمة ويب لمعالجة إضافية.

![مثال على إنشاء باركود Databar متعدد الاتجاهات](databar-example.png "Create omnidirectional Databar barcode example")

*تُظهر لقطة الشاشة ملفي PNG المُولّدين جنبًا إلى جنب.*

## الأسئلة الشائعة والحالات الخاصة

### ماذا لو احتجت بُعد X مختلف؟

يمكنك تعيين أي قيمة عددية صحيحة إلى `XDimension.Pixels`. القيم الأقل من `1` تُهمل، والقيم التي تتجاوز `10` قد تنتج وحدات ضخمة تتجاوز هوامش الطابعة. اختبر المظهر البصري بعد كل تعديل.

### كيف يمكنني ترميز بيانات أخرى مُولدة بواسطة AI (مثل UPC، EAN)؟

استبدل سلسلة البيانات في مُنشئ `BarcodeGenerator` بمعرف التطبيق (AI) المناسب. بالنسبة لرمز UPC‑A، استخدم `"012345678905"` دون إضافة بادئة AI.

### هل يمكنني التصدير إلى صيغ غير PNG؟

نعم. طريقة `Save` تقبل `BarCodeImageFormat.Jpeg`، `BarCodeImageFormat.Gif`، `BarCodeImageFormat.Tiff`، و `BarCodeImageFormat.Bmp`. اختر الصيغة التي تتوافق مع سير عملك اللاحق.

## نصيحة احترافية: إعادة استخدام المولد للمعالجة الدفعية

إذا كنت بحاجة إلى إنشاء عشرات الباركودات بنسب عرض إلى ارتفاع مختلفة، حافظ على كائن `BarcodeGenerator` حياً وعدّل فقط `DataBar.AspectRatio` قبل كل عملية `Save`. هذا يقلل من العبء الناتج عن إعادة إنشاء المولد لكل صورة.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## الخلاصة

أنت الآن تعرف كيف **تنشئ باركود Databar متعدد الاتجاهات** في C# باستخدام Aspose.BarCode. من خلال تهيئة `BarcodeGenerator`، ضبط بُعد X، تعديل **set barcode aspect ratio**، وحفظ ملفات PNG، يمكنك إنتاج صور باركود تلبي متطلبات ملصقات متنوعة.

بعد ذلك، استكشف مواضيع ذات صلة مثل **generate barcode image** لرموز QR، **DataBar stacked omnidirectional barcode** validation، أو دمج ملفات PNG المُولدة في فواتير PDF باستخدام Aspose.PDF. جرّب نسب عرض إلى ارتفاع وأحجام وحدات مختلفة لتحديد الإعداد الأمثل لأجهزة الطباعة الخاصة بك.

---


## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية استخدام مولد الباركود C# لإنشاء باركود DataBar متعدد الاتجاهات](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [باركود Databar المتراكم متعدد الاتجاهات في C# – دليل كامل](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [كيفية إنشاء باركود في C# – إنشاء صورة باركود C# باستخدام DataBar الموسع](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}