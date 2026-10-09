---
category: general
date: 2026-10-09
description: تعلم كيفية إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode – إنشاء
  Macro PDF417 مع دعم كامل للmetadata
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: تعلم كيفية إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode –
  إنشاء Macro PDF417 مع دعم كامل للmetadata، بما في ذلك file ID، segment data، timestamp
  والمزيد.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: كيفية إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: كيفية إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode
url: /ar/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode

إذا كنت بحاجة إلى **create PDF417 barcode C#** بسرعة وموثوقية، فإن هذا الدليل يشرح لك العملية بالكامل باستخدام Aspose.BarCode. سترى كل الإعدادات المطلوبة، من الأبعاد الأساسية إلى مجموعة الحقول الوصفية Macro PDF417 الكاملة، وستنتهي بصورة PNG جاهزة للمعالجة اللاحقة.

## إجابات سريعة
- **أي مكتبة تُنشئ رموز PDF417 الشريطية؟** Aspose.BarCode for .NET.
- **ما هو التنسيق الذي ينتجه المثال؟** صورة PNG غير مضغوطة.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل مع العينة؛ يلزم ترخيص تجاري للإنتاج.
- **أي إصدار من .NET مدعوم؟** .NET 6.0 أو أحدث.
- **هل يمكنني إضافة بيانات وصفية إلى الرمز الشريطي؟** نعم – يدعم Macro PDF417 معرف الملف، عدد القطاعات، الطوابع الزمنية، وأكثر.

## ما هو رمز PDF417 الشريطي؟
رمز PDF417 الشريطي هو تمثيل خطي مكدس يمكنه ترميز ما يصل إلى حوالي 1 KB من البيانات لكل رمز ويدعم بيانات وصفية اختيارية للملفات متعددة القطاعات. يتكون من عدة صفوف من الأنماط الخطية المكدسة، مما يسمح بسعة بيانات عالية مع الحفاظ على قابلية القراءة بواسطة الماسحات الضوئية الثنائية الأبعاد القياسية. يتضمن التنسيق أيضًا مستويات تصحيح الأخطاء لتحسين الموثوقية، وتتيح ميزة الماكرو الاختيارية تقسيم ملفات كبيرة عبر عدة رموز شريطية مع بيانات وصفية تساعد في إعادة تجميعها.

## لماذا تستخدم Aspose.BarCode لـ PDF417؟
يدعم Aspose.BarCode **أكثر من 50 تمثيلًا شريطيًا** ويمكنه توليد رموز Macro PDF417 بحد أقصى **2 000 عمود**، مما يتيح معالجة ملفات أكبر من **10 MB** دون تحميل الحمولة بالكامل في الذاكرة. تضمن هذه القدرة الكمية تشغيل سيناريوهات المؤسسات ذات الإنتاجية العالية بسلاسة، وتوفر خيارات تخصيص واسعة.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود:

- .NET 6.0 (أو أحدث) مثبت  
- Visual Studio 2022 أو أي بيئة تطوير متوافقة مع C#  
- ترخيص صالح لـ **Aspose.BarCode for .NET** (النسخة التجريبية المجانية تعمل مع هذا المثال)  

أضف حزمة Aspose.BarCode NuGet إلى مشروعك:

```bash
dotnet add package Aspose.BarCode
```

## كيفية إنشاء رمز PDF417 الشريطي في C#؟

`BarcodeGenerator` هو الصنف الرئيسي لإنشاء صور الرموز الشريطية.  
`EncodeTypes.MacroPdf417` يحدد تمثيل Macro PDF417 لتوليد الرمز.  
`Save` يكتب الرمز المولّد إلى ملف صورة.

حمّل `BarcodeGenerator` باستخدام تعداد `EncodeTypes.MacroPdf417` والنص المستهدف، ثم استدعِ `Save` – هذا هو تدفق الإنشاء الكامل في ثلاث أسطر. يتعامل المولد مع Unicode تلقائيًا، وتضمن عبارة `using` تحرير الموارد غير المُدارة بعد حفظ الصورة.

