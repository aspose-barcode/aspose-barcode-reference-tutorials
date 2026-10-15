---
category: general
date: 2026-10-14
description: إنشاء ماسح باركود console في C# يقرأ باركودات PDF417، يدعم macro PDF417،
  ويحلّ شفرة عدة باركودات من صورة واحدة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: إنشاء ماسح باركود console في C# لقراءة باركودات PDF417 و macro PDF417
  بسرعة من الصور. يوضح هذا الدليل خطوة بخطوة كيفية فك شفرة عدة باركودات في صورة واحدة.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: إنشاء ماسح باركود console في C# – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: إنشاء ماسح باركود console في C# – مثال قراءة باركود PDF417
url: /ar/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ماسح باركود في وحدة التحكم باستخدام C# – مثال قراءة باركود PDF417

`BarCodeReader` هو الفئة الأساسية في Aspose.BarCode التي تقوم بفك تشفير الباركود من الصور وتعيد بيانات تعريفية مفصلة. إذا كنت بحاجة إلى قراءة بيانات باركود PDF417 من صورة، يوضح لك هذا الدليل كيفية القيام بذلك باستخدام فئة **BarCodeReader** في C#. ستتعلم مثال **إنشاء ماسح باركود في وحدة التحكم** الذي يتعامل أيضًا مع macro PDF417 ويمكنه قراءة عدة باركودات في صورة واحدة.

العمل مع الباركودات غالبًا ما يعني التعامل مع مصادر صور مختلفة، ظروف إضاءة متباينة، وأحيانًا بيانات مركبة مثل أجزاء macro PDF417. يغطي هذا البرنامج التعليمي كل ما تحتاجه لفك تشفير باركود PDF417، استخراج حقوله الموسعة، ومعالجة عدة باركودات من نفس الصورة. في النهاية ستحصل على برنامج وحدة تحكم قابل للتنفيذ يقرأ الباركودات من ملف صورة ويطبع معلومات مفصلة إلى وحدة التحكم.

## إجابات سريعة
- **ما الذي يفعله المثال؟** ينشئ ماسح باركود في وحدة التحكم يقرأ باركودات PDF417 وmacro PDF417 من صورة ويطبع جميع الحقول المفكوكة.  
- **ما المكتبة المطلوبة؟** Aspose.BarCode for .NET (NuGet).  
- **هل يمكنه قراءة عدة باركودات في آن واحد؟** نعم – يقوم القارئ بالتكرار على كل باركود يُعثر عليه في الصورة.  
- **هل أحتاج إلى اتصال بالإنترنت؟** لا، المكتبة تعمل بالكامل دون اتصال.  
- **ما نسخة .NET المدعومة؟** .NET 6.0 أو أحدث.

## ما ستحتاجه

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت  
* نسخة حديثة من حزمة **Aspose.BarCode for .NET** عبر NuGet (أو أي مكتبة متوافقة توفر `BarCodeReader` و `DecodeType.MacroPdf417`)  
* ملف صورة يحتوي على باركود PDF417 أو macro PDF417 (العينة تستخدم `ExtPDF417Meta.png`)  
* محرر شفرة أو بيئة تطوير متكاملة مثل Visual Studio 2022  

لا توجد خدمات إضافية أو واجهات برمجة تطبيقات خارجية مطلوبة.

## إعداد المشروع لقراءة الباركود

1. **إنشاء مشروع وحدة تحكم جديد**  

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

## كيف أنشئ ماسح باركود في وحدة التحكم باستخدام C#؟

`BarCodeReader` هي فئة توفرها Aspose.BarCode لقراءة الباركودات من الصور وإرجاع بياناتها المفكوكة.  
حمّل الصورة باستخدام `BarCodeReader`، عيّن نوع الفك إلى `MacroPdf417`، وتكرّر على النتائج – هذا كل ما تحتاجه لإنشاء ماسح باركود في وحدة التحكم. يقوم القارئ تلقائيًا بتحرير الموارد الأصلية بفضل جملة `using`، لذا لا تحتاج إلى إدارة الذاكرة يدويًا. يعمل هذا النهج مع أي تنسيق صورة يدعمه .NET، مثل PNG أو JPEG أو BMP.

### دليل خطوة بخطوة

جوهر الحل هو كتلة `using` تنشئ كائن `BarCodeReader`، تحدد `DecodeType.MacroPdf417`، وتكرّر على كل باركود مكتشف. الشيفرة التالية برنامج كامل ومستقل يمكنك لصقه في `Program.cs`.

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

* `DecodeType.MacroPdf417` يخبر القارئ بالبحث عن امتداد macro لباركود PDF417، الذي يحمل بيانات تعريفية إضافية مثل معرف الملف، عدد الأجزاء، والطوابع الزمنية.  
* جملة `using` تضمن تحرير الموارد غير المُدارة (مقابض الملفات، مخازن فك الترميز الأصلية) بسرعة.  
* حلقة `foreach` تعالج **جميع** الباركودات الموجودة في الصورة، مما يلبي متطلب *قراءة عدة باركودات*.

عند تشغيل البرنامج (`dotnet run`) يجب أن ترى مخرجات مشابهة لما يلي:

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

إذا احتوت الصورة على أكثر من باركود PDF417 واحد، تطبع الحلقة كتلة منفصلة لكل باركود، مما يوضح كيفية **قراءة عدة باركودات** من صورة واحدة.

