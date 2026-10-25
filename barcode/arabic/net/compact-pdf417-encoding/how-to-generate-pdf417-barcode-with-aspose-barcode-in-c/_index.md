---
category: general
date: 2026-10-24
description: تعلم كيفية إنشاء رمز شريطي PDF417 باستخدام Aspose.BarCode في C# مع إعدادات
  مضغوطة والتحكم في XDimension للرمز الشريطي.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: ar
lastmod: 2026-10-24
og_description: إنشاء رمز شريطي PDF417 في C# باستخدام Aspose.BarCode. اتبع هذا الدليل
  الكامل لإنشاء صور PDF417 مدمجة، والتحكم في XDimension، وتحديد الأعمدة.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: إنشاء رمز شريطي PDF417 باستخدام Aspose.BarCode – خطوة بخطوة بلغة C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: كيفية إنشاء باركود PDF417 باستخدام Aspose.BarCode في C#
url: /ar/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود PDF417 باستخدام Aspose.BarCode في C#

إذا كنت بحاجة إلى **إنشاء باركود PDF417** في تطبيق .NET، يوضح لك هذا الدليل حلاً كاملاً جاهزًا للتنفيذ. ستلاحظ كيف تجعل Aspose.BarCode العملية بسيطة مع توفير تحكم دقيق في **PDF417 المدمج**، **XDimension للباركود**، و**أعمدة PDF417**.

إنشاء باركود هو طلب شائع لأنظمة الجرد، منصات التذاكر، وتدفقات عمل المستندات. بنهاية هذا البرنامج التعليمي ستحصل على برنامج C# مستقل ينتج صورة PNG واضحة لباركود PDF417، جاهزة للتضمين في أي واجهة مستخدم أو للطباعة على ملصق.

## ما ستحتاجه

- .NET 6.0 SDK أو أحدث (الكود يعمل أيضًا مع .NET Framework 4.6+)
- Visual Studio 2022 أو أي محرر C# تفضله
- ترخيص صالح لـ Aspose.BarCode for .NET (الإصدار التجريبي المجاني يكفي للتطوير)
- إلمام أساسي بصياغة C#

> **نصيحة احترافية:** إذا كنت تقيم Aspose.BarCode، قم بتحميل النسخة التجريبية من الموقع الرسمي وأضف حزمة NuGet `Aspose.BarCode` إلى مشروعك. النسخة التجريبية تضيف علامة مائية صغيرة إلى الصورة المُولدة، وتختفي بمجرد تطبيق الترخيص.

## الخطوة 1: تثبيت حزمة NuGet الخاصة بـ Aspose.BarCode

افتح الطرفية في مجلد الحل الخاص بك وشغّل:

```bash
dotnet add package Aspose.BarCode
```

الأمر يجلب أحدث نسخة مستقرة (اعتبارًا من أكتوبر 2026، الإصدار 23.12). إضافة الحزمة تستعيد مساحة الاسم `Aspose.BarCode.Generation` التي ستستخدمها **لإنشاء صور باركود PDF417**.

## الخطوة 2: إنشاء مشروع وحدة تحكم C# أساسي

إذا لم يكن لديك مشروع بعد، أنشئ واحدًا:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

افتح `Program.cs`. الهيكل الأساسي يحتوي بالفعل على طريقة `Main` حيث سنضع كود توليد الباركود.

## الخطوة 3: تهيئة مولّد الباركود

أولاً، استورد مساحة الاسم المطلوبة:

```csharp
using Aspose.BarCode.Generation;
```

ثم، داخل `Main`، أنشئ كائن `BarcodeGenerator` باستخدام رموز PDF417 والبيانات التي تريد ترميزها:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

السلسلة تشمل أحرف Unicode لتوضيح أن Aspose.BarCode يتعامل بشكل صحيح مع المدخلات غير ASCII. إذا كنت تحتاج فقط إلى ASCII، استبدل النص بأي سلسلة عادية.

## الخطوة 4: تعديل XDimension للباركود (حجم الوحدة)

**XDimension للباركود** يحدد عرض أصغر شريط (الوحدة). ضبطه بالبكسل يمنحك تحكمًا دقيقًا في حجم الصورة النهائي:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

