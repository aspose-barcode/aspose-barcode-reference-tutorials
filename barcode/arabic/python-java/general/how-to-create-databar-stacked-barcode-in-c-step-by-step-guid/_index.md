---
category: general
date: 2026-10-21
description: أنشئ شيفرة شريطية Databar مكدسة بسرعة باستخدام C#. تعلّم ضبط بُعد X،
  وضبط نسبة العرض إلى الارتفاع، وحفظ صور PNG في هذا الدرس الشامل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: ar
lastmod: 2026-10-21
og_description: إنشاء شيفرة شريطية مكدسة (Databar) في C# باستخدام Aspose.BarCode.
  اتبع هذا الدليل لتكوين البُعد X، وتغيير نسبة العرض إلى الارتفاع، وتصدير ملفات PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: إنشاء شيفرة شريطية مكدسة من نوع Databar في C# – دليل برمجي كامل
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: كيفية إنشاء باركود داتابار مكدس في C# – دليل خطوة بخطوة
url: /ar/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء شريط بيانات باركود مكدس في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء شريط بيانات باركود مكدس** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك. سترى كيفية ضبط البُعد X، وتغيير نسبة العرض إلى الارتفاع، وحفظ الباركود كملفات PNG.

إنشاء شريط بيانات باركود مكدس لا يتطلب خط أنابيب بناء معقد. يغطي هذا البرنامج التعليمي كل ما تحتاجه: الحزم المطلوبة، شرح الكود سطرًا بسطر، ونصائح لتجنب المشكلات الشائعة. في النهاية ستتمكن من إنتاج صور باركود متعددة بنسب عرض إلى ارتفاع مختلفة في طريقة واحدة.

