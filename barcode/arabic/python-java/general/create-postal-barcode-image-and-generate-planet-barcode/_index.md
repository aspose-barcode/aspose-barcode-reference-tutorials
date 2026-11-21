---
category: general
date: 2026-11-20
description: أنشئ صورة باركود بريدي في C# بسرعة. تعلّم كيفية إنشاء باركود بلانيت وباركود
  RM4SCC مع أنماط أشرطة قابلة للتخصيص.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: ar
lastmod: 2026-11-20
og_description: إنشاء صورة باركود بريدي في C# باستخدام Aspose.BarCode. يوضح هذا الدرس
  كيفية إنشاء باركود كوكبي، وتخصيص أنماط الخطوط، وإنتاج صور RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: إنشاء صورة باركود بريدي في C# – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: إنشاء صورة باركود بريدي وتوليد باركود كوكبي
url: /ar/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود بريدي وتوليد باركود بلانيت

إنشاء صورة باركود بريدي في C# باستخدام مكتبة Aspose.BarCode. إذا كنت بحاجة إلى توليد باركود بلانيت أو باركود RM4SCC لتطبيقات البريد، فإن هذا الدليل يوفر حلاً كاملاً وجاهزًا للتنفيذ.

غالبًا ما تتطلب إنشاء الباركودات لخدمات البريد أبعادًا دقيقة وخيارًا للتبديل بين أنماط الأشرطة المملوءة والفارغة. يوضح هذا الدليل كيفية إعداد مجلد الإخراج، وإنشاء باركودات بلانيت مملوءة وفارغة، وإنتاج باركود RM4SCC بنفس الإعدادات البصرية. في النهاية ستحصل على أربعة ملفات PNG يمكنك استخدامها مباشرة في سير عمل البريد الخاص بك.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 أو أحدث مثبت  
* Visual Studio 2022 (أو أي بيئة تطوير C# تفضلها)  
* حزمة **Aspose.BarCode** من NuGet (`Install-Package Aspose.BarCode`)  

لا يلزم أي تكوين إضافي؛ يستخدم الكود الخط الافتراضي ومشفّر PNG فقط.

## نظرة عامة على إنشاء صورة باركود بريدي

النواة في العملية هي الفئة `BarcodeGenerator`. تقبل قيمة `EncodeTypes` التي تحدد رمزية الباركود (على سبيل المثال، `EncodeTypes.Planet` لباركود بلانيت). بعد تكوين المولّد، تستدعي `Save` لكتابة ملف الصورة.

![Create postal barcode image example](/images/postal_barcode_example.png)

*نص بديل: مثال على إنشاء صورة باركود بريدي يُظهر الأشرطة المملوءة والفارغة.*

## الخطوة 1: إعداد مجلد الإخراج

أولاً حدد مجلدًا سيتم حفظ ملفات PNG فيه. يمكن استخدام مسار مطلق أو نسبي؛ فقط تأكد من وجود المجلد أو دع الكود ينشئه.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

إنشاء المجلد برمجيًا يمنع حدوث استثناء `DirectoryNotFoundException` عندما يُشغَّل الدليل على جهاز جديد.

## الخطوة 2: توليد باركود بلانيت بأشرطة مملوءة

باركود بلانيت بأشرطة مملوءة هو النمط البصري الافتراضي. الكود التالي ينشئ الباركود، يضبط بعد X إلى 4 بيكسل (حجم شائع لتطبيقات البريد)، ويحفظ الصورة.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**لماذا يعمل هذا:**  
* `EncodeTypes.Planet` يخبر المولّد باستخدام رمزية بلانيت، وهو ما تتطلبه العديد من خدمات البريد.  
* `XDimension.Pixels` يتحكم في عرض كل شريط؛ 4 بيكسل ينتج صورة واضحة قابلة للمسح دون حجم ملف مفرط.  
* طريقة `Save` تختار تلقائيًا مشفّر PNG بناءً على تعداد `BarCodeImageFormat`.

## الخطوة 3: توليد باركود بلانيت بأشرطة فارغة

بعض مواصفات البريد تفضّل الأشرطة الفارغة (بيضاء) على خلفية داكنة. يمكنك تحقيق ذلك بتعيين `FilledBars` إلى `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**نصيحة:** عندما تكون `FilledBars` مساوية لـ `false`، يرسم المولّد الأشرطة بلون الخلفية (أبيض افتراضيًا) والمسافات بلون المقدمة (أسود). إذا كنت تحتاج إلى مخطط ألوان مختلف، عدّل `Parameters.Barcode.ForeColor` و `BackColor`.

## الخطوة 4: توليد باركود RM4SCC بأشرطة مملوءة

RM4SCC هو رمز باركود بريدي آخر يُستخدم في المملكة المتحدة. خطوات الإنشاء مماثلة لمثال بلانيت؛ يتغيّر فقط قيمة `EncodeTypes`.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**ما المتوقع:** الصورة PNG الناتجة تعرض باركود RM4SCC مدمج يتوافق مع إرشادات البريد البريطاني. سيكون حجم الصورة مشابهًا لباركودات بلانيت لأن بعد X هو نفسه.

## الخطوة 5: التحقق من الصور المُولَّدة

بعد تشغيل البرنامج، افتح الملفات الأربعة في مجلد `Barcodes`. يجب أن ترى:

* `PostalPlanetFilledBars.png` – أشرطة داكنة على خلفية فاتحة  
* `PostalPlanetEmptyBars.png` – أشرطة فاتحة على خلفية داكنة (عكسية)  
* `PostalRM4SCCFilledBars.png` – نمط RM4SCC قياسي  

إذا بدت أي صورة مشوّهة، تحقق من التالي:

* **بعد X** – القيم الصغيرة (< 2 بيكسل) قد تتسبب في تشويش؛ القيم الكبيرة (> 10 بيكسل) قد تتجاوز حدود حجم الملصق.  
* **سلسلة البيانات** – يجب أن تكون القيمة `"123456"` مطابقة لمتطلبات الطول للرمزية المختارة (بلانيت يتطلب 6 أرقام، RM4SCC أيضًا يتطلب 6 أرقام).  
* **أذونات المجلد** – تأكد من أن التطبيق يملك صلاحية كتابة إلى دليل الإخراج.

## الاختلافات الشائعة والحالات الطرفية

| السيناريو | التعديل |
|----------|------------|
| **بيانات باركود مختلفة** | استبدل `"123456"` بأي سلسلة رقمية صالحة. بالنسبة لبلانيت، يجب أن يكون الطول بالضبط 6 أرقام؛ RM4SCC يتطلب أيضًا 6 أرقام. |
| **ألوان مخصصة** | اضبط `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` و `BackColor = System.Drawing.Color.LightYellow;`. |
| **دقة أعلى** | زد `XDimension.Pixels` إلى 6 أو 8 للحصول على طباعة أكبر. |
| **تنسيقات صورة أخرى** | استخدم `BarCodeImageFormat.Jpeg` أو `BarCodeImageFormat.Bmp` في استدعاء `Save`. |
| **إنشاء دفعي** | كرّر العملية عبر مجموعة من السلاسل واستدعِ نفس منطق المولّد داخل الحلقة، مع إعادة استخدام مسار `outputFolder`. |

## مثال كامل قابل للتنفيذ

انسخ الشيفرة أدناه إلى مشروع C# جديد من نوع console. يتوافق مع .NET 6.0 وينتج جميع صور الباركود الأربعة تلقائيًا.



## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء صورة باركود بريدي بارتفاعات مخصصة في C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [كيفية إنشاء باركود RM4SCC وتوليد باركود بلانيت في C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [إنشاء صورة باركود بريدي في C# – دليل خطوة بخطوة](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}