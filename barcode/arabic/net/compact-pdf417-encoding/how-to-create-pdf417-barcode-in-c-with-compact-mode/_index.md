---
category: general
date: 2026-09-10
description: إنشاء باركود PDF417 في C# بسرعة. تعلّم كيفية تمكين وضع الضغط، ضبط الأعمدة،
  وإنشاء ملف PNG باستخدام BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: ar
lastmod: 2026-09-10
og_description: إنشاء رمز شريط PDF417 في C# عبر تمكين الوضع المدمج، ضبط الأعمدة، وحفظه
  كملف PNG. اتبع الدليل الكامل خطوة بخطوة.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: إنشاء رمز شريطي PDF417 في C# – دليل الوضع المدمج
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: كيفية إنشاء باركود PDF417 في C# باستخدام الوضع المدمج
url: /ar/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود PDF417 في C# مع وضع الضغط

إذا كنت بحاجة إلى **إنشاء باركود PDF417** في تطبيق .NET، يوضح لك هذا الدليل بالضبط كيفية القيام بذلك. ستتعرف على **تمكين وضع الضغط**، ضبط عدد الأعمدة، وحفظ النتيجة كصورة PNG باستخدام مكتبة BarcodeGenerator للغة C#.

إنشاء الباركود هو طلب شائع لتتبع المخزون، أنظمة التذاكر، وتطبيقات المسح الضوئي على الهواتف المحمولة. في نهاية هذا الدرس ستحصل على مثال مكتمل، قابل للتنفيذ، ينتج باركود PDF417 مضغوط جاهز للاستخدام في الإنتاج.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

* .NET 6.0 أو أحدث مثبت (الكود يعمل أيضاً مع .NET Framework 4.7+)
* نسخة حديثة من مكتبة **BarcodeGenerator** (مثال: Aspose.BarCode for .NET)
* بيئة تطوير متكاملة أو محرر مثل Visual Studio 2022 أو VS Code
* صلاحية كتابة في المجلد الذي سيُحفظ فيه ملف PNG

لا توجد حزم NuGet إضافية مطلوبة بخلاف مكتبة الباركود نفسها.