## ما الذي ستحتاجه

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت  
* Visual Studio 2022 (أو أي بيئة تطوير تدعم C#)  
* **Aspose.BarCode for .NET** حزمة NuGet – المكتبة التي توفر `BarcodeGenerator` و `EncodeTypes`  

يمكنك إضافة الحزمة بالأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ مشروع وحدة تحكم جديد أو أضف الكود إلى مشروع موجود. استورد المساحات الاسمية المطلوبة حتى يتعرف المترجم على فئات الباركود.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

تُظهر عبارات `using` هذه `BarcodeGenerator` و `EncodeTypes` و `BarCodeImageFormat` المستخدمة لاحقًا في المثال.

## الخطوة 2: تعريف مجلد الإخراج

اختر مجلدًا حيث سيتم كتابة ملفات PNG المُولدة. يعمل المسار المطلق أو النسبي بنفس الطريقة؛ يستخدم المثال مجلدًا نسبيًا يُدعى `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

إنشاء المجلد برمجيًا يمنع حدوث أخطاء وقت التشغيل عندما يكون الدليل غير موجود.

## الخطوة 3: تهيئة مولد **إنشاء شريط بيانات باركود مكدس**

أنشئ كائن `BarcodeGenerator` باستخدام `EncodeTypes.DatabarStackedOmniDirectional`. تتبع البيانات النموذجية `(01)12345678901231` تنسيق GS1‑128 المطلوب لـ DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

كائن المولد يحمل جميع المعلمات التي تؤثر على المظهر البصري للباركود.

## الخطوة 4: ضبط بُعد X (عرض البكسل لأصغر شريط)

بُعد X يتحكم في الحجم الكلي للباركود دون تعديل البيانات المشفرة. قيمة `2` بكسل توفر صورة واضحة وقابلة للمسح لمعظم دقات الشاشات.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

قم بتعديل هذه القيمة إذا كنت بحاجة إلى باركود أكبر أو أصغر؛ حافظ على النسبة بين العرض والارتفاع ثابتة.

## الخطوة 5: تكوين نسبة العرض إلى الارتفاع وحفظ الصورة الأولى

نسبة العرض إلى الارتفاع تحدد العلاقة بين الارتفاع والعرض لشريط بيانات باركود مكدس. نسبة `15` هي القيمة الافتراضية الشائعة التي تنتج مظهرًا مدمجًا.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

طريقة `Save` تكتب ملف PNG إلى المجلد المحدد سابقًا. اسم الملف يوضح بوضوح نسبة العرض إلى الارتفاع المستخدمة.

### النتيجة المتوقعة لنسبة العرض إلى الارتفاع 15

الصورة المُولدة `DatabarAspectRatio15.png` تشبه الشكل التالي.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*نص بديل:* `create databar stacked barcode image saved with aspect ratio 15`

## الخطوة 6: تغيير نسبة العرض إلى الارتفاع وحفظ صورة ثانية

يمكنك إعادة استخدام نفس كائن `BarcodeGenerator` لإنتاج تنويعات. تغيير `AspectRatio` إلى `30` يضاعف ارتفاع كل مجموعة أشرطة، وهو ما قد يكون مطلوبًا للطباعة عالية الدقة.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### النتيجة المتوقعة لنسبة العرض إلى الارتفاع 30

صورة `DatabarAspectRatio30.png` أطول، مع الحفاظ على نفس العرض وزيادة القابلية للقراءة للمسحات البعيدة.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*نص بديل:* `create databar stacked barcode image saved with aspect ratio 30`

## الكود الكامل

دمج جميع الخطوات ينتج برنامجًا مستقلًا يمكنك تشغيله فورًا.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

قم بتجميع البرنامج وتشغيله. بعد التنفيذ، يحتوي دليل `Barcodes` على ملفي PNG، كل منهما يمثل **إنشاء شريط بيانات باركود مكدس** بنسبة عرض إلى ارتفاع مختلفة.

## نصائح احترافية ومشكلات شائعة

* **نصيحة احترافية:** حافظ على بُعد X بين 1 px و 4 px لمعظم حالات الاستخدام على الشاشات. القيم الأكبر تزيد حجم الملف دون تحسين موثوقية القراءة.  
* **مشكلة:** تغيير قيمة `EncodeTypes` بعد إنشاء المولد لا يحدّث الترميز الداخلي. دائمًا حدد `EncodeTypes` الصحيح في المُنشئ.  
* **نصيحة احترافية:** عندما تحتاج إلى أكثر من نسبتي عرض إلى ارتفاع، استخدم حلقة عبر مصفوفة من القيم الصحيحة واستدعِ `Save` داخل الحلقة. هذا يقلل من تكرار الكود.  
* **مشكلة:** الحفظ إلى مسار بدون صلاحية كتابة يسبب استثناء `UnauthorizedAccessException`. تأكد من تشغيل التطبيق بصلاحيات نظام الملفات المناسبة.

## الخلاصة

أنت الآن تعرف كيفية **إنشاء شريط بيانات باركود مكدس** في C# باستخدام Aspose.BarCode. غطى الدليل إعداد البيئة، ضبط بُعد X، تعديل نسبة العرض إلى الارتفاع، وحفظ ملفات PNG. مع هذه الأساسيات يمكنك توليد تنويعات إضافية، دمج إنشاء الباركود في واجهات برمجة التطبيقات الويب، أو تضمين الصور في تقارير PDF.

بعد ذلك، استكشف المواضيع ذات الصلة مثل **DataBar Stacked Omnidirectional** أفضل ممارسات المسح، تضمين الباركود في ردود **ASP.NET Core**، أو إنشاء **QR codes** باستخدام نفس المكتبة. جرّب `EncodeTypes` مختلفة وصيغ الصور لتتناسب مع احتياجات تطبيقك.

برمجة سعيدة!

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء صور PNG لشريط البيانات باستخدام C# و Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [كيفية ضبط الأعمدة لشريط بيانات موسع مكدس – دليل كامل C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [شريط بيانات مكدس متعدد الاتجاهات في C# – دليل كامل](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}