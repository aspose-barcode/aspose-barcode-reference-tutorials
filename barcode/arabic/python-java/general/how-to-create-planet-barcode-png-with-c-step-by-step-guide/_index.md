---
category: general
date: 2026-09-07
description: إنشاء باركود كوكب بصيغة PNG في C# بسرعة. تعلّم كيفية توليد صور باركود
  كوكب باستخدام Aspose.BarCode مع الأشرطة المملوءة والفارغة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: ar
lastmod: 2026-09-07
og_description: إنشاء صورة PNG لباركود كوكب في C# بسرعة. اتبع هذا الدليل لتعلم كيفية
  إنشاء صور باركود كوكب بأشرطة مملوءة وفارغة باستخدام Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: إنشاء باركود كوكب بصيغة PNG في C# – دليل برمجة كامل
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية إنشاء رمز باركود كوكبي بصيغة PNG باستخدام C# – دليل خطوة بخطوة
url: /ar/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء رمز شريطي كوكبي بصيغة PNG باستخدام C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء ملفات رمز شريطي كوكبي بصيغة PNG** في C#، يوضح لك هذا الدليل الخطوات الدقيقة. سواءً كنت تبني تكاملًا لخدمة بريدية أو لوحة تحكم لوجستية، ستتعلم **كيفية توليد صور رمز شريطي كوكبي** بأشرطة مملوءة وفارغة باستخدام مكتبة Aspose.BarCode.

في هذا الدرس ستقوم بـ:

* إعداد مجلد الإخراج للصور.  
* تكوين `BarcodeGenerator` للرمز الكوكبي.  
* إنشاء PNG بنمط الأشرطة المملوءة الافتراضي.  
* إنشاء PNG بأشرطة فارغة لتباين بصري.  

لا تحتاج إلى خدمات خارجية—كل شيء يعمل محليًا على .NET 6 أو أحدث.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

| المتطلب | لماذا هو مهم |
|-------------|----------------|
| .NET 6 SDK (أو أحدث) | يوفر بيئة التشغيل لتطبيق وحدة التحكم C#. |
| Visual Studio 2022 أو VS Code | أي بيئة تطوير يمكنها تجميع مشاريع C#. |
| Aspose.BarCode for .NET (حزمة NuGet `Aspose.BarCode`) | تزودك بفئة `BarcodeGenerator` المستخدمة لإنشاء رموز شريطية كوكبية. |
| صلاحية كتابة إلى مجلد على القرص | سيتم حفظ ملفات PNG في هذا الموقع. |

قم بتثبيت حزمة NuGet باستخدام الأمر التالي:

```bash
dotnet add package Aspose.BarCode
```

## الخطوة 1: إنشاء مشروع وحدة تحكم جديد

افتح الطرفية ونفّذ:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

سيُنشئ هذا تطبيق وحدة تحكم C# بسيط يُدعى **PlanetBarcodeDemo**.

## الخطوة 2: تعريف دليل الإخراج

القطعة الأولى من الشيفرة تحدد أين سيتم تخزين ملفات PNG المُولدة. يمكنك استخدام مسار مطلق أو نسبي؛ فقط تأكد من وجود المجلد أو دع البرنامج ينشئه.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*لماذا هذه الخطوة؟* فصل الإخراج عن شفرة المصدر يحافظ على تنظيم المشروع ويتجنب الكتابة فوق الملفات عن طريق الخطأ.

## الخطوة 3: توليد رمز شريطي كوكبي بأشرطة مملوءة

يتكون رمز شريطي كوكبي من دوائر متحدة المركز (مملوءة افتراضيًا). نقوم بتكوين بُعد X (عرض كل شريط بالبكسل) ثم حفظ الصورة بصيغة PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**شرح**

* `EncodeTypes.Planet` يخبر Aspose باستخدام رموز كوكبية، وهو شائع في الخدمات البريدية.  
* `XDimension.Pixels = 4` ينتج حجمًا واضحًا وقابلًا للطباعة دون الحاجة لتكبير يدوي.  
* طريقة `Save` تكتب ملف PNG؛ يمكنك أيضًا اختيار JPEG أو BMP بتغيير `BarCodeImageFormat`.

