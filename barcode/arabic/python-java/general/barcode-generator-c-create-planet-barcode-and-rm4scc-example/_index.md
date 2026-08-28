---
category: general
date: 2026-08-03
description: دروس توليد الباركود بلغة C# توضح كيفية إنشاء باركود Planet باستخدام Aspose.BarCode،
  وتعيين البُعد X، وحفظه كصور PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: ar
lastmod: 2026-08-03
og_description: يُرشدك دليل توليد الباركود بلغة C# إلى إنشاء باركود Planet، وضبط البُعد
  X، وحفظه كملف PNG باستخدام Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: مولد الباركود C# – إنشاء باركود Planet خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: مولد الباركود C# – إنشاء مثال لباركود Planet وRM4SCC
url: /ar/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# مولد الباركود C# – إنشاء مثال لباركود Planet و RM4SCC

إذا كنت بحاجة إلى **barcode generator C#** يمكنه إنتاج رموز بريدية محددة، يوضح لك هذا الدليل بالضبط كيفية **إنشاء صور باركود Planet** باستخدام Aspose.BarCode. ستتعرف على كيفية ضبط البُعد X، وإنشاء باركود RM4SCC مطابق، وحفظ كليهما كملفات PNG—كل ذلك في بضع خطوات مختصرة.

يغطي الدليل كل ما تحتاجه لتشغيل الكود على .NET 6 أو أحدث، يشرح لماذا كل إعداد مهم، ويشير إلى الأخطاء الشائعة مثل عرض الوحدة غير الصحيح أو نقص أذونات المجلد. في النهاية ستحصل على صورتين جاهزتين للطباعة تتوافقان مع معايير Planet و RM4SCC.

## المتطلبات المسبقة

* .NET 6 SDK (أو أي نسخة .NET يدعمها Aspose.BarCode)
* Visual Studio 2022 أو أي بيئة تطوير C# تفضلها
* مرجع NuGet إلى **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* إذن كتابة للمجلد الذي تخطط لتخزين ملفات PNG فيه

لا توجد خدمات خارجية إضافية مطلوبة؛ المكتبة تتعامل مع جميع عمليات الترميز محليًا.

## الخطوة 1: تهيئة كائن barcode generator C# 

المهمة الأولى هي إنشاء نسخة من `BarcodeGenerator`. يأخذ المُنشئ نوع الباركود (`EncodeTypes.Planet`) والبيانات التي تريد ترميزها.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*لماذا هذه الخطوة؟*  
`BarcodeGenerator` هو نقطة الدخول لكل باركود تقوم بإنشائه. اختيار `EncodeTypes.Planet` يخبر المكتبة باتباع مواصفة ISO/IEC 24723 المستخدمة من قبل العديد من خدمات البريد.

## الخطوة 2: ضبط البُعد X (عرض الوحدة) لباركود Planet

يحدد البُعد X عرض وحدة الباركود الواحدة (أصغر شريط أو فراغ). قيمة **4 بكسل** تعمل جيدًا لمعظم طابعات الملصقات.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*لماذا هذا مهم*  
إذا كانت الوحدة ضيقة جدًا، قد يصبح الباركود غير قابل للقراءة؛ وإذا كانت عريضة جدًا سيزداد حجم الملصق دون ضرورة. ضبط `Pixels` يتيح لك تحسين الباركود لدرجة دقة طابعتك المحددة.

## الخطوة 3: حفظ باركود Planet كصورة PNG

يقوم Aspose.BarCode بحساب ارتفاع الباركود تلقائيًا بناءً على نوع الرمز المحدد، لذا تحتاج فقط إلى تحديد مسار الملف والصيغة.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*نصيحة*  
استبدل `YOUR_DIRECTORY` بمسار مطلق أو نسبي موجود على جهازك. إذا لم يكن المجلد موجودًا، فإن طريقة `Save` ستطرح استثناء `DirectoryNotFoundException`.

**الناتج المتوقع** – ملف PNG يشبه الشكل الموضح أدناه (الصورة الفعلية غير معروضة هنا، لكنك سترى باركود Planet كلاسيكي مع حمولة رقمية `123456`).

## الخطوة 4: تهيئة مولد ثانٍ لباركود RM4SCC

تتطلب العديد من أنظمة البريد وجود رمزي Planet و RM4SCC على نفس القطعة البريدية. أنشئ نسخة جديدة من `BarcodeGenerator` لنوع الرمز RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*لماذا نسخة منفصلة؟*  
كل نوع رمز له مجموعة إعدادات خاصة به. إعادة استخدام نفس المولد قد يؤدي إلى نقل إعدادات (مثل البُعد X) غير المثالية للباركود الثاني.

