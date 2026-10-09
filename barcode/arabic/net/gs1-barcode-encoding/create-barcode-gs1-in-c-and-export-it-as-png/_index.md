---
category: general
date: 2026-09-29
description: إنشاء باركود GS1 بلغة C# وتوليد صور باركود بصيغة PNG باستخدام BarcodeGenerator.
  اتبع دليلًا خطوة بخطوة لتصدير صورة الباركود بكفاءة.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: ar
lastmod: 2026-09-29
og_description: إنشاء باركود GS1 باستخدام C# وتوليد ملفات PNG للباركود باستخدام BarcodeGenerator.
  اتبع هذا الدليل الكامل لتصدير صورة الباركود بسرعة.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: إنشاء باركود GS1 في C# – تصديره كملف PNG في دقائق
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: إنشاء باركود GS1 في C# وتصديره كملف PNG
url: /ar/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رمز شريطي GS1 في C# وتصديره كملف PNG

إذا كنت بحاجة إلى **إنشاء رمز شريطي GS1** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك. ستشاهد حلاً مختصراً يولد صورة رمز شريطي بصيغة PNG ويصدّر صورة الرمز إلى القرص، كل ذلك باستخدام فئة Aspose.BarCode `BarcodeGenerator`.

إنشاء رمز شريطي GS1 هو مطلب شائع للمخزون، الشحن، وأنظمة نقاط البيع. بنهاية هذا الدرس ستكون قادرًا على كتابة برنامج C# صغير ينشئ رمز شريطي MicroPDF417 متوافق مع GS1 ويحفظه كملف PNG عالي الجودة.

## المتطلبات المسبقة

* **.NET 6** (أو أي نسخة أحدث من .NET) مثبتة.
* **Visual Studio 2022** أو أي بيئة تطوير تدعم C#.
* حزمة NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – توفر واجهة برمجة التطبيقات `BarcodeGenerator` المستخدمة في الأمثلة.
* إلمام أساسي بصياغة C#.

> **نصيحة احترافية:** استخدم النسخة المجانية المجتمعية من Aspose.BarCode عند التجربة؛ النسخة الكاملة تزيل أي علامات مائية للتقييم.

## الخطوة 1 – إنشاء رمز شريطي GS1 باستخدام BarcodeGenerator

أول شيء تحتاجه هو إنشاء كائن `BarcodeGenerator` لتنسيق *MicroPDF417* وإعطائه سلسلة بيانات GS1. معرفات التطبيقات GS1 (AIs) تُحاط بأقواس، مثل `(01)` لـ GTIN‑14 و `(21)` للرقم التسلسلي.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**لماذا هذا مهم:**  
`EncodeTypes.MicroPdf417` يتعامل تلقائيًا مع الإدخال كبيانات GS1 عندما تحتوي السلسلة على معرفات صالحة. هذا يضمن أن الرمز الشريطي المُولد يتوافق مع مواصفات GS1 دون إعدادات إضافية.

## الخطوة 2 – ضبط أبعاد الرمز الشريطي للحصول على الحجم المثالي

حجم الرمز الشريطي البصري يتحكم فيه **بعد X** (عرض الوحدة الواحدة). تعديل `XDimension.Pixels` يتيح لك ضبط حجم الصورة النهائي مع الحفاظ على قابلية القراءة.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **كيفية توليد رمز شريطي PNG** – بعد X لا يؤثر على البيانات المشفرة؛ إنه يغيّر فقط الأبعاد الفيزيائية للصورة المُولدة. إذا كنت بحاجة إلى رمز شريطي أكبر للطباعة عالية الدقة، زد هذه القيمة (مثلاً `3` أو `4`).

## الخطوة 3 – توليد رمز شريطي PNG وتصدير صورة الرمز الشريطي

