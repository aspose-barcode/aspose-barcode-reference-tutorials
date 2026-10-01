---
category: general
date: 2026-09-07
description: دليل توليد الباركود بلغة C# يوضح لك كيفية إنشاء ملفات PNG للباركود وإنشاء
  باركود DataBar مع صفوف وأعمدة قابلة للتخصيص
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: ar
lastmod: 2026-09-07
og_description: 'دليل مولد الباركود C#: تعلم كيفية إنشاء ملفات PNG للباركود وإنشاء
  باركود DataBar بصفوف وأعمدة مخصصة في دقائق قليلة'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: مولد الباركود C# – إنشاء باركود DataBar وصور PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: كيفية استخدام مولد الباركود C# لإنشاء باركود DataBar
url: /ar/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام مولد الباركود C# لإنشاء باركود DataBar

إذا كنت بحاجة إلى **barcode generator C#** لإنشاء باركود عالي الجودة، يوضح هذا الدليل كيفية **إنشاء ملفات PNG للباركود** و**إنشاء باركود DataBar** مع صفوف وأعمدة مخصصة. سواء كنت تبني نظام جرد تجزئة أو منصة تذاكر، فإن الخطوات أدناه تمكنك من إنتاج باركود DataBar Expanded Stacked في مثال واحد مستقل.

في هذا الدرس ستتعلم:

* كيفية إنشاء كائن `BarcodeGenerator` للرمز DataBar Expanded Stacked.  
* كيفية ضبط إعدادات الأعمدة والصفوف لتلبية مواصفات ISO / GS1.  
* كيفية حفظ النتيجة كصورة PNG يمكن تضمينها في صفحات الويب أو طباعتها على الملصقات.  

لا توجد خدمات خارجية مطلوبة—فقط مكتبة Aspose.BarCode لـ .NET (أو أي مكتبة متوافقة تتبع نفس الـ API). يعمل الكود على .NET 6+ ويعمل في Visual Studio أو Rider أو أي بيئة تطوير تدعم C#.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

* .NET 6 SDK أو أحدث مثبتًا.  
* إشارة إلى حزمة NuGet `Aspose.BarCode` (أو مكتبة مكافئة توفر `BarcodeGenerator` و`EncodeTypes` و`BarCodeImageFormat`).  
* إلمام أساسي بصياغة C# وبنية المشروع.  

يمكنك إضافة الحزمة عبر سطر الأوامر:

```bash
dotnet add package Aspose.BarCode
```

## الخطوة 1: تهيئة مولد الباركود C# لـ DataBar Expanded Stacked

الخطوة الأولى هي إنشاء مثيل `BarcodeGenerator` يستهدف رموز **DataBar Expanded Stacked**. هذا الكائن يحتوي على جميع معلمات العرض، بما في ذلك النص المراد ترميزه.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**لماذا هذا مهم:** قيمة التعداد `EncodeTypes.DatabarExpandedStacked` تخبر المكتبة أي معيار باركود يجب تطبيقه. استخدام التعداد الصحيح يضمن أن الصورة المولدة تتوافق مع مواصفات GS1 DataBar.

## الخطوة 2: ضبط عدد الأعمدة (يتم استخدام الصفوف الافتراضية)

يمكن تقسيم DataBar Expanded Stacked إلى عدة أعمدة. تعديل عدد الأعمدة يغيّر الكثافة البصرية ويمكن أن يساعد في ملاءمة سلاسل البيانات الطويلة في مساحة محدودة.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**نصيحة احترافية:** عدد الأعمدة الافتراضي هو 1. ضبطه على 4 يخلق أربعة أعمدة مكدسة، وهو مثالي للسلاسل الرقمية الطويلة مع الحفاظ على ارتفاع الباركود قابلًا للإدارة.

## الخطوة 3: إنشاء صورة PNG للباركود مع تطبيق إعداد العمود

الآن احفظ الباركود كصورة PNG. يحافظ PNG على الحواف الحادة المطلوبة للماسحات الضوئية ويعمل جيدًا على الويب والطباعة.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

الملف `DatabarCols4.png` يحتوي على **barcode PNG** يمكنك تضمينه مباشرة في HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## الخطوة 4: إنشاء مثيل مولد منفصل لتكوين الصفوف

