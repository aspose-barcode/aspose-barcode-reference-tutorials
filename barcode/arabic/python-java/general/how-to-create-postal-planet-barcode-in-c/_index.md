---
category: general
date: 2026-11-23
description: إنشاء رمز شريطي بريدي من نوع Planet في C# باستخدام Aspose.BarCode. تعلّم
  كيفية توليد رمز Planet، ضبط البُعد X، وحفظ الأعمدة المملوءة أو الفارغة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: ar
lastmod: 2026-11-23
og_description: إنشاء رمز شريطي كوكبي بريدي بلغة C# وتعلم كيفية توليد رمز شريطي كوكبي
  باستخدام Aspose.BarCode. اتبع المثال الكامل لإنتاج أشرطة مملوءة وفارغة.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: كيفية إنشاء باركود بوستال بلانت في C# – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: كيفية إنشاء باركود بوستال بلانت في C#
url: /ar/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود Postal Planet في C#

إذا كنت بحاجة إلى **إنشاء باركود Postal Planet** في تطبيق .NET، يوضح لك هذا الدليل بالضبط **كيفية توليد باركود Planet** باستخدام مكتبة Aspose.BarCode. ستتعرف على كيفية ضبط البُعد X، التبديل بين الأشرطة المملوءة والفارغة، وحفظ الصور بصيغة PNG.