### الخطوة 1: إنشاء مولد الرمز الشريطي C# 

صنف `BarcodeGenerator` ينشئ ويُكوّن صور الرموز الشريطية.  

أنشئ كائن `BarcodeGenerator` باستخدام قيمة التعداد `EncodeTypes.MacroPdf417` والنص الذي تريد ترميزه. يمكن للنص أن يحتوي على أحرف Unicode، والتي يتعامل معها المكتبة تلقائيًا.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*لماذا هذا مهم*: `EncodeTypes.MacroPdf417` يخبر المحرك بإنتاج رمز Macro PDF417، الذي يدعم البيانات المقسمة وبيانات وصفية على مستوى الملف. تضمن عبارة `using` تحرير الموارد غير المُدارة بعد حفظ الصورة.

### الخطوة 2: تعريف مظهر الرمز الشريطي الأساسي

`XDimension.Pixels` يحدد حجم كل وحدة من وحدات الرمز الشريطي بالبكسل.

يتكون رمز Macro PDF417 من وحدات مربعة. التحكم في حجم الوحدة وعدد الأعمدة يؤثر على كل من قابلية القراءة وحجم الملف.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*لماذا هذا مهم*: `XDimension.Pixels` يحدد الكثافة البصرية؛ قيمة 2 بكسل تعمل جيدًا للعرض على الشاشة مع الحفاظ على حجم الصورة صغيرًا. عدّل عدد الأعمدة ليتناسب مع قيود التخطيط لديك—المزيد من الأعمدة ينتج رمزًا أوسع وأقصر.

### الخطوة 3: تعيين البيانات الوصفية الخاصة بـ Macro PDF417

`MacroPdf417FileID` يحدد الملف الذي تنتمي إليه جميع قطاعات الرمز.

