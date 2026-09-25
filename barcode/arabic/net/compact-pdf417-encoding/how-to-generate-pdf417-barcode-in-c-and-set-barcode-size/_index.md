---
category: general
date: 2026-08-22
description: تعلم كيفية إنشاء باركود PDF417 في C# باستخدام Aspose.BarCode، وضبط حجم
  الباركود، وتعديل الأعمدة، وتفعيل وضع الضغط.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: ar
lastmod: 2026-08-22
og_description: إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode. يوضح هذا الدليل
  كيفية ضبط حجم الرمز الشريطي، التحكم في الأعمدة، وتفعيل وضع الضغط للحصول على صورة
  أصغر.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: إنشاء باركود PDF417 في C# – ضبط الحجم، الأعمدة، ووضع الضغط
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: كيفية إنشاء باركود PDF417 في C# وتحديد حجم الباركود
url: /ar/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء رمز شريطي PDF417 في C# وتحديد حجم الرمز الشريطي

إذا كنت بحاجة إلى **إنشاء رمز شريطي PDF417** في تطبيق .NET، فإن هذا الدليل يشرح لك العملية بالكامل. سترى بالضبط **كيفية إنشاء PDF417** باستخدام Aspose.BarCode، وضبط **حجم الرمز الشريطي**، وإنتاج صورة PNG مضغوطة يمكن تضمينها في التقارير أو التطبيقات المحمولة.

إنشاء رمز شريطي لا يتطلب محرر رسومات منفصل. بنهاية هذا الدرس ستحصل على طريقة C# كاملة الوظيفة تنتج صورة PDF417 بالأبعاد الدقيقة التي تحتاجها، جاهزة للمعالجة اللاحقة.

## ما ستتعلمه

* تثبيت وإضافة مرجع لمكتبة Aspose.BarCode.
* إنشاء مولد رمز شريطي PDF417 وتحديد النص المشفر.
* **تحديد حجم الرمز الشريطي** عن طريق ضبط X‑dimension وعدد الأعمدة.
* تمكين الوضع المضغوط (المختصر) لتقليل حجم الرمز.
* حفظ النتيجة كملف PNG.
* استكشاف الأخطاء الشائعة مثل الرموز غير القابلة للقراءة والصور ذات الحجم الكبير.

### المتطلبات المسبقة

* .NET 6.0 أو أحدث (تعمل الواجهة البرمجية مع .NET Framework 4.6+ أيضًا).
* إلمام أساسي بـ C# و Visual Studio (أو أي بيئة تطوير C#).
* ترخيص Aspose.BarCode صالح (التقييم المجاني يعمل للاختبار).

> **نصيحة احترافية:** إذا كنت تخطط لإنشاء العديد من الرموز الشريطية داخل حلقة، أعد استخدام كائن `BarcodeGenerator` واحد فقط وقم بتغيير خاصية `CodeText` فقط. هذا يقلل من تخصيص الذاكرة.

