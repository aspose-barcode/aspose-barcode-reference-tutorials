---
category: general
date: 2026-08-12
description: إنشاء صورة الباركود في C# باستخدام BarCodeGenerator. تعلّم كيفية توليد
  DataBar، التحكم في حجم صورة الباركود، وإنشاء عدة باركودات بكفاءة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: ar
lastmod: 2026-08-12
og_description: إنشاء صورة الباركود في C# باستخدام BarCodeGenerator. يوضح هذا الدليل
  خطوة بخطوة كيفية إنشاء رموز DataBar، وضبط حجم صورة الباركود، وإنتاج عدة باركودات.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: إنشاء صورة باركود في C# – دليل BarCodeGenerator الكامل
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: إنشاء صورة باركود في C# باستخدام BarCodeGenerator
url: /ar/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود في C# باستخدام BarCodeGenerator

إذا كنت بحاجة إلى **إنشاء صورة باركود** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك باستخدام فئة `BarCodeGenerator`. سواءً كنت تبني نظام نقاط بيع تجزئة أو أداة تتبع مخزون، ستتعلم كيفية إنشاء رموز DataBar، والتحكم في حجم صورة الباركود، وإنتاج عدة باركودات في تشغيل واحد.

ستكتشف أيضًا كيف يتيح لك API **barcode generator c#** تعديل الأبعاد، وتبديل صيغ الإخراج، ومعالجة الحالات الخاصة مثل سلاسل البيانات غير الصالحة. بنهاية الدليل يمكنك بثقة **إنشاء عدة باركودات** دون كتابة كود متكرر.

## المتطلبات المسبقة

- .NET 6.0 أو أحدث مثبت  
- بيئة تطوير (Visual Studio، Rider، أو VS Code)  
- حزمة NuGet Aspose.BarCode for .NET (أو أي مكتبة متوافقة توفر `BarCodeGenerator`)  

```bash
dotnet add package Aspose.BarCode
```

## ما يغطيه هذا الدليل

1. إعداد مثيل **barcode generator c#** لتشفير DataBar Omni‑directional.  
2. تعديل **حجم صورة الباركود** عن طريق تغيير X‑dimension وارتفاع الشريط.  
3. استخدام حلقة **إنشاء عدة باركودات** بأارتفاعات مختلفة.  
4. حفظ الصور كملفات PNG والتحقق من النتيجة.  

![Create barcode image example](barcode-example.png){alt="مثال على إنشاء صورة باركود"}

## الخطوة 1: تهيئة المُولد – أساسيات إنشاء صورة الباركود

