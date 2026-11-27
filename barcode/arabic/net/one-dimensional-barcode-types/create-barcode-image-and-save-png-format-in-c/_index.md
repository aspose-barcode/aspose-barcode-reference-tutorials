---
category: general
date: 2026-11-27
description: إنشاء صورة باركود في C# وحفظ الصورة بصيغة PNG باستخدام Aspose.BarCode
  – دليل خطوة بخطوة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: ar
lastmod: 2026-11-27
og_description: إنشاء صورة باركود بلغة C# وحفظ الصورة بصيغة PNG باستخدام Aspose.BarCode.
  اتبع هذا الدليل لإنشاء باركود Macro PDF417 خطوة بخطوة.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: إنشاء صورة باركود وحفظها بصيغة PNG في C# – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: إنشاء صورة باركود وحفظها بصيغة PNG في C#
url: /ar/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة الباركود وحفظها بصيغة PNG في C#

إذا كنت بحاجة إلى **إنشاء صورة باركود** في تطبيق .NET، يوضح لك هذا الدليل كيفية توليد باركود Macro PDF417 و**حفظ الصورة بصيغة PNG** باستخدام Aspose.BarCode. ستحصل على مثال كامل قابل للتنفيذ وتفسير لكل إعداد حتى تتمكن من تعديل الكود وفق متطلباتك الخاصة.

إنشاء الباركود يتجاوز استدعاء طريقة واحدة؛ عليك ضبط حجم الوحدة، معلمات الماكرو، وصيغة الإخراج. بنهاية هذا البرنامج التعليمي ستفهم لماذا كل خاصية مهمة، وكيفية التعامل مع الحالات الطرفية الشائعة، وكيفية التحقق من أن ملف PNG تم كتابته بشكل صحيح.

## ما ستحتاجه

- .NET 6.0 أو أحدث (الكود يعمل أيضاً مع .NET Framework 4.6+)
- Aspose.BarCode for .NET (متاح عبر NuGet: `Install-Package Aspose.BarCode`)
- بيئة تطوير متكاملة مثل Visual Studio 2022 أو Visual Studio Code
- صلاحية كتابة في المجلد الذي سيُحفظ فيه ملف PNG

