---
category: general
date: 2026-07-27
description: كيفية قراءة باركود PDF417 في C# بسرعة. تعلّم قراءة عدة باركودات، فك تشفير
  الصور، والحصول على بيانات تعريف Macro PDF417 في مثال كامل للباركود باستخدام C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: ar
lastmod: 2026-07-27
og_description: كيفية قراءة الباركود PDF417 في C# باستخدام هذا الدليل خطوة بخطوة.
  فك تشفير الصور، التعامل مع عدة باركودات، واستخراج بيانات تعريف Macro PDF417 في مثال
  جاهز للتنفيذ.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: كيفية قراءة PDF417 في C# – مثال كامل على الباركود
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: كيفية قراءة PDF417 في C# – مثال كامل على الباركود
url: /ar/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة PDF417 في C# – مثال كامل للباركود

هل تساءلت يومًا **كيف تقرأ باركود PDF417** في تطبيق C# دون أن تفقد أعصابك؟ أنت لست الوحيد. سواء كنت تبني ماسحًا لوجستيًا، أو جهاز تحقق من التذاكر، أو فقط تحتاج إلى استخراج البيانات من هوية مشفرة بـ PDF417، قد يبدو العملية غامضة في البداية.  

في هذا البرنامج التعليمي سنستعرض **مثال باركود c#** يقرأ صورة PDF417، ويتعامل مع **قراءة عدة باركودات** إذا كانت موجودة، ويستخرج جميع بيانات ماكرو PDF417 المفيدة التي قد تحتاجها.

## ما ستبنيه

بنهاية هذا الدليل ستحصل على برنامج صغير في سطر الأوامر يقوم بـ:

1. تحميل صورة الباركود من القرص.  
2. فك تشفير باركود **PDF417** (بما في ذلك Macro PDF417).  
3. طباعة معلومات أساسية مثل نوع الكود والنص.  
4. إخراج مجموعة كاملة من حقول Macro PDF417 (معرف الملف، معرف الجزء، المجموع الاختباري، إلخ).  

بدون خدمات خارجية، فقط حزمة NuGet واحدة وعدة أسطر من C#.

## المتطلبات المسبقة – ما تحتاجه قبل البدء

- **.NET 6.0** أو أحدث (الكود يعمل أيضًا على .NET Framework 4.6+).  
- إصدار حديث من مكتبة **Aspose.BarCode for .NET** – قم بتثبيتها عبر NuGet (`Install-Package Aspose.BarCode`).  
- ملف صورة يحتوي على باركود PDF417 (يستخدم العرض التجريبي `ExtPDF417Meta.png`).  
- فهم أساسي لتطبيقات سطر الأوامر C# (إذا كتبت “Hello World”، فأنت جاهز).

> **نصيحة احترافية:** إذا لم يكن لديك عينة PDF417 جاهزة، قم بإنشاء واحدة على موقع Aspose التجريبي أو استخدم تطبيق هاتف ذكي يمكنه إنشاء علامات PDF417.

## الخطوة 1: إعداد المشروع وتثبيت المكتبة

أولاً، أنشئ مشروع سطر أوامر جديد:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

هذا يجلب تبعيات **مثال باركود c#** التي نحتاجها. افتح `Program.cs` واستبدل الكود الافتراضي بالهيكل أدناه:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## الخطوة 2: تهيئة قارئ الباركود لـ PDF417

جوهر الحل هو الفئة `BarCodeReader`. نخبرها أي ملف يجب مسحه وأي نوع باركود نهتم به—في هذه الحالة `DecodeType.Pdf417` أو النوع الماكرو `DecodeType.MacroPdf417`. استخدام نوع الماكرو يضمن التقاط الحقول الموسعة.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

لماذا نستخدم `MacroPdf417` بدلاً من `Pdf417` العادي؟ يحمل Macro PDF417 بيانات وصفية إضافية (معرف الملف، عدد الأجزاء، الطوابع الزمنية، إلخ) التي تعتمد عليها العديد من التطبيقات الواقعية—مثل قوائم الشحن المقسمة على عدة صفحات.

## الخطوة 3: قراءة جميع الباركودات الموجودة في الصورة

يمكن أن تحتوي صورة واحدة على **قراءة عدة باركودات**—ربما رمز QR بجانب PDF417. تُعيد طريقة `ReadBarCodes()` كائن `IEnumerable<BarCodeResult>` يمكننا التكرار عليه.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

إذا احتوت الصورة على PDF417 واحد فقط، فإن الحلقة لا تزال تُنفّذ مرة واحدة، مما يبقي الكود مرنًا للسيناريوهات المستقبلية حيث قد تحتاج إلى **قراءة عدة باركودات** من نفس الفحص.

## الخطوة 4: عرض معلومات الباركود الأساسية

قبل الغوص في حقول الماكرو، من المفيد إظهار نوع الباركود والنص المفكك. هذا يساعدك على التحقق من أن القارئ تعرف فعليًا على PDF417 وليس على رموز أخرى.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` سيظهر *MacroPdf417* (أو *Pdf417* إذا لم يتم تعيين علم الماكرو)، بينما `CodeText` يحتوي على البيانات الخام المشفرة في الباركود.

## الخطوة 5: استخراج بيانات ماكرو PDF417 الوصفية

خاصية `Extended` تمنحك نظرة عميقة على بنية PDF417 الخاصة. كل حقل نطبعه أدناه يتطابق مباشرة مع مواصفات ماكرو PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

كل سطر يستخرج جزءًا مختلفًا من حمولة الماكرو:

- **FileID** – معرف فريد لمجموعة المستندات بالكامل.  
- **SegmentID** – أي جزء من الملف متعدد الأجزاء الذي تنظر إليه.  
- **SegmentsCount** – العدد الكلي للأجزاء المتوقعة.  
- **FileName, Checksum, FileSize** – مفيدة للتحقق من سلامة الملف المنقول.  
- **TimeStamp, Addressee, Sender** – حقول اختيارية يدمجها العديد من أنظمة اللوجستيات.  

إذا كان أي من هذه الحقول مفقودًا في الباركود المصدر، تُعيد المكتبة `null` أو `0`، ويمكنك التعامل معها حسب الحاجة.

## الخطوة 6: تشغيل المثال الكامل

بجمع كل ذلك معًا، إليك البرنامج الكامل الجاهز للتنفيذ:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### النتيجة المتوقعة

عند تشغيل البرنامج على صورة `ExtPDF417Meta.png` صالحة، يجب أن ترى شيئًا مشابهًا لـ:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

إذا احتوت الصورة على أكثر من باركود،

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شاملة من الكود مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركودات PDF417 – ترميز PDF417 المدمج](/barcode/english/net/compact-pdf417-encoding/)
- [كيفية إنشاء باركود – PDF417 المدمج باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [كيفية قراءة باركودات DataMatrix باستخدام Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}