## الخطوة 1: إنشاء مولد باركود PDF417

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` باستخدام تعداد `EncodeTypes.Pdf417` والنص الذي تريد ترميزه. هذا الكائن يتحكم في عملية الإنشاء بأكملها.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*لماذا هذا مهم*: قيمة `EncodeTypes.Pdf417` تخبر المكتبة باستخدام رموز PDF417، بينما الوسيط الثاني يزودها بالبيانات. يمكنك استبدال `"Compact mode"` بأي سلسلة أبجدية رقمية تحتاج إلى ترميزها.

## الخطوة 2: ضبط بعد X (عرض الوحدة)

بعد X يتحكم في عرض كل مربع صغير (وحدة) في الباركود. القيم الأصغر تنتج صورة أكثر تماسكاً، وهو مفيد عندما تكون المساحة محدودة.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

قيمة `2` بكسل تُعد توازناً جيداً بين قابلية القراءة والضغط لمعظم الماسحات الضوئية القائمة على الشاشة.

## الخطوة 3: تحديد عدد الأعمدة

يمكن لـ PDF417 ترتيب البيانات في شبكة من الصفوف والأعمدة. تعديل عدد الأعمدة يغيّر نسبة أبعاد الباركود.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

ضبط **how to set columns** إلى `3` ينتج باركود قصير وعريض يناسب الملصق بسهولة. يمكنك تجربة قيم من `1` إلى `30` حسب كمية البيانات والماسح المستهدف.

## الخطوة 4: تمكين وضع الضغط

وضع الضغط يزيل الصفوف الفارغة غير الضرورية، مما يجعل الباركود أصغر دون فقدان سلامة البيانات. هذه هي الخطوة الأساسية للحصول على **PDF417 مضغوط**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

عند ضبط `Truncate` إلى `true`، تقوم المكتبة بحساب الحد الأدنى لعدد الصفوف المطلوبة لتخزين البيانات، ولهذا تبدو الصورة النهائية “مضغوطة”.

## الخطوة 5: حفظ الباركود المُولد كصورة PNG

أخيراً، اكتب الباركود إلى ملف. تنسيق PNG يحافظ على الحواف الحادة المطلوبة للمسح الضوئي الموثوق.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

استبدل `YOUR_DIRECTORY` بمسار مطلق أو نسبي يمكن لتطبيقك الكتابة فيه. بعد التنفيذ، ستجد ملف `CompactPdf417.png` يحتوي على الباركود.

### الكود الكامل

جمع جميع الخطوات معاً يمنحك برنامجاً واحداً جاهزاً للتنفيذ:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

تشغيل هذا البرنامج ينتج `CompactPdf417.png` في نفس المجلد الذي يتواجد فيه الملف التنفيذي. افتح الصورة بأي عارض؛ يجب أن ترى باركود PDF417 عالي التباين وكثيف جاهز للمسح.

## كيفية تمكين وضع الضغط في سيناريوهات أخرى

* **إنشاء دفعي** – عند إنشاء العديد من الباركودات، اضبط `Truncate` مرة واحدة على المولد وأعد استخدامه لكل حمولة جديدة.
* **تنسيقات صور مختلفة** – طريقة `Save` نفسها تعمل مع `BarCodeImageFormat.Jpeg` أو `BarCodeImageFormat.Bmp` إذا احتجت نوع ملف مختلف.
* **عدد أعمدة ديناميكي** – إذا كان طول السلسلة المشفرة متغيّرًا، احسب عدد الأعمدة الأمثل بناءً على طول السلسلة ودقة الماسح.

## كيفية ضبط الأعمدة لحالات استخدام محددة

* **طباعة الملصقات** – استخدم عدد أعمدة منخفض (مثال: `2`‑`5`) لجعل الباركود قصيرًا بما يكفي ليتناسب مع الملصقات الضيقة.
* **المسح الضوئي عبر الهاتف المحمول** – عدد أعمدة أعلى (`10`‑`15`) ينتج باركودًا أطول يسهل على كاميرا الهاتف تركيزه.
* **مقايضة تصحيح الأخطاء** – المزيد من الأعمدة يقلل عدد الصفوف، مما قد يؤثر على تصحيح الأخطاء المدمج في الباركود. اختبر مع الماسح المستهدف لتحديد النقطة المثالية.

## الأخطاء الشائعة ونصائح الخبراء

| المشكلة | السبب | الحل |
|-------|-------|------|
| الباركود غير قابل للقراءة | بعد X منخفض جدًا (مثال: `1` بكسل) | زيادة `XDimension.Pixels` إلى ما لا يقل عن `2` |
| الصورة كبيرة جدًا | تم ضبط الأعمدة أعلى من اللازم لحمولة قصيرة | تقليل `Pdf417.Columns` أو تمكين `Truncate` |
| ملف PNG فارغ | المجلد الهدف غير موجود أو لا يملك صلاحية كتابة | التأكد من وجود المجلد ومنح العملية صلاحية الكتابة |
| الماسح يُظهر “بيانات تالفة” | تم تعطيل `Truncate` مع عدد أعمدة كبير | تمكين `Truncate` أو خفض عدد الأعمدة |

## التحقق من النتيجة

يمكنك التحقق من الباركود باستخدام أي تطبيق ماسح PDF417 (تتوفر العديد من التطبيقات المجانية لأندرويد/آي أو إس). افتح `CompactPdf417.png` في التطبيق وتأكد من أن النص المفكك يطابق الحمولة الأصلية (“Compact mode”). إذا اختلف النص، أعد فحص علامة `Truncate` وإعدادات الأعمدة.

## الخطوات التالية

* **دمج مع ASP.NET Core** – إرجاع PNG مباشرةً من إجراء المتحكم بدلاً من حفظه على القرص.
* **إضافة نص قابل للقراءة** – استخدم `barcodeGenerator.Parameters.Barcode.CodeTextParameters` لعرض السلسلة المشفرة أسفل الباركود.
* **استكشاف رموز أخرى** – فئة `BarcodeGenerator` تدعم QR، Code128، DataMatrix، وأكثر. غير قيمة `EncodeTypes` لتجربة الأنواع الأخرى.

---

### الخلاصة

أنت الآن تعرف **كيفية إنشاء باركود PDF417** في C# مع **تمكين وضع الضغط**، والتحكم في **كيفية ضبط الأعمدة**، واستخدام واجهة **barcode generator C#** لتوليد باركود يلبي قيود الحجم الواقعية. طبّق هذه الخطوات في أي مشروع .NET يحتاج إلى باركودات مضغوطة وعالية الكثافة، ووسع النمط لتشمل صيغ باركود أخرى حسب الحاجة. Happy coding!

## ما الذي ينبغي أن تتعلمه لاحقًا؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مصدر يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}