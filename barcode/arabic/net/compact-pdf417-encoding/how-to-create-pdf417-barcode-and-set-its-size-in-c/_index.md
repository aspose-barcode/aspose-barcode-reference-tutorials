---
category: general
date: 2026-09-22
description: تعرّف على كيفية إنشاء باركود PDF417 في C#، وضبط حجم الباركود، وإنشاء
  ملفات صور الباركود مع أمثلة شفرة واضحة خطوة بخطوة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: ar
lastmod: 2026-09-22
og_description: إنشاء رمز شريطي PDF417 في C# بسرعة. يوضح هذا الدليل كيفية ضبط حجم
  الرمز الشريطي، وتفعيل الوضع المدمج، وإخراج صور PNG لأي مشروع .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: إنشاء رمز شريطي PDF417 في C# – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: كيفية إنشاء رمز شريطي PDF417 وتحديد حجمه في C#
url: /ar/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود PDF417 وتحديد حجمه في C#

إذا كنت بحاجة إلى **إنشاء باركود PDF417** في C#، يوضح لك هذا الدليل كيفية توليد الباركود، التحكم في أبعاده، وحفظ النتيجة كملف صورة. سواءً كنت تبني نظام تذاكر، أو ملصق لوجستي، أو هوية آمنة، فإن إتقان تنسيق PDF417 يتيح لك ترميز كميات كبيرة من البيانات في شكل بصري مدمج.

في هذا البرنامج التعليمي ستتعلم:

* **إنشاء باركود PDF417** باستخدام مكتبة Aspose.BarCode (أو أي مكتبة متوافقة).  
* **تحديد حجم الباركود** عن طريق ضبط أبعاد X وعدد الأعمدة.  
* توليد **صورة باركود في C#** بصيغ PNG أو JPEG أو BMP.  

المثال يستخدم النسخة المجانية من Aspose.BarCode for .NET، لكن المفاهيم نفسها تنطبق على مكتبات أخرى توفر خصائص مشابهة.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

* .NET 6.0 SDK أو أحدث مثبتًا.  
* بيئة تطوير C# (Visual Studio، Visual Studio Code، Rider، إلخ).  
* حزمة NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

لا تحتاج إلى أي إعدادات إضافية؛ المكتبة تعمل على Windows وLinux وmacOS.

## الخطوة 1: إنشاء باركود PDF417 أساسي وتحديد حجمه

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` باستخدام تعداد `EncodeTypes.Pdf417` وتزويده بالنص الذي تريد ترميزه. ثم اضبط **أبعاد X** (عرض الوحدة) وعدد **الأعمدة** للتحكم في الحجم الكلي.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**لماذا هذه الإعدادات مهمة**

* `XDimension.Pixels` يحدد أصغر عرض للخط. القيم الأصغر تنتج باركودًا أكثر تكتلاً، بينما القيم الأكبر تزيد من قابلية القراءة على الماسحات ذات الدقة المنخفضة.  
* `Pdf417.Columns` يؤثر على نسبة أبعاد الباركود. عدد أقل من الأعمدة يجعل الباركود أطول؛ عدد أكبر يجعل الشكل أوسع. تعديل عدد الأعمدة هو الطريقة الأساسية **لتحديد حجم الباركود** دون تغيير البيانات المشفرة.

بعد تشغيل الكود، ستجد ملف `Pdf417Basic.png` في المجلد المحدد. الصورة تشبه لقطة الشاشة أدناه:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## الخطوة 2: إنشاء باركود PDF417 مضغوط (وضع القطع) بنفس الحجم

أحيانًا تحتاج إلى باركود أقصر بسبب مساحة محدودة. يوفر PDF417 وضع *truncate* (مضغوط) يزيل نمط الإيقاف ويقلل الارتفاع الكلي. الخاصية `Truncate` تتحكم في هذا السلوك.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**ما الذي يتغير عند `Truncate = true`؟**

* يصبح الباركود أقصر تقريبًا بنسبة 15‑20 % عموديًا، وهو مفيد للملصقات الصغيرة أو شاشات الهواتف.  
* تظل البيانات قابلة للاسترداد بالكامل؛ معظم الماسحات الحديثة تتعرف على وضع القطع تلقائيًا.

الملف الناتج `CompactPdf417.png` يظهر كنسخة أنحف من الباركود الأساسي.

## الخطوة 3: إنشاء باركود Micro PDF417، ضبط الأعمدة، وحفظه

Micro PDF417 هو نسخة عالية الكثافة صُممت للمساحات الصغيرة جدًا (مثل بطاقات الهوية). يدعم 1‑4 أعمدة فقط، وتوفر المكتبة الخاصية نفسها `XDimension` للتحكم في الحجم.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**نقاط رئيسية حول Micro PDF417**

* تعداد `EncodeTypes.MicroPdf417` يختار النسخة المصغرة تلقائيًا.  
* نظرًا لكثافة الرمز، قد تحتاج إلى طابعة DPI أعلى (300 dpi أو أكثر) للحفاظ على قابلية القراءة.  
* ضبط عدد الأعمدة هو المقبض الوحيد المتاح لتغيير الحجم؛ المكتبة لا تزال تحترم `XDimension`.

## كيفية تحديد حجم الباركود لمختلف صيغ الإخراج

الأمثلة أعلاه تستخدم PNG، لكن طريقة `Save` نفسها تعمل مع JPEG أو BMP أو TIFF. إذا كنت تحتاج إلى أبعاد صورة محددة (مثلاً 300 × 150 px)، اجمع بين `XDimension` و`ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