## الخطوة 1: تهيئة مولد الباركود

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` مع تحديد نوع الترميز `EncodeTypes.MacroPdf417` والنص الذي تريد ترميزه.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**لماذا هذا مهم:**  
`EncodeTypes.MacroPdf417` يخبر المكتبة باستخدام نسخة الماكرو من PDF417، والتي تدعم تقسيم الملف وإضافة بيانات وصفية إضافية. المُنشئ يستقبل أيضاً النص القابل للقراءة البشرية الذي سيُضمّن في الباركود.

## الخطوة 2: تعريف حجم الوحدة (البُعد X)

البُعد X يتحكم في عرض وحدة الباركود الواحدة (أصغر عنصر أسود/أبيض). قيمة `2` بكسل تعمل جيداً لصور PNG المعروضة على الشاشة.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**نصيحة عملية:**  
إذا كنت تخطط لطباعة الباركود، زد قيمة البكسل (مثلاً `4` أو `5`) لتجنب التشويش على الطابعات منخفضة الدقة.

## الخطوة 3: ضبط معلمات ماكرو PDF417

ماكرو PDF417 يضيف عدة حقول اختيارية تساعد في تحديد ملف المصدر، ترتيب القطع، وفحوصات التكامل. أدناه مجموعة كاملة من المعلمات النموذجية؛ يمكنك حذف أي منها لا تحتاجه.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**لماذا هذه الحقول مفيدة:**  

| المعامل | الغرض |
|-----------|---------|
| `Columns` | يتحكم في عرض الباركود؛ عدد أقل من الأعمدة ينتج باركود أطول. |
| `MacroPdf417FileID` | معرف فريد يربط جميع القطع معاً. |
| `MacroPdf417SegmentID` | موضع هذه القطعة ضمن الملف الكامل. |
| `MacroPdf417SegmentsCount` | العدد الكلي للقطع؛ مطلوب لإعادة التجميع. |
| `MacroPdf417FileName` | اسم قابل للقراءة البشرية يمكن عرضه بواسطة تطبيقات المسح. |
| `MacroPdf417Checksum` | يساعد المستقبلين على التحقق من سلامة البيانات (CCITT‑16). |
| `MacroPdf417FileSize` | إشارة حجم اختيارية للملف الأصلي. |
| `MacroPdf417TimeStamp` | طابع زمني لإنشاء الملف الأصلي. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | بيانات وصفية للتوجيه أو الملكية. |
| `MacroPdf417Terminator` | يحدد ما إذا كانت هذه هي القطعة النهائية (`Set`) أو قطعة وسطية (`Unset`). |

**حالة طرفية:** إذا أنشأت باركود بقطعة واحدة، اضبط `MacroPdf417SegmentsCount` إلى `1` و`MacroPdf417Terminator` إلى `Unset`. ستقوم المكتبة تلقائياً بحذف الحقول المتعلقة بالقطع غير المتطابقة.

## الخطوة 4: حفظ الباركود المولد كصورة PNG

أخيراً، استدعِ `Save` مع مسار الملف وقيمة التعداد `BarCodeImageFormat.Png`. تقوم الطريقة بكتابة الصورة إلى القرص بصيغة PNG غير مضغوطة.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**لماذا PNG؟**  
PNG يحافظ على قيم البكسل الدقيقة، وهو أمر أساسي لأجهزة مسح الباركود التي تعتمد على تباين حاد. ضغط JPEG قد يضيف تشويهات تُفسد نمط الباركود.

### التحقق من النتيجة

بعد تشغيل البرنامج، يجب أن ترى ملفًا باسم `ExtPDF417Meta.png` في مجلد التنفيذ. فتحه بأي عارض صور سيظهر باركودًا مستطيلًا كثيفًا. يمكنك التحقق من صحة الباركود بمسح الصورة باستخدام قارئ باركود محمول يدعم PDF417 macro؛ عادةً يعرض التطبيق البيانات الوصفية المضمّنة (معرف الملف، رقم القطعة، إلخ).

## المشكلات الشائعة وكيفية تجنّبها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| الباركود يظهر ضبابيًا | البُعد X منخفض بالنسبة للدقة المختارة | زد `XDimension.Pixels` أو قم بالعرض بدقة أعلى (`generator.Parameters.ImageResolution`). |
| الماسح يُظهر “خطأ في المجموع الاختباري” | قيمة `MacroPdf417Checksum` غير صحيحة | دع Aspose يحسب المجموع الاختباري تلقائيًا بحذف الخاصية، أو تأكد من مطابقة القيمة لخوارزمية CCITT‑16. |
| ملف PNG فارغ أو غير مُنشأ | مسار الإخراج غير صالح أو نقص صلاحية الكتابة | استخدم `Path.Combine` مع مجلد معروف قابل للكتابة (مثلاً `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| حقول الماكرو مُهملة | `EncodeTypes` تم ضبطه على `Pdf417` العادي بدلاً من `MacroPdf417` | تأكد من استخدام `EncodeTypes.MacroPdf417` في المُنشئ. |

## مثال كامل قابل للتنفيذ

فيما يلي البرنامج الكامل الذي يمكنك نسخه إلى تطبيق Console. يتوافق مع .NET 6.0 وينتج ملف PNG الموضح أعلاه.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**الإخراج المتوقع (وحدة التحكم):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

فتح `ExtPDF417Meta.png` يُظهر باركود Macro PDF417 واضح جاهز للمسح.

## الخطوات التالية

- **تغيير صيغة الصورة** – استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` إذا كنت بحاجة إلى نوع ملف مختلف. تذكر أن JPEG يضيف تشويهات ضغط قد تؤثر على موثوقية المسح.
- **ضبط الدقة** – استخدم

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء صورة باركود باستخدام Aspose.Barcode في C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [كيفية إنشاء صورة باركود PDF417 في C# مع خيارات Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [كيفية قراءة الباركود من صورة باستخدام C# مع Aspose.BarCode – دليل خطوة بخطوة](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}