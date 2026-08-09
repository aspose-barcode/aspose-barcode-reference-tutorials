---
category: general
date: 2026-08-09
description: إنشاء رمز شريطي PDF417 في C# بسرعة. تعلّم كيفية إنشاء PDF417 باستخدام
  الوضع المدمج، التحكم في الأعمدة، وإخراج PNG باستخدام واجهة برمجة التطبيقات BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: ar
lastmod: 2026-08-09
og_description: إنشاء رمز شريطي PDF417 في C# مع مثال مختصر. يوضح لك هذا الدليل كيفية
  تكوين وضع الضغط، ضبط الأعمدة، وحفظ النتيجة كصورة PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: إنشاء رمز شريطي PDF417 في C# – دليل كامل
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: إنشاء باركود PDF417 في C# – دليل خطوة بخطوة
url: /ar/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود PDF417 في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء باركود PDF417** في تطبيق .NET، فإن هذا الدليل يوضح لك بالضبط كيفية القيام بذلك. سترى برنامجًا كاملاً قابلاً للتنفيذ يُنشئ باركود PDF417 مضغوط، يخصص حجمه، ويحفظ الصورة كملف PNG.

إنشاء باركود PDF417 هو طلب شائع لتذاكر الهواتف المحمولة، تتبع المخزون، وأمان المستندات. يغطي هذا الدليل خيارات التكوين الأساسية، يشرح لماذا كل إعداد مهم، ويقدم نصائح عملية للاستخدام في العالم الحقيقي.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 SDK أو أحدث مثبت  
* بيئة تطوير C# مثل Visual Studio 2022 أو Visual Studio Code  
* حزمة NuGet **Aspose.BarCode for .NET** (الإصدار 23.10 أو أحدث)  

يمكنك تثبيت الحزمة باستخدام أمر سطر الأوامر التالي:

```bash
dotnet add package Aspose.BarCode
```

يفترض الكود أدناه أن الحزمة مُشار إليها وأن لديك صلاحية كتابة إلى دليل الإخراج.

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ مشروع وحدة تحكم جديد وأضف توجيهات `using` المطلوبة. تُظهر هذه المساحات الاسمية فئة `BarcodeGenerator` وتعداد صيغ الصورة.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**لماذا هذا مهم:** استيراد المساحات الاسمية الصحيحة يضمن أن المترجم يستطيع العثور على النوع `BarcodeGenerator` وتعداد `BarCodeImageFormat`. عدم وجود مساحة اسمية يؤدي إلى خطأ تجميع، مما يوقف عملية إنشاء الباركود.

## الخطوة 2: تهيئة `BarcodeGenerator` بترميز PDF417

يتلقى مُنشئ `BarcodeGenerator` معاملين: نوع الباركود (`EncodeTypes.Pdf417`) والنص الذي تريد ترميزه. يدعم PDF417 مجموعة واسعة من الأحرف، بما في ذلك رموز Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**شرح:**  
* `EncodeTypes.Pdf417` يخبر المكتبة باستخدام معيار PDF417.  
* نص العينة يحتوي على أحرف مُعَلمة ورمز حقوق النشر لتوضيح معالجة Unicode.  

إذا كنت بحاجة إلى ترميز بيانات رقمية فقط، يمكنك تمرير سلسلة بسيطة مثل `"1234567890"`.

## الخطوة 3: ضبط البُعد X للحصول على دقة أعلى

يتحكم البُعد X في عرض وحدة الباركود الفردية (أصغر عنصر أسود أو أبيض). ضبط قيمة بكسل أصغر ينتج صورة ذات دقة أعلى.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**لماذا يتم ضبطه؟** قد ينتج بُعد X الافتراضي 3–4 بكسل باركودًا يبدو خشنًا على الشاشات ذات الكثافة العالية DPI. تقليلها إلى **2 بكسل** يوازن بين قابلية القراءة وحجم الملف، خاصةً عندما تقوم بتمكين وضع الضغط لاحقًا.

## الخطوة 4: تكوين عدد الأعمدة

يسمح PDF417 لك بتحديد عدد الأعمدة التي يجب أن يحتويها الباركود. عدد أقل من الأعمدة يجعل الباركود أضيق لكن أطول، بينما عدد أكبر ينتج باركودًا أعرض وأقصر.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**نصيحة عملية:** لتذاكر الهواتف المحمولة التي تحتاج إلى أن تتناسب مع ملصق ضيق، يعمل عدد الأعمدة **3–5** بشكل جيد. زد العدد إذا كان لديك الكثير من البيانات وتريد باركودًا أقصر.

## الخطوة 5: تمكين وضع الضغط لقص الصفوف الفارغة

