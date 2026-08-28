---
category: general
date: 2026-08-19
description: إنشاء ملفات PNG من نوع Databar في C# باستخدام Aspose.BarCode. تعلّم كيفية
  توليد صور Databar، وتكوين معلمات Databar، وحفظ النتيجة بصيغة PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: ar
lastmod: 2026-08-19
og_description: إنشاء ملفات PNG لباركود Databar باستخدام C# و Aspose.BarCode. يشرح
  هذا الدليل كيفية إنشاء صور Databar، وتكوين معلمات Databar مثل البُعد X ونسبة العرض
  إلى الارتفاع، وحفظ ملفات PNG عالية الجودة للطباعة أو الاستخدام على الويب.
og_image_alt: create databar PNG example
og_title: إنشاء صور PNG لبار البيانات في C# – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: كيفية إنشاء صور PNG لباركود Databar باستخدام C# و Aspose.BarCode
url: /ar/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء صور PNG لباركود DataBar باستخدام C# و Aspose.BarCode

إذا كنت بحاجة إلى **إنشاء ملفات PNG لباركود DataBar** في تطبيق .NET، فإن هذا الدليل يوضح لك بالضبط كيفية القيام بذلك. سترى مثالًا كاملاً قابلاً للتنفيذ يولد رموز DataBar مكدسة متعددة الاتجاهات، يضبط المعلمات الرئيسية، ويحفظ ملفي PNG بنسب أبعاد مختلفة.

إنشاء صورة DataBar لا يقتصر فقط على استدعاء طريقة واحدة. عليك أيضًا **تكوين معلمات DataBar** مثل البُعد X (عرض الوحدة) ونسبة الأبعاد لتلبية مواصفات الطباعة أو المسح. بنهاية هذا الدليل ستفهم **كيفية إنشاء رسومات DataBar** التي تعمل بشكل موثوق في السيناريوهات الواقعية.

## المتطلبات المسبقة

- .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.7+)
- Visual Studio 2022 أو أي بيئة تطوير متوافقة مع C#
- ترخيص صالح لـ **Aspose.BarCode for .NET** (التقييم المجاني يعمل للاختبار)
- إلمام أساسي بصياغة C#

> **نصيحة احترافية:** إذا لم يكن لديك ترخيص بعد، يمكنك طلب مفتاح تقييم مؤقت من بوابة Aspose. سلوك الـ API يبقى نفسه؛ فقط العلامة المائية تتغير.

## الخطوة 1: تثبيت حزمة NuGet الخاصة بـ Aspose.BarCode

افتح مشروعك في Visual Studio، انقر بزر الماوس الأيمن على الحل، واختر **Manage NuGet Packages**. ابحث عن `Aspose.BarCode` وقم بتثبيت أحدث نسخة مستقرة.

```bash
dotnet add package Aspose.BarCode
```

هذا الأمر يضيف تجميع `Aspose.BarCode` إلى مشروعك ويجعل فئة `BarcodeGenerator` متاحة.

## الخطوة 2: تهيئة مولد الباركود لباركود DataBar مكدس متعدد الاتجاهات

يستقبل مُنشئ `BarcodeGenerator` معاملين: نوع الباركود وسلسلة البيانات الخام. للحصول على DataBar مكدس متعدد الاتجاهات، تستخدم `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**لماذا هذا مهم:** ثابت `EncodeTypes.DatabarStackedOmniDirectional` يخبر المكتبة بإنشاء باركود يمكن قراءته من أي اتجاه، وهو مثالي لملصقات الأرفف في المتاجر.

## الخطوة 3: ضبط البُعد X (عرض الوحدة) بالبكسل

البُعد X يتحكم في حجم أصغر عنصر شريط. ضبطه بالبكسل يمنحك تحكمًا دقيقًا في حجم الصورة النهائي.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

قيمة **2 بكسل** تمثل توازنًا جيدًا بين قابلية القراءة والضغط لمعظم طابعات الملصقات. عدّل هذه القيمة إذا كنت تحتاج إلى وحدات أكبر أو أصغر.

## الخطوة 4: ضبط نسبة الأبعاد الأولى وحفظ ملف PNG

نسبة الأبعاد تؤثر على ارتفاع DataBar المكدس. نسبة أبعاد **15** تنتج باركود قصير نسبيًا، بينما **30** تجعلها أطول.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

طريقة `Save` تكتب الباركود المُولد إلى ملف PNG. PNG هو تنسيق بدون فقدان، مما يحافظ على الحواف الواضحة المطلوبة لقارئات الباركود.

## الخطوة 5: تغيير نسبة الأبعاد وحفظ PNG ثاني

يمكنك إعادة استخدام نفس كائن `BarcodeGenerator` لإنتاج تنوعات ببساطة عن طريق تغيير نسبة الأبعاد.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

الآن لديك ملفا PNG—`DatabarAspectRatio15.png` و `DatabarAspectRatio30.png`—كل منهما بكثافة بصرية مختلفة.

## الخطوة 6: التحقق من النتيجة

افتح ملفات PNG المُولدة في أي عارض صور. يجب أن ترى باركود DataBar نظيفًا وعالي التباين. مسح الصور باستخدام ماسح باركود على الهاتف الذكي يؤكد أن كلا نسبتي الأبعاد تُفكّ الشيفرة إلى القيمة الأصلية للـ GTIN `12345678901231`.

![create databar PNG example](databar_example.png)

*الصورة أعلاه تُظهر ملفي PNG جنبًا إلى جنب. الصورة اليسرى تستخدم نسبة أبعاد 15، واليمين يستخدم نسبة أبعاد 30.*

## الاختلافات الشائعة وحالات الحافة

| السيناريو | ما الذي يجب تغييره | السبب |
|----------|-------------------|--------|
| **بيانات مختلفة** | استبدل السلسلة `(01)12345678901231` بأي معرف تطبيق GS1 صالح والبيانات | يسمح لك بترميز معرفات المنتجات، أرقام السلسلة، إلخ. |
| **دقة أعلى** | زيادة `XDimension.Pixels` إلى 3 أو 4 | مطلوب عندما يُطبع الباركود بأحجام كبيرة أو يُمسح من مسافة. |
| **أنواع DataBar أخرى** | استخدم `EncodeTypes.DatabarStacked` أو `EncodeTypes.DatabarExpanded` | اختر النوع الذي يناسب تخطيط ملصقك. |
| **خلفية شفافة** | مرّر `BarCodeImageFormat.Png` مع `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | مفيد لتراكب الباركود على ملصقات ملونة. |

> **احذر من:** ضبط بُعد X صغير جدًا (< 1 بكسل) قد ينتج باركودًا يبدو غير واضح بعد

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة تعمل مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء وضبط ارتفاع الباركود لباركود DataBar أحادي البعد باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [إنشاء ترميز GS1 لباركود DataBar أحادي البعد باستخدام Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [إنشاء باركود Aspose.BarCode DataBar باستخدام .NET API – تكوين الصف والعمود](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}