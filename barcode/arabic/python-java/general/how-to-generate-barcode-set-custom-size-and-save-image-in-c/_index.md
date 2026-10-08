---
category: general
date: 2026-09-13
description: تعلم كيفية إنشاء الباركود في C#، وتخصيص حجم الباركود، وحفظ صورة الباركود
  كملف PNG باستخدام Aspose.BarCode. دليل كامل خطوة بخطوة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: ar
lastmod: 2026-09-13
og_description: كيفية إنشاء الباركود في C# بحجم باركود مخصص وحفظ صورة الباركود بصيغة
  PNG. اتبع هذا الدليل الكامل لـ Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: كيفية إنشاء الباركود، تحديد حجم مخصص، وحفظ الصورة في C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: كيفية إنشاء مجموعة باركود بحجم مخصص وحفظ الصورة في C#
url: /ar/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مجموعة باركود بحجم مخصص وحفظ الصورة في C#

إذا كنت تحتاج إلى **كيفية إنشاء باركود** في تطبيق .NET، فإن هذا الدرس يوضح لك حلاً كاملاً. ستتعرف على كيفية تعديل **حجم الباركود المخصص** و**حفظ صورة الباركود** باستخدام بضع أسطر فقط من كود C#.

إنشاء الباركودات هو طلب شائع لأنظمة الجرد، ملصقات الشحن، وتطبيقات نقاط البيع. في نهاية هذا الدليل ستحصل على برنامج قابل للتنفيذ ينشئ باركودين من نوع DataBar‑Stacked‑Omnidirectional، كل منهما بنسبة أبعاد مختلفة، ويكتبهما كملفات PNG على القرص.

**Prerequisites**

- .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.7+)
- Visual Studio 2022 أو أي بيئة تطوير C#
- Aspose.BarCode for .NET (نسخة تجريبية مجانية أو حزمة NuGet مرخصة)

---

## كيفية إنشاء باركود باستخدام Aspose.BarCode

مكتبة Aspose.BarCode تُجرد التفاصيل التقنية منخفضة المستوى لمعايير الباركود، مما يتيح لك التركيز على البيانات التي تريد ترميزها والمظهر البصري الذي تحتاجه.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### لماذا كل سطر مهم

| الخطوة | الشرح |
|--------|-------|
| **1️⃣ إنشاء مولد** | تُخبر القيمة `EncodeTypes.DatabarStackedOmniDirectional` مكتبة Aspose أي نوع من رموز الباركود يجب استخدامها. السلسلة `"(01)12345678901231"` تتبع تنسيق بيانات GS1‑128، حيث `(01)` هو معرف التطبيق لـ GTIN. |
| **2️⃣ تعيين البُعد X** | `XDimension.Pixels` يحدد عرض وحدة الباركود الواحدة (أصغر شريط). تغيير هذه القيمة هو الطريقة الأساسية لتحقيق **حجم باركود مخصص** دون تعديل البيانات المشفرة. |
| **3️⃣ تعيين نسبة الأبعاد وحفظ** | `DataBar.AspectRatio` يتحكم في نسبة الارتفاع إلى العرض لرموز DataBar. نسبة أبعاد 15 تنتج باركود قصير وعريض نسبياً، بينما 30 يجعله أطول. `Save` يكتب التمثيل البصري إلى ملف PNG، مما يلبي متطلب **حفظ صورة الباركود**. |
| **4️⃣ تغيير نسبة الأبعاد وحفظ مرة أخرى** | إعادة استخدام نفس كائن المولد يسمح لك بإنشاء صور متعددة بخصائص بصرية مختلفة مع الحفاظ على ثبات البيانات. |

---

## تعديل حجم الباركود المخصص بخلاف البُعد X

بينما `XDimension.Pixels` يحدد عرض الوحدة، يمكنك أيضًا ضبط الأبعاد الكلية للباركود من خلال دمج خاصيتين:

1. **`BarHeight`** – ارتفاع صريح بالبكسل.  
2. **`BarWidth`** – عرض صريح بالبكسل (يتجاوز X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **نصيحة احترافية:** عند طباعة الباركودات، اختبر دائمًا الصورة المولدة بالحجم النهائي للطباعة. عرض وحدة 2 px يناسب العرض على الشاشة، لكن الملصقات المطبوعة غالبًا ما تحتاج على الأقل إلى 4 px لتظل قابلة للقراءة.

---

## اختيار تنسيق الصورة المناسب لحفظ صورة الباركود

Aspose.BarCode يدعم PNG، JPEG، BMP، GIF، وTIFF. PNG غير مضغوط ويحافظ على حواف واضحة، مما يجعله الخيار الأكثر أمانًا لمعظم التطبيقات. إذا كنت تحتاج إلى ملف أصغر للاستخدام على الويب، فإن JPEG بجودة 90 يعمل جيدًا، لكن كن على علم بأن ضغطه قد يؤثر على موثوقية القراءة.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## مثال كامل قابل للتنفيذ

فيما يلي تطبيق وحدة تحكم مستقل يمكنك نسخه، لصقه، وتشغيله. يوضح **كيفية إنشاء باركود**، تعديل **حجم الباركود المخصص**، و**حفظ صورة الباركود** بصيغتين مختلفتين.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**الناتج المتوقع على وحدة التحكم**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

ستظهر ملفات الصور الأربعة في البرنامج

## ماذا يجب أن تتعلم بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET – دليل خطوة بخطوة](/barcode/english/net/datamatrix-barcode-configuration/)
- [كيفية إنشاء باركود PDF417 باستخدام Aspose – دليل كامل](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [كيفية إنشاء باركود Aztec بنسبة أبعاد مخصصة باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}