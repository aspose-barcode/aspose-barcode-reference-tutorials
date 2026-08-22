---
category: general
date: 2026-08-22
description: كيفية إنشاء الباركود في C# باستخدام Aspose.BarCode. تعلم كيفية إنشاء
  صورة باركود في C# خطوة بخطوة، وتعطيل المكوّن ثنائي الأبعاد، وحفظ ملفات PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: ar
lastmod: 2026-08-22
og_description: كيفية إنشاء الباركود في C# باستخدام Aspose.BarCode. يوضح لك هذا البرنامج
  التعليمي كيفية إنشاء صورة باركود في C# باستخدام DataBar Expanded، وتفعيل المكوّن
  ثنائي الأبعاد، وحفظ ملفات PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: كيفية إنشاء باركود في C# – دليل كامل لإنشاء صورة باركود باستخدام C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: كيفية إنشاء باركود في C# – إنشاء صورة باركود باستخدام DataBar Expanded
url: /ar/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء الباركود في C# – إنشاء صورة باركود c# باستخدام DataBar Expanded

إنشاء باركود في C# هو طلب شائع عندما تحتاج إلى تضمين بيانات قابلة للقراءة آليًا في تطبيقاتك. يوضح هذا الدليل كيفية إنشاء صورة باركود c# باستخدام مكتبة Aspose.BarCode، وتعطيل المكوّن المركب ثنائي الأبعاد، وحفظ النتيجة كملفات PNG.

سترى برنامجًا كاملًا قابلاً للتنفيذ، شرحًا لكل خيار تكوين، ونصائح لتخصيص المخرجات. لا حاجة لأي وثائق خارجية—فقط الشيفرة أدناه وبيئة تطوير .NET.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

* .NET 6.0 SDK أو أحدث مثبت  
* Visual Studio 2022 (أو أي بيئة تطوير تدعم .NET)  
* حزمة NuGet Aspose.BarCode لـ .NET (`Aspose.BarCode`)  

يمكنك إضافة الحزمة بالأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

توفر المكتبة الفئة `BarcodeGenerator` المستخدمة طوال هذا الدرس.

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ تطبيقًا كونسول جديدًا واستورد المساحات الاسمية المطلوبة:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

تحتوي مساحة الاسم `Aspose.BarCode.Generation` على جميع الفئات اللازمة لتكوين وعرض الباركودات.

## الخطوة 2: تهيئة مولد باركود DataBar Expanded

السطر الوظيفي الأول ينشئ كائن `BarcodeGenerator` للرمز **DataBar Expanded** ويزوده بسلسلة البيانات الخام. تتبع سلسلة البيانات تنسيق معرف التطبيق GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

إنشاء المولد يخصص لوحة bitmap الداخلية، بحيث يمكنك تعديل الحجم والمظهر قبل العرض.

## الخطوة 3: تعريف عرض الوحدة (X‑dimension)

الـ X‑dimension يتحكم في عرض أصغر عنصر في الباركود. ضبطه بالبكسل يمنحك تحكمًا دقيقًا في حجم الصورة النهائي.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

قيمة `2` بكسل تعمل جيدًا للعرض على الشاشة؛ زدها للحصول على طباعة ذات دقة أعلى.

## الخطوة 4: تعطيل المكوّن المركب ثنائي الأبعاد

