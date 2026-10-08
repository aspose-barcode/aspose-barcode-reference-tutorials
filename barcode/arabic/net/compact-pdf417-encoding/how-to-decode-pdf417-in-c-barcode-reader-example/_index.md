---
category: general
date: 2026-09-26
description: تعلم كيفية فك تشفير PDF417 في C# مع مثال قارئ الباركود خطوة بخطوة. يوضح
  لك هذا الدليل كيفية قراءة صورة الباركود في C# باستخدام Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: ar
lastmod: 2026-09-26
og_description: كيفية فك تشفير PDF417 في C# بسرعة. اتبع مثال قارئ الباركود هذا لقراءة
  صورة الباركود في C# باستخدام Aspose.BarCode واستخراج تفاصيل الماكرو.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: كيفية فك تشفير PDF417 في C# – دليل شامل لقارئ الباركود
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: كيفية فك تشفير PDF417 في C# – مثال على قارئ الباركود
url: /ar/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية فك ترميز PDF417 في C# – مثال قارئ الباركود

إذا كنت بحاجة إلى **كيفية فك ترميز PDF417** في تطبيق .NET، فإن هذا الدليل يوفر حلاً كاملاً وجاهزًا للتنفيذ. ستتعرف على كيفية قراءة صورة الباركود باستخدام C# ومكتبة Aspose.BarCode، واستخراج معلومات ماكرو PDF417 الموسعة، وعرض كل حقل ذي صلة.

فك ترميز PDF417 لا يقتصر على النص العادي؛ فالصيغة يمكنها حمل بيانات تقسيم الملفات، والطوابع الزمنية، والاختبارات التحققية. يشرح هذا الدليل كل خطوة، ويوضح سبب هيكلة الكود بهذه الطريقة، ويسلط الضوء على الأخطاء الشائعة التي قد تواجهها عند تنفيذ مثال قارئ الباركود بـ C#.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

* .NET 6.0 (أو أحدث) SDK مثبت  
* Visual Studio 2022 (أو أي بيئة تطوير متوافقة مع C#)  
* حزمة NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)  
* صورة عينة ماكرو PDF417 (مثال: `ExtPDF417Meta.png`)

هذه المتطلبات تضمن أن الكود سيُترجم ويعمل دون الحاجة إلى إعدادات إضافية.

## الخطوة 1: تثبيت حزمة NuGet الخاصة بـ Aspose.BarCode

الخطوة الأولى في أي مشروع **read barcode image C#** هي إضافة مكتبة الباركود. افتح الطرفية في مجلد الحل الخاص بك وشغّل الأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

توفر الحزمة الفئات `BarCodeReader` و `DecodeType` والخاصية `Extended` المستخدمة للوصول إلى بيانات الماكرو. تثبيتها مرة واحدة يجعل هذه الفئات متاحة في جميع أنحاء مشروعك.

## الخطوة 2: إنشاء قارئ باركود لصورة ماكرو PDF417

الآن يمكنك إنشاء كائن `BarCodeReader` مع مسار الصورة وتحديد `DecodeType.MacroPdf417`. هذا يخبر المكتبة بالبحث عن صيغة PDF417 الموسعة التي تحتوي على معلومات الماكرو.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**لماذا هذا مهم:**  
`DecodeType.MacroPdf417` يُفعِّل محلل الماكرو المتخصص. إذا حذفت هذا الخيار، سيعيد القارئ فقط النص العادي ويتجاهل حقول الماكرو التي قد تحتاجها لإعادة بناء الملف.

## الخطوة 3: قراءة جميع الباركودات الموجودة في الصورة

يمكن أن تحتوي صورة واحدة على عدة رموز PDF417، خاصة عندما يتم تقسيم البيانات عبر قطاعات. التكرار عبر `ReadBarCodes()` يضمن التقاط كل قطاع.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**لماذا نحتاج إلى الحلقة:**  
بيانات ماكرو PDF417 غالبًا ما تظهر في عدة قطاعات. معالجة كل `BarCodeResult` يضمن جمع مجموعة الحقول الماكرو الكاملة، مثل `MacroPdf417FileID` و `MacroPdf417SegmentsCount`.

## الخطوة 4: استرجاع وعرض بيانات الباركود الأساسية

