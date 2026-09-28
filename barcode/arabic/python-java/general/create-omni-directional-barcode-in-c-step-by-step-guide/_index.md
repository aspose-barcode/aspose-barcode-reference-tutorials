---
category: general
date: 2026-07-15
description: إنشاء باركود متعدد الاتجاهات في C# بسرعة باستخدام Aspose.BarCode – تعلم
  كيفية توليد باركود C# مع ارتفاع الشريط القابل للتعديل وأبعاد X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: ar
lastmod: 2026-07-15
og_description: إنشاء باركود متعدد الاتجاهات في C# باستخدام Aspose.BarCode. تعلّم
  كيفية توليد باركود C# عن طريق تعديل XDimension و BarHeight للحصول على نتائج مثالية.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: إنشاء باركود متعدد الاتجاهات في C# – دليل برمجة شامل
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: إنشاء باركود متعدد الاتجاهات في C# – دليل خطوة بخطوة
url: /ar/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود متعدد الاتجاهات في C# – دليل خطوة بخطوة

هل تساءلت يومًا كيف تولد باركود C# يتوافق مع رموز GS1 DataBar Omni‑Directional؟ لست وحدك. في هذا الدرس سنقوم **بإنشاء صور باركود متعدد الاتجاهات** من الصفر، تعديل البُعد X، واللعب بارتفاع الخطوط—كل ذلك باستخدام مكتبة Aspose.BarCode.

سنتبع سيناريو واقعي: تحتاج إلى باركود مدمج وعالي الكثافة لملصق تجاري، وتريد التحكم الكامل في حجمه البصري. في النهاية ستحصل على ملفين PNG—أحدهما بارتفاع شريط 30 بكسل والآخر بارتفاع 60 بكسل—جاهزين للإدراج في أي سير عمل للطباعة.

## المتطلبات المسبقة

- .NET 6 (أو أي بيئة تشغيل .NET حديثة) مثبتة على جهازك.  
- Visual Studio 2022 أو VS Code—أي بيئة تطوير مفضلة لديك ستكفي.  
- حزمة NuGet مجانية Aspose.BarCode for .NET (`Aspose.BarCode`).

لا توجد تبعيات أخرى مطلوبة. إذا لم تتعامل مع NuGet من قبل، فقط افتح وحدة تحكم مدير الحزم وشغّل:

```powershell
Install-Package Aspose.BarCode
```

## إنشاء باركود متعدد الاتجاهات – فهم الأساسيات

رموز **GS1 DataBar Omni‑Directional** صُممت للمسح الضوئي بأي اتجاه، مما يجعلها مثالية لملصقات حافة الرف. عند استدعاء `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`، تقوم المكتبة بالعمل الشاق: تشفر البيانات، تطبق قواعد الرموز، وتُعد صورة نقطية.

> **نصيحة احترافية:** دائمًا قم بلف البيانات الخام بالتنسيق المناسب لمُعرّف التطبيق (AI)، مثل `"(01)12345678901231"` لرمز GTIN‑14. هذا يُخبر الماسح بما تمثله الأرقام.

## الخطوة 1 – إعداد مولّد الباركود (how to generate barcode c#)

أولاً نقوم بإنشاء كائن المولد. هذا هو الأساس لـ **how to generate barcode c#** باستخدام Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

قيمة التعداد `EncodeTypes.DatabarOmniDirectional` تخبر المحرك أي رموز يستخدم. الوسيط الثاني هو سلسلة البيانات الخام، مغلفة مسبقًا بمعرف GTIN AI.

## الخطوة 2 – تعديل البُعد X (barcode XDimension)

**XDimension الباركود** يتحكم في عرض أصغر شريط. قيمة 2 بكسل تُعد توازنًا جيدًا بين القابلية للقراءة والضغط لمعظم طابعات الملصقات.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

إذا كنت تحتاج مظهرًا أدق أو أكثر خشونة، فقط غيّر الرقم. تذكر: البُعد X هو الوحدة الأساسية؛ جميع عرض الأشرطة الأخرى هي مضاعفات هذه القيمة.

## الخطوة 3 – إنشاء الصورة الأولى بارتفاع شريط 30 بكسل (barcode BarHeight)