يمكن أن يتضمن DataBar Expanded مكوّنًا ثنائي الأبعاد يحمل معلومات إضافية. لتوليد باركود **بدون** هذا المكوّن، اضبط العلامة على `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

تعطيل المكوّن يقلل من التعقيد البصري وينتج ملف PNG أصغر.

## الخطوة 5: حفظ صورة الباركود بدون المكوّن ثنائي الأبعاد

اختر دليلًا للإخراج واكتب الصورة إلى القرص. يضمن تعداد `BarCodeImageFormat.Png` حفظ ملف PNG غير مضغوط.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

بعد هذا الاستدعاء، يحتوي الملف `Databar2DComponentDisabled.png` على باركود DataBar Expanded نظيف.

## الخطوة 6: تمكين المكوّن المركب ثنائي الأبعاد

إذا كنت بحاجة إلى طبقة البيانات الإضافية، أعد تمكين العلامة. يمكن إعادة استخدام نفس كائن المولد، مما يجنب إنشاء كائن ثاني.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## الخطوة 7: حفظ صورة الباركود مع تمكين المكوّن ثنائي الأبعاد

قم بعرض الصورة الثانية باستخدام نفس الإعدادات، باستثناء علم 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

الآن يظهر الملف `Databar2DComponentEnabled.png` الباركود مع النمط الثنائي الأبعاد الإضافي.

## الكود الكامل

انسخ المقتطف الكامل أدناه إلى `Program.cs` وشغّل المشروع. سيُنشئ البرنامج ملفي PNG في المجلد الذي تحدده.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### النتيجة المتوقعة

تشغيل البرنامج يطبع:

```
Barcode images generated successfully.
```

ويُنشئ ملفين:

* `Databar2DComponentDisabled.png` – باركود بدون المكوّن ثنائي الأبعاد  
* `Databar2DComponentEnabled.png` – باركود مع المكوّن ثنائي الأبعاد  

افتح ملفات PNG في أي عارض صور للتحقق من الاختلاف البصري.

## الاختلافات الشائعة والحالات الحدية

| الوضع | التعديل |
|-----------|------------|
| **رموز مختلفة** | استبدل `EncodeTypes.DatabarExpanded` بقيمة أخرى، مثل `EncodeTypes.Code128`. |
| **دقة أعلى** | زيادة `XDimension.Pixels` إلى 4 أو 5، أو ضبط `Resolution` في `barcodeGenerator.Parameters.Image`. |
| **تنسيقات صور أخرى** | استخدم `BarCodeImageFormat.Jpeg`، `BarCodeImageFormat.Bmp`، أو `BarCodeImageFormat.Svg`. |
| **تشغيل في تطبيق ويب** | بث بايتات الصورة مباشرةً إلى استجابة HTTP بدلاً من حفظها على القرص. |
| **إدارة الذاكرة** | غلف المولد داخل كتلة `using` إذا كنت تستهدف .NET Framework لضمان تحرير الموارد غير المُدارة. |

## نصائح احترافية

* **إعادة استخدام المولد** – تغيير علم 2‑D فقط يتجنب إعادة إنشاء الكائن، مما يوفر دورات المعالج.  
* **تحقق من صحة البيانات** – يجب أن تتبع بيانات GS1 القواعد الدقيقة للطول والاختبار الرقمي؛ الإدخال غير الصالح يطرح استثناء `ArgumentException`.  
* **معالجة دفعات** – تكرار عبر مجموعة من سلاسل البيانات، تبديل علم 2‑D حسب الحاجة، وحفظ كل صورة باسم ملف فريد.  

## الخلاصة

أنت الآن تعرف كيفية إنشاء باركود في C# وإنشاء صورة باركود c# مع تحكم كامل في المكوّن المركب ثنائي الأبعاد. يوضح المثال تهيئة المولد، ضبط X‑dimension، تبديل المكوّن، وحفظ ملفات PNG. من هنا يمكنك استكشاف رموز أخرى، تضمين الصور في ملفات PDF، أو دمج توليد الباركود في خدمات ASP.NET Core.

--- 

*الخطوات التالية*: جرّب توليد رموز QR، جرب دقات صور مختلفة، أو أدمج ملفات PNG المُولدة في PDF باستخدام Aspose.PDF. هذه الإضافات تبني على نفس واجهة برمجة `BarcodeGenerator` وتبقي سير عملك متسقًا.

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تُبنى على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف طرق تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET – دليل خطوة بخطوة](/barcode/english/net/datamatrix-barcode-configuration/)
- [كيفية إنشاء وضبط ارتفاع باركود One-Dimensional Databar باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [كيفية إنشاء باركود Aztec بنسبة عرض إلى ارتفاع مخصصة باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}