يمتد Macro PDF417 تنسيق PDF417 القياسي بإضافة حقول تمكّن من إعادة بناء ملفات كبيرة من عدة قطاعات رمزية. كل حقل اختياري، لكن ضبطها يُظهر كامل إمكانيات الـ API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*لماذا هذا مهم*:  
- `MacroPdf417FileID` يربط جميع القطاعات التي تنتمي إلى نفس الملف المنطقي.  
- `MacroPdf417SegmentID` و `MacroPdf417SegmentsCount` تمكّن القارئ من إعادة ترتيب القطع بشكل صحيح.  
- `MacroPdf417Checksum` يوفر فحصًا سريعًا للسلامة دون فك تشفير كامل الحمولة.  
- `MacroPdf417FileSize` و `MacroPdf417TimeStamp` يسمحان للأنظمة اللاحقة بالتحقق من أن الملف المعاد تجميعه يطابق الأصلي.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` مفيدان في سيناريوهات اللوجستيات أو تبادل المستندات.  
- ضبط `MacroPdf417Terminator` على `Set` يحدد هذا الرمز الشريطي كقطعة نهائية، مما يبسط خوارزمية التجميع.

### الخطوة 4: حفظ صورة الرمز الشريطي المُولدة

`Save` يكتب صورة الرمز الشريطي إلى مسار الملف المحدد.

أخيرًا، احفظ الرمز الشريطي كملف PNG. يمكنك اختيار أي تنسيق مدعوم (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*لماذا هذا مهم*: PNG يحافظ على بيانات البكسل بدون فقدان، مما يضمن أن الماسحات الضوئية تقرأ النمط الدقيق للوحدات التي قمت بتكوينها. قد يؤثر تغيير التنسيق على الجودة البصرية وحجم الملف.

#### النتيجة المتوقعة

تشغيل البرنامج الكامل ينتج ملفًا باسم **ExtPDF417Meta.png**. عند فتح الصورة، ستظهر رمز Macro PDF417 مستطيل مع النص “Åspóse.Barcóde©” مُرمّزًا، وتطابق الكثافة البصرية بعدد بكسل X البالغ 2 الذي حددته. قراءة الصورة باستخدام قارئ يدعم PDF417 تُعيد جميع حقول البيانات الوصفية التي عُرّفت في الخطوة 3.

## مثال عملي كامل

انسخ الشيفرة أدناه إلى مشروع وحدة تحكم جديد (`dotnet new console`) واستبدل `YOUR_DIRECTORY` بمسار مطلق أو نسبي موجود على جهازك.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

شغّل البرنامج (`dotnet run`). بعد التنفيذ، تحقق من ظهور ملف PNG في الموقع الذي حددته. استخدم أي تطبيق قراءة رموز شريطية يدعم Macro PDF417 لتأكيد أن البيانات الوصفية مدمجة بشكل صحيح.

## الاختلافات الشائعة وحالات الحافة

- **تنسيقات الصور المختلفة**: استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Tiff` إذا كان نظامك اللاحق يفضّل تنسيقًا آخر.  
- **تغيير حجم الوحدة**: القيم الأكبر لـ `XDimension.Pixels` تحسّن موثوقية المسح على الماسحات منخفضة الدقة ولكنها تزيد حجم الصورة.  
- **قطاعات متعددة**: لإنشاء ملف متعدد القطاعات، أنشئ سلسلة من الرموز الشريطية، زد `MacroPdf417SegmentID` لكل واحدة، واحفظ `MacroPdf417FileID` ثابتًا. يجب أن يحتوي آخر قطاع فقط على `MacroPdf417Terminator` مضبوطة.  
- **دعم Unicode**: يقوم المولد تلقائيًا بترميز أحرف Unicode؛ تأكد من أن سلسلة المصدر تستخدم ترميز UTF‑8 إذا قرأتها من ملف خارجي.  
- **معالجة الأخطاء**: غلف كتلة `using` بكتلة try‑catch لالتقاط `BarCodeException` عند وجود معلمات غير صالحة (مثل عدد الأعمدة خارج النطاق).

## نصائح احترافية

- **الأداء**: أعد استخدام كائن `BarcodeGenerator` واحد عند إنشاء العديد من الرموز الشريطية بنفس الإعدادات؛ غير خاصية `CodeText` فقط بين عمليات الحفظ.  
- **تقدير حجم الملف**: يجب أن يتطابق حقل `MacroPdf417FileSize` مع عدد البايتات للحمولة الأصلية؛ الاختلافات قد تؤدي إلى فشل التحقق في الأنظمة اللاحقة.  
- **الاختبار**: تحقق من صحة الرموز الشريطية المُولدة باستخدام كل من القارئ المدمج في Aspose (`BarCodeReader`) ومُسحّب طرف ثالث لضمان التوافق.

## الخلاصة

يُظهر لك هذا المثال من **Aspose.BarCode** كيفية **إنشاء رمز PDF417 شريطي في C#** مع دعم كامل للبيانات الوصفية Macro، مما يمنحك أساسًا قويًا لبناء خطوط تبادل بيانات قائمة على الرموز الشريطية.

## ماذا يجب أن تتعلم بعد ذلك؟

تغطي الدروس التالية مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء رمز شريطي – PDF417 المدمج باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [كيفية إنشاء منطقة هادئة للرمز الشريطي Code 16K باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [كيفية إنشاء منطقة هادئة للرمز الشريطي ITF-14 باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**آخر تحديث:** 2026-10-09  
**تم الاختبار باستخدام:** Aspose.BarCode 24.11 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء صورة رمز PDF417 في C باستخدام Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [كيفية إنشاء رمز شريطي – PDF417 المدمج باستخدام Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [دروس مولد الرمز الشريطي: كيفية إنشاء رمز PDF417](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}