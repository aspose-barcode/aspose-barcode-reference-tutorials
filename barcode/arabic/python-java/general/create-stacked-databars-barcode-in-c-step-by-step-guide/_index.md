---
category: general
date: 2026-10-02
description: إنشاء شيفرة شريطية مكدسة للبيانات في C# بسرعة. تعلم كيفية ضبط XDimension،
  تعديل نسبة العرض إلى الارتفاع، وتصدير صور PNG باستخدام مولد الشيفرات الشريطية.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: ar
lastmod: 2026-10-02
og_description: إنشاء شيفرة باركود من نوع stacked databars في C# مع مثال كامل للكود.
  ضبط XDimension، تغيير نسبة العرض إلى الارتفاع، وحفظ ملفات PNG في بضع أسطر فقط.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: إنشاء شيفرة شريط بيانات مكدسة في C# – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: إنشاء باركود شريط بيانات مكدس في C# – دليل خطوة بخطوة
url: /ar/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود DataBars مكدس في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء باركود DataBars مكدس** في مشروع .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك. سترى كيفية ضبط بُعد X، وتبديل نسب الأبعاد، وحفظ النتيجة كملفات PNG—all with the Aspose.BarCode library.

إنشاء باركود DataBar مكدس لا يتطلب خط أنابيب رسومي معقد. بحلول نهاية هذا الدليل ستحصل على صورتين PNG جاهزتين للاستخدام توضحان نسب أبعاد مختلفة، وستفهم لماذا هذه المعلمات مهمة لموثوقية القراءة.

## ما ستحتاجه

- .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.6+)
- Visual Studio 2022 أو أي بيئة تطوير C#
- **Aspose.BarCode for .NET** حزمة NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- إذن كتابة إلى مجلد سيتم حفظ ملفات PNG فيه

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ تطبيقًا جديدًا من نوع console (أو أضف الكود إلى مشروع موجود) واستورد المساحات الاسمية المطلوبة:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **لماذا هذا مهم:** `Aspose.BarCode.Generation` توفر الفئة `BarcodeGenerator`، بينما `Aspose.BarCode` تحتوي على تعداد `BarCodeImageFormat` المستخدم لحفظ الصور.

## الخطوة 2: تهيئة المولد لباركود DataBar مكدس متعدد الاتجاهات

القيمة `EncodeTypes.DatabarStackedOmniDirectional` تختار رموز DataBar المكدسة. يجب أن يتبع سلسلة البيانات تنسيق معرف التطبيق GS1 (AI)؛ هنا نستخدم قيمة GTIN‑14 تجريبية.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **لماذا هذا مهم:** نوع الترميز المختار يخبر المكتبة بإنشاء باركود *مكدس*، وهو أمر أساسي للملصقات عالية الكثافة حيث تكون المساحة العمودية محدودة.

## الخطوة 3: تعريف حجم الوحدة (بُعد X) بالبكسل

بُعد X يتحكم في عرض أصغر شريط (الوحدة). قيمة 2 بكسل تعمل جيدًا لمعظم المخرجات بدقة الشاشة.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **لماذا هذا مهم:** الماسحات الضوئية تفسر عرض الوحدة كوحدة قياس أساسية. قيمة صغيرة جدًا قد تتسبب في طباعة ضبابية؛ قيمة كبيرة جدًا تهدر مساحة.

## الخطوة 4: حفظ الصورة الأولى بنسبة أبعاد 15

خاصية `AspectRatio` تؤثر على علاقة الارتفاع إلى العرض لكل جزء مكدس. نسبة أبعاد 15 هي الإعداد الافتراضي الشائع لتطبيقات التجزئة.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **لماذا هذا مهم:** نسبة أبعاد منخفضة تنتج باركودًا أكثر تسطحًا، قد يكون أسهل للقراءة على بعض مواد الملصق. تنسيق PNG يحافظ على جودة غير مضغوطة للاختبار.

## الخطوة 5: تغيير نسبة الأبعاد إلى 30 وحفظ الصورة الثانية

