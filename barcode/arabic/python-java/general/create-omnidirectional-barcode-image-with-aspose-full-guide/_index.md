---
category: general
date: 2026-07-27
description: إنشاء صورة باركود متعددة الاتجاهات باستخدام Aspose.BarCode. تعلم كيفية
  إنشاء باركود باستخدام Aspose، وضبط نسبة العرض إلى الارتفاع، وحفظ ملفات PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: ar
lastmod: 2026-07-27
og_description: إنشاء صورة باركود متعددة الاتجاهات باستخدام Aspose. اتبع هذا الدليل
  لتوليد الباركود باستخدام Aspose، وضبط نسب الأبعاد، وتصدير ملفات PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: إنشاء صورة باركود شاملة الاتجاهات باستخدام Aspose – خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: إنشاء صورة باركود متعدد الاتجاهات باستخدام Aspose – دليل كامل
url: /ar/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود متعدد الاتجاهات باستخدام Aspose – دليل شامل

هل احتجت يومًا إلى **إنشاء صورة باركود متعدد الاتجاهات** لكن لم تكن متأكدًا أي مكتبة تختار؟ لست وحدك. في العديد من مشاريع اللوجستيات والبيع بالتجزئة، يُعد تنسيق DataBar Stacked Omnidirectional هو السر لتشفير مدمج وعالي الكثافة.  

الخبر السار؟ باستخدام **Aspose.BarCode** يمكنك توليد هذا الباركود ببضع أسطر، تعديل نسبة الأبعاد، وحفظ ملف PNG مباشرة على القرص. أدناه سترى بالضبط **كيفية إنشاء باركود باستخدام Aspose**، لماذا كل إعداد مهم، وما يجب الانتباه إليه عند تغيير نسبة الأبعاد.

---

## ما يغطيه هذا الدرس

سنتناول دورة الحياة الكاملة:

1. إعداد مجلد الإخراج.
2. إنشاء مولد DataBar Stacked Omnidirectional.
3. ضبط أبعاد البكسل ونسب الأبعاد.
4. حفظ الباركود كملفات PNG.
5. توسيع المثال لتشمل صيغ أخرى وحالات حافة.

بنهاية الدرس ستحصل على تطبيق C# Console جاهز للتنفيذ ينتج صورتين مختلفتين للباركود. لا أدوات خارجية، فقط كود Aspose النقي.

**المتطلبات المسبقة**

- .NET 6.0 SDK أو أحدث (الكود يعمل أيضًا على .NET Framework 4.7.2).
- حزمة NuGet `Aspose.BarCode` for .NET (`Install-Package Aspose.BarCode`).
- مجلد على القرص يمكن كتابة الصور إليه.

إذا كان لديك كل ذلك، لنبدأ.

---

## الخطوة 1: إعداد مجلد الإخراج

أولًا—أخبر البرنامج أين يضع ملفات PNG. كتابة المسار صراحةً تعمل للعرض التجريبي، لكن في بيئة الإنتاج ربما تقرأه من الإعدادات.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*لماذا هذا مهم:* `Directory.CreateDirectory` عملية متكررة؛ لن تُطلق استثناءً إذا كان المجلد موجودًا مسبقًا، مما يوفر عليك كتلة try‑catch.

---

## الخطوة 2: إنشاء مولد DataBar Stacked Omnidirectional

الآن نقوم بإنشاء المولد بنوع الترميز المحدد والبيانات التجريبية. السلسلة `"(01)12345678901231"` تتبع صيغة معرف التطبيق GS1 لرقم GTIN مكون من 14 رقمًا.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*شرح:* `EncodeTypes.DatabarStackedOmniDirectional` يخبر Aspose باستخدام النسخة متعددة الاتجاهات، القابلة للقراءة من أي اتجاه—مثالية للملصقات الصغيرة التي قد تُدوَّر.

---

## الخطوة 3: ضبط معلمات الباركود العامة

قبل أن نقوم بأي رسم، نحدد أصغر حجم للعنصر (X‑Dimension). قيمة **2 بكسل** تعطي صورة واضحة دون زيادة حجم الملف.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*نصيحة:* إذا احتجت دقة أعلى للطباعة، زد القيمة إلى 3 أو 4. تذكر أن أبعاد X‑Dimension الأكبر تزيد العرض والارتفاع بنسب متساوية.

---

## الخطوة 4: توليد وحفظ بنسبة أبعاد 15

عائلة DataBar تسمح لك بتعديل **نسبة الأبعاد**، التي تتحكم في علاقة الارتفاع إلى العرض. نسبة أبعاد **15** هي القيمة الافتراضية الشائعة للباركود متعدد الاتجاهات.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*ما ستراه:* باركود طويل نسبيًا لا يزال يناسب ملصق بحجم 2 × 1 سم. صيغة PNG تحافظ على جودة غير مضغوطة، مثالية للمعالجة اللاحقة أو الطباعة.

