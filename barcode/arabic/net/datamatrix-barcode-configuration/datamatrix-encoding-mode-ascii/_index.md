---
date: 2026-06-09
description: تعلم كيفية إنشاء رمز شريطي DataMatrix في وضع ASCII باستخدام Aspose.BarCode
  لـ .NET. يوضح هذا الدليل كيفية توليد رمز شريطي بلغة C# بسرعة.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: وضع ترميز DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: إنشاء رمز شريطي DataMatrix في وضع ASCII باستخدام Aspose.BarCode لـ .NET
url: /ar/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود DataMatrix في وضع ASCII باستخدام Aspose.BarCode لـ .NET

## مقدمة

هل ترغب في **إنشاء صور باركود DataMatrix** تستخدم ترميز ASCII الفعال؟ في هذا الدرس ستتعلم كيفية توليد باركود DataMatrix في وضع ASCII باستخدام Aspose.BarCode لـ .NET. سنستعرض كل خطوة — من إعداد المشروع إلى حفظ الصورة النهائية — حتى تتمكن من إضافة توليد الباركود إلى تطبيقات C# الخاصة بك في دقائق.

## إجابات سريعة
- **ما هي المكتبة الأفضل لـ DataMatrix في .NET؟** Aspose.BarCode for .NET  
- **كم عدد أسطر الكود المطلوبة؟** حوالي 5‑7 أسطر لباركود ASCII أساسي  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص مطلوب للإنتاج  
- **المنصات المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7  
- **هل يمكنني تغيير الحجم أو الألوان؟** نعم، Aspose.BarCode يتيح خصائص للأبعاد ولون المقدمة/الخلفية  

## ما هو باركود DataMatrix؟
DataMatrix هو باركود ثنائي الأبعاد يخزن النص والبيانات الثنائية في نمط مربع مدمج.  
يُشفّر باركود DataMatrix المعلومات في شبكة من الوحدات السوداء والبيضاء، مما يسمح بما يصل إلى 2,335 حرفًا أبجديًا رقميًا في رمز واحد. يُستخدم على نطاق واسع في التصنيع واللوجستيات والرعاية الصحية لأنه يمكن طباعته بأحجام صغيرة جدًا مع الحفاظ على قابلية القراءة العالية.

## كيفية إنشاء باركود DataMatrix في وضع ASCII؟
حمّل مساحة الأسماء Aspose.BarCode، أنشئ كائن `BarcodeGenerator`، اضبط `EncodeMode` إلى **EncodeMode.ASCII**، عيّن سلسلة البيانات الخاصة بك، ثم استدعِ `Save` لكتابة ملف الصورة. ينتج هذا النهج باركود DataMatrix متوافق تمامًا مع ترميز ASCII فقط في بضع أسطر من كود C#.

## لماذا نستخدم ترميز ASCII لـ DataMatrix؟
وضع ASCII هو الترميز الافتراضي والأكثر كفاءة للبيانات النصية البسيطة، حيث يقدم أصغر حجم رمز ممكن للسلاسل الأبجدية الرقمية. يدعم جميع الأحرف الـ 128 في ASCII، يعالج البيانات أسرع من الأوضاع الموسعة، ويضمن أقصى توافق مع الماسحات الضوئية القديمة التي تتوقع رموز ASCII القياسية.

## المتطلبات المسبقة

