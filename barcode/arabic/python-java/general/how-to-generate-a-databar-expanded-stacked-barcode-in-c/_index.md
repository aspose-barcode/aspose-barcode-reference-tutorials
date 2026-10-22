---
category: general
date: 2026-10-21
description: إنشاء صورة باركود Databar Expanded Stacked باستخدام C# وBarcodeGenerator.
  اتبع هذا الدليل خطوة بخطوة لإنشاء صور الباركود، وتخصيص الصفوف والأعمدة، وتصدير ملفات
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: ar
lastmod: 2026-10-21
og_description: أنشئ شيفرة باركود Databar موسعة مكدسة في C# باستخدام هذا الدرس. تعلم
  كيفية استخدام BarcodeGenerator، وتحديد الصفوف والأعمدة، وحفظ صور PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: إنشاء شيفرة باركود Databar Expanded Stacked في C# – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية إنشاء باركود Databar موسع مكدس في C#
url: /ar/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيف تولد شيفرة شريطية (باركود) Databar Expanded Stacked باستخدام C#

إذا كنت بحاجة إلى توليد شيفرة شريطية **databar expanded stacked** باستخدام C#، فإن هذا الدليل يوضح لك كيفية ذلك. رموز databar expanded stacked مثالية لتشفير كميات كبيرة من البيانات بشكل مضغوط، ويمكنك إنشاء الصورة ببضع أسطر من الشيفرة فقط. ستتعلم أيضًا كيفية **إنشاء ملفات صورة شيفرة شريطية** بصيغ مختلفة وتخصيص الصفوف أو الأعمدة لتتناسب مع بيئة المسح الخاصة بك.

يغطي هذا البرنامج التعليمي كل ما تحتاجه لبدء إنتاج باركودات databar: تثبيت المكتبة المطلوبة، إعداد مجلد الإخراج، إنشاء الباركود بأعمدة أو صفوف مخصصة، وحفظ النتيجة كملف PNG. في النهاية، ستكون قادرًا على **إنشاء صور باركود databar** برمجيًا وتكييف الشيفرة لتعمل مع صيغ صور أخرى أو سيناريوهات تشغيل مختلفة.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث (الشيفرة تعمل أيضًا مع .NET Core 3.1 و .NET Framework 4.7+)
* بيئة تطوير مثل Visual Studio 2022 أو Visual Studio Code أو Rider
* اتصال بالإنترنت لتثبيت حزمة **Barcode Generator C#** من NuGet (Aspose.BarCode for .NET)

> **نصيحة احترافية:** إذا كنت تستخدم خط أنابيب CI/CD، أضف إشارة حزمة NuGet إلى ملف المشروع لضمان إمكانية إعادة بناء المشروع بنفس النتائج.

## تثبيت مكتبة Barcode Generator C#

يستخدم المثال مكتبة Aspose.BarCode، التي توفر الفئة `BarcodeGenerator` وتعداد `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

الأمر يضيف أحدث نسخة مستقرة إلى مشروعك. بعد التثبيت، يمكنك استيراد مساحة الأسماء في ملفات C# الخاصة بك:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## إعداد مجلد الإخراج

مسار ملف موثوق يمنع حدوث أخطاء وقت التشغيل عندما تحاول المكتبة كتابة الصورة. الشيفرة التالية تنشئ الدليل إذا لم يكن موجودًا:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **لماذا هذا مهم:** محاولة الحفظ إلى دليل غير موجود تُسبب استثناء `IOException`. إنشاء المجلد مسبقًا يجعل الشيفرة قوية لكل من بيئات التطوير المحلية والإنتاج.

## توليد صورة باركود databar expanded stacked

### توليد باركود أساسي

أسهل طريقة لتوليد صورة **databar expanded stacked** هي إنشاء كائن `BarcodeGenerator` مع قيمة `EncodeTypes` المطلوبة وحمل نص عادي.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

تشغيل المقتطف ينتج ملف `DatabarBasic.png` في مجلد *Barcodes*. تحتوي الصورة على رمز databar expanded stacked قياسي بتخطيط افتراضي (4 أعمدة × 4 صفوف).

### تخصيص الأعمدة – إنشاء باركود databar بـ 4 أعمدة

يمكنك التحكم في عدد الأعمدة باستخدام الخاصية `Parameters.Barcode.DataBar.Columns`. المثال التالي ينشئ باركودًا بـ **4 أعمدة** مع الحفاظ على عدد الصفوف الافتراضي.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

الملف الناتج، **DatabarCols4.png**، يبدو هكذا:

![باركود Databar expanded stacked مع 4 أعمدة](databar_cols4.png "باركود Databar expanded stacked مع 4 أعمدة – تم إنشاؤه باستخدام C#")

*نص بديل للصورة (og_image_alt):* **عينة صورة باركود Databar expanded stacked تم إنشاؤها باستخدام C#** – هذا يفي بمتطلبات تحسين محركات البحث لنص بديل الصورة.

### تخصيص الصفوف – إنشاء باركود databar بـ 3 صفوف

وبالمثل، يمكنك تعديل عدد الصفوف عبر `Parameters.Barcode.DataBar.Rows`. الشيفرة أدناه تولد باركودًا بـ **3 صفوف** مع عدد الأعمدة الافتراضي (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

الملف **DatabarRows3.png** يحتوي على رمز databar expanded stacked أقصر قليلًا عموديًا، وهو مفيد للملصقات ذات المساحة المحدودة.

### تصدير إلى صيغ أخرى

إذا كنت تحتاج إلى نوع صورة مختلف (مثل JPEG أو BMP أو SVG)، استبدل `BarCodeImageFormat.Png` بالقيمة المناسبة من التعداد:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

المكتبة تدعم أيضًا صيغ المتجهات مثل SVG، وهي مثالية للطباعة عالية الدقة.

## سيناريوهات متقدمة

### الحفظ إلى تدفق ذاكرة (MemoryStream)

أحيانًا تريد تضمين الباركود مباشرةً في استجابة ويب أو ملف PDF دون التعامل مع نظام الملفات. استخدم `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### معالجة الإدخال غير الصالح

تتحقق `BarcodeGenerator` من صحة الحمولة وفقًا للرمز المختار. إذا احتوت البيانات على أحرف غير مسموح بها، يتم إلقاء استثناء `ArgumentException`. احطّ الشيفرة بكتلة try‑catch لتوفير رسالة خطأ ودية:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### تغيير حجم صورة الباركود

يمكنك تغيير حجم الصورة دون تعديل البيانات المشفرة عن طريق ضبط `Parameters.Image.Width` و `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

تغيير الحجم مفيد عندما يجب أن يفي الباركود بمتطلبات DPI محددة للمسّاحات الضوئية.

## مثال كامل يعمل

فيما يلي تطبيق كونسول كامل جاهز للتنفيذ يوضح جميع الخطوات التي تم مناقشتها:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**الناتج المتوقع**


## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك الخاصة.

- [كيفية ضبط الأعمدة لباركود Databar Expanded Stacked – دليل كامل C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [كيفية بناء مثال مولد باركود في C# باستخدام DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [دليل باركود databar expanded stacked – كيفية الإنشاء وتحديد الحجم في C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}