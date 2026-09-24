---
category: general
date: 2026-08-06
description: أنشئ شريط بيانات مكدس كود شريطي في C# بسرعة. تعلم كيفية ضبط البُعد X،
  وضبط نسبة العرض إلى الارتفاع، وتصدير ملفات PNG باستخدام مولد DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: ar
lastmod: 2026-08-06
og_description: إنشاء شيفرة شريطية مكدسة (databar) في C# باستخدام Aspose.BarCode.
  يوضح هذا الدرس كيفية ضبط البُعد X، وتغيير نسبة العرض إلى الارتفاع، وحفظ الصور بصيغة
  PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: إنشاء شيفرة شريطية Databar مكدسة في C# – دليل برمجي كامل
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: إنشاء شيفرة باركود Databar مكدسة في C# – دليل خطوة بخطوة
url: /ar/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شيفرة شريطية مكدسة DataBar في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء شيفرة شريطية مكدسة DataBar** بصور في C#، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك باستخدام مكتبة Aspose.BarCode. ستتعلم كيفية ضبط بعد X، وتغيير نسبة أبعاد الشيفرة، وحفظ النتيجة كملفات PNG—كل ذلك في بضع خطوات مختصرة.

إنشاء شيفرة DataBar مكدسة شائع عندما يتعين عليك ترميز بيانات GS1‑128 للمسح في المتاجر أو لتتبع اللوجستيات. في الأقسام التالية نغطي كل شيء من إعداد المشروع إلى التحقق من المخرجات، بحيث يمكنك دمج الحل في أي تطبيق .NET دون تفويت أي تفصيل.

## المتطلبات المسبقة

* **.NET 6.0** (أو أحدث) مثبت – يستهدف الكود مجموعة تطوير حديثة.
* نسخة **مرخصة** من **Aspose.BarCode for .NET**. النسخة التجريبية المجانية تعمل للاختبار لكنها تضيف علامة مائية.
* بيئة تطوير متكاملة مثل **Visual Studio 2022** أو **VS Code** مع امتداد C#.
* إلمام أساسي بصياغة **C#** ومفهوم معرفات تطبيق GS1.

> **نصيحة احترافية:** إذا كنت تستخدم مدير الحزم NuGet، فإن الأمر `dotnet add package Aspose.BarCode` يحل جميع الاعتمادات تلقائيًا.

## الخطوة 1: إنشاء مشروع وحدة تحكم جديد

افتح الطرفية أو وحدة التحكم الخاصة بمدير الحزم ونفّذ:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

أمر `dotnet new console` يُنشئ ملف **Program.cs** بسيط. إضافة حزمة **Aspose.BarCode** تجعل فئة `BarcodeGenerator` متاحة.

## الخطوة 2: تهيئة مولد DataBar مكدس متعدد الاتجاهات

افتح **Program.cs** واستبدل المحتوى الافتراضي بالكود التالي. السطر الأول ينشئ كائن **BarcodeGenerator** مُكوَّن للرمز الشريطي **DataBar Stacked Omnidirectional** ويزوده ببيانات حمولة GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**لماذا هذا مهم:** قيمة التعداد `EncodeTypes.DatabarStackedOmniDirectional` تخبر المكتبة بإنتاج **شيفرة شريطية مكدسة DataBar**، وهي النسخة المكدسة من عائلة DataBar متعددة الاتجاهات. يمكن لهذا الرمز أن يحمل حتى 14 حرفًا رقميًا، مما يجعله مثاليًا لأكواد GTIN‑14.

## الخطوة 3: ضبط بعد X (عرض الوحدة)

بعد X يتحكم في عرض أصغر شريط (الوحدة). قيمة صغيرة جدًا قد تُظهر بصورة سيئة على الطابعات منخفضة الدقة، بينما قيمة كبيرة جدًا قد تتجاوز مساحة الملصق.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **نصيحة:** الخاصية `Pixels` مريحة للاختبار على الشاشة. للسيناريوهات الموجهة للطباعة، استخدم `generator.Parameters.Barcode.XDimension.Millimeters` بدلاً من ذلك.

## الخطوة 4: تعديل نسبة الأبعاد وحفظ الصورة الأولى

تؤثر **نسبة الأبعاد** على العلاقة بين الارتفاع والعرض للرمز المكدس. نوع DataBar Stacked Omnidirectional يدعم نسبًا من 10 إلى 30. سنُنشئ صورتين لتوضيح التأثير البصري.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

