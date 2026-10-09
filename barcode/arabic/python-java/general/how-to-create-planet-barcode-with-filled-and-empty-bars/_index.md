---
category: general
date: 2026-09-29
description: إنشاء باركود كوكب في C# مع الأشرطة المملوءة والفارغة – دليل خطوة بخطوة
  باستخدام Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: ar
lastmod: 2026-09-29
og_description: إنشاء باركود كوكب في C# بسرعة. تعلم كيفية عرض الأعمدة المملوءة، التحويل
  إلى الأعمدة الفارغة، وضبط البُعد X باستخدام Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: إنشاء باركود كوكب بأشرطة مملوءة وفارغة – دليل C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: كيفية إنشاء باركود كوكبي بأشرطة مملوءة وفارغة
url: /ar/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود كوكب مع أشرطة مملوءة وفارغة

إذا كنت بحاجة إلى **إنشاء باركود كوكب** بصور في C#، يوضح لك هذا الدليل بالضبط كيفية إنشاء كل من الإصدارات ذات الأشرطة المملوءة والفارغة. سترى كيفية ضبط عرض الشريط (X‑dimension)، وتبديل خاصية `FilledBars`، وحفظ النتائج كملفات PNG—كل ذلك باستخدام مكتبة Aspose.Barcode.

إنشاء باركودات بريدية هو طلب شائع لأنظمة الشحن، وتطبيقات قوائم البريد، ولوحات التحكم اللوجستية. بنهاية هذا الدرس ستحصل على ملفي PNG جاهزين للاستخدام يمكنك تضمينهما في التقارير، أو رسائل البريد الإلكتروني، أو المطبوعات.

