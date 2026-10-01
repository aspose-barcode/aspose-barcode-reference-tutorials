---
date: 2026-08-02
description: تعرف على كيفية إنشاء باركود DataMatrix، توليد datamatrix، واستكشاف high
  density barcode generation باستخدام Aspose.BarCode لمشاريع .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: تكوين DataMatrix ECC 200
og_description: إنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET. يوضح هذا
  البرنامج التعليمي high density barcode generation، إعداد ترخيص Aspose المؤقت، وstep‑by‑step
  كود C#.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: إنشاء باركود DataMatrix – دليل Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: كيفية إنشاء باركود DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET
url: /ar/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET

## مقدمة

في هذا الدليل ستقوم **بإنشاء باركود DataMatrix** (ECC 200) باستخدام Aspose.BarCode لـ .NET. سواءً كنت تبني نظام تتبع المخزون، أو نظام نقاط البيع، أو تقوم بأتمتة سير عمل المستندات، فإن الباركود عالي الكثافة يمكنه تخزين الكثير من البيانات في مساحة صغيرة. سنستعرض كل خطوة من خطوات التكوين، نشرح لماذا كل إعداد مهم، ونزودك بمقاطع C# جاهزة للتنفيذ.

## إجابات سريعة
- **ما هي المكتبة الأفضل لـ DataMatrix في .NET؟** Aspose.BarCode for .NET  
- **ما مستوى ECC الذي يوفره ECC 200؟** تصحيح أخطاء عالي الكثافة للمسح القوي.  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص مؤقت يعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **هل يمكنني إخراج PNG أو JPEG أو TIFF؟** نعم – تدعم طريقة `Save` صيغ صور متعددة.

## ما هو DataMatrix ECC 200؟

DataMatrix ECC 200 هو باركود ثنائي الأبعاد عالي الكثافة يمكنه تخزين ما يصل إلى 2,335 حرفًا أبجديًا رقميًا أو 1,556 بايت من البيانات الثنائية في نمط مربع أو مستطيل مدمج. يستخدم تصحيح الأخطاء Reed‑Solomon لاستعادة الوحدات المفقودة أو المتضررة، مما يجعله مثاليًا لتطبيقات مثل وضع علامات أجزاء الطيران، ووسم الأدوية، واللوجستيات حيث تكون الموثوقية أمرًا حاسمًا.

## لماذا تستخدم توليد الباركود من Aspose؟

يدعم Aspose.BarCode **أكثر من 30 رموزًا**، ويمكنه إنشاء صور تصل إلى 10,000 × 10,000 بكسل دون تحميل الملف بالكامل في الذاكرة، ويوفر مخرجات حتمية عبر Windows وLinux وmacOS. تسمح لك API بالتحكم في كل معلمة عرض، مما يجعله الخيار الأكثر مرونة لتوليد الباركود في سيناريوهات **ASP.NET**.

## المتطلبات المسبقة