استدعاء `generator.Save` يكتب ملف **PNG** إلى دليل العمل الحالي. التعداد `BarCodeImageFormat.Png` يضمن ضغطًا بدون فقد، وهو مثالي للمعالجة اللاحقة أو الإدراج في ملفات PDF.

## الخطوة 5: تغيير نسبة الأبعاد إلى 30 وحفظ الصورة الثانية

الآن نزيد ارتفاع الأشرطة المكدسة بتغيير نسبة الأبعاد إلى **30**. هذا يجعل الرمز أطول دون تعديل بعد X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

تشغيل البرنامج الآن ينتج ملفي PNG:

* **DatabarAspectRatio15.png** – رمز شريطي مدمج مناسب للملصقات الصغيرة.
* **DatabarAspectRatio30.png** – رمز شريطي أطول يحسّن موثوقية المسح على الأسطح منخفضة التباين.

يمكنك فتح الصور بأي عارض للتحقق من أن الأشرطة مكدسة بشكل صحيح وأن البيانات المشفرة تتطابق مع سلسلة GS1 الأصلية.

## الخطوة 6: التحقق من القيمة المشفرة (اختياري)

إذا كنت بحاجة لتأكيد أن الشيفرة الشريطية تمثل فعلاً السلسلة المدخلة، يمكنك فك تشفيرها باستخدام نفس المكتبة:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

يجب أن يُظهر المُفكك `(01)12345678901231`، مما يثبت أن عملية **إنشاء شيفرة شريطية مكدسة DataBar** حافظت على البيانات.

## المشكلات الشائعة وكيفية تجنّبها

| المشكلة | السبب | الحل |
|-------|----------------|-----|
| الشيفرة تظهر ضبابية | تم ضبط بعد X منخفض جدًا بالنسبة لدقة الإخراج | زيادة `XDimension.Pixels` أو استخدام `Millimeters` للطباعة |
| الماسح يُبلغ “الرمز غير موجود” | نسبة الأبعاد خارج النطاق المدعوم 10‑30 | الحفاظ على النسبة بين 10 و30؛ 15 و30 قيم آمنة |
| ملف PNG يحتوي على علامة مائية | استخدام ترخيص التقييم المجاني لـ Aspose.BarCode | شراء ترخيص كامل أو استخدام النسخة التجريبية للاختبار فقط |
| فشل فك التشفير في الصورة الثانية | تم تكوين المُفكك للرمز الشريطي الخطأ | استخدم `DecodeType.DatabarStackedOmniDirectional` عند قراءة الشيفرات المكدسة |

## الخطوات التالية

الآن بعد أن أصبحت قادرًا على **إنشاء شيفرة شريطية مكدسة DataBar**، قد ترغب في:

* **إدراج ملفات PNG في فواتير PDF** باستخدام مكتبة PDF مثل **Aspose.PDF**.
* **إنشاء شيفرات شريطية في الوقت الفعلي عبر واجهة ويب API** – إرجاع بايتات PNG مباشرةً من متحكم ASP.NET Core.
* **تجربة متغيرات DataBar أخرى** (مثل `DatabarExpanded`، `DatabarLimited`) بتغيير تعداد `EncodeTypes`.
* **ضبط الألوان** عبر تعيين `generator.Parameters.Barcode.ForeColor` و `BackColor` لتصاميم مخصصة للعلامة التجارية.

كل من هذه المواضيع يبني على المفاهيم الأساسية التي تم تغطيتها هنا: تهيئة `BarcodeGenerator`، ضبط المعلمات البصرية، وحفظ النتيجة باستخدام `BarCodeImageFormat`.

---

### الخلاصة

يوضح هذا الدليل كيفية **إنشاء شيفرة شريطية مكدسة DataBar** بصور في C# باستخدام Aspose.BarCode. تعلمت ضبط **بعد X**، تعديل **نسبة أبعاد الشيفرة الشريطية**، وتصدير النتيجة كملفات **PNG** باستخدام `BarcodeGenerator`. مع خطوة فك التشفير الاختيارية، يمكنك أيضًا التحقق من صحة بيانات GS1 المشفرة. طبّق هذه الأنماط في تطبيقات المخزون، الشحن، أو نقاط البيع الخاصة بك، واستكشف العديد من خيارات التخصيص التي توفرها المكتبة. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

تغطي الدروس التالية مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروح خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [ضبط ارتفاع شيفرة DataBar أحادية البعد](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [إنشاء صورة شيفرة شريطية – قسيمة GS1 UPC-A DataBar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}