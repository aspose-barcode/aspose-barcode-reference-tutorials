---
category: general
date: 2026-08-15
description: قراءة الباركود من صورة في C# باستخدام BarCodeReader. تعلم كيفية قراءة
  عدة باركودات في C#، قراءة باركود PDF417، وشاهد مثالًا كاملاً لـ BarCodeReader في
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: ar
lastmod: 2026-08-15
og_description: اقرأ الباركود من الصورة في C# مع دليل خطوة بخطوة. اكتشف كيفية قراءة
  عدة باركودات في C#، فك تشفير رموز PDF417، وتشغيل مثال كامل لـ C# BarCodeReader.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: قراءة الباركود من صورة في C# – دليل BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: قراءة الباركود من صورة في C# – دليل BarCodeReader
url: /ar/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة الباركود من صورة في C# – دليل BarCodeReader

إذا كنت بحاجة إلى **قراءة الباركود من صورة** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك باستخدام الفئة `BarCodeReader`. ستتعرف أيضًا على كيفية **قراءة عدة باركودات C#**، فك تشفير رمز PDF417، والحصول على مثال كامل **C# BarCodeReader** يمكنك نسخه إلى مشروعك.

يغطي الدرس كل خطوة—من إضافة حزمة NuGet المطلوبة إلى طباعة حقول PDF417 الموسعة—حتى تحصل على برنامج كونسول قابل للتنفيذ. لا تحتاج إلى وثائق خارجية؛ جميع الشيفرات والشروحات مضمّنة.

## ما ستحتاجه

قبل أن تبدأ، تأكد من توفر ما يلي:

* .NET 6.0 SDK أو أحدث (الشيفرة تعمل مع .NET Core و .NET Framework)
* Visual Studio 2022 أو أي محرر يدعم C#
* حزمة NuGet `Aspose.BarCode` (أو المكتبة المكافئة التي توفر `BarCodeReader`)
* ملف صورة يحتوي على باركود Macro PDF417 (مثال: `ExtPDF417Meta.png`)

وجود هذه المتطلبات يضمن أن العينة تُجمّع دون إعدادات إضافية.

## قراءة الباركود من صورة باستخدام BarCodeReader

الخطوة الأولى هي إنشاء كائن `BarCodeReader` يشير إلى ملف الصورة ويخبر المكتبة بنوع الباركود الذي يجب البحث عنه.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**لماذا يعمل هذا:**  
`BarCodeReader` يفتح الصورة، يفحصها للعثور على `DecodeType` المحدد، ويعيد مجموعة من كائنات `BarCodeResult`. يحتوي كل نتيجة على بيانات الباركود العامة (`CodeTypeName`, `CodeText`) ولـ Macro PDF417، كائن `Extended.Pdf417` يُظهر جميع الحقول الإضافية المعرفة في المعيار.

## قراءة عدة باركودات C# في صورة واحدة

أحيانًا تحتوي الصورة على أكثر من باركود (مثال: رمز QR بجانب PDF417). للتعامل مع هذا السيناريو، ما عليك سوى حذف `DecodeType` الصريح أو تمرير `DecodeType.AllSupported` ثم التكرار عبر النتائج.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**لماذا تحتاج هذا:**  
تحديد `AllSupported` يخبر المحرك بمحاولة كل صيغة باركود يعرفها، مما يضمن التقاط كل رمز في الصورة. هذا هو النهج الموصى به عندما لا يمكنك توقع أنواع الباركود مسبقًا.

## كيفية قراءة باركود PDF417 باستخدام C#

إذا كنت تهتم فقط بصيغة PDF417 الكلاسيكية (غير الماكرو)، غيّر `DecodeType` إلى `Pdf417`. يبقى باقي الشيفرة كما هو، باستثناء أن الحقول الموسعة غير متاحة.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**لماذا هذا مهم:**  
PDF417 الكلاسيكي لا يُظهر الخصائص الخاصة بالماكرو، لذا لا حاجة لكتلة `Extended.Pdf417`. استخدام `DecodeType` الدقيق يسرّع عملية المسح لأن المكتبة تتخطى الخوارزميات غير المدعومة.

## مثال كامل لـ C# BarCodeReader يمكنك نسخه

فيما يلي البرنامج الكامل الذي يجمع السيناريوهات الثلاثة في تطبيق كونسول سهل التشغيل. استبدل `YOUR_DIRECTORY/ExtPDF417Meta.png` بالمسار الفعلي لصورتك.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### النتيجة المتوقعة

عند احتواء صورة العينة على باركود Macro PDF417، يطبع الكونسول شيئًا مشابهًا لـ:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

إذا كانت الصورة تحتوي فقط على PDF417 عادي، سيكون قسم “Macro PDF417” فارغًا، وسيظهر قسم “Classic PDF417” النص المفكك.

## الخلاصة

أنت الآن تعرف كيف **تقرا الباركود من صورة** في C# باستخدام `BarCodeReader`، وكيف **تقرا عدة باركودات C#** في ملف واحد، والخطوات الدقيقة **لقراءة باركود PDF417**—كلا النسختين الماكرو والكلاسيكية. مثال **C# BarCodeReader** الكامل جاهز للنسخ إلى أي مشروع .NET، ويمكنك توسيعه للتعامل مع صيغ أخرى أو دمجه في خط معالجة صور أكبر.

**الخطوات التالية**

* استكشف أنماط معالجة الأخطاء مثل `try / catch` حول كتلة القارئ.  
* جرّب كائن `ReaderParameters` لضبط سرعة ودقة الكشف.  
* اجمع قراءة الباركود مع مكتبات ما قبل معالجة الصور (


## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}