زيادة نسبة الأبعاد تجعل كل جزء مكدس أطول، مما قد يحسن موثوقية القراءة على خلفيات منخفضة التباين.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **لماذا هذا مهم:** قد يتطلب تجار التجزئة أو شركاء اللوجستيات أبعاد باركود محددة. توفير النسختين يتيح لك مقارنة أداء القراءة بسرعة.

## مثال كامل قابل للتنفيذ

فيما يلي البرنامج الكامل الذي يمكنك نسخه ولصقه في `Program.cs`. يتجCompile ويعمل دون تعديل بعد تثبيت حزمة Aspose.BarCode NuGet.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### النتيجة المتوقعة

تشغيل البرنامج ينشئ ملفين في مجلد التنفيذ:

| اسم الملف                     | نسبة الأبعاد | الوصف البصري |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | باركود مكدس أقصر وأكثر تسطحًا |
| `DatabarAspectRatio30.png`    | 30           | باركود مكدس أطول وأكثر استطالة |

يمكنك فتح ملفات PNG بأي عارض صور للتحقق من أن الباركود تم توليده بشكل صحيح.

![إنشاء مثال باركود DataBars مكدس](placeholder-image.png){alt="إنشاء مثال باركود DataBars مكدس"}

## أسئلة شائعة وحالات خاصة

| السؤال | الجواب |
|----------|--------|
| **هل يمكنني استخدام بُعد X مختلف؟** | نعم. القيم النموذجية تتراوح بين 1 إلى 4 بيكسل. القيم الأكبر تزيد من حجم الباركود ولكن قد تحسن القابلية للقراءة على الطابعات منخفضة الدقة. |
| **ماذا إذا احتجت إلى رموز مختلفة؟** | استبدل `EncodeTypes.DatabarStackedOmniDirectional` بقيمة `EncodeTypes` أخرى، مثل `DatabarStacked` (غير موجه في جميع الاتجاهات) أو `DatabarLimited`. |
| **كيف أغير تنسيق الإخراج؟** | استخدم `BarCodeImageFormat.Jpeg` أو `Gif` أو `Bmp` في استدعاء `Save`. |
| **هل تنسيق GTIN‑14 إلزامي؟** | تتوقع رموز DataBar سلسلة رقمية مسبوقة بمعرف تطبيق مناسب (مثال: `(01)` لـ GTIN‑14). عدل البيانات وفقًا لحالتك. |
| **ماذا عن إعدادات DPI؟** | يحترم المولد خاصية `Resolution`. للطباعة عالية الدقة، اضبط `barcodeGen.Parameters.ImageResolution.DpiX` و `DpiY` وفقًا لذلك. |

## نصائح احترافية

- **إنشاء دفعات:** ضع منطق الحفظ داخل حلقة ومرر لها قائمة من أرقام GTIN لإنتاج آلاف الباركودات تلقائيًا.
- **التحقق:** استخدم `barcodeGen.Validate()` قبل الحفظ لاكتشاف البيانات غير الصالحة مبكرًا.
- **الأداء:** إعادة استخدام نفس كائن `BarcodeGenerator` (مع تغيير المعلمات فقط) أسرع من إنشاء كائن جديد لكل صورة.

## الخطوات التالية

الآن بعد أن تمكنت من **إنشاء باركود DataBars مكدس** بنسب أبعاد مخصصة، فكر في استكشاف:

- إضافة نص قابل للقراءة بشرية أسفل الباركود (`barcodeGen.Parameters.Barcode.CodeText`).
- التصدير إلى **PDF** لأوراق ملصقات قابلة للطباعة (`BarCodeImageFormat.Pdf`).
- دمج المولد في واجهة برمجة تطبيقات ويب لتقديم الباركود عند الطلب.
- تجربة كلمات مفتاحية ثانوية أخرى مثل *C# barcode generator* و *barcode aspect ratio* لضبط التنفيذ وفقًا للأجهزة المحددة.

برمجة سعيدة، واستمتع بالمرونة التي يقدمها Aspose.BarCode لمشاريع الباركود في C#!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء باركود DataBar مكدس في C# – دليل خطوة بخطوة](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [باركود DataBar مكدس متعدد الاتجاهات في C# – دليل كامل](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [كيفية إنشاء صور PNG لباركود DataBar باستخدام C# و Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}