---
category: general
date: 2026-09-16
description: تعلم كيفية تعيين أعمدة الباركود في C# باستخدام BarcodeGenerator وكذلك
  تعيين صفوف الباركود لباركود DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: ar
lastmod: 2026-09-16
og_description: قم بتعيين أعمدة الباركود في C# بسرعة. يوضح لك هذا الدليل كيفية تكوين
  الأعمدة والصفوف وتنسيق الصورة باستخدام BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: تعيين أعمدة وصفوف الباركود في C# – دليل كامل لمولد الباركود
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية تعيين أعمدة وصفوف الباركود باستخدام C# BarcodeGenerator
url: /ar/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين أعمدة الصفوف للباركود باستخدام C# BarcodeGenerator

إذا كنت بحاجة إلى تعيين أعمدة الباركود في تطبيق C#، فإن هذا الدرس يوضح الخطوات الدقيقة المطلوبة. سترى كيفية تكوين كل من الأعمدة والصفوف لباركود DataBar Expanded Stacked، ثم حفظ النتيجة كصورة PNG.

إنشاء الباركود برمجياً يوفر عليك العمل اليدوي في التصميم ويضمن التناسق عبر التقارير والفواتير وملصقات المنتجات. يغطي المثال أدناه سير العمل الكامل، من تثبيت المكتبة إلى إنتاج صورتين—واحدة بعدد أعمدة مخصص وأخرى بعدد صفوف مخصص.

## المتطلبات المسبقة

* .NET 6.0 أو أحدث مثبت.
* إشارة إلى حزمة **Aspose.BarCode for .NET** على NuGet. قم بتثبيتها باستخدام:

```bash
dotnet add package Aspose.BarCode
```

* صلاحية كتابة إلى مجلد سيتم حفظ ملفات PNG المولدة فيه.

هذه المتطلبات تضمن أن الكود يُترجم ويعمل دون إعدادات إضافية.

## كيفية تعيين أعمدة الباركود في C#

الخطوة الأساسية الأولى هي إنشاء كائن `BarcodeGenerator` للرمز **DataBar Expanded Stacked** وتعيين عدد الأعمدة المطلوب.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**لماذا يعمل هذا:**  
`EncodeTypes.DatabarExpandedStacked` يخبر المكتبة أي رمز يجب رسمه. ضبط `Parameters.Barcode.DataBar.Columns` يغيّر تخطيط الوحدات الداخلية، مما يؤثر مباشرة على العرض البصري للباركود. طريقة `Save` تكتب الصورة إلى القرص بالتنسيق المطلوب `BarCodeImageFormat`.

### النتيجة المتوقعة
افتح `C:\Barcodes\DatabarCols4.png` في أي عارض صور. يجب أن ترى باركود DataBar Expanded Stacked أوسع من الافتراضي لأنه يستخدم أربعة أعمدة.

## كيفية تعيين صفوف الباركود في C#

بعد حفظ الصورة المعتمدة على الأعمدة، قد ترغب في باركود يختلف في الارتفاع عبر تعديل الصفوف. العملية مشابهة لتكوين الأعمدة لكن باستخدام الخاصية `Rows` بدلاً من ذلك.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**لماذا يعمل هذا:**  
إعادة تهيئة المولد تضمن أن إعداد العمود السابق لا يتداخل مع تكوين الصفوف. تغيير `Parameters.Barcode.DataBar.Rows` يغيّر ارتفاع الباركود، مما ينتج صورة أطول عندما يتجاوز عدد الصفوف الافتراضي.

### النتيجة المتوقعة
افتح `C:\Barcodes\DatabarRows3.png`. سيظهر الباركود أطول، معكساً تكوين الثلاثة صفوف.

## مثال كامل من البداية إلى النهاية

فيما يلي برنامج واحد ينشئ الصورتين في تنفيذ واحد. إبقاء الكود في ملف واحد يوضح كيف يمكنك التبديل بين تكوينات الأعمدة والصفوف دون إعادة تشغيل التطبيق.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

تشغيل البرنامج ينتج ملفين PNG:

* **DatabarCols4.png** – باركود بأربعة أعمدة.  
* **DatabarRows3.png** – باركود بثلاثة صفوف.

كلا الملفين يستخدمان تنسيق صورة **barcode** PNG، الذي يحافظ على الحواف الحادة ويدعم الضغط غير الفاقد—مثالي للطباعة والعرض الرقمي.

## الأسئلة الشائعة والنصائح

| السؤال | الجواب |
|----------|--------|
| *هل يمكنني استخدام JPEG بدلاً من PNG؟* | نعم. استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg`. JPEG أصغر حجماً لكنه يضيف تشويهات ضغط قد تؤثر على موثوقية القارئ. |
| *ما هو الحد الأقصى لعدد الأعمدة أو الصفوف؟* | المكتبة تتحقق من القيم وفقاً لمواصفات DataBar. القيم خارج النطاق المسموح تُسبب استثناء `ArgumentException`. راجع وثائق Aspose.BarCode للحصول على الحدود الدقيقة. |
| *هل يجب تحرير `BarcodeGenerator`؟* | الفئة تنفذ `IDisposable`. ضع المولد داخل كتلة `using` إذا كنت تنشئ العديد من المثيلات داخل حلقة لتحرير الموارد غير المُدارة فوراً. |
| *كيف أغيّر حجم الباركود دون تعديل الأعمدة/الصفوف؟* | استخدم `barcodeGenerator.Parameters.Image.Width` و `Height` لتكبير الصورة الناتجة مع الحفاظ على تخطيط الوحدات دون تغيير. |

**نصيحة احترافية:** عند توليد الباركود للطباعة عالية الدقة، قم بزيادة أبعاد الصورة الناتجة (`Width`/`Height`) بدلاً من عدد الأعمدة أو الصفوف. هذه الطريقة تحافظ على حجم الوحدة القياسي المحدد من قبل الرمز مع حصولك على صورة أكثر وضوحًا.

## الخلاصة

أنت الآن تعرف كيفية تعيين أعمدة الصفوف للباركود في C# باستخدام الفئة **BarcodeGenerator**. غطى الدليل تهيئة المولد، تكوين عدد الأعمدة والصفوف، حفظ الباركود بصيغة PNG، ومعالجة التغييرات الشائعة مثل تغيير تنسيق الصورة وتحرير الموارد.

بعد ذلك، استكشف المواضيع ذات الصلة مثل **تخصيص ألوان الباركود**، **إضافة نص قابل للقراءة البشرية**، و**دمج الباركود في مستندات PDF**. جميع هذه الإضافات تبني على نمط التكوين نفسه الموضح هنا، مما يتيح لك إنشاء حلول باركود متكاملة لأي تطبيق .NET.

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف نهج تنفيذ بديلة في مشاريعك الخاصة.

- [مثال مولد الباركود في C# – تعيين الأعمدة، الصفوف وتصدير الصورة](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [دليل باركود DataBar Expanded Stacked – كيفية الإنشاء وتحديد الحجم في C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [مثال مولد الباركود في C# – تعيين العرض والارتفاع](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}