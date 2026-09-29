---
category: general
date: 2026-09-29
description: كيفية ضبط عرض رمز الباركود GS1 DataBar Omni‑Directional وكيفية تغيير
  الارتفاع باستخدام C#. اتبع دليلًا خطوة بخطوة مع الكود الكامل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: ar
lastmod: 2026-09-29
og_description: كيفية ضبط عرض شريط GS1 DataBar Omni‑Directional وكيفية تغيير الارتفاع
  في C#. تعلم استدعاءات API الدقيقة وشاهد مثالًا كاملاً قابلًا للتنفيذ.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: كيفية ضبط عرض رمز شريط GS1 DataBar – دليل C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: كيفية تعيين العرض وضبط الارتفاع لباركود GS1 DataBar Omni‑Directional في C#
url: /ar/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضبط العرض وتعديل الارتفاع لباركود GS1 DataBar Omni‑Directional في C#

ضبط عرض باركود GS1 DataBar Omni‑Directional هو مهمة شائعة عندما تحتاج إلى حجم دقيق لمعدات المسح. في هذا الدرس ستتعلم أيضًا **كيفية تغيير الارتفاع** بحيث يتناسب الباركود مع تخطيطك بشكل مثالي. يوجهك الدليل عبر العملية الكاملة، من إعداد المشروع إلى مثال شفرة قابل للتنفيذ بالكامل.

سنتناول:

* الحزمة المطلوبة عبر NuGet وإصدار .NET.
* لماذا بعد X (عرض الوحدة) مهم لقراءة الباركود.
* استدعاءات API الدقيقة **كيفية ضبط العرض** و**كيفية تغيير الارتفاع**.
* معالجة الحالات الخاصة مثل الحد الأدنى لعرض الوحدة وعرض الدقة العالية.
* مثال كامل جاهز للنسخ واللصق ينتج ملفي PNG بارتفاعات شريط مختلفة.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

