---
category: general
date: 2026-09-23
description: يُظهر دليل توليد الباركود بلغة C# كيفية إنشاء صور الباركود بنسب أبعاد
  مخصصة باستخدام مكتبة Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: ar
lastmod: 2026-09-23
og_description: دليل مولد الباركود بلغة C# يوضح لك كيفية إنشاء صور الباركود، وضبط
  نسب الأبعاد، وتصدير ملفات PNG باستخدام Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: إنشاء باركود عالي الجودة باستخدام مولد باركود C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: كيفية استخدام مولد الباركود C# لأكواد DataBar
url: /ar/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام مولد الباركود C# لأكواد DataBar

إذا كنت بحاجة إلى **c# barcode generator** يمكنه إنتاج رموز DataBar المكدسة Omni‑Directional، فإن هذا الدليل يقدم لك حلاً كاملاً جاهزًا للتنفيذ. ستتعرف على كيفية إنشاء صور الباركود، التحكم في البُعد X، وتغيير نسبة العرض إلى الارتفاع دون مغادرة بيئة التطوير المتكاملة.

إنشاء الباركود هو طلب شائع لأنظمة المخزون، بطاقات الشحن، وتطبيقات نقاط البيع. بنهاية هذا البرنامج التعليمي يمكنك إنشاء ملفات PNG بأي نسبة عرض إلى ارتفاع تختارها، وستفهم كيف تعدل الكود لأنواع باركود أخرى.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت  
* Visual Studio 2022 (أو أي محرر C# تفضله)  
* إشارة NuGet إلى **Aspose.BarCode** – المكتبة التي تشغل فئة `BarcodeGenerator`  

لا تحتاج إلى مكتبة رسومات منفصلة؛ فـ Aspose.BarCode يتعامل مع ترميز الصورة داخليًا.

## الخطوة 1: تثبيت حزمة NuGet الخاصة بـ Aspose.BarCode

افتح طرفية في مجلد المشروع وشغّل الأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

يضيف هذا الأمر أحدث نسخة مستقرة من المكتبة إلى ملف المشروع، مما يجعل فئة `BarcodeGenerator` متاحة للاستخدام.

## الخطوة 2: تعريف مجلد الإخراج

اختر مجلدًا سيُحفظ فيه ملفات PNG التي سيتم إنشاؤها. يعمل كل من المسار المطلق والمسار النسبي بنفس الطريقة، لكن المسار النسبي يحافظ على قابلية نقل المشروع.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

إنشاء الدليل برمجيًا يمنع حدوث أخطاء وقت التشغيل إذا كان المجلد غير موجود.

## الخطوة 3: إنشاء مولد باركود C# مع بيانات تجريبية

يتطلب مُنشئ `BarcodeGenerator` معاملين: نوع الباركود وسلسلة البيانات. لأحد رموز DataBar المكدسة Omni‑Directional تستخدم `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

سلسلة البيانات تتبع تنسيق معرف التطبيق GS1. يحتوي تعداد `EncodeTypes` على أكثر من 150 معيار باركود؛ يمكنك التبديل إلى نوع آخر بتغيير قيمة التعداد.

## الخطوة 4: ضبط بُعد X (حجم البكسل) للباركود

يتحكم بُعد X في عرض أضيق شريط. قيمة بكسل مقدارها 2 تنتج صورة واضحة وعالية الدقة مناسبة لمعظم الشاشات.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

تعديل بُعد X اختياري، لكنه يمنحك تحكمًا دقيقًا في كثافة الباركود البصرية.

## الخطوة 5: إنشاء باركود بنسبة عرض إلى ارتفاع 15 وحفظه كـ PNG

خاصية `AspectRatio` تنتمي إلى الكائن الفرعي `DataBar`. تغيير هذه القيمة يمد أو يضغط الباركود عموديًا مع الحفاظ على البيانات المشفرة.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

طريقة `Save` تكتب الباركود إلى مسار الملف المحدد. يضمن تعداد `BarCodeImageFormat.Png` ضغطًا بدون فقدان.

![c# barcode generator output example](generated_barcode_example.png)

*الصورة: باركود تم إنشاؤه بنسبة عرض إلى ارتفاع 15.*

## الخطوة 6: تغيير نسبة العرض إلى الارتفاع إلى 30 وإنشاء صورة ثانية

إعادة استخدام نفس مثيل `BarcodeGenerator` يتجنب تخصيص كائن جديد. ما عليك سوى تحديث `AspectRatio` واستدعاء `Save` مرة أخرى.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

الآن لديك ملفا PNG يختلفان فقط في التحجيم العمودي. هذه التقنية مفيدة عندما تحتاج إلى نفس البيانات مع أحجام ملصقات مختلفة.

## التغييرات الشائعة والحالات الحدية

### التبديل إلى نوع باركود آخر

إذا كنت تحتاج إلى QR code أو Code 128 أو PDF417، استبدل قيمة التعداد في المُنشئ:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

جميع خطوات الإعداد الأخرى (بُعد X، الحفظ) تظل كما هي.

### معالجة الأحرف غير المدعومة

يتحقق `BarcodeGenerator` من صحة سلسلة الإدخال مقابل الرموز المختارة. إدخال حرف غير قانوني يثير استثناء `ArgumentException`. احفظ الإنشاء داخل كتلة try‑catch لتقديم رسالة خطأ ودية:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### التصدير إلى صيغ صور أخرى

يدعم Aspose.BarCode صيغ BMP، JPEG، TIFF، و SVG. غيّر المعامل الثاني في `Save` وفقًا لذلك:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### إخراج عالي الدقة للطباعة

عند الطباعة على طابعات DPI عالية، زد بُعد X واختر ضبط خاصية `Resolution` إذا رغبت:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

هذه الإعدادات تنتج ملفات أكبر ولكنها تحافظ على حواف واضحة على الوسائط المادية.

## النتيجة المتوقعة

تشغيل البرنامج الكامل ينشئ الملفات التالية داخل `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – رمز DataBar بارتفاع قياسي  
* `DatabarAspectRatio30.png` – نسخة ممدودة عموديًا  

كلا الصورتين يحتويان على نفس بيانات GS1 المشفرة، ويمكنك التحقق منهما باستخدام أي تطبيق ماسح باركود.

## الكود الكامل

انسخ الكود أدناه إلى مشروع وحدة تحكم جديد (`dotnet new console`) وشغّله. يطبع البرنامج رسائل حالة إلى وحدة التحكم ويكتب ملفات PNG إلى القرص.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

تشغيل البرنامج ينتج مخرجات وحدة التحكم مشابهة لـ:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## الخلاصة

أصبح لديك الآن **c# barcode generator** يمكنه إنشاء رموز DataBar المكدسة Omni‑Directional، ضبط بُعد X، وتصدير ملفات PNG بنسب عرض إلى ارتفاع مخصصة. النمط نفسه يعمل مع أي رموز باركود أخرى يدعمها Aspose.BarCode، مما يجعل من السهل دمج إنشاء الباركود في حلول المخزون، الشحن، أو نقاط البيع.

إذا رغبت في الاستكشاف أكثر، جرّب:

* إنشاء رموز QR أو PDF417 (`how to generate barcode` للتطبيقات المحمولة)  
* التصدير إلى SVG للرسومات القابلة للتوسيع على الويب  
* تضمين الصور المُنشأة مباشرةً في فواتير PDF باستخدام Aspose.PDF  

جرّب قيم `AspectRatio` مختلفة، أحجام بُعد X، وصيغ إخراج لتتناسب تمامًا مع احتياجاتك.

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}