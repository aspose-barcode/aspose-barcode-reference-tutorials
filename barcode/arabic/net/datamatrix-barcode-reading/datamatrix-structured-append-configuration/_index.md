---
date: 2026-06-14
description: تعلم كيفية قراءة DataMatrix وإنشاء باركودات Structured Append في .NET
  باستخدام Aspose.BarCode، مكتبة الباركود السريعة والموثوقة.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: تكوين DataMatrix Structured Append
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: كيفية قراءة DataMatrix Append باستخدام Aspose.BarCode لـ .NET
url: /ar/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين الإلحاق الهيكلي لـ DataMatrix باستخدام Aspose.BarCode لـ .NET

إذا كنت مطورًا يبحث عن **how to read datamatrix** باستخدام الإلحاق الهيكلي في تطبيقات .NET الخاصة بك، فإن Aspose.BarCode لـ .NET هو الحل المناسب لك. في هذا الدليل خطوة بخطوة، سنستعرض إنشاء وترميز رموز DataMatrix التي يتم تقسيمها عبر رموز متعددة. بنهاية هذا البرنامج التعليمي ستكون قادرًا على إنشاء وتكوين وقراءة رموز DataMatrix ذات الإلحاق الهيكلي باستخدام Aspose.BarCode لـ .NET.

## الإجابات السريعة
- **ما المكتبة التي تتعامل مع الإلحاق الهيكلي لـ DataMatrix؟** Aspose.BarCode for .NET.
- **كم عدد الرموز التي يمكن أن يحتويها تسلسل الإلحاق الهيكلي الواحد؟** حتى 16 رمز DataMatrix.
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للتطوير والاختبار.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **هل يمكنني قراءة الباركود بدون ملف صورة؟** نعم، يمكنك فك الترميز من مصفوفة بايت أو تدفق.

## ما هو كيفية قراءة datamatrix؟
**how to read datamatrix** يشير إلى عملية فك ترميز رموز DataMatrix، وعند الحاجة، تجميع قطع تسلسل الإلحاق الهيكلي لاستعادة البيانات الأصلية. يوفر Aspose.BarCode دعمًا مدمجًا لهذا سير العمل، حيث يتعامل تلقائيًا مع ترتيب الرموز وربط البيانات.

## لماذا تستخدم Aspose.BarCode للإلحاق الهيكلي لـ DataMatrix؟
يدعم Aspose.BarCode **أكثر من 30 نوعًا من الرموز الشريطية** ويمكنه فك ترميز الصور حتى **10,000 × 10,000 px** في أقل من **200 ms** على عتاد الخادم العادي. كما أن المكتبة توفر **نشر بدون تبعيات**، مما يعني أنك لا تحتاج إلى ملفات DLL أصلية إضافية، وتعمل عبر بيئات .NET على Windows وLinux وmacOS.

## المتطلبات المسبقة