## الخطوة 5: ضبط البُعد X لباركود RM4SCC

RM4SCC يحترم أيضًا إعداد البُعد X، لذا نطبق نفس عرض البكسل لضمان التناسق البصري.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*نصيحة احترافية*  
إذا كنت بحاجة إلى باركود أطول (مثلاً للملصقات الكبيرة)، يمكنك أيضًا ضبط `Height.Pixels`. تركه غير محدد يتيح للمكتبة حساب الارتفاع المثالي تلقائيًا.

## الخطوة 6: حفظ باركود RM4SCC كصورة PNG

أخيرًا، احفظ باركود RM4SCC على القرص.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

الآن لديك ملفا PNG—`PostalPlanetBarHeightNone.png` و `PostalRM4SCCBarHeightNone.png`—يمكنك تضمينهما في ملصقات البريد، طباعتهما على الأظرف، أو إرسالهما إلى خدمة طباعة طرف ثالث.

## اختياري: تعديل الارتفاع أو استخدام صيغ صور أخرى

إذا كان سير عملك يتطلب ارتفاعًا محددًا للباركود أو صيغة صورة مختلفة (مثل JPEG أو BMP)، يمكنك تعديل المعلمات قبل استدعاء `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**حالة حدية** – عند ضبط ارتفاع مخصص، تأكد من أن القيمة تحترم الحد الأدنى للارتفاع المطلوب وفقًا للمعيار ISO؛ وإلا قد يفشل الباركود في التحقق.

## المشكلات الشائعة وكيفية تجنّبها

| المشكلة | لماذا يحدث | الحل |
|---------|------------|------|
| `DirectoryNotFoundException` | المجلد الهدف غير موجود أو تم كتابة اسمه بشكل خاطئ. | أنشئ المجلد أولاً أو استخدم `Path.Combine` مع `Environment.CurrentDirectory`. |
| عدم قراءة الباركود على طابعات منخفضة الدقة | البُعد X صغير جدًا بالنسبة لدقة DPI للطابعة. | زد `XDimension.Pixels` إلى 5 – 6 لطابعات 203 dpi، أو اختبر على ملصق تجريبي. |
| استخدام نوع رمز خاطئ | تمرير `EncodeTypes.Code128` بدلاً من `EncodeTypes.Planet`. | تحقق من أن قيمة enum `EncodeTypes` تتطابق مع المعيار البريدي المطلوب. |
| مرجع فارغ على `Parameters` | استخدام نسخة أقدم من Aspose.BarCode حيث تختلف الواجهة البرمجية. | حدّث إلى أحدث حزمة NuGet (v23.12 أو أحدث). |

## مثال كامل قابل للتنفيذ

فيما يلي البرنامج الكامل الذي يمكنك نسخه ولصقه وتشغيله. يتضمن عبارات `using`، معالجة الأخطاء، وتعليقات تشرح كل سطر.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

تشغيل البرنامج ينشئ مجلد `Barcodes` بجوار الملف التنفيذي ويضع ملفي PNG داخلها. افتحهما بأي عارض صور للتحقق من النتيجة.

## الخلاصة

أصبح لديك الآن حل **barcode generator C#** يمكنه **إنشاء صور باركود Planet**، ضبط البُعد X للطباعة المثالية، وإنتاج باركود RM4SCC مطابق—كل ذلك بضع أسطر من الشيفرة. النهج يعمل مع .NET 6+، يتطلب حزمة NuGet Aspose.BarCode فقط، ويمكن توسيعه إلى رموز أخرى مثل Code128، QR، أو DataMatrix بتغيير قيمة `EncodeTypes`.

### ما التالي؟

* جرّب قيمًا مختلفة لـ `XDimension.Pixels` لتتناسب مع DPI طابعتك.  
* أنشئ باركود بصيغ أخرى (PDF، SVG) بتغيير enum `BarCodeImageFormat`.  
* دمج ملفي PNG في ملصق واحد باستخدام مكتبة رسومية مثل **SkiaSharp**.  
* استكشف كامل API الخاص بـ Aspose.BarCode للميزات المتقدمة مثل التحقق من checksum أو الخطوط المخصصة.

لا تتردد في تعديل الشيفرة للمعالجة الدفعية أو دمجها في خدمة ويب ASP.NET Core تُعيد صور الباركود عند الطلب. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [كيفية حفظ PNG باستخدام DataMatrix C40 مع Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [دروس مولد الباركود C# – تخصيص نسب أبعاد Code 16K Barcode مع Aspose.BarCode لـ .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}