كائن `BarCodeResult` يحتوي على النوع والنص المفكك. عرض هذه القيم يساعد على التحقق من أن القارئ حدد الرمز بشكل صحيح قبل الخوض في تفاصيل الماكرو.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**نصيحة:** إذا كان `CodeText` فارغًا، قد تكون الصورة تالفة أو وضعية الفك غير صحيحة. تحقق مرة أخرى من `DecodeType` المستخدم أثناء التهيئة.

## الخطوة 5: استخراج معلومات ماكرو PDF417 الموسعة

توجد بيانات الماكرو تحت `barcodeResult.Extended.Pdf417`. كل خاصية تمثل حقلًا معرفًا في مواصفات PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**معنى كل حقل**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | المعرف الذي يجمع جميع القطاعات التي تنتمي إلى نفس الملف المنطقي. |
| `MacroPdf417SegmentID` | فهرس القطاع الحالي (يبدأ من 1). |
| `MacroPdf417SegmentsCount` | إجمالي عدد القطاعات المطلوبة لإعادة بناء الملف الأصلي. |
| `MacroPdf417FileName` | اسم الملف الاختياري المضمن في الماكرو. |
| `MacroPdf417Checksum` | اختبار CRC‑16 للتحقق من سلامة البيانات. |
| `MacroPdf417FileSize` | الحجم المتوقع للملف المعاد بناؤه (بالبايت). |
| `MacroPdf417TimeStamp` | التاريخ والوقت عندما تم إنشاء الماكرو. |
| `MacroPdf417Addressee` | معرف المستلم الاختياري. |
| `MacroPdf417Sender` | معرف المرسل الاختياري. |
| `MacroPdf417Terminator` | علم النهاية؛ يجب أن يكون `true` في آخر قطاع. |

فهم هذه الحقول يتيح لك إعادة بناء الملف الأصلي، والتحقق من سلامة البيانات، وتطبيق منطق أعمال مخصص (مثل رفض المستندات القديمة).

## الخطوة 6: التعامل مع عدة قطاعات وإعادة بناء الملف الأصلي (متقدم)

عندما يكون `MacroPdf417SegmentsCount` أكبر من 1، تحتاج إلى جمع كل قطاع، وترتيبه حسب `MacroPdf417SegmentID`، ثم دمج قيم `CodeText`. إليك تنفيذًا مختصرًا:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**لماذا هذا مهم:**  
بدون الترتيب والدمج، ستكون البيانات المفكوكة غير مكتملة أو مشوشة. يوضح المقتطف أيضًا برمجة دفاعية عبر فحص عدد القطاعات.

## الخطوة 7: إنهاء البرنامج مع معالجة الأخطاء وأفضل الممارسات

مثال **c# barcode reader example** جاهز للإنتاج يجب أن يتوقع أخطاء الإدخال/الإخراج، الصيغ غير المدعومة، والصور التالفة.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**قائمة التحقق لأفضل الممارسات**

* تحقق من مسار الصورة قبل إنشاء `BarCodeReader`.  
* استخدم عبارات `using` لضمان تحرير الموارد غير المُدارة.  
* سجّل حقول الماكرو لتتبع التدقيق—خاصة `MacroPdf417Checksum` و `MacroPdf417TimeStamp`.  
* عند التعامل مع ملفات كبيرة، فكر في تدفق الحمولة المدمجة إلى القرص بدلاً من الاحتفاظ بها بالكامل في الذاكرة.

## النتيجة المتوقعة

تشغيل البرنامج الكامل ضد صورة صالحة `ExtPDF417Meta.png` ينتج مخرجات مشابهة للتالي:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

إذا كانت جميع القطاعات الثلاثة موجودة، سيطبع كتلة إعادة البناء الحمولة الكاملة بعد رسالة التحقق.

## الخلاصة

أنت الآن تعرف **كيفية فك ترميز PDF417** في C# باستخدام مثال قارئ باركود قوي. غطى الدليل تثبيت Aspose.BarCode، تهيئة `BarCodeReader` لماكرو PDF417، التكرار عبر عدة باركودات، استخراج حقول الماكرو، إعادة بناء البيانات المقسمة، وتطبيق معالجة الأخطاء.

من هنا يمكنك:

* دمج القارئ في واجهة برمجة تطبيقات ويب تستقبل الصور المرفوعة.  
* تخزين بيانات الماكرو في قاعدة بيانات لأغراض التدقيق.  
* توسيع الحل ليشمل رموز ثنائية الأبعاد أخرى عن طريق تغيير `DecodeType` (e

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}