إذا كنت بحاجة إلى التحكم في عدد الصفوف بدلاً من الأعمدة، أنشئ مثيلًا جديدًا من `BarcodeGenerator`. إعادة استخدام نفس المثيل بعد تغيير أحد الأبعاد قد يؤدي إلى ظهور تشوهات غير متوقعة في التخطيط، لذا فإن إنشاء كائن جديد هو الخيار الأكثر أمانًا.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## الخطوة 5: ضبط عدد الصفوف (يتم استخدام الأعمدة الافتراضية)

تؤثر الصفوف على التكدس العمودي لوحدات الباركود. زيادة عدد الصفوف قد تجعل الباركود أطول، وهو ما قد يكون مطلوبًا لبعض أحجام الملصقات.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**لماذا الصفوف مقابل الأعمدة:** الأعمدة تقسم الباركود أفقياً، بينما الصفوف تمده عموديًا. اختر الاتجاه الذي يتناسب مع تخطيط ملصقك.

## الخطوة 6: إنشاء صورة PNG للباركود مع تطبيق إعداد الصفوف

أخيرًا، احفظ الباركود المعدل بالصفوف كملف PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

الآن لديك ملفا PNG مميزان:

* `DatabarCols4.png` – 4 أعمدة، صف واحد.  
* `DatabarRows3.png` – عمود واحد، 3 صفوف.

كلا الصورتين جاهزتين للاستخدام الفوري في التطبيقات أو التقارير أو الملصقات المطبوعة.

## كيفية إنشاء ملفات PNG للباركود في C# بأبعاد مخصصة

النمط المعروض أعلاه يمكن إعادة استخدامه لأي نوع من DataBar أو لأي رموز أخرى تدعمها المكتبة. إليك قالبًا مختصرًا يمكنك نسخه ولصقه في فئة مساعدة:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

استدعِ الطريقة هكذا:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**حالات الحافة التي يجب مراعاتها**

* **طول البيانات** – يمكن لـ DataBar Expanded Stacked ترميز ما يصل إلى 74 حرفًا رقميًا. تجاوز هذا الحد يسبب استثناء. تحقق من طول الإدخال قبل استدعاء المولد.  
* **الأبعاد غير الصالحة** – المكتبة تقيد الأعمدة بين 1‑4 والصفوف بين 1‑3 لهذا الرمز. القيم خارج هذه النطاقات سيتجاهلها النظام أو تتسبب في خطأ.  
* **دقة الصورة (DPI)** – إذا كنت تحتاج إلى دقة أعلى للطباعة، اضبط `generator.Parameters.ImageResolution` قبل الحفظ.

## النتيجة المتوقعة

عند فتح `DatabarCols4.png` أو `DatabarRows3.png` يجب أن ترى باركود DataBar واضحًا وعالي التباين. مسح الصورة باستخدام ماسح متوافق مع GS1 سيعيد النص الأصلي `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*نص بديل: مثال على باركود DataBar Expanded Stacked محفوظ كملف PNG باستخدام مولد الباركود C#*

## الخلاصة

يظهر هذا الدرس كيف يمكن استخدام **barcode generator C#** لإنشاء **باركود DataBar** و**إنشاء ملفات PNG للباركود** بأبعاد صفوف وأعمدة مخصصة. باتباع الخطوات الست—تهيئة المولد، ضبط الأعمدة أو الصفوف، وحفظ الصورة كـ PNG—تحصل على صور جاهزة للإنتاج مناسبة لأنظمة الجرد، التذاكر، أو أي سيناريو يتطلب عرض باركود موثوق.

بعد ذلك، يمكنك استكشاف:

* إضافة ألوان أو صور خلفية إلى PNG (ما زال متوافقًا مع معظم الماسحات).  
* استخدام رموز أخرى مثل QR أو Code 128 أو PDF417 عبر نفس واجهة `BarcodeGenerator` API.  
* تضمين PNG المولدة مباشرة في عروض ASP.NET Core MVC أو مكونات Blazor.

لا تتردد في تجربة سلاسل بيانات مختلفة، أبعاد مختلفة، وصيغ صور مختلفة (مثل JPEG أو BMP). النمط نفسه ينطبق، مما يجعل **barcode generator C#** أداة متعددة الاستخدامات في صندوق أدوات أي مطور .NET. برمجة سعيدة!

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}