1. **بيئة التطوير** – Visual Studio أو Rider أو أي بيئة تطوير متوافقة مع C#.  
2. **Aspose.BarCode for .NET** – حمّل أحدث حزمة من [هنا](https://releases.aspose.com/barcode/net/).  
   - الوثائق: [توثيق Aspose.BarCode لـ .NET](https://reference.aspose.com/barcode/net/)  
   - مساعدة المجتمع: [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  
3. **معرفة أساسية بـ C#** – الإلمام ببنية مشروع .NET سيساعدك على متابعة الخطوات بسرعة.  
4. **يمكن العثور على منتجات Aspose الأخرى** [هنا](https://releases.aspose.com/).

## استيراد مساحات الأسماء

لبدء العمل، أضف توجيهات `using` المطلوبة في أعلى ملف C# الخاص بك:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

تمنحك هذه المساحات إمكانية الوصول إلى فئة `BarcodeGenerator` والأنواع المتعلقة بالصور اللازمة لحفظ الناتج.

## الخطوة 1: إنشاء دليل

اختر مجلدًا سيتم تخزين صور الباركود المولدة فيه. استبدل `"Your Directory Path"` بمسار مطلق أو نسبي موجود على جهازك.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

يتأكد الكود من وجود الدليل قبل محاولة كتابة أي ملفات، مما يمنع حدوث أخطاء وقت التشغيل.

## الخطوة 2: ترميز البيانات في وضع ASCII

فئة `BarcodeGenerator` تنشئ وتضبط صور الباركود. تعداد `DataMatrixEncodeMode` يحدد خوارزمية الترميز لرموز DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

بعد تشغيل الكود، ستجد الملف `datamatrix_ascii.png` في المجلد الذي حددته. يحتوي الصورة على باركود DataMatrix يشفّر السلسلة `"1234567890"` باستخدام وضع ASCII المدمج.

## المشكلات الشائعة والحلول

- **أخطاء الوصول إلى الملف** – تأكد من أن التطبيق يمتلك صلاحيات كتابة للمجلد المستهدف. تشغيل Visual Studio كمسؤول يمكن أن يحل مشاكل الصلاحيات على Windows.  
- **حجم الرمز غير صحيح** – إذا ظهر الباركود كبيرًا جدًا أو صغيرًا جدًا، عدّل `generator.Parameters.Image.Width` و`Height` أو دع Aspose يحسب الحجم الأمثل تلقائيًا بحذف تلك الخصائص.  
- **أحرف غير مدعومة** – وضع ASCII يقبل فقط الأحرف في النطاق 0‑127. للبيانات Unicode، انتقل إلى `DataMatrixEncodeMode.Base256` أو وضع مناسب آخر.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا في تطبيق تجاري؟**  
ج: نعم، يلزم وجود ترخيص Aspose صالح للاستخدام في الإنتاج؛ النسخة التجريبية مجانية للتقييم.

**س: هل تعمل المكتبة مع .NET Core؟**  
ج: بالتأكيد – Aspose.BarCode يدعم بالكامل .NET Core 3.1+، .NET 5، .NET 6، والإصدارات الأحدث.

**س: كم عدد الأحرف التي يمكنني تشفيرها في وضع ASCII؟**  
ج: يصل إلى 2,335 حرفًا أبجديًا رقميًا في رمز DataMatrix واحد عند استخدام ترميز ASCII.

**س: هل يمكنني تغيير لون المقدمة أو الخلفية للباركود؟**  
ج: نعم، عدّل `generator.Parameters.Image.ForeColor` و`BackColor` إلى أي قيمة من `System.Drawing.Color`.

**س: أين يمكنني العثور على أمثلة أكثر تقدماً؟**  
ج: الوثائق الرسمية تحتوي على عشرات العينات التي تغطي الأحجام المخصصة، الألوان، ومستويات تصحيح الأخطاء.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.BarCode لـ .NET مع لغات برمجة أخرى غير C#؟

ج1: يدعم Aspose.BarCode عدة لغات برمجة، لكن هذا الدرس يركز على C#.

### س2: ما هي أوضاع الترميز المختلفة المتاحة في باركودات DataMatrix؟

ج2: تدعم باركودات DataMatrix أوضاع ترميز متعددة، بما في ذلك ASCII، C40، Text، وBase256. كل وضع يناسب نوعًا مختلفًا من البيانات.

### س3: هل يمكنني تخصيص مظهر الباركود المولّد، مثل حجمه ولونه؟

ج3: نعم، يوفر Aspose.BarCode مجموعة واسعة من المعلمات لتخصيص مظهر الباركود، بما في ذلك الحجم واللون وغيرها.

### س4: هل هناك نسخة تجريبية مجانية من Aspose.BarCode لـ .NET؟

ج4: نعم، يمكنك تجربة Aspose.BarCode لـ .NET مجانًا من [هنا](https://releases.aspose.com/).

### س5: أين يمكنني شراء ترخيص لـ Aspose.BarCode لـ .NET؟

ج5: يمكنك شراء الترخيص من موقع Aspose عبر [هنا](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-06-09  
**تم الاختبار باستخدام:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [ترميز DataMatrix بالبايتات باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [قراءة باركود DataMatrix C# – توليد وضع DataMatrix (تلقائي)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [كيفية توليد باركودات DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}