زيادة `ImageResolution` مع تعديل `XDimension` يحافظ على جودة الصورة عند الطباعة عالية الدقة.

## الأخطاء الشائعة ونصائح الخبراء

| المشكلة | السبب | الحل |
|---------|-------|------|
| الباركود يظهر ضبابيًا على الشاشة | DPI منخفض مع `XDimension` صغير | زيادة `ImageResolution` و/أو `XDimension.Pixels` |
| الماسح لا يقرأ وضع القطع | برنامج الماسح القديم لا يدعم الخاصية | استخدم الوضع الكامل (غير مقطوع) للأجهزة القديمة |
| Micro PDF417 غير قابل للقراءة | طباعة بأقل من 300 dpi أو تباين غير كاف | اطبع على ورق غير لامع بدقة 300 dpi أو أعلى، وتأكد من لون خلفية داكن |
| ملف الإخراج تالف | عدم وجود صلاحية كتابة للمجلد المستهدف | تحقق من أن `YOUR_DIRECTORY` موجود وقابل للكتابة |

**نصيحة الخبراء:** دائمًا احفظ الباركود بصيغة PNG عندما تحتاج إلى جودة غير مضغوطة للمعالجة اللاحقة (مثل دمجه في ملفات PDF). PNG يحافظ على قيم البكسل بدقة، بينما JPEG يضيف ضوضاء ضغط قد تؤثر على قراءة الباركود.

## مثال كامل قابل للتنفيذ

فيما يلي تطبيق كونسول كامل يوضح الأنواع الثلاثة للباركود في تشغيل واحد. انسخ الكود إلى مشروع .NET كونسول جديد وشغّله.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**الناتج المتوقع**

تشغيل البرنامج ينشئ ثلاثة ملفات PNG داخل مجلد `Barcodes`:

* `Pdf417Basic.png` – باركود PDF417 قياسي بثلاثة أعمدة.  
* `CompactPdf417.png` – نفس البيانات في وضع القطع (مضغوط)، أقصر قليلًا.  
* `MicroPdf417.png` – نسخة Micro PDF417 عالية الكثافة بأربعة أعمدة.

افتح أي صورة بعارض صور؛ يجب أن ترى البنية المتراصة المميزة.

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود – PDF417 مضغوط باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [كيفية ضبط مستوى الخطأ في باركود PDF417 – دليل كامل](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [إنشاء بيانات تعريفية لباركود PDF417 في C# – دليل خطوة بخطوة كامل](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}