1. **بيئة التطوير** – Visual Studio مع إطار .NET المناسب المثبت.  
2. **Aspose.BarCode for .NET** – قم بتنزيله وتثبيته من الموقع، [هنا](https://releases.aspose.com/barcode/net/).  
3. **الترخيص** – احصل على ترخيص مؤقت للاختبار من [هنا](https://purchase.aspose.com/temporary-license/).  
4. **أساسيات C#** – الإلمام بصياغة C# وبنية المشروع.

الآن بعد أن غطينا الأساسيات، دعنا ننتقل إلى تكوين DataMatrix ECC 200.

## استيراد مساحات الأسماء

مساحة الأسماء `Aspose.BarCode.Generation` تحتوي على جميع الفئات المطلوبة لإنشاء الباركود. استوردها في أعلى ملفك:

```csharp
using Aspose.BarCode.Generation;
```

## كيفية إنشاء باركود DataMatrix (ECC 200) خطوة بخطوة

لإنشاء باركود DataMatrix ECC 200، ما عليك سوى تحميل البيانات التي تريد ترميزها، ضبط بعض المعلمات الأساسية على `BarcodeGenerator`، ثم استدعاء `Save` لكتابة ملف الصورة. يتعامل هذا التدفق المكوّن من ثلاث خطوات مع الترميز، وتصحيح الأخطاء، واختيار صيغة الإخراج، مما يتيح لك دمج إنشاء الباركود في أي تطبيق .NET بأقل قدر من الشيفرة.

### الخطوة 1: تهيئة مولد الباركود

`BarcodeGenerator` هو الفئة الأساسية في Aspose.BarCode التي تنشئ وتعرض الباركود. تقبل نوع الرمز والنص المراد ترميزه.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

استبدل `"Your Directory Path"` بالمجلد الذي ترغب في حفظ الصورة فيه.

### الخطوة 2: ضبط XDimension ونوع ECC

`XDimension` يحدد حجم البكسل لكل وحدة من DataMatrix، بينما `DataMatrixEcc` يختار مستوى تصحيح الأخطاء. يوفر ECC 200 أعلى قدرة تصحيح لهذا الرمز.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

قم بتعديل قيمة البكسل إذا كنت بحاجة إلى وحدات أكبر أو أصغر؛ القيم النموذجية هي 4‑6 بكسل للعرض على الشاشة و8‑10 بكسل للملصقات المطبوعة.

### الخطوة 3: إنشاء وحفظ صورة الباركود

طريقة `Save` تكتب الباركود إلى ملف. يمكنك اختيار PNG أو JPEG أو TIFF بتمرير قيمة التعداد `BarCodeImageFormat` المقابلة.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

غيّر `BarCodeImageFormat.Png` إلى `BarCodeImageFormat.Jpeg` أو `BarCodeImageFormat.Tiff` إذا كان سير عملك يتطلب صيغة مختلفة.

## المشكلات الشائعة & استكشاف الأخطاء

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| الباركود يظهر غير واضح | XDimension منخفض جدًا | زيادة `XDimension.Pixels` إلى 6‑8 |
| الفحص يفشل على الهاتف المحمول | مستوى ECC غير صحيح | تأكد من `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| لم يتم إنشاء الملف | سلسلة مسار غير صالحة | استخدم مسارًا مطلقًا أو تأكد من وجود المجلد |

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا الكود في تطبيق وحدة تحكم .NET Core؟**  
A: نعم، نفس الـ API يعمل في مشاريع .NET Core و .NET 5 و .NET 6.

**س: كيف أغيّر صيغة الإخراج إلى JPEG؟**  
A: استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Jpeg` في استدعاء `Save`.

**س: هل يمكن تضمين الباركود مباشرةً في ملف PDF؟**  
A: نعم – أنشئ الصورة أولاً، ثم أضفها إلى PDF باستخدام Aspose.PDF أو أي مكتبة PDF.

**س: ماذا لو احتجت إلى ترميز أحرف Unicode؟**  
A: يدعم DataMatrix UTF‑8؛ ما عليك سوى تمرير سلسلة Unicode إلى المولد كما هو موضح.

**س: هل تدعم المكتبة إنشاء دفعة من عدة باركودات؟**  
A: بالتأكيد – ضع كود الإنشاء داخل حلقة وغيّر البيانات/القيمة لكل تكرار.

## الخلاصة

لقد غطينا كل ما تحتاجه **لإنشاء باركود DataMatrix** (ECC 200) باستخدام Aspose.BarCode لـ .NET: من المتطلبات المسبقة واستيراد مساحات الأسماء إلى ضبط X‑dimension، اختيار مستوى ECC، وحفظ الصورة بالصيغ التي تفضلها. جرب الخصائص الإضافية مثل الهوامش، لون الخلفية، والدوران لتعديل المخرجات وفقًا لحالتك الخاصة.

إذا واجهت أي تحديات، فإن المجتمع جاهز للمساعدة على [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13). برمجة سعيدة!

---

**آخر تحديث:** 2026-08-02  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء باركود DataMatrix ECC 000-140 باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [كيفية قراءة باركود DataMatrix باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-reading/)
- [إنشاء باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}