## إنشاء رمز شريطي PDF417 باستخدام Aspose.BarCode

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` للرمز الشريطي PDF417. هذا الكائن هو نقطة الدخول لجميع عمليات الرموز الشريطية.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*لماذا هذا مهم*: `EncodeTypes.Pdf417` يخبر المكتبة باستخدام معيار PDF417، الذي يدعم كميات كبيرة من البيانات وتصحيح الأخطاء. كما أن المُنشئ يقبل البيانات التي تريد ترميزها، مما يلغي الحاجة لتعيين `CodeText` منفصل لاحقًا.

## ضبط حجم الرمز الشريطي وعدد الأعمدة

رموز PDF417 تتكون من صفوف وأعمدة من وحدات مستطيلة صغيرة. التحكم في عرض الوحدة (X‑dimension) وعدد الأعمدة يتيح لك ضبط الأبعاد الكلية بدقة.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*شرح*:  
* **X‑dimension** (`Pixels`) يحدد عرض كل وحدة. القيم الأصغر تنتج رمزًا شريطيًا أكثر تماسكًا، بينما القيم الأكبر تزيد من قابلية القراءة على الماسحات ذات الدقة المنخفضة.  
* **Columns** تتحكم في التخطيط الأفقي. عدد أقل من الأعمدة يجعل الرمز الشريطي أطول؛ وعدد أكبر يجعل الرمز أوسع. اضبط هذين الإعدادين معًا لتحقيق **حجم الرمز الشريطي** الدقيق الذي تحتاجه.

## تمكين الوضع المضغوط للحصول على رمز شريطي أصغر

PDF417 يتضمن وضعًا “مضغوطًا” (أو مختصرًا) يزيل الحشو غير الضروري ويقلل من البصمة الكلية. هذا مفيد بشكل خاص عندما تكون مساحة الشاشة محدودة.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*لماذا تمكين الاختصار؟*  
عندما تكون `Truncate` مساوية لـ `true`، يتجاهل المولد نمط الإيقاف وبعض كلمات تصحيح الأخطاء التي لا تحتاجها معظم سيناريوهات المسح. الصورة الناتجة أصغر بنحو 15‑20 % دون التضحية بسلامة البيانات في الاستخدامات العادية.

## حفظ الرمز الشريطي كصورة PNG

بعد ضبط الحجم والوضع، احفظ الرمز الشريطي على القرص. PNG هو تنسيق غير فقدان، مما يضمن بقاء حواف الوحدات حادة.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

الملف `CompactPdf417.png` سيحتوي على رمز PDF417 واضح يطابق الأبعاد التي ضبطتها في الخطوات السابقة.

### النتيجة المتوقعة

فتح ملف PNG المحفوظ يجب أن يعرض رمز PDF417 موجهًا عموديًا يتكون من ثلاثة أعمدة، كل وحدة بعرض 2 بكسل، وبحجم إجمالي تقريبًا **120 × 240 بكسل** (العرض × الارتفاع). مسح الصورة بأي قارئ PDF417 قياسي يعيد النص الأصلي “Sample text for PDF417”.

## المشكلات الشائعة وكيفية تجنبها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| الرمز غير قابل للقراءة | X‑dimension صغير جدًا بالنسبة للماسح | زيادة `XDimension.Pixels` إلى 3 أو 4 |
| الصورة عريضة جدًا بالنسبة للواجهة | تم ضبط عدد أعمدة كبير جدًا | تقليل `Pdf417.Columns` أو تمكين `Truncate` |
| استثناء `ArgumentOutOfRangeException` | عدد الأعمدة سالب أو صفر | تأكد من أن `Columns` عدد صحيح موجب (الحد الأدنى 1) |
| ملف PNG فارغ | مسار الإخراج غير موجود أو لا يملك صلاحية كتابة | تحقق من وجود الدليل وأن التطبيق لديه صلاحيات كتابة |

> **نصيحة احترافية:** استخدم `barcodeGenerator.ValidateParameters()` قبل استدعاء `Save()` لاكتشاف أخطاء التكوين مبكرًا.

## مثال كامل قابل للتنفيذ

فيما يلي برنامج وحدة تحكم مستقل يدمج جميع الخطوات السابقة. انسخه في مشروع C# جديد، استعد حزمة Aspose.BarCode عبر NuGet، وشغله لرؤية النتيجة.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**تشغيل البرنامج** ينتج `CompactPdf417.png` في دليل العمل للتنفيذ. امسح الصورة باستخدام تطبيق هاتف محمول (مثل “Barcode Scanner”) للتحقق من أن النص المشفر يطابق السلسلة الأصلية.

## الخطوات التالية والمواضيع ذات الصلة

* **زيادة مستوى تصحيح الأخطاء** – اضبط `Pdf417.ErrorLevel` للبيئات التي تحتوي على مسحات ضوضائية.  
* **تغيير الاتجاه** – اضبط `Pdf417.Rotate` إلى `RotationAngle.Rotate90` إذا كنت تحتاج إلى تخطيط أفقي.  
* **إدراج الرمز الشريطي في ملف PDF** – اجمع بين Aspose.PDF و Aspose.BarCode لوضع الصورة مباشرةً في المستند.  
* **إنشاء رموز شريطية ثنائية الأبعاد أخرى** – فئة `BarcodeGenerator` نفسها تدعم DataMatrix و QR و Aztec؛ فقط استبدل `EncodeTypes.Pdf417` بالرمز الشريطي المطلوب.

من خلال إتقان تقنيات **إنشاء رمز شريطي PDF417**، يمكنك أتمتة إصدار التذاكر، وضع علامات المخزون، ونقل البيانات بأمان عبر مجموعة واسعة من تطبيقات .NET.

## الخلاصة

أنت الآن تعرف كيفية **إنشاء رمز شريطي PDF417** في C#، وتحديد **حجم الرمز الشريطي** بدقة، وضبط الأعمدة، وتمكين الوضع المضغوط، وحفظ النتيجة كملف PNG. استخدم هذه الإعدادات لتناسب أي قيود واجهة مستخدم أو متطلبات مسح، ووسع النهج لتطبيقات رموز شريطية أخرى حسب الحاجة. برمجة سعيدة!

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء رمز شريطي PDF417 – ترميز PDF417 مضغوط](/barcode/english/net/compact-pdf417-encoding/)
- [كيفية إنشاء رمز شريطي – PDF417 مضغوط باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [كيفية إنشاء رموز DataMatrix باستخدام Aspose.BarCode لـ .NET – دليل خطوة بخطوة](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}