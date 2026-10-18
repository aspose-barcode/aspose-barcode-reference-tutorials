---
category: general
date: 2026-10-18
description: تعلم كيفية إنشاء باركود PDF417 باستخدام C# و Aspose.BarCode. يغطي هذا
  البرنامج التعليمي إنشاء PDF417 الأساسي، المدمج، الماكرو والمايكرو مع الكود الكامل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: ar
lastmod: 2026-10-18
og_description: إنشاء شيفرة PDF417 في C# باستخدام Aspose.BarCode. اتبع هذا الدليل
  لإنشاء شيفرات PDF417 الأساسية، المدمجة، الماكرو والمايكرو خطوة بخطوة.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: إنشاء باركود PDF417 في C# – دليل Aspose.BarCode الكامل
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode – دليل خطوة بخطوة
url: /ar/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شيفرة PDF417 في C# باستخدام Aspose.BarCode – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء شيفرة PDF417** في تطبيق .NET، فإن هذا الدليل يشرح لك العملية بالكامل. ستتعرف على كيفية إنشاء شيفرة أساسية، تمكين الوضع المدمج، إضافة بيانات ماكرو، وإنتاج نسخة مصغرة—كل ذلك مع شروحات واضحة وكود قابل للتنفيذ.

إنشاء شيفرات PDF417 شائع في اللوجستيات، تذاكر الدخول، وإدارة المستندات. بنهاية هذا الدليل ستكون قادرًا على دمج إنشاء الشيفرات في أي مشروع C# دون الحاجة إلى أدوات خارجية.

## المتطلبات المسبقة

* .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.7+)
* Visual Studio 2022 أو أي بيئة تطوير C#
* **Aspose.BarCode for .NET** حزمة NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* صلاحية كتابة في المجلد الذي سيتم حفظ ملفات PNG المولدة فيه

لا يلزم أي إعداد إضافي؛ المكتبة تتعامل مع جميع تفاصيل الترميز على المستوى المنخفض.

## الخطوة 1: إنشاء شيفرة PDF417 أساسية

الخطوة الأولى تُنشئ شيفرة PDF417 عادية بحجم مخصص وعدد أعمدة محدد.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**لماذا هذه الإعدادات مهمة**

* `XDimension.Pixels` يتحكم في الحجم الفعلي لكل عنصر من عناصر الشيفرة. قيمة 2 تنتج صورة واضحة على معظم الشاشات والطابعات.
* `Pdf417.Columns` يحدد عدد الأعمدة التي تحتويها الشيفرة. عدد أقل من الأعمدة يقلل العرض؛ عدد أكبر يزيد سعة البيانات.

تشغيل الكود يُنشئ الملف `Pdf417Basic.png`، والذي يبدو كرمز PDF417 نموذجي بثلاثة أعمدة بيانات وعمود بيانات ميتا كامل على الجانب الأيمن.

## الخطوة 2: تمكين الوضع المدمج (المقتطع)

الوضع المدمج يزيل عمود البيانات الميتا على الجانب الأيمن، مما يجعل الشيفرة أضيق. هذا مفيد عندما تكون المساحة محدودة لكن يمكن إعادة بناء البيانات من الصفوف المتبقية.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**لماذا القص؟**  
عند كون `Truncate` `true`، يتجاهل المُولد العمود الاختياري الأيمن الذي يخزن تصحيح الأخطاء وبيانات الميتا على مستوى الملف. الشيفرة الناتجة تشغل أعمدة أقل مع الحفاظ على قابلية القراءة لمعظم قارئات PDF417.

## الخطوة 3: إنشاء شيفرة Macro PDF417 مع بيانات ماكرو على مستوى الملف

Macro PDF417 يوسع الصيغة القياسية بمعرفات القطاعات، مما يسمح بتقسيم مستند كبير إلى عدة شيفرات. هذا مفيد لتشفير سلاسل طويلة أو ملفات متعددة الصفحات.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**شرح حقول الماكرو**