| المتطلب | السبب |
|------------|--------|
| .NET 6.0 SDK أو أحدث | المثال يستخدم ميزات C# الحديثة ويعمل على Windows أو Linux أو macOS. |
| Visual Studio 2022 (أو أي بيئة تطوير C#) | يوفر IntelliSense لواجهة Aspose.Barcode API. |
| **Aspose.Barcode for .NET** حزمة NuGet | تحتوي على `BarcodeGenerator`، `EncodeTypes`، ودعم صيغ الصور. قم بالتثبيت باستخدام `dotnet add package Aspose.Barcode`. |
| إذن كتابة إلى مجلد سيتم حفظ ملفات PNG فيه | المولد يكتب الصور الناتجة إلى القرص. |

## كيفية ضبط عرض الباركود

خطوة **كيفية ضبط العرض** تُنفّذ عن طريق ضبط خاصية `XDimension` في معلمات الباركود. تمثل `XDimension` عرض الوحدة (أصغر شريط أو فراغ) بوحدات البكسل أو النقاط أو المليمترات. ضبطها بشكل صحيح يضمن أن الباركود يفي بمواصفات الماسح.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### لماذا بعد X مهم

* **تحمل الماسح** – معظم الماسحات تتطلب حدًا أدنى لعرض الوحدة؛ قيمة صغيرة جدًا قد تتسبب في أخطاء القراءة.
* **دقة الطباعة** – عند الطباعة بدقة 300 dpi، وحدة 2 px تعادل تقريبًا 0.17 mm، وهو ضمن النطاق الموصى به لـ GS1 DataBar.
* **حجم الصورة** – قيم XDimension الأكبر تزيد من عرض الباركود الكلي، مما قد يؤثر على قيود التخطيط.

### نصائح لضبط العرض بشكل موثوق

* **لا تقم أبداً بتعيين XDimension أقل من 1 px** – المكتبة ستقيد القيمة، لكن الباركود الناتج قد يكون غير قابل للقراءة.
* **طابق DPI المستهدف** – إذا كنت تُظهر الصورة بدقة عالية (مثال: TIFF بـ 600 dpi)، زد XDimension بصورة متناسبة.
* **اختبر مع ماسح حقيقي** – بعد تغيير العرض، تحقق من صحة الباركود على الجهاز الذي سيقرأه.

## كيفية تغيير ارتفاع الباركود

بمجرد تعريف العرض، يمكنك التحكم في الحجم العمودي عبر خاصية `BarHeight`. يوضح الكود التالي **كيفية تغيير الارتفاع** من 30 px إلى 60 px ويحفظ صورتين منفصلتين.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### فهم ارتفاع الشريط

* **التوازن البصري** – الشريط الأطول يحسن القراءة على خلفيات منخفضة التباين لكنه يزيد من البصمة العمودية للصورة.
* **الحدود التنظيمية** – بعض المعايير (مثل تسمية التجزئة) تحدد أقصى ارتفاع للشريط؛ عدّل وفقًا لذلك.
* **نسبة الأبعاد** – تغيير الارتفاع لا يؤثر على عرض الوحدة؛ يمكنك ضبط كلاهما بشكل مستقل.

### معالجة الحالات الخاصة لتعديل الارتفاع

| الحالة | النهج الموصى به |
|-----------|----------------------|
| ارتفاع < 10 px | زد الارتفاع إلى ما لا يقل عن 10 px؛ الشريط القصير جدًا قد يتجاهله الماسح. |
| أشرطة طويلة جدًا (≥ 100 px) | تأكد من أن وسيط الإخراج (ورق، ملصق) يمكنه استيعاب المساحة الإضافية. |
| الحاجة إلى مقياس متناسب | احسب `BarHeight = XDimension * desiredRatio` للحفاظ على التناسق البصري. |

## مثال كامل قابل للتنفيذ

فيما يلي البرنامج الكامل الذي يجمع خطوات **كيفية ضبط العرض** و**كيفية تغيير الارتفاع**. انسخ الشفرة إلى مشروع وحدة تحكم جديد، استعد حزمة Aspose.Barcode NuGet، ثم شغّلها. سيظهر ملفا PNG في مجلد `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**الناتج المتوقع**

تشغيل البرنامج ينتج ملفي PNG:

* `DatabarBarHeight30Pixels.png` – باركود بارتفاع 30 px، وحدات عرضها 2 px.
* `DatabarBarHeight60Pixels.png` – نفس الباركود بارتفاع عمودي مضاعف.

افتح أي من الصورتين في أي عارض؛ ستلاحظ رمز GS1 DataBar Omni‑Directional نظيفًا جاهزًا للمسح.

## الأسئلة الشائعة وإجاباتها

| السؤال | الإجابة |
|----------|--------|
| *هل يمكنني استخدام المليمترات بدلاً من البكسل؟* | نعم. اضبط `generator.Parameters.Barcode.XDimension.Millimeters` و `BarHeight.Millimeters`. تقوم المكتبة بتحويل القيم إلى بكسل الجهاز بناءً على DPI الصورة. |
| *ماذا لو احتجت نوع باركود مختلف؟* | استبدل `EncodeTypes.DatabarOmniDirectional` بأي قيمة أخرى من `EncodeTypes` (مثال: `EncodeTypes.QR`). خصائص العرض والارتفاع تعمل بنفس الطريقة. |
| *هل هناك طريقة لتوليد SVG بدلاً من PNG؟* | استخدم `BarCodeImageFormat.Svg` في استدعاء `Save`. تظل إعدادات العرض/الارتفاع سارية. |
| *هل أحتاج إلى استدعاء `generator.Dispose()`؟* | `BarcodeGenerator` يطبق `IDisposable`. في تطبيق وحدة تحكم يمكنك وضعه داخل كتلة `using`، لكن في الأمثلة القصيرة يمكن تركه اختياريًا. |

## الخلاصة

أنت الآن تعرف **كيفية ضبط عرض** باركود GS1 DataBar Omni‑Directional **وكيفية تغيير ارتفاعه** باستخدام Aspose.Barcode API في C#. يوضح المثال الكامل إنشاء مولد، ضبط `XDimension` و `BarHeight`، وحفظ ملفات PNG بأحجام رأسية مختلفة.

من هنا يمكنك:

* تجربة `EncodeTypes` أخرى (مثل QR أو Code128).
* العرض إلى صيغ عالية الدقة مثل TIFF للطباعة.
* دمج المولد في واجهة ويب API تُعيد الباركود حسب الطلب.

برمجة سعيدة، ولتكن باركوداتك دائمًا قابلة للمسح بنجاح!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية تغيير ارتفاع الباركود في C# – دليل كامل](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [مثال مولد باركود في C# – ضبط العرض والارتفاع](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [كيفية استخدام مولد باركود C# لإنشاء باركود DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}