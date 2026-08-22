---
category: general
date: 2026-08-22
description: كيفية قراءة رموز PDF417 الشريطية في C# مع دليل خطوة بخطوة، يغطي كيفية
  قراءة عدة رموز من صورة واستخراج تفاصيل MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: ar
lastmod: 2026-08-22
og_description: كيفية قراءة رموز PDF417 الشريطية في C# بسرعة. يوضح لك هذا الدرس كيفية
  قراءة عدة رموز شريطية من صورة واسترجاع المعلومات الموسعة لـ MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: كيفية قراءة باركود PDF417 في C# – دليل برمجي كامل
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية قراءة رموز PDF417 الشريطية في C# – دليل كامل
url: /ar/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة باركود PDF417 في C# – دليل كامل

إذا كنت بحاجة إلى **كيفية قراءة PDF417** في تطبيق .NET، فإن هذا الدرس يقدّم لك حلاً جاهزًا للتنفيذ. ستتعلم كيفية قراءة عدة باركودات من صورة واحدة، استخراج مجموعة بيانات MacroPdf417 الكاملة، وعرضها في وحدة التحكم. يعمل النهج مع مكتبة Aspose.BarCode for .NET ويتطلب فقط بضع أسطر من الشيفرة.

قراءة الباركودات من صورة هي مهمة شائعة في أنظمة الجرد، التحقق من التذاكر، وإدارة المستندات. بنهاية هذا الدليل ستكون قادرًا على فك تشفير أي باركود PDF417 أو MacroPdf417، ومعالجة عدة رموز في صورة واحدة، وفهم الحقول الموسعة التي يوفرها MacroPdf417.

## المتطلبات المسبقة

- .NET 6.0 SDK أو أحدث (الشيفرة تُجمّع أيضًا مع .NET Framework 4.7+)
- Visual Studio 2022 أو أي محرر C# تفضله
- حزمة NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- صورة نموذجية تحتوي على باركود MacroPdf417 (مثال: `MacroPdf417.png`)

لا توجد إعدادات إضافية مطلوبة؛ المكتبة تتعامل مع تحميل الصورة وفك الترميز داخليًا.

## كيفية قراءة باركود PDF417 من صورة في C#

جوهر الحل هو الفئة `BarCodeReader`. تقوم بفتح الصورة، اكتشاف جميع الباركودات من النوع المحدد، وإرجاع مجموعة من كائنات `BarCodeResult`. الشيفرة التالية تُظهر برنامجًا كاملاً لوحدة التحكم.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### لماذا كل سطر مهم

| الخطوة | الغرض |
|------|---------|
| **1️⃣ Initialize** | ينشئ كائن `BarCodeReader` مرتبط بملف الصورة ويقصر الاكتشاف على رموز MacroPdf417، مما يسرّع المعالجة. |
| **2️⃣ Iterate** | `ReadBarCodes()` تُعيد **جميع** الباركودات التي تطابق النوع المطلوب، مما يتيح لك **قراءة عدة باركودات** دون حلقات إضافية. |
| **3️⃣ Basic output** | يعرض `CodeTypeName` العام والنص القابل للقراءة `CodeText`. هذا مفيد للتسجيل أو التحقق السريع. |
| **4️⃣ Extended data** | يحمل MacroPdf417 بيانات تعريفية إضافية (معرف الملف، عدد القطاعات، الطوابع الزمنية، إلخ). كائن `Extended.Pdf417` يُظهر كل حقل مباشرة، بحيث يمكنك تخزين أو التحقق من حزمة البيانات الكاملة. |

تشغيل البرنامج ضد صورة MacroPdf417 صالحة ينتج مخرجات وحدة تحكم مشابهة لما يلي:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

تؤكد المخرجات أن المكتبة نجحت في قراءة الباركود، استخراج النص، وتوفير كل حقل من حقول MacroPdf417.

## قراءة عدة باركودات من صورة واحدة

تضع العديد من السيناريوهات الواقعية عدة رموز PDF417 على ملصق واحد—مثل بيان شحن يحتوي على رمز الناقل، رقم تتبع، وإقرار جمركي. كتلة الشيفرة السابقة بالفعل **تقرأ عدة باركودات** لأن `ReadBarCodes()` تُعيد مجموعة من جميع التطابقات. لا حاجة لإعدادات إضافية؛ عليك فقط التكرار عبر النتائج كما هو موضح.

