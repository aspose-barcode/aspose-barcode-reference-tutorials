---
category: general
date: 2026-10-12
description: كيفية ضبط ارتفاع الباركود وإنشاء باركود DataBar باستخدام C# و Aspose.BarCode.
  اتبع دليلًا خطوة بخطوة مع الكود الكامل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: ar
lastmod: 2026-10-12
og_description: كيفية تعيين ارتفاع الباركود في C# وإنشاء باركود DataBar باستخدام Aspose.BarCode.
  تعلّم الكود الكامل، ولماذا كل خطوة مهمة، وكيفية تغيير ارتفاع الباركود.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: كيفية ضبط ارتفاع الباركود وإنشاء باركود DataBar في C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية ضبط ارتفاع الباركود، وإنشاء باركود DataBar في C#
url: /ar/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضبط ارتفاع الباركود، إنشاء باركود DataBar في C#

إذا كنت بحاجة إلى **how to set barcode** أبعاد الباركود برمجياً، يوضح لك هذا الدليل الخطوات الدقيقة. ستتعلم كيفية إنشاء باركود DataBar Omni‑directional، ضبط ارتفاعه، وحفظ النسختين كملفات PNG.

تغيير ارتفاع شريط الباركود هو طلب شائع عند دمج الباركود في الإيصالات، ملصقات المنتجات، أو شاشات الهواتف المحمولة. المثال أدناه يستخدم مكتبة Aspose.BarCode، التي تدعم مجموعة كاملة من رموز GS1 DataBar.

## ما ستحققه

* ارتفاع **how to set barcode** لباركود DataBar Omni‑directional  
* كود **generate barcode c#** الذي ينشئ صورتين بأارتفاعات مختلفة  
* فهم رموز **how to create databar** ولماذا ارتفاع الشريط مهم  
* تطبيق منطق **change barcode height** دون إعادة إنشاء المولد  

لا توجد أدوات خارجية مطلوبة بخلاف حزمة Aspose.BarCode NuGet وبيئة تشغيل .NET 6+.

## المتطلبات المسبقة

* .NET 6 SDK أو أحدث مثبت  
* Visual Studio 2022 (أو أي محرر C#)  
* Aspose.BarCode for .NET – تثبيت عبر `dotnet add package Aspose.BarCode`  

> **نصيحة احترافية:** استخدم ترخيص التجربة المجانية من Aspose إذا لم يكن لديك مفتاح تجاري؛ API يعمل بنفس الطريقة.

## الخطوة 1: تثبيت حزمة Aspose.BarCode

افتح طرفية في مجلد المشروع الخاص بك وشغّل:

```bash
dotnet add package Aspose.BarCode
```

تضيف الحزمة مساحة الاسم `Aspose.BarCode`، التي تحتوي على الفئة `BarcodeGenerator` التي سنستخدمها لإنشاء صور **generate barcode c#**.

## الخطوة 2: إنشاء مولد باركود DataBar

الإجراء الأول الملموس لمعلمات **how to set barcode** هو إنشاء كائن `BarcodeGenerator` باستخدام الترميز المطلوب وسلسلة البيانات.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*لماذا هذا مهم:* `EncodeTypes.DatabarOmniDirectional` ينتج DataBar مدمجًا ومتعدد الاتجاهات يمكن مسحه من أي زاوية—مثالي للملصقات الصغيرة.

## الخطوة 3: ضبط معلمات الباركود العامة (بما في ذلك ارتفاع الشريط الأولي)

الآن نجيب على **how to set barcode** الأبعاد X‑dimension وارتفاع الشريط قبل حفظ الصورة الأولى.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

تتحكم X‑dimension في العرض الكلي لكل شريط؛ إعداد 2‑بكسل ينتج صورة واضحة وقابلة للقراءة على معظم الشاشات. خطوة **change barcode height** لاحقًا ستعيد استخدام نفس المولد، مما يوفر الوقت والذاكرة.

## الخطوة 4: حفظ صورة الباركود الأولى (ارتفاع 30 بكسل)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

الملف `DatabarHeight30.png` الآن يحتوي على باركود DataBar بارتفاع شريط 30 بكسل.

## الخطوة 5: تغيير ارتفاع الشريط فقط إلى 60 بكسل

للتوضيح **change barcode height**، نقوم بتعديل خاصية `BarHeight` فقط. جميع الإعدادات الأخرى تبقى دون تغيير، وهذا هو الطريقة الأكثر كفاءة لإنتاج أحجام متعددة من مولد واحد.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## الخطوة 6: حفظ صورة الباركود الثانية (ارتفاع 60 بكسل)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

الآن لديك ملفي PNG، كل منهما بارتفاع شريط مختلف لكن البيانات وX‑dimension متطابقة.

## مثال كامل قابل للتنفيذ

فيما يلي البرنامج الكامل الذي يمكنك نسخه ولصقه في تطبيق كونسول جديد (`dotnet new console`) وتشغيله فورًا.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### النتيجة المتوقعة

تشغيل البرنامج ينتج ملفين في دليل العمل للتنفيذ:

* `DatabarHeight30.png` – باركود DataBar بارتفاع شريط 30 بكسل.  
* `DatabarHeight60.png` – نفس الباركود، لكن كل شريط ارتفاعه ضعف ذلك.

يمكن فتح كلتا الصورتين في أي عارض صور أو تضمينهما مباشرة في ملفات PDF، صفحات HTML، أو ملصقات مطبوعة.

## لماذا تعديل ارتفاع الشريط مهم

* **موثوقية المسح:** بعض الماسحات تواجه صعوبة مع الأشرطة القصيرة جدًا على وسائط منخفضة الدقة؛ زيادة الارتفاع تحسن الكشف.  
* **قيود التصميم:** قد يحتاج تطبيق الهاتف المحمول إلى باركود مدمج (30 px) بينما قد يتطلب الإيصال المطبوع واحدًا أكبر (60 px).  
* **الامتثال التنظيمي:** بعض الصناعات تفرض حدًا أدنى لارتفاع الشريط لرموز GS1 DataBar.  

من خلال إعادة استخدام نفس كائن `BarcodeGenerator`، تتجنب عبء إعادة تحليل سلسلة البيانات، وهو مفيد بشكل خاص في بيئات ذات إنتاجية عالية.

## التغييرات الشائعة وحالات الحافة

| الحالة | التعديل الموصى به |
|-----------|-------------------|
| الحاجة إلى X‑dimension مختلف | غيّر `XDimension.Pixels` قبل أول `Save`. |
| الرغبة في ترميز مختلف (مثال: DataBar Stacked) | استخدم `EncodeTypes.DatabarStacked` عند إنشاء `BarcodeGenerator`. |
| ضرورة تضمين الباركود في PDF | استخدم `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` وأضف الـ stream إلى مكتبة PDF. |
| التشغيل على .NET Framework 4.6 | الكود نفسه يعمل؛ فقط استدعِ التجميع المناسب لـ Aspose.BarCode. |

## نصائح احترافية لتوليد باركود موثوق

* **Cache the generator** عند توليد العديد من الباركودات بنفس البيانات ولكن بأحجام مختلفة.  
* **

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء وضبط ارتفاع الباركود لباركود DataBar أحادي الأبعاد باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [كيفية إنشاء صور PNG لباركود DataBar باستخدام C# و Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [كيفية إنشاء باركود بحجم مخصص وحفظ الصورة في C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}