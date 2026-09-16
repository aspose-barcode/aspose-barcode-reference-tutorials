---
category: general
date: 2026-08-03
description: إنشاء رمز شريطي PDF417 في C# بسرعة. تعلم كيفية توليد رمز شريطي PDF417
  وكيفية حفظ صورة الرمز الشريطي بصيغة PNG باستخدام Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: ar
lastmod: 2026-08-03
og_description: إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.Barcode. اتبع هذا الدليل
  لإنشاء رمز شريطي PDF417 وكيفية حفظ صورة الرمز الشريطي بكفاءة.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: إنشاء باركود PDF417 في C# – دليل برمجة كامل
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: إنشاء رمز شريطي PDF417 في C# – دليل خطوة بخطوة
url: /ar/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شيفرة PDF417 في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء شيفرة PDF417** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية توليد شيفرة PDF417 وكيفية حفظ صورة الشيفرة. ستحصل في النهاية على ملف PNG يمكن استخدامه في التقارير، التذاكر، أو تطبيقات المسح على الهواتف المحمولة.

يغطي الدرس كل شيء من إعداد المشروع حتى ملف PNG النهائي. لا تحتاج إلى وثائق خارجية؛ فقط اتبع الخطوات وشغّل الكود.

## ما ستحتاجه

قبل أن تبدأ، تأكد من توفر ما يلي:

* .NET 6.0 SDK أو أحدث (الكود يعمل أيضاً مع .NET Framework 4.7+)
* Visual Studio 2022 أو أي بيئة تطوير تدعم C#
* اتصال بالإنترنت لتثبيت حزمة **Aspose.Barcode for .NET** عبر NuGet

هذه المتطلبات المسبقة تضمن أن الكود يُترجم دون الحاجة إلى إعدادات إضافية.

## إنشاء شيفرة PDF417 – إعداد المشروع

1. افتح موجه الأوامر وأنشئ مشروع console جديد:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. أضف مكتبة Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. افتح ملف `Program.cs` الذي تم إنشاؤه. توضح عبارات `using` في الأعلى كيفية الوصول إلى فئات الشيفرة:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

المشروع الآن جاهز **لإنشاء شيفرة PDF417**.

## كيفية توليد شيفرة PDF417 باستخدام Aspose.Barcode

تكمن جوهر عملية إنشاء الشيفرة في الفئة `BarcodeGenerator`. تقوم بتحديد نوع الترميز (`EncodeTypes.Pdf417`) والبيانات التي تريد ترميزها.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### لماذا هذا مهم

* **EncodeTypes.Pdf417** يوجه المكتبة لاستخدام معيار PDF417، الذي يدعم أحجام بيانات كبيرة وتصحيح الأخطاء.
* توفير أحرف Unicode يثبت أن المولد يتعامل مع مدخلات غير ASCII دون إعدادات إضافية.

## كيفية ضبط مظهر الشيفرة

يمكنك التحكم في حجم كل وحدة، عدد الأعمدة، وما إذا كانت الشيفرة تستخدم الوضع المضغوط (truncated). تؤثر هذه الإعدادات على كل من قابلية القراءة وحجم الملف.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### نصيحة عملية

إذا كنت بحاجة إلى شيفرة أطول لوجود مساحة أفقية محدودة، قم بزيادة قيمة `Columns`. ضبط `Truncate` على `true` يقلل الارتفاع الكلي بإزالة مناطق الصمت، وهو مثالي لشاشات الهواتف المحمولة.

## كيفية حفظ صورة الشيفرة بصيغة PNG

بعد ضبط المولد، استدعِ الدالة `Save` مع مسار الملف وصيغة الصورة المطلوبة. تقوم الطريقة بكتابة الصورة مباشرة إلى القرص.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### النتيجة المتوقعة

تشغيل البرنامج ينشئ ملف `CompactPdf417.png` في مجلد المشروع. عند فتح الملف ستظهر شيفرة PDF417 مضغوطة ترمز السلسلة *Åspóse.Barcóde©*. يمكن تضمين الصورة في HTML، تقارير PDF، أو طباعتها على الملصقات.

## الكود الكامل

فيما يلي البرنامج الكامل القابل للتنفيذ. انسخه إلى `Program.cs` ثم نفّذ الأمر `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### التحقق من النتيجة

بعد انتهاء البرنامج، يمكنك التحقق من وجود الملف بأمر سريع:

```bash
dotnet run && ls -l CompactPdf417.png
```

إذا ظهر الملف، فإن عملية **إنشاء شيفرة PDF417** نجحت.

## الاختلافات الشائعة وحالات الحافة

| الحالة | التعديل |
|-----------|------------|
| **سلسلة بيانات أطول** | زيادة `Columns` أو ضبط `Rows` لاستيعاب المزيد من الكلمات المشفرة. |
| **صيغة صورة مختلفة** | استبدال `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Gif`. |
| **دقة أعلى** | ضبط `generator.Parameters.ImageResolution` قبل استدعاء `Save`. |
| **لون الخلفية** | استخدم `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **معالجة الاستثناءات** | غلف `generator.Save` بكتلة `try/catch` لالتقاط أخطاء الإدخال/الإخراج. |

تتيح لك هذه التعديلات تخصيص الشيفرة لتناسب الأجهزة أو متطلبات العلامة التجارية الخاصة بك.

## الخلاصة

أنت الآن تعرف كيف **تنشئ شيفرة PDF417** في C# باستخدام Aspose.Barcode، وتضبط مظهرها، و**تحفظ صورة الشيفرة** بصيغة PNG. يوضح المثال الكامل كل خطوة مطلوبة، من إعداد المشروع حتى التحقق، لتتمكن من دمج توليد الشيفرات في أي حل .NET.

بعد ذلك، يمكنك استكشاف مواضيع ذات صلة مثل **كيفية توليد رموز QR**، **إدراج الشيفرات في مستندات PDF**، أو **تخصيص ألوان الشيفرة**. جميع هذه المواضيع تعتمد على نفس واجهة برمجة التطبيقات، مما يتيح لك توسيع قدرات المسح في تطبيقك بأقل جهد. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}