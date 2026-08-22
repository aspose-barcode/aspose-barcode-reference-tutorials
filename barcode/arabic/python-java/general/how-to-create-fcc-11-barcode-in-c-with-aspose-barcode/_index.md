---
category: general
date: 2026-08-22
description: إنشاء رمز شريطي FCC 11 بلغة C# باستخدام Aspose.BarCode. تعلم الكود خطوة
  بخطوة، ضبط الأبعاد، وإنشاء صور PNG لبريد أستراليا.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: ar
lastmod: 2026-08-22
og_description: إنشاء رمز شريطي FCC 11 بلغة C# باستخدام Aspose.BarCode. اتبع هذا الدليل
  المختصر لإنشاء رموز شريطية بصيغة PNG لبريد أستراليا، بما في ذلك المتغيرات FCC 59
  وFCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: إنشاء رمز شريطي FCC 11 في C# – دليل Aspose.BarCode الكامل
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: كيفية إنشاء باركود FCC 11 في C# باستخدام Aspose.BarCode
url: /ar/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود FCC 11 في C# باستخدام Aspose.BarCode

إذا كنت بحاجة إلى **إنشاء باركود FCC 11** في تطبيق .NET، يوضح لك هذا الدليل الشيفرة الدقيقة المطلوبة. ستتعرف على كيفية ضبط أبعاد الباركود، اختيار جدول الترميز المناسب، وحفظ النتيجة كملف PNG.

إنشاء باركودات Australia Post هو طلب شائع في مجال اللوجستيات، أنظمة البريد، وتتبع المخزون. يغطي هذا البرنامج التعليمي صيغة FCC 11 ويظهر أيضًا كيفية إنتاج باركودات FCC 59 و FCC 62 باستخدام جداول ترميز مختلفة، بحيث يمكنك إعادة استخدام النمط نفسه لخدمات بريدية أخرى.

## ما ستحتاجه

* .NET 6.0 SDK أو أحدث مثبت  
* Visual Studio 2022 (أو أي بيئة تطوير متوافقة مع C#)  
* رخصة صالحة لـ **Aspose.BarCode for .NET** – نسخة المجتمع صالحة للتقييم  
* إذن كتابة لمجلد سيتم حفظ ملفات PNG فيه  

هذه المتطلبات المسبقة تضمن أن الشيفرة تُترجم وتعمل دون الحاجة إلى إعدادات إضافية.

## الخطوة 1: تثبيت حزمة Aspose.BarCode NuGet

افتح طرفية في مجلد المشروع وشغّل:

```bash
dotnet add package Aspose.BarCode
```

الأمر يضيف أحدث نسخة مستقرة من المكتبة إلى ملف المشروع الخاص بك. الحزمة تحتوي على الفئة `BarcodeGenerator` المستخدمة طوال هذا الدرس.

## الخطوة 2: تعريف مجلد الإخراج

أنشئ مجلدًا سيتم تخزين الصور المولدة فيه. يمكن أن يكون المسار مطلقًا أو نسبيًا للملف التنفيذي.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` يضمن وجود المجلد، مما يمنع حدوث أخطاء وقت التشغيل عندما تقوم طريقة `Save` بكتابة الملف.

## الخطوة 3: توليد باركود FCC 11

صيغة FCC 11 هي الترميز الافتراضي لباركودات Australia Post البريدية. الشيفرة التالية تنشئ باركودًا يرمّز السلسلة الرقمية `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**لماذا هذا يعمل:**  
* `EncodeTypes.AustraliaPost` يخبر المكتبة بتطبيق قواعد ترميز Australia Post.  
* سلسلة البيانات `1101234567` تتبع مواصفات FCC 11: الرقمان الأولان (`11`) يحددان الصيغة، يليه مرجع عميل مكوّن من 7 أرقام.  
* `XDimension` و `BarHeight` يتحكمان في حجم الباركود المطبوع، وهو مهم لقراءة الماسح الضوئي.  

بعد تشغيل البرنامج، ستجد الملف `PostalAustraliaPostFCC11.png` في مجلد `Barcodes`. الصورة تبدو هكذا:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## الخطوة 4: إنشاء باركودات Australia Post إضافية (اختياري)

بينما الهدف الأساسي هو **إنشاء باركود FCC 11**، غالبًا ما تحتاج إلى باركودات FCC 59 أو FCC 62 لفئات بريد مختلفة. الشيفرة أدناه تعيد استخدام نفس كائن `BarcodeGenerator`، مع تغيير سلسلة البيانات وجدول الترميز الاختياري فقط.

### 4.1 FCC 59 مع ترميز N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 مع ترميز N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 مع ترميز C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 مع ترميز Other

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

جميع الصور الأربعة تُحفظ جنبًا إلى جنب في نفس المجلد، مما يسهل مقارنة الاختلافات البصرية.

## الخطوة 5: فهم جداول الترميز

Australia Post يحدد ثلاثة جداول ترميز:

* **N‑Table** – يفسّر معلومات العميل الرقمية. استخدمه عندما يحتوي الحمولة على أرقام فقط.  
* **C‑Table** – يدعم الأحرف الأبجدية الرقمية، مفيد لأرقام المرجع التي تشمل حروف.  
* **Other** – بديل للبيانات المخصصة أو الموسعة.  

اختيار الجدول الصحيح يضمن أن الماسح الضوئي يفسّر المعلومات بالضبط كما هو مقصود. إذا تجاهلت خاصية `AustralianPostEncodingTable`، فإن المكتبة تستخدم N‑Table افتراضيًا، مما قد يقتطع الأحرف غير الرقمية.

## نصائح، حالات حافة، ومشكلات شائعة

| الحالة | النهج الموصى به |
|-----------|----------------------|
| طول سلسلة البيانات أقصر من المطلوب | أضف أصفارًا بادئة إلى الجزء الرقمي لتلبية مواصفات FCC. |
| الباركود يظهر ضبابيًا عند الطباعة | زد `XDimension` إلى 5 أو 6 بكسل وتحقق من إعدادات DPI للطابعة. |
| الماسح يُرجع “تنسيق غير صالح” | تأكد من أن جدول الترميز الصحيح (N‑Table, C‑Table, Other) يتطابق مع محتوى البيانات. |
| التشغيل على Linux بدون واجهة رسومية | تأكد من الإشارة إلى حزمة `System.Drawing.Common`، أو استخدم طريقة `Save` مع `BarCodeImageFormat.Png` التي لا تحتاج إلى سياق عرض. |
| الحاجة إلى تنسيق صورة مختلف | استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg` أو `BarCodeImageFormat.Tiff` حسب الحاجة. |

هذه النصائح العملية مستمدة من تطبيقات حقيقية لحلول باركودات البريد.

## مثال كامل قابل للتنفيذ

فيما يلي برنامج مستقل يمكنك نسخه إلى مشروع وحدة تحكم جديد (`dotnet new console`) وتنفيذه دون تعديل.



## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك الخاصة.

- [كيفية إنشاء باركود جافا – باركود أستراليا بوست باستخدام Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [إنشاء ترميز Databar أحادي البعد GS1 باستخدام Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [كيفية إنشاء منطقة هادئة للباركود .NET لتشفير Code 16K باستخدام Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}