توليد باركود Planet شائع لخدمات البريد التي تتطلب رموزًا ذات كثافة عالية وقابلة للقراءة آليًا. بنهاية هذا البرنامج التعليمي ستحصل على ملفي PNG—أحدهما بأشرطة صلبة والآخر بأشرطة مجوفة—جاهزين للتكامل مع أي سير عمل بريدي.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت.
* Visual Studio 2022 (أو أي محرر C#) مُعد لتطوير .NET.
* رخصة NuGet سارية لـ **Aspose.BarCode for .NET**. قم بتثبيت الحزمة باستخدام:

```bash
dotnet add package Aspose.BarCode
```

لا توجد خدمات خارجية إضافية مطلوبة؛ المكتبة تقوم بكل عمليات الترميز محليًا.

## الخطوة 1 – إنشاء باركود Postal Planet

العملية الأولى هي إنشاء كائن `BarcodeGenerator` للرمز **Planet** وتوفير البيانات التي سيتم ترميزها. يجب أن تكون سلسلة البيانات رقمية وتصل إلى 12 رقمًا كحد أقصى وفقًا لمواصفات البريد.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

إنشاء المولد يخصص جميع البُنى الداخلية اللازمة للتصوير. قيمة التعداد `EncodeTypes.Planet` تختار خوارزمية الترميز الصحيحة لتنسيق البريد.

## الخطوة 2 – ضبط البُعد X لتحسين الرؤية

البُعد X يحدد عرض الوحدة الواحدة (أصغر عنصر شريط). قيمة 4 بكسل توفر تمثيلًا بصريًا واضحًا دون تكبير الصورة الكلية.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

تعديل البُعد X ضروري عندما يُطبع الباركود على وسائط منخفضة الدقة. سيتم إعادة استخدام نفس الإعداد لإصدار الأشرطة الفارغة للحفاظ على تناسق الصورتين.

## الخطوة 3 – حفظ الباركود بأشرطة مملوءة

بشكل افتراضي، يقوم المولد برسم **أشرطة مملوءة** (وحدات سوداء صلبة). حفظ الصورة يتم باستدعاء طريقة واحدة تكتب ملف PNG إلى القرص.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

استبدل `YOUR_DIRECTORY` بالمسار الفعلي حيث تريد حفظ ملفات الإخراج. يضمن تعداد `BarCodeImageFormat.Png` ضغطًا بدون فقدان، وهو مثالي للمعالجة اللاحقة.

## الخطوة 4 – إنشاء مولد باركود Planet آخر للأشرطة الفارغة

لإنتاج نسخة تستخدم **أشرطة فارغة** (وحدات بيضاء على خلفية سوداء)، تحتاج إلى كائن `BarcodeGenerator` ثاني. إعادة استخدام نفس سلسلة البيانات يضمن أن الصورتين تمثلان نفس الرمز البريدي.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

إنشاء مولد منفصل يعزل خاصية `FilledBars`، مما يسمح لك بتبديل النمط البصري دون التأثير على الصورة الأولى.

## الخطوة 5 – ضبط المولد لرسم أشرطة فارغة

علامة `FilledBars` تقلب وضعية الرسم. ضبطها على `false` يخبر المكتبة برسم الأشرطة كخالية (شفافة) مع الحفاظ على الخلفية صلبة.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

الحفاظ على بُعد X نفسه كما في النسخة المملوءة يضمن أن ملفي PNG لهما نفس الأبعاد، مما يبسط حسابات التخطيط في قوالب الطباعة.

## الخطوة 6 – حفظ الباركود الذي يرسم أشرطة فارغة

أخيرًا، اكتب صورة الأشرطة الفارغة إلى القرص. يُستخدم نفس تنسيق PNG، لكن يمكنك التحويل إلى JPEG أو BMP بتغيير قيمة `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

في هذه المرحلة لديك ملفان:

* `PostalPlanetFilledBars.png` – أشرطة سوداء صلبة.
* `PostalPlanetEmptyBars.png` – أشرطة مجوفة على خلفية سوداء.

كلاهما يطابق مواصفات البريد للرمز Planet.

## الكود المصدر الكامل

دمج جميع الخطوات معًا ينتج تطبيقًا صغيرًا من نوع console يمكنك تشغيله مباشرة.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

قم بتجميع البرنامج وتشغيله:

```bash
dotnet run
```

ستطبع وحدة التحكم *Barcodes generated successfully.* وتظهر ملفا PNG في مجلد المشروع.

## النتيجة المتوقعة

فيما يلي تمثيل بصري لصورة الأشرطة المملوءة. النسخة ذات الأشرطة الفارغة تبدو متطابقة باستثناء أن الأشرطة شفافة.

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*نص بديل للصورة:* **مثال على باركود Postal Planet تم إنشاؤه بأشرطة مملوءة** (يحتوي على الكلمة المفتاحية الأساسية).

كلا الصورتين بحجم 150 × 150 بكسل افتراضيًا، لكن يمكنك التحكم في الحجم الكلي باستخدام معلمات `ImageWidth` و `ImageHeight` إذا احتجت دقة مختلفة.

## تنويعات اختيارية

### تغيير تنسيق الصورة

إذا كان نظامك اللاحق يفضّل JPEG، استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg`. JPEG يضيف تشوهات ضغط، لذا استخدمه فقط عندما يكون حجم الملف قيّدًا حاسمًا.

### تكبير الباركود

يمكنك تكبير الباركود مع الحفاظ على عرض الوحدة عن طريق تعديل خاصية `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

قِيَم DPI الأعلى تحسّن جودة الطباعة على الطابعات الليزرية.

### استخدام لون خلفية مخصص

يمكن ضبط الخلفية باستخدام:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

هذا مفيد للاختبار البصري لكن يجب تجنبه في ملصقات البريد الإنتاجية، التي تتطلب خلفية بيضاء.

## الأسئلة المتكررة

**هل يعمل هذا مع .NET Core؟**  
نعم. تستهدف مكتبة Aspose.BarCode .NET Standard 2.0، المتوافقة مع .NET 5، .NET 6، و .NET Core 3.1.

**ماذا لو احتوت سلسلة البيانات على أحرف غير رقمية؟**  
باركودات Planet تقبل مدخلات رقمية فقط. إدخال أحرف أو رموز سيؤدي إلى رفع استثناء `BarcodeException`. تحقق من صحة المدخل قبل إنشاء المولد.

**هل يمكن توليد الباركود في الذاكرة دون كتابة إلى القرص؟**  
استخدم طريقة `GenerateBarCodeImage` للحصول على كائن `System.Drawing.Image`، ثم قم ببثه مباشرة إلى استجابة أو قاعدة بيانات.

## الخلاصة

أنت الآن تعرف **كيفية إنشاء باركود Postal Planet** في C# وتفهم **كيفية توليد باركود Planet** بأنماط الأشرطة المملوءة والفارغة. غطى الدليل سير العمل الكامل—من تهيئة المولد، ضبط البُعد X، تبديل علم `FilledBars`، إلى حفظ ملفات PNG. جرّب تنسيقات الصور، إعدادات DPI، وألوان الخلفية لتكييف الباركود مع نظام البريد الخاص بك.

في الخطوة التالية، استكشف رموز بريدية أخرى مثل **POSTNET** أو **Intelligent Mail** باستخدام نفس واجهة Aspose.BarCode API. تعديل المعلمات مثل `EncodeTypes.Postnet` يتبع النمط نفسه الموضح هنا، مما يتيح لك بناء مجموعة شاملة لتوليد الباركود في قاعدة شفرة واحدة.

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف نهج تنفيذ بديلة في مشاريعك.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}