يزيل وضع الضغط الصفوف غير الضرورية من مصفوفة الباركود، مما يقلل من حجم الصورة الإجمالي دون فقدان البيانات المشفرة.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**متى تستخدمه:** إذا كنت تنشئ باركودات للتخزين أو النقل عبر الشبكة، يمكن لوضع الضغط تقليل ملف PNG بنسبة تصل إلى 30 %. ومع ذلك، قد لا تدعم بعض القارئات القديمة PDF417 المقصوص؛ اختبر ذلك مع الأجهزة المستهدفة.

## الخطوة 6: حفظ الباركود كصورة PNG

اختر مسار الإخراج واستدعِ `Save`. ينتج تعداد `BarCodeImageFormat.Png` صورة غير مضغوطة مناسبة لمعظم التطبيقات.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**التحقق من النتيجة:** افتح ملف PNG في أي عارض صور. يجب أن ترى باركودًا كثيفًا وعالي التباين يطابق نص العينة. مسح الصورة باستخدام قارئ PDF417 (مثل ZXing أو تطبيق هاتف ذكي) يعيد السلسلة الأصلية `"Åspóse.Barcóde©"`.

![صورة باركود PDF417 تم إنشاؤها وحفظها كملف PNG](compact-pdf417.png "باركود PDF417 تم إنشاؤه في C#")

*الصورة أعلاه توضح النتيجة النهائية لكود الدليل.*

## مثال كامل قابل للتنفيذ

بجمع كل الأجزاء معًا، إليك برنامج وحدة تحكم كامل يمكنك نسخه، لصقه، وتشغيله.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### النتيجة المتوقعة

تشغيل البرنامج يطبع:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

الملف `CompactPdf417.png` يحتوي على باركود PDF417 مضغوط يرمز إلى سلسلة Unicode المقدمة. مسح الصورة باستخدام قارئ PDF417 قياسي يعيد النص الدقيق.

## تنوعات شائعة وحالات حافة

| الحالة | التعديل | السبب |
|-----------|------------|--------|
| **حجم بيانات أطول** (مثال، > 150 حرف) | زيادة `generator.Parameters.Barcode.Pdf417.Columns` إلى 6‑8 | المزيد من الأعمدة يمنع الباركود من أن يصبح طويلًا جدًا. |
| **الحاجة إلى خلفية شفافة** | استخدام `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG الشفاف يندمج بشكل أفضل مع طبقات واجهة المستخدم. |
| **إنشاء JPEG للويب** | تغيير الصيغة إلى `BarCodeImageFormat.Jpeg` واختيارياً ضبط `ImageQuality` | JPEG يقلل حجم الملف على حساب فقدان الدقة غير الضائعة. |
| **معالجة إدخال فارغ أو null** | حماية الإدخال قبل إنشاء المولد: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | يمنع استثناءات وقت التشغيل ويضمن باركودات ذات معنى. |

## نصائح للاستخدام في بيئة الإنتاج

* **معالجة الاستثناءات:** غلف منطق الإنشاء داخل كتلة `try/catch` لتسجيل الأخطاء مثل نقص مساحة القرص أو المعاملات غير الصالحة.  
* **الأداء:** أعد استخدام كائن `BarcodeGenerator` واحد عند إنشاء العديد من الباركودات بنفس الإعدادات؛ فقط قم بتحديث خاصية `CodeText` بين عمليات الحفظ.  
* **الأمان:** عندما يحتوي النص المشفر على معلومات حساسة، فكر في تشفيره قبل تمريره إلى المولد وفك تشفيره بعد المسح.  

## الخلاصة

أنت الآن تعرف كيف **تنشئ باركود PDF417** في C# باستخدام مكتبة Aspose.BarCode، وتضبط وضع الضغط، وتتحكم في عدد الأعمدة، وتصدّر النتيجة كصورة PNG. غطى هذا الدليل كل خطوة من إعداد المشروع إلى التعامل مع الحالات الخاصة، مقدمًا لك حلًا جاهزًا للاستخدام في تطبيقات تعتمد على الباركود.

بعد ذلك، استكشف المواضيع ذات الصلة مثل **إنشاء رموز QR في C#**، **إنشاء باركودات دفعةً**, و**دمج مسح الباركود مع التطبيقات المحمولة**. كل منها يبني على أساسيات `BarcodeGenerator` التي تعلمتها الآن.

برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود PDF417 – ترميز PDF417 مضغوط](/barcode/english/net/compact-pdf417-encoding/)
- [كيفية إنشاء باركود – PDF417 مضغوط باستخدام Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [كيفية إنشاء باركود Aztec بنسبة أبعاد مخصصة باستخدام Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}