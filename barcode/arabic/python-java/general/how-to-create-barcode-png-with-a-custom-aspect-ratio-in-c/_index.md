---
category: general
date: 2026-10-05
description: إنشاء باركود PNG باستخدام C# وتعلم كيفية ضبط نسبة الأبعاد إلى 15 للباركودات
  المتراصة DataBar متعددة الاتجاهات.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: ar
lastmod: 2026-10-05
og_description: إنشاء رمز شريطي بصيغة PNG باستخدام C# واكتشف كيفية ضبط نسبة العرض
  إلى الارتفاع 15 للباركودات المتراصة DataBar متعددة الاتجاهات في بضع خطوات.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: إنشاء باركود PNG في C# – ضبط نسبة العرض إلى الارتفاع 15 دليل
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: كيفية إنشاء باركود PNG بنسبة أبعاد مخصصة في C#
url: /ar/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء صورة PNG للباركود بنسبة عرض إلى ارتفاع مخصصة في C#

إذا كنت بحاجة إلى **create barcode PNG** في C#، يوضح لك هذا الدليل **how to set aspect ratio** 15 لباركود DataBar مكدس متعدد الاتجاهات. سنستعرض كل استدعاء API، نشرح لماذا نسبة العرض إلى الارتفاع مهمة، ونقدم لك مثالًا كاملاً قابلاً للتنفيذ يمكنك إضافته إلى أي مشروع .NET.

إنشاء صورة باركود هو طلب شائع لأنظمة المخزون، ملصقات الشحن، وتطبيقات نقاط البيع. بنهاية هذا الدرس ستحصل على ملف PNG يطابق المواصفات البصرية الدقيقة المطلوبة من شريك عملك. لا أدوات خارجية، لا تعديل يدوي للصور—فقط الكود.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود:

* .NET 6.0 أو أحدث (المثال يستخدم .NET 6 لكنه يعمل مع .NET 5+)
* Visual Studio 2022 (أو أي بيئة تطوير تدعم .NET)
* حزمة **Aspose.BarCode for .NET** عبر NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* صلاحية كتابة في المجلد الذي تريد حفظ ملف PNG فيه

هذه المتطلبات قليلة؛ نفس الكود يعمل في .NET Core، .NET Framework، أو تطبيق كونسول.