إذا رغبت في قصر القارئ على PDF417 القياسي (بدون ماكرو) مع الاستمرار في معالجة عدة رموز، استبدل `DecodeType.MacroPdf417` بـ `DecodeType.Pdf417`. يبقى باقي المنطق دون تغيير.

## فهم البيانات الموسعة في MacroPdf417

MacroPdf417 هو امتداد لمواصفات PDF417 العادية. يقسّم الأحمال الكبيرة إلى عدة قطاعات ويضيف رأسًا صغيرًا يصف الملف بالكامل. أهم الحقول هي:

- **MacroPdf417FileID** – معرف فريد يُشارك بين جميع قطاعات نفس الملف.
- **MacroPdf417SegmentID** – رقم تسلسل القطاع الحالي.
- **MacroPdf417SegmentsCount** – إجمالي عدد القطاعات المتوقعة.
- **MacroPdf417FileName** – اسم ملف اختياري يُنقل مع الباركود.
- **MacroPdf417Checksum** – قيمة فحص الأخطاء للملف الكامل.
- **MacroPdf417FileSize** – حجم الحمولة الثنائية الأصلية.
- **MacroPdf417TimeStamp** – طابع زمني بصيغة ISO‑8601 عند توليد الباركود.
- **MacroPdf417Addressee / Sender** – حقول نصية اختيارية للتوجيه.
- **MacroPdf417Terminator** – يحدد ما إذا كان هذا القطاع هو الأخير.

عند استلام جميع القطاعات، يمكنك إعادة بناء الملف الأصلي بترتيبها حسب `MacroPdf417SegmentID` وربط قيم `CodeText`. هذا المنطق سهل التنفيذ بمجرد توفر الحقول.

## الأخطاء الشائعة ونصائح الخبراء

- **جودة الصورة مهمة** – ملفات PNG/JPEG منخفضة الدقة أو مضغوطة بشدة قد تتسبب في فقدان الاكتشاف. استخدم DPI لا يقل عن 300 dpi للباركودات المطبوعة.
- **الرموز المختلطة** – إذا احتوت الصورة على كل من MacroPdf417 و PDF417 العادي، أنشئ قارئين (واحد لكل `DecodeType`) أو استخدم `DecodeType.AllSupported` وصفّ النتائج حسب `result.CodeTypeName`.
- **استهلاك الذاكرة** – جملة `using` تُفرغ كائن `BarCodeReader` فورًا، مما يمنع بقاء مخازن الصور الكبيرة في الذاكرة.
- **سلامة الخيوط** – `BarCodeReader` غير آمن للاستخدام المتعدد الخيوط. أنشئ نسخة منفصلة لكل خيط إذا كنت تفكّ شفرة صورًا بشكل متوازي.
- **معالجة الأخطاء** – غلف استدعاء `ReadBarCodes()` بكتلة try/catch لالتقاط `BarCodeException` في حال كانت الصور تالفة.

## ملخص المثال الكامل العامل

فيما يلي البرنامج الكامل الذي يمكنك نسخه إلى مشروع وحدة تحكم جديد. يتضمن جميع توجيهات `using`، ثابت لمسار الصورة، ونمط التخلص من الموارد.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

ابنِ المشروع باستخدام `dotnet build` وشغّله بـ `dotnet run`. ستطبع وحدة التحكم البيانات الأساسية لكل باركود والحمولة الكاملة لـ MacroPdf417.

## الخطوات التالية

- **إعادة بناء الملفات المتعددة الأجزاء** – جمع جميع القطاعات، ترتيبها حسب `MacroPdf417SegmentID`، وربط `CodeText` لتكوين الملف الأصلي.

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود PDF417 – ترميز PDF417 المدمج](/barcode/english/net/compact-pdf417-encoding/)
- [كيفية قراءة باركود PDF417 مع أحرف تركية في Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [كيفية استخدام Aspose لباركود PDF417 (الصينية) في Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}