---
category: general
date: 2026-08-03
description: إنشاء صورة باركود بصيغة PNG باستخدام C# وتعلم كيفية تغيير نسبة العرض
  إلى الارتفاع لصور DataBar. اتبع هذا المثال الكامل مع الشيفرة والنصائح.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: ar
lastmod: 2026-08-03
og_description: إنشاء صورة باركود PNG باستخدام C# وتعرّف على كيفية تغيير نسبة الأبعاد
  لباركود DataBar. يقدم هذا الدليل كودًا جاهزًا للتنفيذ ونصائح عملية.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: إنشاء صورة باركود PNG في C# – مثال كامل مع التحكم في نسبة العرض إلى الارتفاع
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: إنشاء باركود PNG في C# – دليل خطوة بخطوة
url: /ar/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود PNG في C# – دليل خطوة‑بخطوة

إذا كنت بحاجة إلى **إنشاء باركود PNG** في C#، فإن هذا الدليل يوضح لك بالضبط كيفية القيام بذلك. ستقوم بإنشاء باركود DataBar مكدس متعدد الاتجاهات، حفظه كملف PNG، وتعلم **كيفية تغيير نسبة العرض إلى الارتفاع** لتناسب بيئات المسح المختلفة.

يغطي الدليل كل ما تحتاجه: الحزم المطلوبة، برنامج كامل قابل للتنفيذ، وتفسيرات لأسباب أهمية كل إعداد. في النهاية ستحصل على ملفي PNG—أحدهما بنسبة عرض إلى ارتفاع 15 والآخر بنسبة 30—جاهزين للاختبار أو الاستخدام الإنتاجي.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- .NET 6.0 SDK أو أحدث مثبت
- Visual Studio 2022 (أو أي بيئة تطوير C#)
- إشارة NuGet إلى **Aspose.BarCode** (المكتبة التي توفر `BarcodeGenerator`)
- صلاحية كتابة في الدليل الذي سيتم حفظ ملفات PNG فيه

يمكنك إضافة حزمة Aspose.BarCode بالأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ تطبيقًا كونسول جديدًا واستورد المساحات الاسمية المطلوبة لتوليد الباركود وإجراء عمليات الإدخال/الإخراج للملفات.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**لماذا هذا مهم:** استيراد `Aspose.BarCode.Generation` يمنحك الوصول إلى `BarcodeGenerator`. إبقاء الكود داخل `Main` يجعل المثال مستقلاً وسهل التشغيل.

## الخطوة 2: إنشاء مولد باركود للـ DataBar المكدس متعدد الاتجاهات

أنشئ كائن `BarcodeGenerator` باستخدام النوع `EncodeTypes.DatabarStackedOmniDirectional` وسلسلة بيانات عينة من نوع GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**لماذا هذا مهم:** نوع الترميز المختار ينتج DataBar عالي الكثافة يمكن قراءته بواسطة معظم الماسحات الحديثة. تتبع سلسلة البيانات تنسيق معرف التطبيق GS1 (01)، وهو شائع لتحديد المنتجات.

## الخطوة 3: تحديد بعد X (عرض الوحدة) بالبكسل

حدد عرض الوحدة للتحكم في الحجم الكلي للباركود دون التأثير على قابلية قراءته.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**لماذا هذا مهم:** بعد X بقيمة 2 بكسل ينتج باركودًا ليس صغيرًا جدًا للماسحات ولا كبيرًا جدًا للمساحات المعتادة على الملصقات.

## الخطوة 4: حفظ أول PNG بنسبة عرض إلى ارتفاع 15

قم بتعديل نسبة عرض إلى ارتفاع للـ DataBar، ثم احفظ الصورة كملف PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**لماذا هذا مهم:** نسبة العرض إلى الارتفاع تتحكم في العلاقة بين الارتفاع والعرض للـ DataBar المكدس. النسبة 15 هي القيمة الافتراضية الشائعة التي توازن بين القابلية للقراءة وارتفاع الملصق.

## الخطوة 5: تغيير نسبة العرض إلى الارتفاع إلى 30 وحفظ PNG ثاني

عدّل نفس كائن المولد لاستخدام نسبة عرض إلى ارتفاع أكبر، ثم احفظ الصورة الثانية.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**لماذا هذا مهم:** زيادة نسبة العرض إلى الارتفاع تمتد الباركود عموديًا، مما قد يحسن موثوقية المسح على الأجهزة منخفضة الدقة أو عندما يُطبع الملصق على وسائط ضيقة.

## النتيجة المتوقعة

تشغيل البرنامج ينشئ ملفي PNG:

| الملف                               | نسبة العرض إلى الارتفاع | الأبعاد التقريبية (بالبكسل) |
|------------------------------------|--------------------------|------------------------------|
| `DatabarAspectRatio15.png`         | 15                       | 200 × 300 (width × height)   |
| `DatabarAspectRatio30.png`         | 30                       | 200 × 600 (width × height)   |

كلا الصورتين تحتويان على باركود DataBar واضح وقابل للقراءة يشفّر معرف GS1 `(01)12345678901231`.

## الأسئلة الشائعة والحالات الخاصة

### كيف يمكن تغيير خصائص بصرية أخرى؟

يمكنك تعديل لون المقدمة، لون الخلفية، أو إضافة نص قابل للقراءة البشرية عبر كائن `generator.Parameters.Barcode`. مثال:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### ماذا لو احتجت إلى تنسيق صورة مختلف؟

استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Gif` حسب الحاجة. يظل PNG هو الخيار الأفضل للصور الخالية من الفقدان للباركود.

### هل تؤثر نسبة العرض إلى الارتفاع على سرعة المسح؟

نسب العرض إلى الارتفاع الأعلى تزيد من ارتفاع الباركود، ما قد يحسن موثوقية المسح على الأجهزة التي تواجه صعوبة مع الرموز المكدسة القصيرة. ومع ذلك، قد لا تتناسب الباركودات الطويلة جدًا مع الملصقات الصغيرة، لذا اختبرها مع الأجهزة المستهدفة.

### هل يمكن توليد عدة باركودات داخل حلقة؟

نعم. أنشئ كائن `BarcodeGenerator` جديد لكل سلسلة بيانات أو أعد استخدام نفس الكائن مع تحديث `CodeText` و `DataBar.AspectRatio`. هذا يقلل من استهلاك الذاكرة عند إنشاء دفعات كبيرة.

## نصائح احترافية

- **إعادة استخدام المولد**: تغيير `CodeText` أو `AspectRatio` فقط دون إنشاء كائن جديد يسرّع معالجة الدفعات.
- **تحقق من المخرجات**: استخدم ماسحًا يدويًا أو تطبيقًا على الهاتف لتأكيد أن PNG المولد يُقرأ بشكل صحيح قبل النشر.
- **تسمية الملفات**: أدرج نسبة العرض إلى الارتفاع في اسم الملف (كما هو موضح) لتتبع الاختلافات أثناء الاختبار.

## الخلاصة

أصبحت الآن تعرف كيف **تنشئ ملفات باركود PNG** في C# وكيف **تغيّر نسبة العرض إلى الارتفاع** بدقة لرموز DataBar المكدسة متعددة الاتجاهات. يوضح المثال الكامل تهيئة المولد، ضبط بعد X، تعديل نسبة العرض إلى الارتفاع، وحفظ الصورة—كل ذلك في برنامج واحد قابل للتنفيذ.

من هنا يمكنك استكشاف أنواع باركود إضافية، تجربة الألوان، أو دمج المولد في نظام تقارير أو جرد أكبر. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروحات خطوة‑بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}