## إنشاء صورة PNG للباركود باستخدام Aspose.BarCode

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` بالنوع الصحيح للباركود. في هذه الحالة نستخدم `EncodeTypes.DatabarStackedOmniDirectional`، الذي ينتج DataBar مكدس يمكن قراءته من أي اتجاه.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*لماذا هذا مهم:* المُنشئ يأخذ وسيطين—**رمز الباركود** و**سلسلة البيانات**. تنسيق DataBar يتطلب معرف تطبيق GS1، لذلك تبدأ بيانات العينة بـ `(01)`.

## كيفية ضبط نسبة العرض إلى الارتفاع لباركود DataBar المكدس

العرض البصري لباركود DataBar يتحكم فيه خاصية **aspect ratio**. كلما ارتفعت النسبة، أصبحت الأشرطة أوسع، مما قد يحسن موثوقية القراءة على الطابعات منخفضة الدقة.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

خاصية `XDimension` تحدد حجم الوحدة الواحدة (أصغر شريط أو فراغ). الحفاظ على قيمتها 2 px يعطي صورة حادة وعالية الكثافة مناسبة لمعظم طابعات الملصقات.

## ضبط نسبة العرض إلى الارتفاع 15 – استعراض الكود

الآن نطبق متطلب **set aspect ratio 15**. هذا هو جوهر الدرس ويظهر استدعاء API الدقيق الذي تحتاجه.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*لماذا 15؟* النسبة الافتراضية لباركود DataBar المكدس هي 12. رفعها إلى 15 يوسع عرض كل شريط بنسبة 25 %، وهو ما يتطابق غالبًا مع مواصفات مزودي الخدمات اللوجستية الذين يطلبون باركود أوسع لتسريع عملية المسح.

## حفظ الباركود كملف PNG

بعد ضبط المولد، الخطوة الأخيرة هي كتابة الصورة إلى القرص. طريقة `Save` تقبل مسار الملف وتنسيق الصورة كقيمة enum.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

تنسيق PNG يحافظ على جودة غير مضغوطة، مما يضمن أن الباركود يُظهر بدقة كما صُمم على أي شاشة أو طابعة.

## مثال كامل والنتيجة المتوقعة

فيما يلي البرنامج الكامل الذي يمكنك نسخه إلى طريقة `Main` في تطبيق كونسول. يتضمن جميع الخطوات المذكورة أعلاه، بالإضافة إلى رسالة تحقق صغيرة.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**النتيجة المتوقعة**

عند تشغيل البرنامج يتم إنشاء ملف باسم `DatabarAspectRatio15.png` يحتوي على باركود DataBar مكدس واضح وعريض. عند فتح ملف PNG، يجب أن ترى باركودًا مُمتدًا أفقيًا لا يزال يتوافق مع مواصفات GS1 DataBar.

![صورة PNG للباركود بنسبة العرض إلى الارتفاع 15](barcode-aspect15.png)

*نص بديل للصورة:* **إنشاء صورة PNG للباركود تُظهر DataBar مكدس بنسبة العرض إلى الارتفاع 15**

### نصائح ومشكلات شائعة

| الحالة | التوصية |
|-----------|----------------|
| **الصورة تبدو ضبابية** | زد قيمة `XDimension.Pixels` إلى 3 px أو أكثر، لكن حافظ على حجم الصورة الكلي أقل من 500 px لتجنب ملفات ضخمة. |
| **المسّاح لا يستطيع قراءة الرمز** | تأكد من أن سلسلة البيانات تتبع تنسيق GS1 (بادئة `(01)`). كما يجب أن تكون دقة الطابعة لا تقل عن 300 dpi. |
| **تحتاج إلى تنسيق ملف مختلف** | استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Gif`—الـ API يدعم جميع صيغ الصور النقطية الرئيسية. |
| **التنفيذ في تطبيق ويب** | استخدم `generator.Save(Stream, BarCodeImageFormat.Png)` لكتابة الصورة مباشرة إلى استجابة HTTP دون الحاجة إلى نظام الملفات. |

### توسيع المثال

* **عدة باركودات في صورة واحدة:** أنشئ كائنات `BarcodeGenerator` إضافية وارسمها على `Bitmap` واحد باستخدام `Graphics`.  
* **إضافة نص قابل للقراءة البشرية:** عيّن `generator.Parameters.Caption.Visible = true` وخصص الخط عبر `generator.Parameters.Caption.Font`.  
* **نسبة عرض إلى ارتفاع ديناميكية:** احصل على قيمة النسبة من ملف إعدادات أو قاعدة بيانات لتوليد باركودات بعروض مختلفة حسب الحاجة.

## الخلاصة

في هذا الدرس تعلمت كيفية **create barcode PNG** في C# وضبط **aspect ratio** 15 بدقة لباركود DataBar مكدس متعدد الاتجاهات. الكود الكامل القابل للتنفيذ يوضح كل استدعاء API مطلوب، يشرح سبب أهمية كل إعداد، ويقدم نصائح عملية للنشر في بيئات الإنتاج.  

بعد ذلك، يمكنك استكشاف **كيفية ضبط نسبة العرض إلى الارتفاع** لأنواع باركود أخرى (مثل QR Code أو Code 128) أو دمج المولد في خدمة ASP .NET Core تُعيد صور الباركود عند الطلب. Happy coding!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية إنشاء صور PNG للباركود databar باستخدام C# و Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [كيفية إنشاء باركود databar مكدس في C# باستخدام Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [تخصيص نسبة العرض إلى الارتفاع لباركود databar مكدس متعدد الاتجاهات في .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}