قيمة `2` بكسل تنتج صورة مدمجة دون التضحية بموثوقية القراءة. زد القيمة للحصول على باركود أكبر أو قللها لتصاميم أكثر كثافة.

## الخطوة 5: ضبط خيارات PDF417 المدمج

إعدادان خاصان بـ PDF417 يؤثران بشكل كبير على البصمة البصرية:

| الإعداد | المعنى | القيمة النموذجية للمخرجات المدمجة |
|---------|---------|-----------------------------------|
| `Columns` | عدد أعمدة البيانات | `3` |
| `Truncate` (الوضع المدمج) | يحذف المنطقة الهادئة اليمنى ويقلل عدد الصفوف | `true` |

طبقهما كما يلي:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

استخدام **أعمدة PDF417** مضبوطة على `3` مع `Truncate = true` ينتج باركود *PDF417 مدمج* يناسب الملصق القياسي مع الحفاظ على قابلية القراءة لمعظم الماسحات.

## الخطوة 6: حفظ صورة الباركود

أخيرًا، اكتب الباركود إلى القرص. المثال يحفظ بصيغة PNG، لكن Aspose.BarCode يدعم BMP، JPEG، GIF، TIFF، وSVG أيضًا:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

الثابت `BarCodeImageFormat.Png` يخبر المكتبة بإنتاج PNG غير مضغوط، وهو مثالي للمعالجة اللاحقة أو الطباعة.

## الكود الكامل القابل للتنفيذ

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

تشغيل البرنامج ينتج ملف `CompactPdf417.png` في مجلد المشروع الجذر. افتح الملف بأي عارض صور؛ سترى باركود PDF417 مضغوط يرمّز السلسلة *Åspóse.Barcóde©*.

![Screenshot of generated PDF417 barcode using Aspose.BarCode](placeholder-image.png "Generated PDF417 barcode")
*نص بديل للصورة: لقطة شاشة للباركود PDF417 المُولّد باستخدام Aspose.BarCode* – يحتوي هذا النص البديل على الكلمة المفتاحية الأساسية لتحسين الوصولية وتحسين محركات البحث.

## التحقق من النتيجة

1. افتح ملف PNG. يجب أن يتكون الباركود من ثلاثة أعمدة بيانات رأسية مع تخطيط مدمج (بدون مناطق هادئة إضافية على الجانب الأيمن).
2. امسح الصورة باستخدام ماسح باركود على هاتف ذكي يدعم PDF417. يجب أن يتطابق النص المفكك مع السلسلة الأصلية.
3. إذا فشل الماسح، جرّب زيادة `XDimension.Pixels` إلى `3` أو `4`. الوحدات الأكبر تحسّن القابلية للقراءة على الأجهزة منخفضة الدقة.

## الاختلافات الشائعة والحالات الطرفية

### 1. تغيير صيغة الصورة

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG هو تنسيق قائم على المتجهات، مما يحافظ على وضوح الباركود عند أي مستوى تكبير — مفيد للصفحات الويب.

### 2. ترميز كميات كبيرة من البيانات

يمكن لـ PDF417 تخزين ما يصل إلى ~1.1 KB من النص. عندما يتجاوز حجم الحمولة قدرة ثلاثة أعمدة، تضيف المكتبة صفوفًا تلقائيًا. للحفاظ على الباركود مدمجًا، يمكنك:

- تقليل طول البيانات (مثلاً، استخدم معرفًا بدلاً من رسالة كاملة)
- زيادة عدد **أعمدة PDF417** (مثال: `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. استخدام ترخيص لإزالة علامة الماء التجريبية

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

ضع ملف الترخيص بجوار الملف التنفيذي. بعد تطبيق الترخيص، لا تحتوي الصورة المُولدة على علامة مائية.

### 4. معالجة الاستثناءات

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

الأخطاء الشائعة تشمل عدم وجود أذونات كتابة كافية أو صيغة صورة غير مدعومة.

## لماذا هذه الإعدادات مهمة

- **XDimension للباركود** – يتحكم في الوزن البصري لكل شريط. القيم الصغيرة تجعل الباركود غير قابل للقراءة؛ القيم الكبيرة تُهدر المساحة.
- **أعمدة PDF417** – عدد أقل من الأعمدة ينتج باركودًا أضيق لكنه يزيد عدد الصفوف.

## ماذا يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generate PDF417 barcode with compact settings in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}