---
category: general
date: 2026-08-03
description: قراءة الباركود PDF417 من صورة باستخدام C# BarCodeReader – مثال كامل لقارئ
  الباركود يوضح أيضًا كيفية قراءة عدة باركودات.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: ar
lastmod: 2026-08-03
og_description: اقرأ رمز PDF417 بسرعة باستخدام مثال BarCodeReader بلغة C#. اتبع هذا
  الدليل خطوة بخطوة لفك تشفير macro PDF417 وقراءة عدة رموز شريطية من صورة.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: قراءة رمز PDF417 الشريطي في C# – مثال كامل لقارئ الباركود
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: قراءة الباركود PDF417 في C# – مثال على قارئ الباركود
url: /ar/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة الباركود PDF417 في C# – مثال على قارئ الباركود

إذا كنت بحاجة إلى قراءة بيانات باركود PDF417 من صورة، يوضح لك هذا الدليل كيفية القيام بذلك باستخدام الفئة **BarCodeReader** في C#. ستتعلم مثالًا على قارئ الباركود يتعامل أيضًا مع macro PDF417 ويمكنه قراءة عدة باركودات في صورة واحدة.

العمل مع الباركودات غالبًا ما يعني التعامل مع مصادر صور مختلفة، ظروف إضاءة متباينة، وأحيانًا بيانات مركبة مثل مقاطع macro PDF417. يغطي هذا البرنامج التعليمي كل ما تحتاجه لفك تشفير باركود PDF417، استخراج حقوله الموسعة، ومعالجة عدة باركودات من نفس الصورة. في النهاية ستحصل على برنامج كونسول قابل للتنفيذ يقرأ الباركودات من ملف صورة ويطبع معلومات مفصلة إلى الكونسول.

## ما ستحتاجه

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت  
* نسخة حديثة من حزمة **Aspose.BarCode for .NET** على NuGet (أو أي مكتبة متوافقة توفر `BarCodeReader` و `DecodeType.MacroPdf417`)  
* ملف صورة يحتوي على باركود PDF417 أو macro PDF417 (العينة تستخدم `ExtPDF417Meta.png`)  
* محرر شفرة أو بيئة تطوير متكاملة مثل Visual Studio 2022  

لا توجد خدمات إضافية أو واجهات برمجة تطبيقات خارجية مطلوبة.

## إعداد المشروع لقراءة الباركود

1. **إنشاء مشروع كونسول جديد**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **إضافة مكتبة الباركود**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **نسخ صورة الباركود**  

   ضع `ExtPDF417Meta.png` (أو أي صورة تحتوي على باركود PDF417) في مجلد المشروع.  
   لهذا البرنامج التعليمي نفترض أن الملف موجود في `YOUR_DIRECTORY/ExtPDF417Meta.png`.

المشروع الآن جاهز للترجمة والتنفيذ مثال قارئ الباركود.

## كيفية قراءة باركود PDF417 باستخدام BarCodeReader

جوهر الحل هو كتلة `using` تنشئ مثيلًا من `BarCodeReader`، تحدد `DecodeType.MacroPdf417`، وتكرر عبر كل باركود مكتشف. الشيفرة التالية برنامج كامل ومستقل يمكنك لصقه في `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**لماذا يعمل هذا**:  

* `DecodeType.MacroPdf417` يخبر القارئ بالبحث عن امتداد macro لباركود PDF417، والذي يحمل بيانات وصفية إضافية مثل معرف الملف، عدد المقاطع، والطوابع الزمنية.  
* جملة `using` تضمن تحرير الموارد غير المدارية (مقابض الملفات، مخازن فك الترميز الأصلية) بسرعة.  
* حلقة `foreach` تعالج **جميع** الباركودات الموجودة في الصورة، مما يلبي متطلب *قراءة عدة باركودات*.

عند تشغيل البرنامج (`dotnet run`)، يجب أن ترى مخرجات مشابهة للتالي:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

إذا احتوت الصورة على أكثر من باركود PDF417 واحد، تطبع الحلقة كتلة منفصلة لكل باركود، وبالتالي توضح كيفية **قراءة عدة باركودات** من صورة واحدة.

## قراءة عدة باركودات من صورة

يمكن لنفس مثيل `BarCodeReader` فك تشفير عدة أنواع باركود في آن واحد. لتوسيع النطاق من macro PDF417 فقط إلى أي PDF417 (أو حتى QR، Code128، إلخ)، عدل علم `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* هو قناع بت، لذا يمكنك دمج أي عدد من الصيغ المدعومة. هذه المرونة تجعل المقتطف **مثالًا على قارئ الباركود** يعمل لمجموعة واسعة من حالات الاستخدام، مثل مسح ملصقات المنتجات، التذاكر، أو بطاقات الهوية.

## الوصول إلى حقول macro PDF417 بأمان

يضيف macro PDF417 مجموعة غنية من الخصائص الموسعة. ومع ذلك، ليس كل باركود يحتوي على كل حقل. محاولة الوصول إلى خاصية مفقودة قد تؤدي إلى استثناء `NullReferenceException`. النهج الأكثر أمانًا هو التحقق من كل خاصية قبل طباعتها:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*لماذا هذا مهم*: في عمليات النشر الواقعية قد تتلقى باركودات PDF417 عادية لا تحتوي على بيانات macro. الفحص الوقائي يضمن استمرار تشغيل تطبيقك دون تعطل.

## الأخطاء الشائعة وأفضل الممارسات

| المشكلة | لماذا يحدث | الحل الموصى به |
|-------|----------------|-----------------|
| مسار الصورة غير صحيح | `BarCodeReader` يرمي استثناء ملف غير موجود قبل أي عملية فك ترميز | استخدم `Path.Combine` وتحقق من وجود الملف باستخدام `File.Exists` |
| صورة منخفضة الدقة | لا يستطيع المفكك تحديد حواف الباركود، مما ينتج عنه عدم اكتشاف أي باركود | قدم دقة لا تقل عن 300 dpi للحصول على نتائج موثوقة |
| دوران الباركود > 45° | العديد من المكتبات تفترض وضعية رأسية | فعّل `reader.RecognitionOptions.RotateImage = true` إذا كان |

## ماذا يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}