---

## الخطوة 5: تغيير نسبة الأبعاد إلى 30 وحفظ مرة أخرى

هل تريد باركودًا أقصر؟ فقط عدل خاصية `AspectRatio` واستدعِ `Save` مرة أخرى. لا حاجة لإعادة إنشاء المولد.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*لماذا نعيد استخدام نفس المولد؟* كائنات Aspose خفيفة؛ تعديل خاصية وإعادة الحفظ أسرع من إنشاء نسخة جديدة، ويضمن بقاء إعدادات الترميز (مثل X‑Dimension) ثابتة.

---

## مثال كامل يعمل

بدمج كل ما سبق، إليك البرنامج الكامل المستقل الذي يمكنك نسخه ولصقه في مشروع Console جديد.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**الناتج المتوقع**

عند تشغيل البرنامج يتم إنشاء مجلد فرعي `Barcodes` يحتوي على:

- `DatabarAspectRatio15.png` – مظهر أطول، كلاسيكي.
- `DatabarAspectRatio30.png` – مظهر أقصر، مناسب للملصقات العريضة.

كلا الصورتين تعرضان نفس بيانات GTIN؛ الفرق فقط في النسب البصرية.

---

## توسيع المثال (حالات حافة وتنوعات)

### 1. صيغ صور مختلفة

يدعم Aspose صيغ BMP، JPEG، TIFF، و SVG بالإضافة إلى PNG. استبدل قيمة الـ enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG صيغة متجهة، مما يعني إمكانية تكبيرها دون فقدان الحدة—مفيد لتطبيقات الويب المتجاوبة.

### 2. تخصيص الألوان

قد تحتاج باركود أبيض على خلفية داكنة. اضبط `ForeColor` و `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. التعامل مع نسب أبعاد غير صالحة

يتحقق Aspose من النطاق (عادة 5‑50). إذا مررت قيمة خارج النطاق، سيتم إلقاء `ArgumentException`. احط عملية الحفظ بكتلة try‑catch لتظهر رسالة ودية:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. توليد دفعي

عند وجود قائمة من أرقام GTIN، قم بالتكرار عليها، حدّث `CodeText`، واحفظ كل ملف باسم فريد. يمكن إعادة استخدام كائن المولد، مما يقلل استهلاك الذاكرة.

---

## الأخطاء الشائعة والنصائح المتقدمة

- **لا تنس ضبط `XDimension`** قبل الحفظ؛ القيمة الافتراضية (0.33 مم) قد تنتج صورًا غير واضحة على الشاشات منخفضة الدقة.
- **نسبة الأبعاد هي الارتفاع إلى العرض**، وليس العكس. الرقم الأكبر يجعل الباركود *أقصر* عموديًا.
- **مسارات الملفات:** استخدم `Path.Combine` لتجنب مشاكل الفواصل الخاصة بالأنظمة—خاصة إذا كان الكود يعمل داخل حاويات Linux.
- **الترخيص:** Aspose.BarCode تجاري. في وضع التجربة يظهر علامة مائية على الصورة. سجِّل ترخيصًا مبكرًا لتجنب المفاجآت في الإنتاج.

---

## الخلاصة

الآن تعرف كيف **تنشئ صورة باركود متعدد الاتجاهات** باستخدام Aspose، تعدل نسبة الأبعاد، وتصدّر ملفات PNG—كل ذلك في أقل من 30 سطرًا من C#. قدم هذا الدرس العملية خطوة بخطوة، شرح لماذا كل إعداد مهم، وتطرق إلى توسيعات مثل صيغ مختلفة، ألوان، وتوليد دفعي.

هل أنت مستعد للتحدي التالي؟ جرّب توليد رموز QR، دمج الباركود في ملف PDF، أو دمج الناتج في API ASP.NET Core. نفس مبادئ **إنشاء باركود باستخدام Aspose** تنطبق على جميع أنواع الباركود، لذا يمكنك إعادة استخدام ما تعلمته اليوم.

هل لديك أسئلة أو تريد مشاركة تعديلاتك؟ اترك تعليقًا أدناه—برمجة سعيدة!

## ما الذي ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مصدر يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف نهج تنفيذ بديلة في مشاريعك.

- [كيفية توليد باركود Aztec بنسبة أبعاد مخصصة باستخدام Aspose.BarCode لـ .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [كيفية إنشاء باركود Aspose Java - ضبط جودة الصورة](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [كيفية توليد صورة باركود في Java باستخدام Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}