الآن يمكنك رسم الرمز الشريطي وكتابته إلى ملف PNG. طريقة `Save` تأخذ مسار الهدف وتنسيق الصورة المطلوب.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**ما يحدث في الخلفية:**  
`BarcodeGenerator.Save` يحول الرمز الشريطي إلى صورة نقطية (bitmap)، يطبق بعد X الذي ضبطته مسبقًا، ويشفّر الصورة كملف PNG. يمكن استخدام الملف الناتج مباشرة في صفحات الويب، أو طباعته على الملصقات، أو تضمينه في ملفات PDF.

## مثال كامل لكود المصدر

فيما يلي تطبيق وحدة تحكم كامل ومستقل يمكنك نسخه، لصقه، وتشغيله. يوضح **كيفية توليد ملفات رمز شريطي PNG**، **تصدير صورة الرمز الشريطي**، ويتضمن معالجة أخطاء أساسية.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### النتيجة المتوقعة

عند تشغيل البرنامج، يجب أن ترى:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

فتح ملف PNG يعرض رمز شريطي **GS1 MicroPDF417** واضح يُشفّر GTIN‑14 `12345678901234` والرقم التسلسلي `ABC123`. مسحه بأي ماسح متوافق مع GS1 سيعيد السلسلة الأصلية للبيانات.

## الأخطاء الشائعة وأفضل الممارسات

| المشكلة | لماذا يحدث | كيفية تجنبه |
|-------|----------------|-----------------|
| **تنسيق AI غير صحيح** | فقدان الأقواس أو الترتيب الخاطئ يجعل الرمز غير GS1. | احرص دائمًا على وضع كل AI بين أقواس، مثل `(01)`. |
| **بعد X صغير جدًا** | يصبح الرمز غير قابل للقراءة على الأجهزة منخفضة الدقة. | حافظ على `XDimension.Pixels` ≥ 2 لمعظم الطابعات؛ زد القيمة للإخراج عالي DPI. |
| **مجلد الإخراج غير موجود** | `Save` يرمي استثناء `DirectoryNotFoundException`. | استخدم `Directory.CreateDirectory` قبل استدعاء `Save`. |
| **استخدام EncodeType غير صحيح** | بعض الأنواع (مثل `Code128`) لا تدعم بيانات GS1 مباشرة. | اختر `EncodeTypes.MicroPdf417` أو أي نوع متوافق مع GS1. |
| **غياب مرجع NuGet** | أخطاء تجميع مثل `The type or namespace name 'Aspose' could not be found`. | قم بتثبيت حزمة `Aspose.BarCode` عبر NuGet. |

## توسيع المثال

* **تنسيقات صورة مختلفة** – استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Gif` أو `Bmp` إذا كنت بحاجة إلى تنسيق آخر.
* **إخراج عالي الدقة** – اضبط `generator.Parameters.ImageResolution.DpiX` و `DpiY` قبل الحفظ.
* **التضمين في PDF** – استخدم `Aspose.Pdf` لوضع PNG داخل فاتورة PDF أو ملصق.

## الخلاصة

أنت الآن تعرف كيفية **إنشاء رمز شريطي GS1** في C# باستخدام Aspose.BarCode `BarcodeGenerator`، **توليد رمز شريطي PNG**، و**تصدير صورة الرمز الشريطي** إلى نظام الملفات. يغطي الدليل كل خطوة — من تهيئة المولد ببيانات GS1، ضبط بعد X، إلى حفظ ملف PNG النهائي — مع معالجة الأخطاء الشائعة وتقديم أفكار للتوسيع.

لا تتردد في تجربة معرفات تطبيقات GS1 أخرى، أو رموز شريطية مختلفة، أو صور عالية الدقة. عندما تتقن هذه الأساسيات، يصبح إنشاء رموز شريطية متوافقة للمخزون، الشحن، أو التجزئة جزءًا روتينيًا من أدوات .NET الخاصة بك.

## ماذا يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة كود كاملة تعمل مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء صور رموز شريطية GS1 في C# – كيفية توليد رمز شريطي C# بسرعة](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [إنشاء رمز شريطي PNG في C# – دليل خطوة بخطوة](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [إنشاء صورة رمز شريطي في C# – دليل برمجة كامل](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}