1. مكتبة Aspose.BarCode لـ .NET – قم بتنزيلها من [هنا](https://releases.aspose.com/barcode/net/).
2. يمكنك أيضًا تصفح منتجات Aspose الأخرى [هنا](https://releases.aspose.com/).
3. بيئة تطوير .NET مثل Visual Studio 2022 أو Visual Studio Code مع امتداد C#.

الآن، لنبدأ في إنشاء وقراءة رموز DataMatrix ذات الإلحاق الهيكلي.

## استيراد مساحات الأسماء

الخطوة الأولى هي استيراد مساحات الأسماء التي تكشف عن واجهة برمجة تطبيقات الباركود.

فئة `BarCodeWriter` هي نقطة الدخول في Aspose.BarCode لإنشاء الباركود، بينما يتعامل `BarCodeReader` مع فك الترميز.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

الآن بعد أن قمت باستيراد مساحات الأسماء المطلوبة، لنقم بإنشاء باركود إلحاق هيكلي.

## كيفية قراءة رموز DataMatrix ذات الإلحاق الهيكلي؟

حمّل الصورة (أو التدفق) التي تم إنشاؤها إلى `BarCodeReader`، فعّل خيار `ReadStructuredAppend`، واستدعِ `ReadBarcode`. سيعيد القارئ تلقائيًا البيانات المدمجة ويظهر تفاصيل التسلسل مثل `StructuredAppendFileId` و `StructuredAppendTotalCount` و `StructuredAppendSegmentId`. يتم إرجاع النتيجة المدمجة كسلسلة واحدة، ويمكنك أيضًا استرجاع معرّفات القطع الفردية عبر خاصية `StructuredAppendSegmentId` للقارئ لمعالجة مخصصة.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

في هذه الخطوة، نستخدم القارئ لاستخراج معرّف الباركود، العدد الكلي، ومعرّف الملف، مؤكدين أن تكوين الإلحاق الهيكلي تم تفسيره بشكل صحيح.

## الخطوة 1: إعداد تكوين الإلحاق الهيكلي لـ DataMatrix

لإنشاء باركود DataMatrix بإلحاق هيكلي، تحتاج إلى إعداد تكوينه. يتضمن ذلك تحديد مسار الدليل، معرّف الباركود، عدد الباركودات، ومعرّف الملف.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

في هذه الخطوة، قمنا بتكوين باركود DataMatrix بالمعلمات المطلوبة.

## المشكلات الشائعة والحلول

- **ترتيب القطع غير الصحيح:** تأكد من أن قيم `StructuredAppendSegmentId` متسلسلة بدءًا من 0؛ وإلا لن يتمكن القارئ من إعادة تجميع البيانات بشكل صحيح.
- **عدد إجمالي غير متطابق:** يجب أن يكون `StructuredAppendTotalCount` متطابقًا عبر جميع الرموز؛ أي عدم تطابق سيتسبب في اعتبار القارئ التسلسل غير مكتمل.
- **جودة الصورة:** يمكن أن تتسبب الصور منخفضة الدقة في فشل فك الترميز. استهدف على الأقل **300 dpi** عند رسم الباركود إلى صورة bitmap.

## الأسئلة المتكررة

### س1: ما هو الإلحاق الهيكلي لـ DataMatrix، ولماذا يُستخدم؟

ج1: الإلحاق الهيكلي لـ DataMatrix هو ميزة تتيح لك تقسيم كمية كبيرة من البيانات إلى عدة باركودات أصغر. هذا مفيد بشكل خاص عندما تكون مساحة الباركود الواحد محدودة أو تحتاج إلى تنظيم البيانات بفعالية. يُستخدم عادةً في اللوجستيات والرعاية الصحية والتصنيع.

### س2: هل يمكنني استخدام Aspose.BarCode لـ .NET في مشروعي المفتوح المصدر؟

ج2: نعم، يوفر Aspose.BarCode لـ .NET نسخة تجريبية مجانية يمكنك استخدامها في المشاريع المفتوحة المصدر. يمكنك العثور على النسخة التجريبية [هنا](https://releases.aspose.com/).

### س3: هل هناك دعم مجتمعي متاح لـ Aspose.BarCode لـ .NET؟

ج3: نعم، يمكنك طلب الدعم المجتمعي والتفاعل مع المستخدمين الآخرين على منتدى Aspose.BarCode [هنا](https://forum.aspose.com/c/barcode/13).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode لـ .NET؟

ج4: إذا كنت بحاجة إلى ترخيص مؤقت للتقييم أو الاختبار، يمكنك الحصول عليه من [هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل يدعم Aspose.BarCode لـ .NET أنواع باركود أخرى؟

ج5: نعم، يدعم Aspose.BarCode لـ .NET مجموعة واسعة من أنواع الباركود، بما في ذلك رموز QR، Code 128، EAN‑13، والعديد غيرها. يمكنك استكشاف الوثائق الكاملة [هنا](https://reference.aspose.com/barcode/net/) لرؤية القائمة الكاملة لأنواع الباركود المدعومة.

---

**آخر تحديث:** 2026-06-14  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [برمجة قارئ DataMatrix باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [إنشاء رموز DataMatrix باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [تكوين ماكرو DataMatrix الرئيسي باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}