| الخاصية | الغرض |
|----------|---------|
| `MacroPdf417FileID` | معرف فريد للملف بأكمله؛ جميع القطاعات تشترك في هذه القيمة. |
| `MacroPdf417SegmentID` | فهرس القطاع الحالي (يبدأ من 1). |
| `MacroPdf417SegmentsCount` | العدد الإجمالي للقطاعات التي تشكل مجموعة البيانات الكاملة. |

يمكن لقارئ يدعم Macro PDF417 إعادة تجميع البيانات الأصلية بقراءة جميع القطاعات واستخدام هذه المعرفات.

## الخطوة 4: إنشاء شيفرة Micro PDF417 للبيانات القصيرة

Micro PDF417 هو نسخة مدمجة صُممت للحمولات الصغيرة (حتى 90 حرف). يحد نطاق الأعمدة إلى 1‑4، مما يجعل الشيفرة مناسبة للملصقات الصغيرة أو الأجهزة ذات مساحة عرض محدودة.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**متى تستخدم Micro PDF417**  
استخدم هذه النسخة عندما تكون حمولة البيانات قصيرة وتحتاج إلى أصغر شيفرة ممكنة. إنها مثالية لبطاقات الجرد، بطاقات الدخول، أو أي سيناريو تكون فيه مساحة الشاشة محدودة.

## مثال كامل يعمل

فيما يلي تطبيق وحدة تحكم مستقل يولد الأنواع الأربعة من الشيفرات في تشغيل واحد. انسخ الكود إلى مشروع C# جديد، استبدل `YOUR_DIRECTORY` بمسار مجلد موجود، ثم شغّله.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**الناتج المتوقع**

تشغيل البرنامج يُنشئ أربعة ملفات PNG في المجلد المحدد:

* `Pdf417Basic.png` – شيفرة قياسية بثلاثة أعمدة
* `CompactPdf417.png` – نفس البيانات، مع عمود أيمن مقطوع
* `MacroPdf417.png` – شيفرة ماكرو تحتوي على بيانات الميتا للقطاعات
* `MicroPdf417.png` – شيفرة مصغرة مدمجة للسلاسل القصيرة

افتح أي صورة بعارض صور؛ ستلاحظ أنماط PDF417 المميزة. مسحها باستخدام قارئ شيفرات محمول (مثل ZXing أو Scandit) يُعيد السلاسل النصية الأصلية.

## أسئلة شائعة ونصائح

* **ماذا لو كانت الشيفرة غير واضحة؟**  
  زد `XDimension.Pixels` إلى 3 أو 4. الأحجام الأكبر للوحدات تُنتج صورًا ذات دقة أعلى، لكن بحجم ملف أكبر.

* **هل يمكنني إخراج SVG بدلاً من PNG؟**  
  نعم. استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Svg` في استدعاءات `Save`.

* **هل أحتاج لتحديد مستوى تصحيح الأخطاء يدويًا؟**  
  Aspose.BarCode يختار مستوىً أمثل تلقائيًا. لحالات الاستخدام المتخصصة يمكنك تعديل `Pdf417.ErrorCorrectionLevel`.

* **كيف أدمج الشيفرة في مستند PDF؟**  
  استخدم `Aspose.Pdf` لإضافة PNG أو SVG المولدة كعنصر صورة في صفحة PDF.

* **هل المكتبة آمنة للاستخدام في بيئات متعددة الخيوط؟**  
  كل كائن `BarcodeGenerator` مستقل؛ يمكنك إنشاء مولدات على خيوط متعددة دون مشاركة حالة.

## الخلاصة

أنت الآن تعرف كيفية **إنشاء شيفرة PDF417** في C# باستخدام Aspose.BarCode، بما يشمل النسخ الأساسية، المدمجة، الماكرو، والمصغرة.

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء شيفرة pdf417 في C# – دليل خطوة بخطوة](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [كيفية إنشاء شيفرة PDF417 في C# مع وضع مدمج](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [كيفية إنشاء شيفرة macro PDF417 في C# باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}