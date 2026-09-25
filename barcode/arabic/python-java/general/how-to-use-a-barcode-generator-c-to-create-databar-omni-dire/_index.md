---
category: general
date: 2026-08-22
description: يظهر درس توليد الباركود بلغة C# كيفية إنشاء ملفات PNG للباركود، وإنشاء
  باركود DataBar، وتعديل ارتفاع الباركود في بضع خطوات فقط.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: ar
lastmod: 2026-08-22
og_description: دليل مولد الباركود C# يشرح لك كيفية إنشاء صورة باركود PNG، وإنشاء
  باركود DataBar، وتعديل ارتفاع الباركود بكفاءة.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: مولد الباركود C# – إنشاء باركود DataBar وتعديل الارتفاع
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: كيفية استخدام مولد الباركود C# لإنشاء باركود DataBar Omni‑directional
url: /ar/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام مولد الباركود C# لإنشاء باركود DataBar متعدد الاتجاهات

إذا كنت بحاجة إلى **barcode generator C#** يمكنه إنتاج صور PNG عالية الجودة، فإن هذا الدليل يغطي ما تحتاجه. ستتعلم كيفية إنشاء ملفات PNG للباركود، وإنشاء باركود DataBar متعدد الاتجاهات، وضبط ارتفاع الباركود دون مغادرة بيئة التطوير المتكاملة (IDE).

إنشاء الباركود برمجيًا يزيل الخطوة اليدوية لاستخدام محرر رسومي. في نهاية هذا البرنامج التعليمي ستحصل على ملفي PNG—أحدهما بارتفاع شريط 30 بكسل والآخر بارتفاع شريط 60 بكسل—جاهزين للإدراج في الفواتير أو الملصقات أو أنظمة المخزون.

**المتطلبات المسبقة**

- .NET 6.0 أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.7+)
- إشارة إلى حزمة NuGet `Aspose.BarCode` (أو أي مكتبة توفر واجهة برمجة تطبيقات مشابهة)
- إلمام أساسي بـ C# وVisual Studio أو بيئة التطوير التي تفضلها

---

## الخطوة 1: إعداد مشروع مولد الباركود C#

إنشاء **barcode generator C#** هو أول ما تقوم به. يأخذ المُنشئ معاملين: نوع الباركود (`EncodeTypes.DatabarOmniDirectional`) وبيانات الحمولة. في هذا المثال تتبع الحمولة تنسيق معرف التطبيق GS1 لرقم GTIN مكوّن من 14 رقمًا.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**لماذا هذا مهم:** يحدد تعداد `EncodeTypes.DatabarOmniDirectional` للمكتبة إنشاء DataBar يمكن قراءته من أي اتجاه، وهو مثالي للملصقات الصغيرة في المتاجر.

---

## الخطوة 2: تعريف أبعاد الوحدة (X‑dimension)

تتحكم أبعاد X في عرض وحدة الباركود الواحدة. ضبطها على 2 بكسل يعطي صورة واضحة وقابلة للقراءة مع الحفاظ على حجم الملف منخفضًا.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**نصيحة:** إذا كنت بحاجة إلى باركود أكثر ضيقًا بسبب مساحة محدودة، قلل القيمة إلى 1 بكسل، لكن اختبر القابلية للقراءة باستخدام الماسح.

---

## الخطوة 3: إنشاء PNG أول بارتفاع شريط 30 بكسل

ارتفاع الشريط يحدد مدى طول الخطوط. ارتفاع 30 بكسل هو الإعداد الافتراضي الشائع للملصقات القياسية.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

الملف `DatabarBarHeight30Pixels.png` الآن يحتوي على **generate barcode PNG** يمكن استخدامه مباشرة في صفحات الويب أو طباعته عند الحاجة.

---

## الخطوة 4: ضبط ارتفاع الباركود إلى 60 بكسل وحفظ PNG ثاني

تغيير ارتفاع الشريط بسيط كإسناد قيمة جديدة لنفس الخاصية. هذا يوضح قدرة **adjust barcode height** للمولد.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

الآن لديك `DatabarBarHeight60Pixels.png`، وهو مثالي للتعبئة الكبيرة حيث يجب مسح الباركود من مسافة.

**المخرجات المتوقعة**

- `DatabarBarHeight30Pixels.png` – باركود DataBar متعدد الاتجاهات مدمج، ارتفاعه 30 بكسل.
- `DatabarBarHeight60Pixels.png` – نفس الباركود، مضاعف الارتفاع لتحسين الرؤية.

كلا الصورتين بصيغة PNG، تحافظان على جودة غير مضغوطة وتدعمان الشفافية إذا لزم الأمر.

---

## كيفية إنشاء ملفات PNG للباركود بصيغ مختلفة

بينما يركز هذا الدليل على PNG، فإن طريقة `Save` تقبل صيغًا أخرى مثل `Jpeg` و`Bmp` و`Svg`. لتعلم **how to generate barcode** بصيغة أخرى، استبدل `BarCodeImageFormat.Png` بالقيمة المطلوبة من تعداد الصيغ:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

اختيار SVG مفيد عندما تحتاج إلى صورة متجهة يمكن تكبيرها دون تشويش.

---

## الأخطاء الشائعة عند **create DataBar barcode** الصور

| المشكلة | السبب | الحل |
|--------|-------|------|
| الباركود يبدو غير واضح | أبعاد X منخفضة جدًا بالنسبة لدقة الهدف | زيادة `XDimension.Pixels` إلى 3 أو 4 |
| الماسح لا يستطيع قراءة الكود | ارتفاع الشريط قصير جدًا بالنسبة لبصريات الماسح | استخدم حدًا أدنى 30 بكسل أو اتبع مواصفات الماسح |
| تم رفض سلسلة البيانات | تنسيق GS1 غير صحيح | تأكد من أن السلسلة تبدأ بمعرف التطبيق المناسب، مثل `(01)` لـ GTIN‑14 |

معالجة هذه النقاط مبكرًا توفر الوقت عند دمج الباركود في خطوط الإنتاج.

---

## نصيحة متقدمة: إعادة استخدام نفس المولد لعدة باركودات

إذا كنت بحاجة إلى **generate barcode PNG** لدفعة من المنتجات، أعد استخدام نفس كائن `BarcodeGenerator` وقم فقط بتحديث خاصية `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

هذا النمط يقلل من عبء إنشاء الكائنات ويجعل الشيفرة أكثر اختصارًا.

---

## الخاتمة

أصبح لديك الآن سير عمل كامل لـ **barcode generator C#** يقوم **بإنشاء DataBar barcodes**، **بإنشاء ملفات PNG للباركود**، ويسمح لك **بتعديل ارتفاع الباركود** عبر تغيير خاصية واحدة. يغطي المثال كل شيء من إعداد المشروع إلى التعامل مع الحالات الخاصة، بحيث يمكنك دمج إنشاء الباركود في أي تطبيق .NET بثقة.

**الخطوات التالية**

- استكشف رموز الباركود الأخرى (`EncodeTypes.QR`, `EncodeTypes.Code128`) لتوسيع حلّك.
- اجمع المولد مع ASP.NET Core لتقديم الباركود مباشرة عبر نقطة نهاية API.
- جرب خيارات الألوان (`generator.Parameters.Barcode.ForeColor`) لأغراض العلامة التجارية.

برمجة سعيدة، ولتكن عمليات المسح دائمًا سريعة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}