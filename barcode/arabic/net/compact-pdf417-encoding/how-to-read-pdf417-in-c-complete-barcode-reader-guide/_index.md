---
category: general
date: 2026-08-09
description: كيفية قراءة PDF417 في C# باستخدام BarCodeReader. تعلم قراءة ملفات PNG
  للباركود، ومعالجة عدة باركودات، واستخراج البيانات الوصفية الموسعة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: ar
lastmod: 2026-08-09
og_description: كيفية قراءة PDF417 في C# باستخدام Aspose.BarCode. يوضح هذا البرنامج
  التعليمي كيفية قراءة ملفات PNG للباركود، ومعالجة عدة باركودات في صورة واحدة، واسترجاع
  بيانات التعريف الموسعة لـ PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: كيفية قراءة PDF417 في C# – دليل قارئ الباركود
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: كيفية قراءة PDF417 في C# – دليل شامل لقارئ الباركود
url: /ar/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة PDF417 في C# – دليل قارئ الباركود الكامل

إذا كنت بحاجة إلى **كيفية قراءة PDF417** في تطبيق .NET، فإن هذا الدليل يزودك بحل جاهز للتنفيذ. ستتعرف على كيفية قراءة صورة PNG لباركود، ومعالجة عدة باركودات في نفس الصورة، واستخراج الحقول الموسعة لـ PDF417 التي يخفيها العديد من الماسحات.

قراءة باركودات PDF417 شائعة في اللوجستيات، وإصدار التذاكر، وإدارة المستندات. بحلول نهاية هذا الدرس يمكنك فك تشفير صورة Macro PDF417، وعرض كل نتيجة، واستخدام المعلومات الإضافية (معرف الملف، عدد القطاعات، الطوابع الزمنية، إلخ) في منطق عملك الخاص.

## المتطلبات المسبقة

- .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.7+)
- Visual Studio 2022 أو أي بيئة تطوير C#
- **Aspose.BarCode for .NET** (نسخة تجريبية مجانية أو حزمة NuGet مرخصة)
- صورة PNG تحتوي على باركود Macro PDF417 (ملف العينة اسمه `ExtPDF417Meta.png`)

> **نصيحة احترافية:** قم بتثبيت المكتبة باستخدام وحدة تحكم NuGet:  
> `dotnet add package Aspose.BarCode`

## كيفية قراءة PDF417 باستخدام BarCodeReader في C#

جوهر الحل هو الفئة `BarCodeReader`. تقبل مسار الصورة وعداد `DecodeType` الذي يخبر المحرك بالرمز الذي يجب البحث عنه.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
        }
    }
}
```

### لماذا يعمل هذا

- **`DecodeType.MacroPdf417`** يخبر القارئ بالبحث عن نسخة Macro PDF417، التي تخزن الحقول الإضافية التي تراها في الخطوة 4.
- كتلة `using` تقوم بتحرير القارئ تلقائيًا، وتحرير مقابض الملفات.
- `ReadBarCodes()` تُرجع **كل** الباركودات التي تطابق النوع المطلوب، مما يلبي متطلب *قراءة عدة باركودات* حتى إذا كانت الصورة تحتوي على واحد فقط.

تشغيل البرنامج يطبع مخرجات مشابهة لـ:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## استخدام قارئ الباركود C# لقراءة عدة باركودات

إذا كانت الصورة تحتوي على عدة رموز Macro PDF417 (مثلاً، صفحة ممسوحة ضوئيًا تحتوي على دفعة من التذاكر)، فإن حلقة `foreach` نفسها تعالج كل واحدة. لا يلزم أي كود إضافي؛ القارئ يجمع النتائج داخليًا.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### الأخطاء الشائعة

- **تنسيق الصورة:** القارئ يدعم PNG، JPEG، BMP، وTIFF. إذا جربت تنسيقًا لا يستطيع فك تشفيره، ستحصل على مجموعة فارغة. لهذا يسلط الدرس الضوء على *قراءة باركود PNG*.
- **الدقة:** الصور منخفضة الدقة (< 300 dpi) قد تتسبب في فقدان القطاعات. قم بزيادة الدقة أو اطلب مسحًا بجودة أعلى عندما يكون ذلك ممكنًا.
- **علامة Macro:** نسيان `DecodeType.MacroPdf417` يقتصر المحرك على PDF417 العادي ويتجاهل البيانات الموسعة. دائمًا حدد نوع الماكرو عندما تحتاج إلى حقول *قراءة باركود موسعة*.

## قراءة ملفات PNG للباركود – أفضل الممارسات

التعامل مع ملفات PNG سهل لأن التنسيق يحافظ على بيانات البكسل بدون فقدان. إليك قائمة سريعة:

1. تحقق من وجود الملف قبل إنشاء القارئ.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. استخدم `Image.FromFile` فقط عندما تحتاج إلى معالجة مسبقة (دوران، قص). يمكن لـ `BarCodeReader` فتح الملف مباشرة، مما يجنب تخصيص ذاكرة إضافية.
3. إذا كان PNG يحتوي على شفافية، يظل القارئ يعمل لأن الباركود يُرسم على بكسلات غير شفافة.

## الوصول إلى بيانات PDF417 الموسعة

الكائن `Extended.Pdf417` يكشف كل حقل اختياري معرف في مواصفة PDF417. يمكنك ربط هذه الحقول بنموذج نطاق، تخزينها في قاعدة بيانات، أو استخدامها للتحقق.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

املأ النموذج:



## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات المعروضة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية قراءة باركود DataMatrix باستخدام Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [كيفية إنشاء باركود – PDF417 مضغوط باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [قراءة باركود DataMatrix C# – توليد وضع DataMatrix (تلقائي)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}