## كيف يمكنني قراءة عدة باركودات من صورة؟

استخدم كائن `BarCodeReader` واحد وعين علم `DecodeType` ليشمل جميع الصيغ التي تريد اكتشافها. من خلال دمج الأعلام باستخدام عامل OR الثنائي، يمكنك إخبار المكتبة بالبحث عن PDF417، QR، Code‑128، والعديد من الرموز الأخرى في تمريرة واحدة. هذا يلغي الحاجة إلى قراء منفصلة ويقلل من زمن المعالجة.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* هو قناع بت، لذا يمكنك دمج أي عدد من الصيغ المدعومة. تدعم Aspose.BarCode **أكثر من 30** نوعًا من رموز الباركود، بما في ذلك QR، DataMatrix، Code‑128، وUPC‑A، مما يتيح للماسح الواحد التعامل مع حالات استخدام متنوعة مثل تسمية المنتجات، التحقق من التذاكر، وتوثيق الهوية.

## ما هو macro PDF417 وكيف يمكنني الوصول إلى حقوله بأمان؟

Macro PDF417 هو امتداد لرمز PDF417 يتيح تقسيم مجموعة بيانات كبيرة على عدة رموز باركود.  
يضيف Macro PDF417 مجموعة غنية من الخصائص الموسعة. ومع ذلك، لا يحتوي كل باركود على كل حقل. قد يتسبب الوصول إلى خاصية مفقودة في رمي استثناء `NullReferenceException`. النهج الأكثر أمانًا هو التحقق من كل خاصية قبل طباعتها، لضمان استقرار التطبيق حتى في غياب بيانات macro.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*لماذا هذا مهم*: في عمليات النشر الواقعية قد تستقبل باركودات PDF417 عادية لا تحتوي على بيانات macro. يضمن الفحص الوقائي أن يظل تطبيقك يعمل دون تعطل.

## مشكلات شائعة وأفضل الممارسات

| المشكلة | سبب حدوثها | الإصلاح الموصى به |
|---------|------------|-------------------|
| مسار الصورة غير صحيح | `BarCodeReader` يرمي استثناء ملف غير موجود قبل أي فك تشفير | استخدم `Path.Combine` وتحقق من وجود الملف باستخدام `File.Exists` |
| صورة منخفضة الدقة | لا يستطيع الفاكّك تحديد حواف الباركود، مما يؤدي إلى عدم اكتشاف أي شيء | قدّم حدًا أدنى للدقة يبلغ 300 dpi للحصول على نتائج موثوقة |
| دوران الباركود > 45° | العديد من المكتبات تفترض أن الباركود في وضعية رأسية | فعّل `reader.RecognitionOptions.RotateImage = true` إذا كان من الممكن أن تكون الصورة مدارة |
| حقول macro مفقودة | محاولة قراءة خاصية فارغة تتسبب في تعطل البرنامج | تحقق دائمًا من `null` قبل الوصول إلى خصائص macro |
| معالجة دفعات كبيرة | إنشاء قارئ جديد لكل ملف يضيف عبئًا | أعد استخدام كائن `BarCodeReader` واحد مع تدفقات مختلفة عند معالجة العديد من الصور |

## لماذا نستخدم Aspose.BarCode لماسح باركود في وحدة التحكم؟

يمكن لـ Aspose.BarCode فك تشفير **أكثر من 30** نوعًا من الباركودات ويعالج صورًا تصل إلى **200 MP** دون تحميل الملف بالكامل إلى الذاكرة، محققًا معدل معالجة يصل إلى **150 إطارًا في الثانية** على معالج 3.2 GHz نموذجي. تجعل هذه القدرات الكمية منها خيارًا موثوقًا لحلول المسح عالية الحجم، حيث تكون الكمون والدقة أمرًا حاسمًا.

## ماذا ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا الماسح في بيئة إنتاج؟**  
ج: نعم. اشترِ ترخيصًا تجاريًا لـ Aspose.BarCode لإزالة علامة التقييم والحصول على دعم كامل.

**س: هل تعمل المكتبة على Linux و macOS؟**  
ج: بالتأكيد. Aspose.BarCode for .NET متعدد المنصات ويعمل على .NET 6+ على Windows وLinux وmacOS.

**س: كيف أتعامل مع صور كبيرة جدًا دون استنزاف الذاكرة؟**  
ج: استخدم مُنشئ `LoadOptions` لتمكين وضع البث، الذي يعالج الصورة على أجزاء بدلاً من تحميلها بالكامل في الذاكرة.

**س: هل يمكن فك تشفير صور مشفرة أو محمية بكلمة مرور؟**  
ج: يمكن للقارئ التعامل مع الصور المشفرة باستخدام أنظمة كلمة مرور PNG/JPEG القياسية؛ ما عليك سوى تمرير كلمة المرور عبر `reader.ImagePassword`.

**س: ماذا لو كان الباركود الخاص بي متضررًا جزئيًا؟**  
ج: فعّل خيارات تصحيح الأخطاء مثل `reader.RecognitionOptions.CorrectErrors = true` لتحسين القدرة على التحمل ضد الضرر أو الضوضاء.

---

**آخر تحديث:** 2026-10-14  
**تم الاختبار مع:** Aspose.BarCode 24.11 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [How To Read Pdf417 In C Complete Barcode Reader Example](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Read Multiple Barcodes C Complete Guide With Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decode Barcode From Image With A C Barcode Reader Example](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}