## الخطوة 4: توليد رمز شريطي كوكبي بأشرطة فارغة

أحيانًا يُطلب تصور بأشرطة فارغة (شفافة)—مثلاً عندما يُوضع الرمز فوق خلفية ملونة. ضبط `FilledBars` إلى `false` ينتج هذا النمط.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**شرح**

* `FilledBars = false` يعطل الدوائر الصلبة، تاركًا فقط الحدود.  
* جميع الإعدادات الأخرى (بُعد X، سلسلة البيانات) تبقى متطابقة، مما يضمن أن الصورتين تمثلان نفس البيانات.

## الخطوة 5: تشغيل البرنامج والتحقق من الإخراج

قم بالترجمة والتنفيذ:

```bash
dotnet run
```

يجب أن ترى رسائل في وحدة التحكم تؤكد حفظ الملفات، وسيحتوي مجلد `Barcodes` على:

* `PostalPlanetFilledBars.png` – رمز شريطي كوكبي بأشرطة مملوءة كلاسيكي.  
* `PostalPlanetEmptyBars.png` – نفس البيانات مُصوَّرة بأشرطة فارغة.

افتح ملفات PNG في أي عارض صور. كلا الصورتين تُشفر السلسلة الرقمية **123456** ويمكن قراءتها بواسطة قارئات الرموز الشريطية البريدية القياسية.

## أسئلة شائعة ومعالجة الحالات الخاصة

### ماذا لو احتجت إلى تنسيق بيانات مختلف؟

تقبل الرموز الكوكبية سلاسل رقمية تصل إلى 12 رقمًا. إذا مررت قيمة غير رقمية، سيُطلق Aspose استثناءً من نوع `ArgumentException`. تحقق من صحة الإدخال قبل إنشاء المولد:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### كيف أغيّر حجم الصورة دون تعديل سمك الشريط؟

استخدم خاصية `Resolution` أو قم بتكبير الصورة الناتجة بعد الحفظ:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### هل يمكنني توليد صيغ صور أخرى؟

نعم. استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg` أو `Bmp` أو `Gif`. تدعم الـ API جميع صيغ الرسوم النقطية الشائعة.

### ماذا عن تخصيص الألوان؟

عيّن `BarColor` و `BackColor` على معلمات `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

هذه الخيارات تعمل لكل من النسختين المملوءة والفارغة.

## نصائح احترافية للاستخدام في بيئات الإنتاج

* **قم بتخزين المولد في الذاكرة** عندما تحتاج إلى إنشاء العديد من الرموز بنفس الإعدادات—إنشاء الكائن مرارًا يضيف عبئًا.  
* **حرّر** كائنات `BarcodeGenerator` إذا أنشأت الكثير داخل حلقة (فهي تنفذ `IDisposable`).  
* **تحقق من دليل الإخراج** مبكرًا لتجنب استثناءات وقت التشغيل على الأدلة المحمية من الكتابة.  

## الخلاصة

أصبح بإمكانك الآن **إنشاء ملفات رمز شريطي كوكبي بصيغة PNG** في C# وتعرف **كيفية توليد صور رمز شريطي كوكبي** بأشرطة مملوءة وفارغة. المثال الكامل القابل للتنفيذ يوضح إعداد دليل الإخراج، تكوين `BarcodeGenerator`، وحفظ النتائج كملفات PNG.

الخطوات التالية قد تشمل:

* إضافة **نص قابل للقراءة** أسفل الرمز (`planetFilled.Parameters.Caption.Visible = true`).  
* دمج ملفات PNG المُولدة في **فاتورة PDF** باستخدام Aspose.PDF.  
* التحول إلى رموز شريطية بريدية أخرى مثل **IMB** أو **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

لا تتردد في تجربة سمك الشريط، الألوان، ودقة الصورة لتتناسب مع متطلبات تطبيقك الخاصة. Happy coding!

## ماذا يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}