الخطوة الأولى هي إنشاء كائن `BarCodeGenerator` باستخدام الترميز المطلوب. للحصول على رمز DataBar Omni‑directional تستخدم `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**لماذا هذا مهم:** إنشاء المُولد يحدد قواعد الترميز وبيانات الحمولة. إذا تجاهلت قيمة `EncodeTypes` الصحيحة، ستنتج المكتبة باركود غير مدعوم أو ستطرح استثناءً.

## الخطوة 2: ضبط X‑dimension وارتفاع الشريط – التحكم في حجم صورة الباركود

الحجم البصري للباركود يتحكم فيه معاملان:

| Parameter | ما يتحكم فيه | النطاق المعتاد |
|-----------|--------------|----------------|
| `x_dimension.pixels` | عرض أصغر وحدة (النقطة) | 1 – 4 px |
| `bar_height.pixels`  | ارتفاع الشرائط العمودية | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**نصيحة احترافية:** X‑dimension أصغر ينتج صورة ذات دقة أعلى ولكن قد يكون من الصعب مسحها على طابعات منخفضة الجودة. اضبط القيمة بناءً على جهاز المسح المستهدف.

## الخطوة 3: حفظ أول باركود – إنشاء صورة باركود بارتفاع 30 px

الآن يمكنك توليد الصورة وكتابتها إلى القرص. طريقة `Save` تقبل مسار ملف وتعداد صيغة الصورة.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**النتيجة المتوقعة:** ملف PNG باسم `Databar30.png` يظهر في `C:\Barcodes`. فتح الملف يظهر رمز DataBar Omni‑directional بنمط واضح وعالي التباين.

## الخطوة 4: تغيير الارتفاع وتوليد صور إضافية – إنشاء عدة باركودات

لـ **إنشاء عدة باركودات** بأبعاد مختلفة تحتاج فقط إلى تعديل خاصية `BarHeight` واستدعاء `Save` مرة أخرى. هذا يتجنب إعادة إنشاء المُولد، مما يوفر الذاكرة ووقت المعالج.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**لماذا هذا يعمل:** كائن `BarCodeGenerator` يحتفظ بجميع إعدادات التكوين. تعديل خاصية واحدة يحدث محرك الرسم للنداء التالي لـ `Save`، مما يتيح لك **إنشاء عدة باركودات** بكفاءة.

## الخطوة 5: متقدم – كيفية توليد DataBar ببيانات مخصصة

المثال أعلاه يستخدم حمولة GS1 ثابتة. في السيناريوهات الواقعية غالبًا ما تحتاج إلى تضمين معرفات منتجات متغيرة. المكتبة تقبل أي سلسلة تتطابق مع مواصفات DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**نقطة رئيسية:** ضبط `generator.CodeText` يحدث البيانات المشفرة دون إعادة إنشاء الكائن. هذا هو النمط الموصى به لـ **how to generate databar** عند التعامل مع مجموعات بيانات كبيرة.

## الخطوة 6: التحقق وحل المشكلات – التأكد من صحة حجم صورة الباركود

بعد توليد الصور، قد ترغب في التأكد برمجياً من أن الأبعاد تطابق توقعاتك. فئة `Image` من `System.Drawing` يمكنها قراءة الملف وإبلاغ حجمه.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

إذا لم يعكس الارتفاع القيمة التي ضبطتها، تحقق من:

- **X‑dimension**: قيمة صغيرة جدًا قد تتسبب في تقريب الارتفاع من قبل المُعالج.  
- **Image format**: بعض الصيغ (مثل JPEG) تطبق ضغطًا قد يغيّر أبعاد البكسل عند الحفظ. PNG يحافظ على الأبعاد الدقيقة.

## الخطوة 7: أفضل الممارسات لحجم صورة الباركود والأداء

| التوصية | السبب |
|----------------|--------|
| احتفظ بـ `x_dimension.pixels` بين 2 – 3 px لمعظم الماسحات. | يوفر توازنًا بين قابلية القراءة وحجم الملف. |
| استخدم PNG للإخراج غير الفاقد عندما سيتم طباعة الصورة. | يضمن أبعادًا دقيقة وحوافًا حادة. |
| أعد استخدام كائن `BarCodeGenerator` واحد عند توليد العديد من الباركودات. | يقلل من عبء تخصيص الكائنات. |
| تحقق من صحة سلسلة الإدخال وفقًا لمعيار GS1 قبل تعيينها إلى `CodeText`. | يمنع الاستثناءات أثناء التشغيل والقراءات غير الصالحة. |
| احفظ الصور المولدة في مجلد مخصص مع تسمية واضحة (مثال: `Databar_{GTIN}.png`). | يبسط المعالجة اللاحقة ومسارات التدقيق. |

## مثال كامل يعمل

فيما يلي البرنامج الكامل الذي يدمج جميع الخطوات من التهيئة حتى التحقق. انسخ الكود إلى مشروع وحدة تحكم جديد وشغّله.



## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة تعمل مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء صورة باركود – قسيمة GS1 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [إنشاء صورة باركود DotCode – الصفوف والأعمدة (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [كيفية إنشاء منطقة هادئة للباركود ITF-14 باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}