## المتطلبات المسبقة

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 أو أحدث | يوفر بيئة التشغيل لمثال C#. |
| Visual Studio 2022 (أو أي بيئة تطوير C#) | يسمح لك بتجميع وتشغيل الكود. |
| **Aspose.Barcode for .NET** NuGet package | يوفر الفئة `BarcodeGenerator` و `EncodeTypes.Planet`. قم بتثبيته باستخدام `dotnet add package Aspose.Barcode`. |
| إذن كتابة إلى مجلد على القرص | طريقة `Save` تكتب ملفات PNG إلى المسار الذي تحدده. |

## الخطوة 1: إعداد المشروع واستيراد المساحات الاسمية

أنشئ مشروع وحدة تحكم جديد (أو أضف الكود إلى مشروع موجود) وأشر إلى مساحة الأسماء Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

تمنحك توجيهات `using` هذه إمكانية الوصول إلى الفئات `BarcodeGenerator` و `EncodeTypes` وتعدادات تنسيقات الصور المطلوبة في هذا الدرس.

## الخطوة 2: إنشاء باركود كوكب مع أشرطة مملوءة افتراضية

يستخدم الباركود الأول طريقة العرض الافتراضية للمكتبة، والتي تملأ الأشرطة.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**لماذا يعمل هذا:**  
`EncodeTypes.Planet` يخبر Aspose.Barcode باستخدام ترميز **Planet**، وهو باركود بريدي تستخدمه خدمة البريد الأمريكية (USPS). خاصية `XDimension` تتحكم في عرض كل شريط؛ ضبطها على 4 بيكسل ينتج باركودًا يطبع بشكل جيد على طابعات الملصقات القياسية. بشكل افتراضي، تكون `FilledBars` مساوية لـ `true`، لذا تظهر الأشرطة صلبة.

## الخطوة 3: إنشاء باركود كوكب بأشرطة فارغة

لإنشاء نفس البيانات بأشرطة *فارغة*، كل ما عليك هو عكس علامة `FilledBars` مع الحفاظ على باقي الإعدادات كما هي.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**لماذا هذا مهم:**  
تتطلب بعض أنظمة البريد نمط **الأشرطة الفارغة** لتحسين قابلية القراءة عندما يُطبع الباركود على خلفيات داكنة أو عند استخدام نظام ألوان متباين. بتعيين `FilledBars = false`، يرسم المولد فقط حدود الأشرطة، ويترك الداخل شفافًا.

## الناتج المتوقع

بعد تشغيل البرنامج، يحتوي المجلد `C:\Barcodes` (أو المسار الذي اخترته) على ملفي PNG:

| File | Visual description |
|------|---------------------|
| `PlanetFilledBars.png` | الأشرطة عبارة عن مستطيلات سوداء صلبة على خلفية بيضاء. |
| `PlanetEmptyBars.png`  | الأشرطة هي حدود سوداء؛ داخل كل شريط شفاف (يظهر الخلفية). |

كلتا الصورتان تشفران نفس السلسلة الرقمية `"123456"` وتستخدمان عرض شريط 4 بيكسل، مما يضمن مظهرًا متسقًا باستثناء نمط التعبئة.

## التحويرات الشائعة وحالات الحافة

### تغيير عرض الشريط

إذا كان طابعتك تتطلب عرض شريط مختلف، عدّل قيمة `XDimension.Pixels`. للطابعات عالية الدقة، قد يكون القيمة **2** أو **3** بيكسل مفضلة؛ للطابعات منخفضة الدقة، قد تحسن القيم **5** أو **6** بيكسل من موثوقية المسح.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### استخدام تنسيق صورة مختلف

يدعم Aspose.Barcode تنسيقات PNG و JPEG و BMP و GIF و TIFF. استبدل `BarCodeImageFormat.Png` بقيمة تعداد أخرى لتتناسب مع سير عملك اللاحق.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### إنشاء عدة باركودات في حلقة

عند الحاجة إلى مجموعة من باركودات Planet (مثلاً لقائمة بريدية)، ضع منطق المولد داخل حلقة `foreach` وغيّر سلسلة البيانات في كل تكرار.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### معالجة الإدخال غير الصالح

ترميز Planet يقبل فقط سلاسل رقمية مكونة من **5‑8** أرقام. توفير قيمة غير صالحة يسبب استثناء `ArgumentException`. احمِ نفسك باستخدام طريقة تحقق بسيطة.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## نصحة احترافية: تحقق من الباركود باستخدام محاكي الماسح

يتضمن Aspose.Barcode فئة `BarcodeReader` يمكنك استخدامها لتأكيد أن الصورة المولدة تُفك تشفيرها إلى البيانات الأصلية.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

إذا كان الناتج يظهر `"123456"` لكلا الملفين، فقد تم إنشاء الباركود بشكل صحيح.

## الخلاصة

أنت الآن تعرف كيف **إنشاء باركود كوكب** بصور في C# مع كل من أنماط الأشرطة المملوءة والفارغة، وتتحكم في **Planet barcode XDimension**، وتحفظ النتائج بصيغة PNG باستخدام مكتبة **Aspose.Barcode**. عدّل عرض الشريط، أو غيّر تنسيقات الصور، أو استخدم حلقة على مجموعة من القيم لتتناسب مع أي سير عمل للرموز البريدية.

بعد ذلك، قد ترغب في استكشاف:

* **إضافة نص قابل للقراءة البشرية** أسفل الباركود (`barcodeGenerator.Parameters.Caption.Show = true`).
* **دمج الباركودات في مستندات PDF** باستخدام Aspose.PDF.
* **إنشاء ترميزات بريدية أخرى** مثل **USPS POSTNET** أو **Intelligent Mail**.

لا تتردد في تجربة المعلمات ودمج الكود في نظام الشحن أو البريد الخاص بك. برمجة سعيدة!

## ما الذي ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شاملة من الشيفرة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء باركود كوكب في C# – دليل كامل خطوة بخطوة](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [إنشاء باركود كوكب في C# – دليل برمجة كامل](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [مولد باركود C# – مثال إنشاء باركود كوكب وRM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}