الآن نضبط **BarHeight الباركود** إلى 30 بكسل ونحفظ الصورة. هذا ينتج باركود بحجم معتدل يتناسب جيدًا مع ملصق قياسي.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

طريقة `Save` تكتب ملف PNG إلى القرص. يمكنك استبدال `BarCodeImageFormat.Jpeg` إذا كنت تفضل إخراج JPEG.

## الخطوة 4 – زيادة ارتفاع الشريط إلى 60 بكسل للملصقات الأكبر (barcode BarHeight)

أحيانًا يُطلب باركود أكبر—ربما لملصق رف يبعد أكثر عن الماسح. لنضاعف الارتفاع.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

لاحظ أننا **لا** نحتاج إلى إعادة إنشاء المولد؛ فقط نعدل المعامل ونعيد استخدام نفس الكائن. هذا يوفر الذاكرة ويحافظ على نظافة الكود.

## الخطوة 5 – حفظ الصورة الثانية (how to generate barcode c#)

أخيرًا، نحفظ PNG الثاني. لديك الآن ملفان يختلفان فقط في ارتفاع الشريط.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### النتيجة المتوقعة

- `DatabarBarHeight30Pixels.png` – باركود متعدد الاتجاهات بارتفاع 30 بكسل.  
- `DatabarBarHeight60Pixels.png` – نفس البيانات، لكن بارتفاع شريط 60 بكسل.

افتح الملفات في أي عارض صور؛ سترى أشرطة واضحة وقابلة للمسح تحترم مواصفات GS1 DataBar Omni‑Directional.

## أسئلة شائعة وحالات خاصة

### ماذا لو احتجت إلى بُعد X مختلف؟

فقط عيّن قيمة جديدة قبل استدعاء `Save`. للطباعة ذات الكثافة الفائقة قد تنزل إلى 1 بكسل، لكن اختبر مع الماسح أولًا—بعض الأجهزة تواجه صعوبة مع أشرطة أقل من 2 بكسل.

### هل يمكن إضافة نص قابل للقراءة البشرية أسفل الباركود؟

نعم. اضبط `barcodeGenerator.Parameters.Barcode.CodeText` إلى سلسلة نصية واختياريًا عدل `barcodeGenerator.Parameters.Barcode.CodeLocation` إلى `BarCodeTextLocation.Below`. هذا مفيد في بيئات التجزئة حيث يجب أن يكون رقم GTIN مرئيًا.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### هل PNG هو أفضل تنسيق للطباعة؟

PNG هو تنسيق غير مضغوط، يحافظ على الحواف الحادة المطلوبة لماسحات الباركود. إذا كان نظامك اللاحق يتوقع تنسيقًا مختلفًا (TIFF، BMP)، فقط غيّر تعداد `BarCodeImageFormat`.

## مثال كامل يعمل (create omni-directional barcode)

فيما يلي البرنامج الكامل الجاهز للتنفيذ. انسخه والصقه في مشروع كونسول جديد واضغط **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

شغّل البرنامج، تحقق من مجلد الإخراج، وسترى ملفي PNG كما هو موصوف.

## ملخص

لقد عرضنا كود **how to generate barcode C#** الذي ينشئ **create omni-directional barcode** باستخدام Aspose.BarCode. من خلال تعديل **XDimension الباركود** و **BarHeight الباركود**، تحصل على تحكم دقيق في الحجم البصري دون التضحية بموثوقية المسح.

## ما التالي؟

- جرب إعدادات أخرى لـ **GS1 DataBar Omni-Directional** مثل `Color` أو `Margin`.  
- دمج عدة باركودات على لوحة واحدة باستخدام `Graphics` لتصاميم ملصقات معقدة.  
- دمج المولد في واجهة ويب API حتى يتمكن نظام التجارة الإلكترونية الخاص بك من إصدار باركودات عند الطلب.

هل لديك تعديل ترغب بمشاركته؟ اترك تعليقًا، ولنستمر في النقاش. برمجة سعيدة!

## ما الذي ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة كود كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية توليد باركود – تكوين Code 39 باستخدام Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [كيفية إنشاء منطقة هادئة للباركود ITF-14 باستخدام Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [كيفية إنشاء منطقة هادئة للباركود Code 16K باستخدام Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}